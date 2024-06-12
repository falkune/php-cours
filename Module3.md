# Module 3 : Contrôle de Flux
Dans ce module, nous allons explorer les structures de contrôle en PHP, qui permettent de diriger le flux d'exécution de votre programme en fonction de différentes conditions et itérations.

**Conditions (if, else, elseif, switch)**
Les structures conditionnelles permettent de prendre des décisions dans le code.
```php
<?php
$a = 10;
$b = 20;

if ($a < $b) {
    echo "$a est inférieur à $b";
} elseif ($a == $b) {
    echo "$a est égal à $b";
} else {
    echo "$a est supérieur à $b";
}
?>
```
Le switch est une autre façon de gérer des conditions multiples.
```php
<?php
$jour = "lundi";

switch ($jour) {
    case "lundi":
        echo "Aujourd'hui, c'est lundi";
        break;
    case "mardi":
        echo "Aujourd'hui, c'est mardi";
        break;
    default:
        echo "Aujourd'hui, c'est un autre jour";
}
?>
```
***Boucles (for, while, do-while, foreach)***
Les boucles permettent de répéter des blocs de code.
***Boucle for***
```php
<?php
for ($i = 0; $i < 10; $i++) {
    echo "Le nombre est : $i <br>";
}
?>
```
***Boucle while***
```php
<?php
$i = 0;
while ($i < 10) {
    echo "Le nombre est : $i <br>";
    $i++;
}
?>
```
***Boucle do-while***
```php
<?php
$i = 0;
do {
    echo "Le nombre est : $i <br>";
    $i++;
} while ($i < 10);
?>
```
***Boucle foreach***
```php
<?php
$fruits = array("Pomme", "Banane", "Orange");
foreach ($fruits as $fruit) {
    echo "Le fruit est : $fruit <br>";
}
?>
```
**Exercices Pratiques**

***Exercice 1 : Affichage de texte***
Créez un fichier PHP qui affiche "Hello, World!" en utilisant echo.
***Exercice 2 : Variables et Opérateurs***
Créez un script PHP qui déclare deux variables, leur affecte des valeurs et affiche le résultat de leur addition, soustraction, multiplication et division.
***Exercice 3 : Conditions et Boucles***
Créez un script PHP qui utilise une boucle for pour afficher les nombres de 1 à 10. Ensuite, utilisez une condition if pour vérifier si chaque nombre est pair ou impair et affichez un message correspondant.

**Conclusion**
Vous avez maintenant une bonne compréhension des structures de contrôle en PHP. Ces outils sont essentiels pour écrire des programmes interactifs et dynamiques. Dans le prochain module, nous aborderons les fonctions et l'inclusion de fichiers en PHP, ce qui vous permettra de réutiliser et d'organiser votre code de manière plus efficace.

