# Module 2 : Syntaxe de Base de PHP

Dans ce module, nous allons explorer les éléments fondamentaux de la syntaxe PHP. Vous apprendrez à déclarer et utiliser des variables, utiliser différents types de données et opérateurs, et afficher des informations à l'écran.

1) **Syntaxe et Structure de Base**
PHP s'intègre dans le code HTML en utilisant des balises spécifiques. Voici comment vous pouvez insérer du code PHP dans un fichier HTML.
    ```php
    <?php 
    // Votre Code PHP ici
    ?>
    ```
2) **Instruction echo**
L'instruction echo en PHP est utilisée pour afficher des chaînes de caractères et d'autres types de données sur une page web. C'est l'une des instructions les plus couramment utilisées pour générer du contenu dynamique sur un site web.
    **Exemple:**
    ```php
    <!DOCTYPE html>
    <html>
    <head>
        <title>Page PHP</title>
    </head>
    <body>
        <h1>Bonjour, monde !</h1>
        <?php
        echo "Ceci est généré par PHP!";
        ?>
        <?php echo '<p> ceci est un paragraphe </p>'; ?>
        <p> <?php echo "ça aussi c'est un paragraphe"; ?> </p>
        <p> <?= "et en voila un dernier !"; ?> </p>
    </body>
    </html>
    ```
3)  **Variables et Types de Données**
En programmation, les variables sont utilisées pour stocker des données de différents types. Comprendre comment déclarer des variables et utiliser les types de données est fondamental pour écrire des scripts efficaces et fonctionnels. Voici un guide complet sur les variables et les types de données en PHP.
    - **Règles de nommage des variables**
    Le choix des noms de variables est une étape cruciale dans la programmation, car il affecte la lisibilité, la maintenance et la compréhension de votre code. En PHP, il existe des règles et des conventions spécifiques pour nommer les variables. Voici les principales règles et bonnes pratiques :
        - ***Commencer par un Symbole Dollar***
        Toutes les variables en PHP doivent commencer par le symbole dollar ($).
            ```php
            <?php
            $variable;
            ?>
            ```
        - ***Premier Caractère Alphabétique ou Underscore***
        Le premier caractère après le symbole dollar doit être une lettre (a-z, A-Z) ou un underscore (_).
            ```php
            $variable;
            $_variable;
            ```
        - ***Caractères Suivants***
        Les caractères suivants peuvent être des lettres (a-z, A-Z), des chiffres (0-9), ou des underscores (_).
            ```php
            $variable1;
            $variable_name;
            ```
        - ***Sensible à la Casse***
        Les noms de variables sont sensibles à la casse, ce qui signifie que $Variable et $variable sont considérés comme deux variables distinctes.
            ```php
            $Variable = "valeur1";
            $variable = "valeur2";
            ```
    - **Bonnes Pratiques**
        - ***Noms Significatifs***
        Utilisez des noms de variables descriptifs qui reflètent leur contenu ou leur usage. Cela améliore la lisibilité et la compréhension du code.
            ```php
            $userName;  // Bon
            $u;         // Mauvais
            ```
        - ***Utilisation d'une convention de nommage CamelCase ou Snake_Case...***
        Choisissez une convention de nommage et respectez-la tout au long de votre code.
            - CamelCase (pour les variables composées de plusieurs mots, utilisez une majuscule pour chaque mot sauf le premier)
            - Snake_Case (séparez les mots avec des underscores)
        - ***Utilisation d'Underscore pour les Variables Privées***
        Dans la programmation orientée objet, il est courant d'utiliser un underscore (_) au début du nom des variables privées ou protégées.
    - ***Types de Données***
    PHP est un langage faiblement typé, ce qui signifie que vous n'avez pas besoin de déclarer explicitement le type de données des variables. PHP détermine automatiquement le type de la variable en fonction de sa valeur. Voici les principaux types de données en PHP :
        - String (chaîne de caractères)
        - Integer (entier)
        - Float (nombre à virgule flottante)
        - Boolean (booléen)
        - Array (tableau)
        - Object (objet)
            ***Exemples :***
            ```php
            <?php 
            $chaine = "Hello, world!"; // String
            $entier = 42; // Integer
            $flottant = 3.14; // Float
            $booleen = true; // Boolean
            $tableau = array(1, 2, 3); // Array
            ?>
            ```
4) ***Opérateurs***
Les opérateurs en PHP sont des symboles qui permettent de réaliser des opérations sur des variables et des valeurs. Voici un guide complet des différents types d'opérateurs disponibles en PHP.
    - ***Opérateurs Arithmétiques***
    Les opérateurs arithmétiques sont utilisés pour effectuer des opérations mathématiques sur des valeurs numériques.
        - Addition (+) :
            ```php
            $sum = $a + $b;
            ```
        - Soustraction (-) :
            ```php
            $difference = $a - $b;
            ```
        - Multiplication (*) :
            ```php
            $product = $a * $b;
            ```
        - Division (/) :
            ```php
            $quotient = $a / $b;
            ```
        - Modulo (%) :
            ```php
            $remainder = $a % $b;
            ```
        - Exponentiation (**) :
            ```php
            $result = $a ** $b; // PHP 5.6 et versions ultérieures
            ```
    - ***Opérateurs d'Affection***
    Les opérateurs d'affectation sont utilisés pour assigner des valeurs aux variables.
        - Assignation simple (=) :
            ```php
            $a = 5;
            ```
        - Addition et assignation (+=) :
            ```php
            $a += 5; // Equivalent à $a = $a + 5;
            ```
        - Soustraction et assignation (-=) :
            ```php
            $a -= 5; // Equivalent à $a = $a - 5;
            ```
        - Multiplication et assignation (*=) :
            ```php
            $a *= 5; // Equivalent à $a = $a * 5;
            ```
        - Division et assignation (/=) :
            ```php
            $a /= 5; // Equivalent à $a = $a / 5;
            ```
        - Modulo et assignation (%=) :
            ```php
            $a %= 5; // Equivalent à $a = $a % 5;
            ```
    - ***Opérateurs de Comparaison***
    Les opérateurs de comparaison sont utilisés pour comparer deux valeurs.
        - Égal (==) :
            ```php
            $a == $b;
            ```
        - Identique (===) :
            ```php
            $a === $b; // Comparaison stricte (valeur et type)
            ```
        - Différent (!= ou <>) :
            ```php
            $a != $b;
            ```
        - Non identique (!==) :
            ```php
            $a !== $b; // Comparaison stricte (valeur et type)
            ````
        - Inférieur (<) :
            ```php
            $a < $b;
            
        - Supérieur (>) :
            ```php
            $a > $b;
            
        - Inférieur ou égal (<=) :
            ```php
            $a <= $b;
            ```
        - Supérieur ou égal (>=) :
            ```php
            $a >= $b;
    - ***Opérateurs Logiques***
    Les opérateurs logiques sont utilisés pour combiner des expressions conditionnelles.
        - ET (&& ou and) :
            ```php
            $a && $b;
            $a and $b;
            ```
        - OU (|| ou or) :
            ```php
            $a || $b;
            $a or $b;
            ```
        - NON (!) :
            ```php
            !$a;
            ```
        - XOR (ou exclusif) :
            ```php
            $a xor $b;
            ```
    - Autres Opérateurs
        - Concaténation (.) :
            ```php
            $fullName = $firstName . " " . $lastName;
            ```
        - Concaténation et assignation (.=) :
            ```php
            $text .= "suite du texte"; // Equivalent à $text = $text . "suite du texte";
            ```
        - Opérateurs d'Incrémentation et de Décrémentation
            ```php
            $a++;
            $a--;
            ```
            