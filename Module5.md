# Module 5 : Manipulation de Formulaires
Dans ce module, nous allons explorer comment manipuler des formulaires en PHP, y compris la collecte, la validation et le traitement des données des formulaires soumis par les utilisateurs.

#### Introduction aux Formulaires HTML
Les formulaires HTML permettent aux utilisateurs de saisir des données qui peuvent être envoyées à un serveur pour traitement. Voici un exemple de formulaire simple :

```html
<!DOCTYPE html>
<html>
<head>
    <title>Formulaire de test</title>
</head>
<body>
    <form action="traitement_formulaire.php" method="post">
        <label>Nom :</label>
        <input type="text" name="nom"><br><br>

        <label>Email :</label>
        <input type="email" name="email"><br><br>

        <label>Sexe :</label>
        <input type="radio" name="sexe" value="homme"> Homme
        <input type="radio" name="sexe" value="femme"> Femme<br><br>

        <label>Couleurs préférées :</label><br>
        <input type="checkbox" name="couleurs[]" value="rouge"> Rouge<br>
        <input type="checkbox" name="couleurs[]" value="vert"> Vert<br>
        <input type="checkbox" name="couleurs[]" value="bleu"> Bleu<br><br>

        <label>Pays :</label>
        <select name="pays">
            <option value="france">France</option>
            <option value="allemagne">Allemagne</option>
            <option value="espagne">Espagne</option>
        </select><br><br>

        <label>Message :</label><br>
        <textarea name="message" rows="4" cols="50"></textarea><br><br>

        <input type="submit" value="Envoyer">
    </form>
</body>
</html>

```
##### Collecte des Données de Formulaires en PHP
Les données des formulaires peuvent être envoyées en utilisant les méthodes **GET** ou **POST**. En PHP, vous pouvez accéder aux données envoyées en utilisant les superglobales $_GET ou $_POST.

##### Exemple avec Méthode POST
Créez un fichier PHP nommé traitement_formulaire.php pour traiter les données soumises.
```php
<?php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    // Collecter les données du formulaire
    $nom = htmlspecialchars($_POST['nom']);
    $email = htmlspecialchars($_POST['email']);
    $sexe = isset($_POST['sexe']) ? htmlspecialchars($_POST['sexe']) : '';
    $couleurs = isset($_POST['couleurs']) ? $_POST['couleurs'] : [];
    $pays = htmlspecialchars($_POST['pays']);
    $message = htmlspecialchars($_POST['message']);

    // Afficher les données pour vérification
    echo "<h2>Informations soumises :</h2>";
    echo "Nom : " . $nom . "<br>";
    echo "Email : " . $email . "<br>";
    echo "Sexe : " . $sexe . "<br>";
    echo "Couleurs préférées : " . implode(", ", $couleurs) . "<br>";
    echo "Pays : " . $pays . "<br>";
    echo "Message : " . nl2br($message) . "<br>";
}
?>
```

1) ***Méthode de requête*** : Nous vérifions d'abord que la méthode de requête est POST pour nous assurer que le formulaire a été soumis.
    ```php
    <?php
    if ($_SERVER["REQUEST_METHOD"] == "POST")
    ?>
    ```
2) ***Collecte et sécurisation des données*** : Pour chacun des champ du formulaire, sa valeur est collecté et la fonction ***htmlspecialchars*** est utilisée pour échapper les caractères spéciaux et prévenir les attaques XSS.
    ```php
    <?php
    $nom = htmlspecialchars($_POST['nom']);
    $email = htmlspecialchars($_POST['email']);
    ?>
    ```
3) ***Champs optionnels*** : Pour les champs qui peuvent ne pas être définis (comme les radio boutons et les checkboxes), nous vérifions leur existence avec isset.
    ```php
    <?
    $sexe = isset($_POST['sexe']) ? htmlspecialchars($_POST['sexe']) : '';
    $couleurs = isset($_POST['couleurs']) ? $_POST['couleurs'] : [];
    ?>
    ```
4) ***Implode pour les checkboxes*** : Les checkboxes peuvent renvoyer plusieurs valeurs, il faut les recuperer dans un tableau et les afficher en utilisant la fonction implode.
    ```php
    <?php
    echo "Couleurs préférées : " . implode(", ", $couleurs) . "<br>";
    ?>
    ```


##### Exemple avec Méthode GET
La méthode GET permet d'envoyer des données de formulaire en les incluant dans l'URL de la requête. Lorsqu'un formulaire utilise la méthode GET, les données sont visibles dans la barre d'adresse du navigateur sous forme de paramètres de l'URL.
En PHP, le traitement des données envoyées via la méthode GET se fait en utilisant la superglobale $_GET au lieu de $_POST. Les deux méthodes de traitement des données sont très similaires. 

```html
<form action="traitement_formulaire.php" method="get">
    ...
</form>
```
Dans l'attribut method on met **get** a la place de **post**.
```php
<?php
if ($_SERVER["REQUEST_METHOD"] == "GET") {
    // Collecter les données du formulaire
    $nom = htmlspecialchars($_GET['nom']);
    $email = htmlspecialchars($_GET['email']);
    $sexe = isset($_GET['sexe']) ? htmlspecialchars($_GET['sexe']) : '';
    $couleurs = isset($_GET['couleurs']) ? $_GET['couleurs'] : [];
    $pays = htmlspecialchars($_GET['pays']);
    $message = htmlspecialchars($_GET['message']);

    // Afficher les données pour vérification
    echo "<h2>Informations soumises :</h2>";
    echo "Nom : " . $nom . "<br>";
    echo "Email : " . $email . "<br>";
    echo "Sexe : " . $sexe . "<br>";
    echo "Couleurs préférées : " . implode(", ", $couleurs) . "<br>";
    echo "Pays : " . $pays . "<br>";
    echo "Message : " . nl2br($message) . "<br>";
}
```
Bien que la méthode GET soit facile à utiliser, elle présente plusieurs inconvénients qui la rendent inadéquate pour le traitement de formulaires sensibles ou volumineux :
1) **Limites de taille** : Les URLs ont des limites de taille (environ 2000 caractères selon les navigateurs), ce qui restreint la quantité de données que vous pouvez envoyer via GET.
2) **Visibilité des données** : Les données envoyées via GET sont visibles dans la barre d'adresse du navigateur. Cela pose des problèmes de sécurité et de confidentialité, notamment pour les informations sensibles telles que les mots de passe ou les données personnelles.
3) **Cache et historique du navigateur** : Les données envoyées via GET sont stockées dans l'historique du navigateur et peuvent être mises en cache. Cela peut être problématique pour des informations qui ne devraient pas être mémorisées ou réutilisées par erreur.

### Téléverser des images
Voici comment vous devriez définir votre formulaire HTML pour permettre le téléversement de fichiers :
```html
<form action="upload.php" method="post" enctype="multipart/form-data">
    <label for="image">Choisir une image :</label>
    <input type="file" name="image" id="image">
    <input type="submit" value="Télécharger">
</form>
```
Créez un fichier nommé upload.php avec le code suivant :
```php
<?php
if ($_SERVER["REQUEST_METHOD"] == "POST" && isset($_FILES["image"])) {
    $target_dir = "uploads/";
    $target_file = $target_dir . $_FILES["image"]["name"];
    
    // Créer le répertoire s'il n'existe pas
    if (!is_dir($target_dir)) {
        mkdir($target_dir, 0777, true);
    }

    // Déplacer le fichier téléchargé vers le répertoire cible
    if (move_uploaded_file($_FILES["image"]["tmp_name"], $target_file)) {
        echo "Le fichier ". htmlspecialchars($_FILES["image"]["name"]) . " a été téléversé avec succès.<br>";
        echo '<img src="'.$target_file.'" alt="Image téléversée">';
    } else {
        echo "Désolé, une erreur s'est produite lors du téléversement de votre fichier.";
    }
}
?>
```