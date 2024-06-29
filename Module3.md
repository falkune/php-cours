# Module 3 : Contrôle de Flux
Dans ce module, nous allons explorer les structures de contrôle en PHP, qui permettent de diriger le flux d'exécution de votre programme en fonction de différentes conditions et itérations.

Les contrôles de flux sont utilisés pour diriger l'exécution du code en fonction de conditions spécifiques. Ils permettent de créer des chemins d'exécution multiples dans un programme, rendant possible l'exécution de différentes sections de code selon les différentes situations.

**Les structures conditionnelles (if, else, elseif, switch)**
1) **if** : Exécute un bloc de code si une condition est vraie.
2) **else if** : Ajoute une autre condition à vérifier si la précédente était fausse.
3) **else** : Exécute un bloc de code si toutes les conditions précédentes sont fausses.
    ```php
    <?php
    $age = 18
    if ($age < 18){
        echo "Vous êtes mineur.";
    }
    else if ($age == 18){
        echo "Vous avez exactement 18 ans.";
    }
    else{
    echo "Vous êtes majeur.";
    }
    ?>
    ```
4) **switch** : Permet de sélectionner l'une des nombreuses branches à exécuter en fonction de la valeur d'une expression
    ```php
    <?php
    $numeroJour = 3;

    switch ($numeroJour) {
        case 1:
            echo "Lundi";
            break;
        case 2:
            echo "Mardi";
            break;
        case 3:
            echo "Mercredi";
            break;
        case 4:
            echo "Jeudi";
            break;
        case 5:
            echo "Vendredi";
            break;
        case 6:
            echo "Samedi";
            break;
        case 7:
            echo "Dimanche";
            break;
        default:
            echo "Jour invalide";
            break;
    }
    ?>
    ```
**Les structures itératives (for, while, do-while, foreach)**
Les structures itératives, aussi appelées boucles, sont des mécanismes en programmation qui permettent de répéter l'exécution d'un bloc de code tant qu'une condition donnée est vraie ou pour un nombre spécifique de fois.
1) ***Boucle for*** : Est utilisée lorsque le nombre d'itérations est connu à l'avance. Elle comporte trois parties : l'initialisation, la condition, et l'incrémentation/décrémentation.
    ```php
    <?php
    for ($i = 0; $i < 10; $i++) {
        echo "Le nombre est : $i <br>";
    }
    ?>
    ```
2) ***Boucle while*** : Continue à exécuter un bloc de code tant qu'une condition donnée est vraie.
    ```php
    <?php
    $i = 0;
    while ($i < 10) {
        echo "Le nombre est : $i <br>";
        $i++;
    }
    ?>
    ```
3) ***Boucle do-while*** : Similaire à la boucle while, mais elle exécute le bloc de code au moins une fois avant de vérifier la condition.
    ```php
    <?php
    $i = 0;
    do {
        echo "Le nombre est : $i <br>";
        $i++;
    } while ($i < 10);
    ?>
    ```
4) ***Boucle foreach*** : Particulièrement utile pour itérer sur des tableaux (arrays). Elle permet d'accéder directement aux valeurs des éléments du tableau.
    ```php
    <?php
    $fruits = array("Pomme", "Banane", "Orange");
    foreach ($fruits as $fruit) {
        echo "Le fruit est : $fruit <br>";
    }
    ?>
    ```
**Exercices Pratiques**

***Exercice 2 : Variables et Opérateurs***
Créez un script PHP qui déclare deux variables, leur affecte des valeurs et affiche le résultat de leur addition, soustraction, multiplication et division.

***Exercice 3 : Conditions et Boucles***
Créez un script PHP qui utilise une boucle for pour afficher les nombres de 1 à 10. Ensuite, utilisez une condition if pour vérifier si chaque nombre est pair ou impair et affichez un message correspondant.

**Conclusion**
Vous avez maintenant une bonne compréhension des structures de contrôle en PHP. Ces outils sont essentiels pour écrire des programmes interactifs et dynamiques. Dans le prochain module, nous aborderons les fonctions et l'inclusion de fichiers en PHP, ce qui vous permettra de réutiliser et d'organiser votre code de manière plus efficace.

