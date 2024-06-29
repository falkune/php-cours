# Module 4 : Fonctions et Inclusion de Fichiers
Dans ce module, nous allons explorer les fonctions en PHP, comment les créer et les utiliser, ainsi que la manière d'inclure des fichiers pour organiser et réutiliser votre code.


##### Définir une Fonction
Une fonction en PHP est un bloc de code que vous pouvez définir une fois et appeler plusieurs fois. Voici comment vous pouvez définir une fonction :

```php
<?php
function direBonjour() {
    echo "Bonjour, monde!";
}
?>
```
##### Appeler une Fonction
Pour utiliser une fonction, il suffit de l'appeler par son nom :
```php
<?php
direBonjour(); // Appelle la fonction et affiche "Bonjour, monde!"
?>
```
##### Fonctions avec Paramètres
Les fonctions peuvent prendre des paramètres, qui sont des valeurs que vous passez à la fonction pour qu'elle les utilise.
```php
<?php
function saluer($nom) {
    echo "Bonjour, $nom!";
}

saluer("Alice"); // Affiche "Bonjour, Alice!"
saluer("Bob"); // Affiche "Bonjour, Bob!"
?>
```
##### Fonctions avec Valeur de Retour
Les fonctions peuvent aussi retourner des valeurs avec le mot-clé return.
```php
<?php
function additionner($a, $b) {
    return $a + $b;
}

$resultat = additionner(5, 3); // $resultat contient 8
echo $resultat; // Affiche 8
?>
```
##### Fonctions avec Valeurs par Défaut
Vous pouvez définir des valeurs par défaut pour les paramètres de vos fonctions.
```php
<?php
function saluer($nom = "inconnu") {
    echo "Bonjour, $nom!";
}

saluer(); // Affiche "Bonjour, inconnu!"
saluer("Alice"); // Affiche "Bonjour, Alice!"
?>
```
##### Fonctions Anonymes et Closures
PHP supporte également les fonctions anonymes, souvent utilisées comme arguments pour d'autres fonctions.
```php
<?php
$direBonjour = function($nom) {
    echo "Bonjour, $nom!";
};

$direBonjour("Alice"); // Affiche "Bonjour, Alice!"
?>
```
##### Inclusion de Fichiers
L'inclusion de fichiers vous permet de diviser votre code en morceaux réutilisables. PHP offre plusieurs fonctions pour inclure des fichiers : ***include***, ***require***, ***include_once***, et ***require_once***.

##### include et require
***include*** et ***require*** incluent et évaluent le fichier spécifié. La différence est que require génère une erreur fatale et arrête le script si le fichier ne peut pas être inclus, tandis que include génère une erreur avertissement et continue l'exécution.

```php
<?php
include 'header.php'; // Inclut le fichier header.php
require 'config.php'; // Inclut le fichier config.php
?>
```

##### include_once et require_once
***include_once*** et ***require_once*** fonctionnent comme include et require, mais ils vérifient si le fichier a déjà été inclus et, si c'est le cas, ne l'incluent pas à nouveau. Ceci est utile pour éviter les redéfinitions de fonctions ou de variables.
```php
<?php
include_once 'header.php'; // Inclut le fichier header.php une seule fois
require_once 'config.php'; // Inclut le fichier config.php une seule fois
?>
```
***Exemple Pratique***
Créez un site web simple avec des fichiers séparés pour l'en-tête, le pied de page et le contenu principal.
***header.php***
```html
<!DOCTYPE html>
<html>
<head>
    <title>Mon Site Web</title>
</head>
<body>
    <header>
        <h1>Bienvenue sur Mon Site Web</h1>
    </header>
```
***footer.php***
```html
    <footer>
        <p>&copy; 2024 Mon Site Web</p>
    </footer>
</body>
</html>
```
***index.php***
```php
<?php include 'header.php'; ?>

<main>
    <p>Ceci est le contenu principal de la page.</p>
</main>

<?php include 'footer.php'; ?>
```
