# Module 6 : Manipulation de Bases de Données
Dans ce module, nous allons explorer comment PHP peut interagir avec des bases de données pour stocker, récupérer, mettre à jour et supprimer des données. Nous utiliserons MySQL, l'un des systèmes de gestion de bases de données les plus populaires.

##### Introduction à MySQL
MySQL est un système de gestion de bases de données relationnelles (SGBDR) qui utilise le langage SQL (Structured Query Language) pour gérer les données. Avant de commencer à manipuler des bases de données avec PHP, assurez-vous d'avoir MySQL installé sur votre système.

##### Connexion à une Base de Données MySQL
Pour se connecter à une base de données MySQL en PHP, vous pouvez utiliser l'extension mysqli ou PDO (PHP Data Objects). Nous utiliserons ici mysqli.

##### Connexion avec PDO
```php
<?php
$dsn = "mysql:host=localhost;dbname=test";
$username = "root";
$password = "";

try {
    $conn = new PDO($dsn, $username, $password);
    $conn->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
    echo "Connexion réussie";
} catch (PDOException $e) {
    echo "La connexion a échoué: " . $e->getMessage();
}
?>
```
##### Exécution de Requêtes SQL
***Insertion de Données***
```php
<?php
$sql = "INSERT INTO Utilisateurs (nom, email) VALUES ('John Doe', 'john@example.com')";

if ($conn->query($sql) === TRUE) {
    echo "Nouvel enregistrement créé avec succès";
} else {
    echo "Erreur: " . $sql . "<br>" . $conn->error;
}
?>
```
***Sélection de Données***
```php
<?php
$sql = "SELECT id, nom, email FROM Utilisateurs";
$result = $conn->query($sql);

if ($result->num_rows > 0) {
    // Afficher les données de chaque ligne
    while($row = $result->fetch_assoc()) {
        echo "id: " . $row["id"]. " - Nom: " . $row["nom"]. " - Email: " . $row["email"]. "<br>";
    }
} else {
    echo "0 résultats";
}
?>
```
