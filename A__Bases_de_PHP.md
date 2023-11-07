# Utile 

Une plateforme en ligne très pratique pour tester PHP entre autres : https://onecompiler.com  
IL est possible de mémoriser nos tests, à condition de créer un compte gratuitement.  
###
Nous pouvons utiliser cette plateforme pour effectuer des petits scripts et les partager facilement


# Les types de données

Des nombres, booléens, chaînes de caractères, et plus complexes : des tableaux et objets.  
http://php.net/manual/fr/language.types.php

# Variables

Une variable est un moyen de mémoriser une information qui, comme son nom l’indique, peut faire varier son contenu.  
http://php.net/manual/fr/language.variables.basics.php

> **NB :**  
> Une variable commence par **$**.  
> Une ligne d'instruction finit par un **point virgule**.

# Constantes

Une constante est utilisée pour garder une information que l’on juge invariable durant l’exécution du programme.  
Une constante est tapée en majuscule et ne commence par **$**.  
http://php.net/manual/fr/language.constants.php

# Concaténation de chaînes

Elle permet de mettre bout à bout des données de types différents. Le résultat est une chaîne de caractères.  
La concaténation des chaînes de caractères fait partie des opérations très fréquentes en PHP.  
http://php.net/manual/fr/language.operators.string.php

> **NB :** Une chaine délimitée par des guillemets permet d'interpreter des variables.

```php
    $eleve = "Pierre";
    $ville = "Lyon";
    $age = 23;

    // concaténaton
    echo "L'élève " . $eleve . "agé de " . $age . " ans, habite " . $ville;

    // interprétation dans la chaîne.
    echo "L'élève $eleve agé de $age ans, habite $ville.";
```

# Opérateurs Arithmétiques.

Il est ici question d'additions, de soustractions, d'increments, etc...

> **NB :** Bien comprendre la nuance entre _additionner_ et _incrémenter_.

http://php.net/manual/fr/language.operators.arithmetic.php 
###  
http://php.net/manual/fr/language.operators.increment.php

# Opérateurs de comparaison

Le résultat d'une opération de comparaison est booléen, vrai ou faux.  
 http://php.net/manual/fr/language.operators.comparison.php

# Opérateurs logiques

ET s'écrit **&&**  
OU s'écrit **||**  
NON s'écrit **!**  
http://php.net/manual/fr/language.operators.logical.php

# Tableaux

## Tableau linéaire

C’est une collection de données où chaque « item » du tableau est accessible grâce à l’index de position.

```php

	$marques = ['Peugeot','Renault','Ford','Fiat', 'Volvo'];
	// nombre d'items
	$nombre_items = count($marques);
	// index dernier item
	$der = count($marques)-1;

	var_dump($nombre_items);

	echo "<pre>";
	var_dump($marques[2]);  // Ford

```

## Tableau associatif simple

Chaque donnée est reliée à une clé. L’ordre importe peu.

```php

	$voiture = [
		'modele'=>'Twingo',
		'marque'=>'Renault',
		'couleur'=>'grise'
	];

	var_dump($voiture['modele']);

```

## Tableau associatif multidimensionnel

Avec ce type de tableau, nous rapprochons un peu des bases de données relationnelles.

```php
	$artistes = [
            [
                'nom'=>'King',
                'prenom'=>'Arthur',
                'style'=>'Blues',
                'instrument'=>'guitare'
            ],
            [
                'nom'=>'Swingi',
                'prenom'=>'Bud',
                'style'=>'jazz',
                'instrument'=>'Contrebasse'
           ]
    ];
    echo $artistes[1]['nom'] .' '. $artistes[1]['style'];
```
## Les fonctions dédiées au tableaux 
Elles sont très nombreuses et permettent des traitements simples ou très complexes. 
On peut  : insérer, supprimer, concaténer, ajouter au début ou à la fin, extraire des portions, etc...  
### voir la doc
http://php.net/manual/fr/book.array.php


# Structures conditionnelles

Il n'est pas rare qu'un programme PHP doive évaluer une expression pour continuer l'exécution du programme.

http://php.net/manual/en/language.control-structures.php

### Evaluer un nombre comme étant positif, négatif ou nul

```php

	// nombre donné
	$nb =  -1;

	if( $nb > 0 )
	{
		echo "$nb est POSITIF";
	}
	else if( $nb < 0 )
	{
		echo "$nb est NEGATIF";
	}
	else
	{
		echo "$nb est NUL";
	}

```

### Tester par exemple, si une image existe avant de l'afficher

```php

	define('PATH_PHOTOS','images/');
	$photo = 'cha.jpg';
	$photodefaut = 'defaut.jpg';

	if( file_exists(PATH_PHOTOS.$photo)){
		$maPhoto = PATH_PHOTOS.$photo;
	}else{
		$maPhoto = PATH_PHOTOS.$photodefaut;
	}

```

### Evaluer un score :

```php

	/*-------- Syntaxe 1 -------------------------------*/


		$total = 6;

		if ( $total < 5) {
			echo "très insuffisant";
		}else if ( $total >=5 && $total <= 9) {
			echo " des progrès doivent être faits";
		}else if( $total >=10 && $total <= 14){
			echo "Bon travail";
		}else{
			echo "Très bon travail";
		}

	/*-------- Syntaxe 2 -------------------------------*/


		if ( $total < 5) :
			echo "très insuffisant";
		else if ( $total >=5 && $total <= 9) :
			echo " des progrès doivent être faits";
		else if( $total >=10 && $total <= 14) :
			echo "Bon travail";
		else:
			echo "Très bon travail";
		endif;

```

# Structures de boucle

un structure permet d’exécuter très rapidement une série d’instructions de même nature.
Ci dessous : une boucle **for** compte jusqu'à 200.

```php
	for($i=1 ; $i<=200 ; $i++):
		 echo "compte $i <br>";
     endfor;
```

Ci dessous, une boucle **while** permet d'extraire deux couleurs tirées au hasard dans un tableau

```php
    $T =  ['red','blue','orange','pink','purple','yellow','cyan'];
    $T2 = [];
	$nb = 2;
	while($nb>0) :
		# tirage
		$r = rand(0,count($T)-1);
		# extrait une couleur dans 1 tableau de 1 valeur
		$extract_T = array_splice($T, $r, 1);
		# extrait la couleur
		array_push($T2, array_shift($extract_T));
		$nb --;
	endwhile;
    var_dump($T2);
```

**NB :** Une structure de boucle ne rend la main qu’une fois qu’elle a terminé.

# Les fonctions

Le rôle des fonctions est de placer dans un structure nommée, une suite d'instructions dont le programme peut avoir besoin plusieurs fois, à plusieurs endroits du programme.  
**Attention**, on ne parle pas de répétition au sens de répéter en _boucle_.  
Les fonctions permettent aussi de modulariser un programme afin de le rendre plus maintenable , plus lisible.

## Déclaration et exécution

```php
    /*
        Déclare fonction
    */
    function donneUneCouleur(){
        $tab_couleurs = ['red','green','blue','orange'];
        $r =  rand(0, count($tab_couleurs)-1);
        $une_couleur = $tab_couleurs[$r];
        // affiche
        echo $une_couleur;
    }
    /*
        execute fonction
    */
    donneUneCouleur();
```

## Fonction qui retourne un résultat

IL est courant qu’une fonction retourne une valeur en mémoire, cela permet de d’exploiter plus facilement le résultat.

```php
    /*
        Déclare fonction
    */
    function donneUneCouleur(){
        $tab_couleurs = ['red','green','blue','orange'];
        $r =  rand(0, count($tab_couleurs)-1);
        $une_couleur = $tab_couleurs[$r];
        // return résultat
        return $une_couleur;
    }
    /*
        affiche le résultat de la fonction
    */
    echo donneUneCouleur();
```

## Fonction paramétrable.

Les fonctions paramétrables optimisent le r est aussi d'éviter de réécrire des blocs de code qui sont récurrents dans un programme.

```php
    /*
        Déclare fonction paramétrable
    */
    function donneUneCouleur( $_tab ){

        $r =  rand(0, count($_tab)-1);
        $une_couleur = $_tab[$r];
        // return résultat
        return $une_couleur;
    }

    // tableau de couleur déclaré comme variable globale.

    $tab_couleurs = ['red','green','blue','orange'];
    /*
        execute fonction avec passage d'argument
    */
    echo donneUneCouleur( $tab_couleurs );
```

# Modèle de construction de page

Pour des construction de page simple, il est bon de déclarer d'abord des variables et contrôler avant d'afficher.

```php
<?php
     # variables PHP

     $name = "Louis";
     $ville = "Paris";

     $texte = "Lorem ipsum repellat voluptatem qui voluptate sed similique commodi";
?>
```

Ensuite l'intégration dans un modèle de page

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>Page de <?= $name ?></title>
  </head>
  <body>
    <h1>
      Username :
      <?= $name ?>
    </h1>
    <p>
      Ville
      <?= JOB ?>
    </p>
    <p>
      Infos :
      <?php echo $texte ?>
    </p>
  </body>
</html>
```
