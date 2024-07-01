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


## Exercices:
Exercice 1 : Détermination de la saison
Ecrire un script PHP qui affiche la saison en fonction du mois actuel. Utiliser une structure switch pour déterminer la saison.
(decembre, janvier et fevrier pour hiver), (mars, avril, mai pour printemps),
(juin, juillet, aout pour été) et (semptembre, octobre, novembre pour automne)

Exercice 2 : Calcul de remise
Ecrire un script PHP qui calcule le prix après une remise en fonction du montant d'achat de l'utilisateur. Si le montant d'achat est supérieur ou égal à 100€, appliquer une remise de 10%. Sinon, ne pas appliquer de remise..

Exercice 3 : Validation d'un nombre pair ou impair
Ecrire un script PHP qui vérifie si un nombre saisi par l'utilisateur est pair ou impair et affiche un message correspondant.


Exercice 4 : Le problème de Sissa

AVANT PROPOS 

Une légende Indienne raconte qu'un vieux sage, Sissa, inventa le jeu d'échec est que son seigneur, impresionné, 
voulu le récompenser en lui offrant ce qu'il désirait. L'humble vieillard souhaita juste un peu de riz pour ses vieux jours.
Lorsque le seigneur demanda combien de riz exactement, le vieux sage répondit : 
"Exactement assez pour mettre 1 grain de riz sur la premier case de mon damier, puis 2 sur la deuxième case, 4 sur la troisième, 8 sur la suivante, et ainsi de suite pour les 64 cases du damier."
Le seigneur, enthousiaste, donna son accord. 

EXERCICE 

Etape 1 :
Ecrivez un programme qui affiche la quantité de grains à déposer sur chacune des cases du damier.

Etape 2 :
A la fin de votre programme, affichez le nombre total de grains de riz que le seigneur doit au vieux sage.

Etape 3 :
Enfin, en sachant qu'il y a, environ, 3500 grains par kilo de riz, calculez le poids total de riz que cela représente.


