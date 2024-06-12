# Module 5 : Manipulation de Formulaires
Dans ce module, nous allons explorer comment manipuler des formulaires en PHP, y compris la collecte, la validation et le traitement des données des formulaires soumis par les utilisateurs.

#### Introduction aux Formulaires HTML
Les formulaires HTML permettent aux utilisateurs de saisir des données qui peuvent être envoyées à un serveur pour traitement. Voici un exemple de formulaire simple :

```html
<!DOCTYPE html>
<html>
<head>
    <title>Formulaire de Contact</title>
</head>
<body>
    <form action="process_form.php" method="post">
        <label for="nom">Nom:</label>
        <input type="text" id="nom" name="nom"><br><br>
        <label for="email">Email:</label>
        <input type="email" id="email" name="email"><br><br>
        <input type="submit" value="Envoyer">
    </form>
</body>
</html>
```
##### Collecte des Données de Formulaires en PHP
Les données des formulaires peuvent être envoyées en utilisant les méthodes **GET** ou **POST**. En PHP, vous pouvez accéder aux données envoyées en utilisant les superglobales $_GET ou $_POST.

##### Exemple avec Méthode POST
Le fichier process_form.php pourrait ressembler à ceci :
```php
<?php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $nom = $_POST['nom'];
    $email = $_POST['email'];
    
    echo "Nom: " . htmlspecialchars($nom) . "<br>";
    echo "Email: " . htmlspecialchars($email) . "<br>";
}
?>
```
##### Exemple avec Méthode GET
Pour utiliser la méthode GET, modifiez l'attribut method du formulaire et accédez aux données avec $_GET.

```html
<form action="process_form.php" method="get">
    ...
</form>
```
```php
<?php
if ($_SERVER["REQUEST_METHOD"] == "GET") {
    $nom = $_GET['nom'];
    $email = $_GET['email'];
    
    echo "Nom: " . htmlspecialchars($nom) . "<br>";
    echo "Email: " . htmlspecialchars($email) . "<br>";
}
?>
```
##### Validation des Données de Formulaires
Il est important de valider les données des formulaires pour assurer qu'elles sont correctes et sécurisées.
```php
<?php
$nomErr = $emailErr = "";
$nom = $email = "";

if ($_SERVER["REQUEST_METHOD"] == "POST") {
    if (empty($_POST["nom"])) {
        $nomErr = "Le nom est requis";
    } else {
        $nom = nettoyerDonnee($_POST["nom"]);
        if (!preg_match("/^[a-zA-Z-' ]*$/", $nom)) {
            $nomErr = "Seules les lettres et les espaces sont autorisés";
        }
    }
    
    if (empty($_POST["email"])) {
        $emailErr = "L'email est requis";
    } else {
        $email = nettoyerDonnee($_POST["email"]);
        if (!filter_var($email, FILTER_VALIDATE_EMAIL)) {
            $emailErr = "Format d'email invalide";
        }
    }
}

function nettoyerDonnee($data) {
    $data = trim($data);
    $data = stripslashes($data);
    $data = htmlspecialchars($data);
    return $data;
}
?>
```
##### Exemple avec Messages d'Erreur
```php
<!DOCTYPE html>
<html>
<head>
    <title>Formulaire de Contact</title>
</head>
<body>
    <h2>Formulaire de Contact</h2>
    <form action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]);?>" method="post">
        Nom: <input type="text" name="nom" value="<?php echo $nom;?>">
        <span class="error">* <?php echo $nomErr;?></span>
        <br><br>
        Email: <input type="text" name="email" value="<?php echo $email;?>">
        <span class="error">* <?php echo $emailErr;?></span>
        <br><br>
        <input type="submit" name="submit" value="Envoyer">
    </form>
</body>
</html>
```
##### Sauvegarde des Données dans un Fichier
Vous pouvez sauvegarder les données des formulaires dans un fichier pour les utiliser ultérieurement.
```php
<?php
if ($_SERVER["REQUEST_METHOD"] == "POST" && empty($nomErr) && empty($emailErr)) {
    $data = "Nom: " . $nom . " | Email: " . $email . "\n";
    file_put_contents("data.txt", $data, FILE_APPEND);
    echo "Données sauvegardées avec succès!";
}
?>
```
##### Envoi d'un Email avec les Données du Formulaire
Vous pouvez envoyer un email avec les données du formulaire.
```php
<?php
if ($_SERVER["REQUEST_METHOD"] == "POST" && empty($nomErr) && empty($emailErr)) {
    $to = "admin@example.com";
    $subject = "Nouveau message de contact";
    $message = "Nom: " . $nom . "\nEmail: " . $email;
    $headers = "From: webmaster@example.com";
    
    if (mail($to, $subject, $message, $headers)) {
        echo "Email envoyé avec succès!";
    } else {
        echo "Erreur lors de l'envoi de l'email.";
    }
}
?>
```
##### Exercices Pratiques
***Exercice 1 : Formulaire de Contact***
Créez un formulaire de contact avec les champs suivants : nom, email, sujet et message. Validez les données et affichez un message de confirmation ou d'erreur.

***Exercice 2 : Sauvegarde des Données***
Modifiez le formulaire de contact pour sauvegarder les données dans un fichier contacts.txt.

***Exercice 3 : Envoi d'Email***
Ajoutez la fonctionnalité d'envoi d'email au formulaire de contact. Envoyez les données saisies par l'utilisateur à une adresse email spécifiée.

##### Conclusion
Vous avez maintenant appris à manipuler des formulaires en PHP, à valider et traiter les données saisies par les utilisateurs, à les sauvegarder et même à envoyer des emails. Dans le prochain module, nous aborderons les interactions avec les bases de données en PHP, ce qui vous permettra de stocker et de gérer des données de manière plus sophistiquée.