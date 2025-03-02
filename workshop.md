# Workshop - Le langage Go

## Installation

Windows/Mac : [ça se passe ici](https://go.dev/learn/)

Ubuntu/autres distribs Debian : `sudo apt install golang-go`

Fedora : `sudo dnf install go`

Autres distributions Linux : Confer manuel de votre distribution.

## Partie I - Découverte du langage

### Exercice 1 - Hello World

Créez un fichier `hello_world.go`, contenant un code en Go qui une fois lancé écrit `Hello, world !` sur la sortie standard.

![output attendu](https://i.imgur.com/kd5Z7IR.png)

### Exercice 2 - Compilation

Compilez l'exercice précédent sous la forme d'un programme `hello-world`

![output attendu](https://i.imgur.com/n4QgHB1.png)

### Exercice 3 - my_print_alpha

Créez un programme "my_print_alpha" qui une fois lancé, imprime l'alphabet en minuscule sur la sortie standard, suivi du caractère `\n`.

![output attendu](https://i.imgur.com/NmHOk4s.png)

### Exercice 4 - my_print_comb

Créez un programme "my_print_comb" qui imprime, dans l'ordre croissant, tous les nombres composés par 3 chiffres **différents** (012, 013, 014, 015, 016, 017, 018, 019, 023, . . . , 789). Si plusieurs nombres peuvent être réalisés avec les 3 chiffres, seul le plus petit doit être affiché.

![output attendu](https://i.imgur.com/ZU62ZBJ.png)

### Exercice 5 - Goroutine

Le but de cet exercice sera de découvrir les goroutines, élément important du Go permettant de gérer le multi-threading.

Créez un fichier `goroutines.go` qui contiendra une fonction print_numbers, qui prendra en paramètre un int et imprimera tout les nombres de 0 au nombre donné, avec un retour à la ligne entre chaque.

Lancez la fonction depuis le main dans une goroutine.

`go print_numbers`

Le programme se ferme instantanément, sans print quoi que ce soit. Que se passe-t-il ?

En fait, la fonction main se termine sans attendre que la goroutine soit finie. Votre mission pour cet exercice donc trouver un moyen d'attendre la fin de la goroutine pour fermer le programme.

![Output attendu pour un 10 à la fonction](https://i.imgur.com/lbOravm.png)

### Exercice 5++ - Goroutine v2

Maintenant que vous savez lancer une goroutine, pourquoi ne pas en lancer plusieurs en même temps ? Reprenez l'exercice au-dessus et lancez en 2 à la fois.

Si vous passez de grands nombres, vous pourrez observer que le print ne se synchronise pas, car les deux fonctions s'exécutent simultanément !

## Partie II - Mise en pratique

### Exercice 1 - Convertisseur d'argent

Réalisez un programme qui prend en argument une somme d'argent et une monnaie, et qui donne la valeur de la somme en la monnaie choisie.

⚠️ La monnaie de base sera l'Euro.

![Valeur attendue](https://imgur.com/kHs2B7J.png)

Monnaies à implémenter : Dollar, Yen, Yuan, Euro, Roupie Indienne

### Exercice 2 - my_ls

Réaliser un programme qui liste les fichiers contenus dans votre dossier. Vous n'avez pas besoin d'implémenter d'options.

![Output attendu](https://imgur.com/ooBahAJ.png)

### Exercice 3 - Requêtes internet

⚠️ `api.reddit.com`
⚠️ `https://mholt.github.io/json-to-go/`

#### Etape 1

Réalisez un programme qui va prendre tous les profils qui ont commenté sur une publication Reddit.

#### Etape 2

A l'aide des goroutines, faites en sorte que votre programme passe dans chaque profil et affiche sa description ainsi que ses 5 derniers posts.

### Etape 3

Réalisez un programme qui analyse les mots les plus fréquents dans les titres des posts ou dans les commentaires d'une publication spécifique Reddit. Votre programme devra afficher une liste des mots les plus utilisés, accompagnés de leur fréquence.

### Etape 4

Créez un programme qui récupère des statistiques sur une publication Reddit. Les données affichées devront inclure :

- Le nombre total de commentaires.
- Le nombre d'utilisateurs uniques ayant commenté.
- Le score total cumulé des commentaires.

### Étape 4

⚠️ Si vous en êtes arrivés à cet exercice, premièrement, félicitations. Deuxièmement, venez me voir pour obtenir une clé API OpenAI si besoin une fois que vous aurez rédigé une POC de communication avec cette API.

Réalisez un programme qui récupère tous les posts d'un thread Reddit, puis envoie une requête à l'API OpenAI pour :

1. Générer un résumé du thread, basé sur le contenu des commentaires et du post principal.
2. Identifier et afficher quelques posts/commentaires particulièrement intéressants (par exemple, ceux ayant reçu le plus de votes ou qui contiennent des informations pertinentes).

Résultat attendu :
Votre programme prend un thread reddit en paramètre, et résume le thread ainsi que les réponses intéressantes dessus.
