# Module 2 : Syntaxe de Base de PHP

Dans ce module, nous allons explorer les éléments fondamentaux de la syntaxe PHP. Vous apprendrez comment déclarer des variables, utiliser différents types de données et opérateurs, et afficher des informations à l'écran.

1) **Syntaxe et Structure de Base**
PHP s'intègre dans le code HTML en utilisant des balises spécifiques. Voici comment vous pouvez insérer du code PHP dans un fichier HTML :
    ```php
    <?php
    // Votre code PHP ici
    ?>
    ```
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
    </body>
    </html>
    ```
    **Affichage de Texte avec echo et print**
    echo et print sont utilisés pour afficher des données à l'écran.
    ```php
    <?php
    echo "Bonjour, monde!"; // Utilisation de echo
    print "Hello, world!"; // Utilisation de print
    ?>
    ```
    echo peut prendre plusieurs arguments :
    ```php
    <?php
    echo "Bonjour", " monde!";
    ?>
    ```
    print ne peut prendre qu'un seul argument :
    ```php
    <?php
    print "Hello, world!";
    ?>
    ```

2)  **Variables et Types de Données**
    ***Déclaration de Variables***
    Les variables en PHP sont déclarées avec le signe ***$*** suivi du nom de la variable.
    ```php
    <?php
    $nom = "John";
    $age = 30;
    ?>
    ```
    **T*ypes de Données***
    PHP supporte plusieurs types de données :
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

    ***Opérateurs***
    PHP utilise divers opérateurs pour effectuer des opérations sur des variables.

    - Opérateurs arithmétiques : +, -, *, /, %
    - Opérateurs d'affectation : =, +=, -=, *=, /=, %=
    - Opérateurs de comparaison : == , != , <>, === , !==, >, <, >=, <=
    - Opérateurs logiques : &&, ||, !, and, or, xor

    ***Exemple***
    ```php
    <?php
    $a = 10;
    $b = 20;

    $addition = $a + $b; // 30
    $egalite = ($a == $b); // false
    $et_logique = ($a < $b && $a > 5); // true
    ?>
    ```

Vous avez maintenant une compréhension de base de la syntaxe de PHP. Vous pouvez déclarer des variables, utiliser différents types de données et opérateurs. Dans le prochain module, nous allons voir comment contrôler le flux de vos programmes avec des conditions et des boucles.
