# Module 6 : Manipulation de Bases de Données
Dans ce module, nous allons explorer comment PHP peut interagir avec des bases de données pour stocker, récupérer, mettre à jour et supprimer des données. Nous utiliserons MySQL, l'un des systèmes de gestion de bases de données les plus populaires.

##### Introduction à MySQL
MySQL est un système de gestion de bases de données relationnelles (SGBDR) qui utilise le langage SQL (Structured Query Language) pour gérer les données. Avant de commencer à manipuler des bases de données avec PHP, assurez-vous d'avoir MySQL installé sur votre système.

##### Connexion à une Base de Données MySQL
Pour se connecter à une base de données MySQL en PHP, vous pouvez utiliser l'extension mysqli ou PDO (PHP Data Objects).

##### Connexion avec PDO
```php
<?php
$username = "root";
$password = "";

try {
    $conn = new PDO("mysql:host=localhost;dbname=test", $username, $password);
    echo "Connexion réussie";
} catch (PDOException $e) {
    echo "La connexion a échoué: " . $e->getMessage();
}
?>
```
##### Exécution de Requêtes SQL
***Insertion de Données***
```php
// preparation de la requete
$request = $conn->prepare("INSERT INTO nom_de_la_table (champ1, champ2,...) VALUES (?, ?,...)");

// execution de la requete
$request->execute(array($valeur1, $valeur2, ...));
```

***Récuperation de Données***
```php
// preparation de la requete
$request = $conn->prepare("SELECT * FROM la_table");

// execution de la requete
$request->execute();

// recuperation du resultat de la requette
$resultat = $request->fetchAll();
$resultat = $request->fetch();
```
***Modification de Données***
```php
// preparation de la requete
$request = $conn->prepare("UPDATE nom_table SET nom_colonne = ? WHERE nom_colonne = ?");

// execution de la requete
$request->execute(array($valeur1, $valeur2));
```

***Suppression de Données***
```php
// preparation de la requete
$request = $conn->prepare("DELETE FROM nom_table WHERE nom_colonne = ?");

// execution de la requete
$request->execute(array($valeur));
```