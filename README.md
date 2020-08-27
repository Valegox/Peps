# Peps

<p align="center">
	<img width="250" src="https://github.com/PastequeBuild/Peps/blob/master/logo.png?raw=true">
</p>

Vidéo de présentation: https://www.youtube.com/watch?v=FkgnLjq8gAI

Peps est un projet en développement depuis le 16 juin 2020. L'objectif est de permettre à n'importe qui de développer facilement des jeux pour appareils iOS et Android.  
Le code est écrit depuis un site. Le développeur peut essayer simultanément sa création sur son téléphone via l'application Peps.  
On peut publier ses jeux sur la plateforme Peps afin que n'importe qui puisse l'essayer.

Interface du site:


![alt website](https://github.com/PastequeBuild/Peps/blob/master/website.png?raw=true)

![alt website](https://github.com/PastequeBuild/Peps/blob/master/website_style.png?raw=true)

Interface de l'application (Doodle Jump étant un exemple):

<p align="center">
	<img width="250" src="https://github.com/PastequeBuild/Peps/blob/master/app.png?raw=true">
</p>

# Documentation du langage Peps
Le site et l'application sont encore en cours de développement. Il sera bientôt possible d'essayer une bêta.
Ce que vous voyez sur la documentation a déjà été réalisé ou est en cours de réalisation.
## Setup
1. Installez l’application Peps sur App Store ou Play Store.
2. Rendez-vous sur le site de Peps et créez un projet.
3. Tapez CONSOLE à la toute première ligne de code de votre projet, vous devriez voir la console s’afficher sur votre téléphone. Pour la retirer, enlevez CONSOLE.
4. Enjoy !
## Types primitifs
Les types primitifs sont les types les plus simples que l’on puisse trouver en Peps.
(Note: dans cette documentation, anyType désignera n’importe quel type primitif).
### string
- Description: Chaîne de caractères définie par des guillemets.
- Exemple: ```“Ma chaîne de caractères"```
### number
- Description: Nombre pouvant être entier ou à virgule (la virgule est représentée par un point).
- Exemples: ```8``` ```42.7```
### boolean
- Description: Type n’ayant que deux valeurs possibles: true (vrai) ou false (faux)
- Exemples: ```true``` ```false```
### undefined
- Description: Type représentant une valeur indéfinie. Valeur retournée lorsque l’élément demandé n’a pas été défini, ou lorsque la variable a été définie comme indéfinie.
- Exemple: ```undefined```
## Fonctions basiques
### Afficher des valeurs sur la console
```
print(anyType param1,  anyType param2, ..., anyType paramN)
```
- Description: Affiche des valeurs sur la console.
- Paramètres: Autant de paramètres que l’on veut de n’importe quel type.
- Type de valeur retourné par la fonction: ```undefined```.
### Attendre avant d'exécuter une fonction
```
wait(number delay, function functionTriggeredAfterWait)
```
- Description: Exécute une fonction après un délai défini.
- Paramètres: 
  - ```delay```: le délai d’attente avant exécution de la fonction en millisecondes,
  - ```functionTriggeredAfterWait```: la fonction exécutée après le délai choisi.
- Type de valeur retournée par la fonction: ```undefined```.
### Exécuter une fonction toutes les n secondes
Créer l'intervalle:
```
setInterval(string intervalName, function triggeredFunction, number delay)
```
- Description: Exécute une fonction à intervalle d'un délai défini.
- Paramètres:
  - ```intervalName```: nom de l'intervalle que l'on crée,
  - ```triggeredFunction```: fonction exécutée à l'intervalle défini,
  - ```delay```: le délai entre chaque exécution de fonction.
- Type de valeur retournée par la fonction: ```undefined```.

Arrêter l'intervalle:
```
clearInterval(string intervalName)
```
- Description: Arrête un intervalle.
- Paramètre:
  - ```intervalName```: nom de l'intervalle que l'on veut tuer.
- Type de valeur retournée par la fonction: ```undefined```.

Attention: les intervalles sont globaux, ils ne doivent pas être créés deux fois avec le même nom dans différents composants. On peut tuer un intervalle créé dans un composant A depuis un composant B.
### Animer un composant

### Générer un nombre aléatoire compris entre deux nombres
```
randomNumber(number min, number max)
```
- Description: Génère un nombre aléatoire entre un nombre minimum et un nombre maximum.
- Paramètres:
  - ```min```: le nombre minimum
  - ```max```: le nombre maximum
- Type de valeur retournée par la fonction: ```number```.
### Quitter le jeu
```
quitGame()
```
- Description: Dès que la fonction est exécutée, le jeu se ferme et l'utilisateur est redirigé sur la page de navigation Peps
- Type de valeur retournée par la fonction: ```undefined```.
### Faire vibrer l'appareil
```
vibrate(string intensity)
```
- Description: Fait vibrer l'appareil sur une courte durée.
- Paramètre:
  - ```intensity```: l'intensité de la vibration. Voici les trois niveaux d'intensité:
  	- ```light```
	- ```medium```
	- ```heavy```
- Type de valeur retournée par la fonction: ```undefined```.
## Variables
### Définition d'une variable
```
varName =  value
```
```varName``` étant le nom de la variable, ```value``` étant sa valeur (de type ```anyType```)
### Récupération d'une variable
Il suffit de taper le nom de la variable là où l'on veut récupérer sa valeur.
```
message = "Bonjour"
print(message) //affiche "Bonjour" sur la console
```
## Types complexes
Les types complexes sont les types qui retournent une ou plusieurs valeurs dont le type est simple.
### function
#### Description
Fonction qui exécute du code et retourne une valeur.
#### Exemples
##### Définition d'une fonction
```
function myFunctionName(myParameter):
  myCode(myParameter) //on considère le paramètre myParameter comme une variable interne à la fonction.
  return("my value")
  
//ici nous sommes à l'extérieur de la fonction, on ne peut plus récupérer myParameter.
 ```
##### Utilisation d'une fonction
```
myFunctionName(42) //ceci exécutera la fonction, donc myCode(42)
```
##### Utilisation d’une fonction en tant que paramètre
```
print(myFunctionName(42)) //ceci exécutera la fonction, donc myCode(42) et affichera la valeur retournée, ici "my value".
```
##### Type de valeur primitif retourné par le type complexe
```anyType```
### equality
#### Description
Egalité permettant de réaliser des tests entre deux valeur anyType au sein du code. Plusieurs types d’égalités:
- ```==``` : Vérifier si deux valeurs sont égales;
- ```!=``` : Vérifier si deux valeurs ne sont pas égales;
- ```>``` : Vérifier si une valeur est plus grande que l’autre;
- ```<``` : Vérifier si une valeur est plus petite qu’une autre;
- ```>=``` : Vérifier si une valeur est plus grande ou égale qu’une autre;
- ```<=``` : Vérifier si une valeur est plus petite ou égale qu’une autre.
#### Exemples
```
print(2 == 2) //affiche true sur la console
```
```
print("test" != "test") //affiche false sur la console
```
#### Type de valeur primitif retourné par le type complexe
```boolean```
### operation
#### Description
Opération mathématique entre plusieurs valeurs de type number à partir des opérateurs suivants:
- ```+``` : addition
- ```--``` : soustraction (deux ```-``` dans une opération, un seul ```-``` pour le signe de la valeur)
- ```*``` : multiplication
- ```/``` : division
#### Exemples
```
print(2 + 2) //affiche 4 sur la console
```
```
print(5 / 7 * 86 + 42 - 8) //affiche 95.42857142857143 sur la console
```
#### Type de valeur primitif retourné par le type complexe
```number```
### array (ou list)
#### Description
Le type ```array``` constitue ce qu'on appelle une liste de valeurs ```anyType```.
#### Exemples
```
print([5, "hello", true])
```
Une liste peut contenir elle même une liste:
```
print([2, ["test", 0], false])
```
On peut récupérer un élément précis d'une liste à partir de sa position, le premier élément correspondant à la position 1.
Pour cela on utilise le caractère ```@``` suivi de la position.
```
print([9, 42, 17]@2) //affiche 42
```
#### Fonctions associées au type
##### size()
La fonction ```size()``` retourne la taille de son paramètre de type ```array```.
###### Forme
```
size(array parameter)
```
###### Exemple
```
print(size([5, 10])) //affiche 2 sur la console car il y a deux éléments dans la liste
```
##### add()
La fonction ```add()``` ajoute une valeur a la fin d'une liste stockée en tant que variable.
###### Forme
```
add(variable arrayToModify, anyType valueToAdd)
```
###### Exemple
```
myArray = [1, 2]
print(myArray) //affiche [1,2] sur la console
add(myArray, 3)
print(myArray) //affiche [1,2,3] sur la console
```
### map
#### Description
Le type ```map``` correspond à un ensemble de clés-valeurs.
#### Exemple
```
{ name: "Jean", age: 27, married: false }
```
On peut récupérer une valeur de l'objet à partir de sa clé. Pour cela on utilise le caractère ```.``` suivi de la clé.
```
user = { name: "Jean", age: 27, married: false }
print(user.name) //affiche "Jean" sur la console
```
Si l'on ne connaît la clé mais que l'on peut la retrouver à l'aide d'une fonction ou d'une variable, on peut utiliser des crochets ```[]```:
```
key = "name"
user = { name: "Jean", age: 27, married: false }
print(user.[key]) //affiche "Jean" sur la console
```
Attention: pour l'instant, il est interdit de faire suivre plusieurs ```.``` et/ou ```@``` dans une même ligne. Il faut créer plusieurs variables.
#### Fonctions associées au type
##### keysList()
La fonction ```keysList()``` retourne une liste de ```string``` regroupant toutes les clés d'une ```map```.
###### Forme
```
keysList(map parameters)
```
###### Exemple
```
user = { name: "Jean", age: 27, married: false }
print(keysList(user)) //affiche ["name", "age", "married"] sur la console
```
##### setKey()
La fonction ```setKey()``` défini une clé dans un ```map```.
###### Forme
```
setKey(variable mapToModify, string keyName, anyType value)
```
###### Exemple
```
user = { name: "Jean", age: 27, married: false }
setKey(user, "livingPlace", "Paris")
print(user) //affiche { name: "Jean", age: 27, married: false, livingPlace: "Paris" } sur la console
```
## Conditions
### if
#### Description
Le contenu du ```if()``` est exécuté si le paramètre renvoie la valeur ```true```.
#### Forme
```
if (boolean myCondition):
  myCodeExecutedOnlyIfMyConditionIsTrue()
```
#### Exemple
```
if (2 + 2 == 4):
  print("2 + 2 est égal à 4")
```
### else
#### Description
Le contenu du ```else``` correspond à "sinon". Il est toujours précédé d'un ```if()```.
#### Forme
```
if (boolean myCondition):
  myCodeExecutedOnlyIfMyConditionIsTrue()
else:
  myCodeExecutedOnlyIfMyConditionIsFalse()
```
#### Exemple
```
if (2+2 == 5):
  print("2 + 2 est égal à 5") //cette ligne ne sera pas exécutée
else:
  print("2 + 2 n'est pas égal à 5") //cette ligne sera exécutée
```
## Boucles
### While
#### Description
La boucle ```while``` correspond au souhait d'exécuter du code tant qu'une valeur booléenne reste ```true```. La valeur en question doit donc devenir ```false``` à un moment donné si l'on ne veut pas que la boucle soit continue indéfiniment et que le code devienne inutilisable.
Il est impossible d'utiliser ```wait()``` ou ```return()``` à l'intérieur d'un ```while()```.
#### Forme
```
while (boolean myCondition):
	myCodeExecutedWhileMyConditionIsTrue()

myCodeExecutedOnceMyConditionIsFalse()
```
#### Exemple
Compter jusqu'à 10:
```
count = 0

print("Le comptage va commencer.")

while (count <= 10):
	print(count)
	count = count + 1

print("Le comptage est terminé.")
```
## Composants
Un jeu codé en Peps regroupe plusieurs composants. Un composant peut être visible ou invisible. Il existe deux types de composants visibles:
- Les aires
- Les textes


On peut styliser ces composants depuis l'interface du site, mais aussi y inclure du code. Les composants sont structurés hiérarchiquement, on parle de composant parent et de composant enfant.
### Activer et désactiver un composant en lui confiant des données
Pour qu'un composant vive, il faut que son parent l'active à travers cette fonction basique:
```
enable(string componentName, map dataToPass, string componentID)
```
Le composant enfant a accès à ```dataToPass``` depuis l'objet ```PARENT```.

Il est impossible d'appeler une fonction passée dans l'objet ```PARENT``` à la première exécution lors du ```enable()```.

```componentID``` correspond à un indentifiant que plusieurs composants peuvent avoir en commun.

On peut à tout moment tuer le composant:
```
disable(string componentName) //tuer le ou les composants enfants ayant ce nom
disable(string componentID) //tuer le ou les composants enfants ayant cet ID
```
Seul le parent d'un composant peut directement tuer son enfant. Lorsqu'un composant est tué, l'ensemble de ses enfants le sont aussi.
Un composant mort n'exécute plus aucun code, et devient invisible s'il a été paramétré préalablement comme visible.
### Le composant Main
```Main``` est un composant défini par défaut au sommet de la chaîne hierarchique des composants. Il n'a donc pas de parent, et tous les composants du jeu sont ses enfants. ```Main``` est activé dès le lancement du programme. Il est impossible de le tuer. C'est à l'intérieur de ce composant que l'on peut afficher la console à l'aide du mot-clé ```CONSOLE```, placé au tout début du code.
## Evenements
Le code d'un bloc événement n'est exécuté que lorsque celui-ci se réalise.
### Forme
```
on my event:
	myCode()
```
### Exemple
Dire "Hello" lorsque l'on appuie sur le composant visible dans lequel le code se trouve.
```
on touch:
	print("Hello")
```
Si le composant est invisible, il n'y aura pas d'erreur mais le ```print("hello")``` ne sera jamais appelé car il est impossible d'appuyer sur le composant.
### Liste des types d'événements
- ```on touch``` lorsque l'on appuie sur le composant
- ```on parent update``` lorsque l'objet ```PARENT``` est mit à jour (lié à une modification de variable passée en argument de ```enable()``` dans le composant parent)
## L'objet DEVICE
L'objet ```map``` ```DEVICE``` est accessible depuis n'importe quel composant. Il permet de récupérer les dimensions de l'écran l'appareil en pixels, ainsi que l'OS (```"android"``` ou ```"ios"```).
## Styliser ses composants dynamiquement
Il est possible de styliser ses composants de manière statique depuis l'interface de développement. Néanmmoins, il est possible que vous vouliez changer des particularités visuelles depuis le code.
### Forme
```
setStyle(string property, anyType value)
```
### Exemple
Admettons que vous vouliez définir la couleur de fond en rouge dès que l'on appuie sur le composant.
```
on touch:
	setStyle("backgroundColor", "red")
```
### Liste des propriétés de style
#### Composants "aire"
- ```backgroundColor```: couleur de fond
- ```position```: type de position
- ```left```: coordonnée x
- ```bottom```: coordonnée y
- ```zIndex```: coordonnée z
- ```opacity```: opacité
- ```height```: hauteur
- ```width```: largeur
- ```borderWidth```: épaisseur des bordures
- ```margin```: marge extérieure aux bordures
- ```padding```: marge intérieure aux bordures
- ```borderRadius```: arrondi aux angles
- ```alignDirection```: direction des composants enfants
- ```alignHorizontal```: alignement des composants enfants sur l'axe horizontal
- ```alignVertical```: alignement des composants enfants sur l'axe vertical
- ```flexWrap```: comportement des composants enfants lorsqu'ils dépassent le composant parent
#### Composants "texte"
- ```textContent```: texte
- ```color```: couleur
- ```position```: type de position
- ```left```: coordonnée x
- ```bottom```: coordonnée y
- ```zIndex```: coordonnée z
- ```fontSize```: taille du texte
- ```fontWeight```: épaisseur du texte
- ```textDecorationLine```: soulignage
- ```fontStyle```: italique
- ```fontFamily```: police d'écriture
- ```margin```: marge extérieure aux bordures
## Animer un composant
La première solution qui vous viendra à l'esprit si vous voulez animer votre composant sera de placer un ```setStyle()``` à l'intérieur d'un ```setInterval()```. Cette solution n'est pas optimale car elle génère des problèmes de fluidité sur Android. La manière la plus rapide et optimisée de créer une animation est d'utiliser la fonction Peps ```animate()```.
### Forme
```
animate(string animationType, number finalValue, number duration, number numberOfTimes, function callback)
```
### Paramètres
- ```animationType```: le type d'animation, en voici la liste:
	- ```spin``` pour exercer une rotation du composant sur lui même,
	- ```moveX``` pour déplacer le composant horizontalement,
	- ```moveY``` pour déplacer le composant verticalement.
- ```finalValue```: la valeur finale de l'animation. Le sens de l'animation dépend de son signe.
	- pour les rotations, 0 correspond à 0 degrès, 0.5 correspond à 180 degrès et 1 correspond à 360 degrès.
	- pour les déplacements, il s'agit de la valeur en pixel.
- ```duration```: la durée de l'animation en millisecondes.
- ```numberOfTimes```: le nombre de fois que l'animation se produit en boucle. Pour que l'animation continue indéfiniment, ```numberOfTime``` doit être égal à -1.
- ```callback```: fonction Peps effectuée une fois que l'animation est terminée.
## Exemples de code
### Dire bonjour en fonction d'une heure
Ce programme permet de dire bonjour en fonction d'une heure définie sous la variable ```time```.
```
CONSOLE //doit être placé au début du code afin d'afficher la console sur l'application

time = 17 //définition de la variable time

if (time <= 12):
	sayGoodMorning("Patrick")
else:
	if (time <= 18):
		sayGoodAfternoon("Jean")
	else:
		sayGoodEvening("Antonio")

//cette fonction permet de dire bonjour le matin
function sayGoodMorning(name):
	print("Good morning", name)

//cette fonction permet de dire bonjour l'après midi
function sayGoodAfternoon(name):
	print("Good afternoon", name)

//cette fonction permet de dire bonjour le soir
function sayGoodEvening(name):
	print("Good evening", name)
```
### Afficher le prix de consoles de jeux
```
CONSOLE //doit être placé au début du code afin d'afficher la console sur l'application

print("Prix de la Xbox One:", getPrice("Xbox One"))
print("Prix de la PS 5:", getPrice("PlayStation 5"))

//cette fonction permet de récupérer le prix d'une console de jeu en fonction de son paramètre article
function getPrice(article):
	if (article == "Xbox One"): //on vérifie le nom du paramètre article
		return(200)
	else:
		if (article == "PlayStation 5"): //ici aussi
			return(450)
```
### Faire un compte à rebours
```
CONSOLE //doit être placé au début du code afin d'afficher la console sur l'application

print("Début du compte à rebours")

i = 10

while (i >= 0): //tant que i est supérieur ou égal à 0
	print(i)
	i = i - 1 //on retire 1 à i

print("BONNE ANNÉE !")
```
# Todolist
### Support
- [x] Initialisation + Interfaces de base + liaison de l'application au site (frontend & database)
- [x] Interface du site
- [x] Interface de l'application
- [x] Système d'authentification avec projets dédiés à chaque compte
- [ ] Documentation sur un site dédié
### Langage de programmation: bases algorithmiques
- [x] Lecture algorithmique et envoi du futur code Peps sur la base de données
- [x] Affichage de la console lorsque le code commence par le mot-clé CONSOLE
- [x] Initialisation du transpileur et des types primitifs
- [x] Fonction basique ```print()```
- [x] Type complexe: ```equality```
- [x] Type complexe: ```operation```
- [x] Fonctions basiques ```setVar()``` et ```getVar()``` (remplacées ensuite par une syntaxe de variables plus classique)
- [x] Pouvoir définir une fonction exécutant du code (type complexe: ```function```)
- [x] Permettre de retourner une valeur au sein de la fonction à l'aide de ```return()```
- [x] Accès aux paramètres à l'intérieur d'une fonction définie avec ```getVar()```
- [x] Fonction basique ```wait()```
- [x] Conditions ```if()``` ```else```
- [x] Commentaires ```//```
- [x] Fonction basique de boucle: ```while()```
- [x] Type ```array``` (liste) et fonctions basiques ```add()```, ```remove()``` et ```size()``` associées
- [x] Pouvoir stocker une valeur de type ```function``` dans une variable ainsi que comme paramètre de fonction créée
- [x] Fonction basique ```randomNumber()```
- [x] Fonctions basiques ```setInterval()``` et ```clearInterval()```
- [x] Type ```map``` (dictionnaire) et fonctions basiques associées
- [x] Pouvoir associer différentes valeurs ```anyType``` en un seul ```string```
- [ ] Pouvoir définir les ```array``` et les ```map``` sur plusieurs lignes de code
### Transpileur évolué
- [x] Représentation hierarchique et intéractive des composants sur l'interface de programmation
- [x] Séparation du code en plusieurs composants + suite algorithmique des composants
- [x] Possibilité de rendre un composant visible à travers une image ou un objet stylisable
- [x] Evenements associés à l'intéraction de l'utilisateur (lorsqu'on touche l'écran)
- [x] Pouvoir modifier du contenu textuel et du style depuis le code
- [x] Ajout des propriétés de style correspondant au type de position et aux coordonnées X, Y et Z d'un composant
- [x] Possibilité de créer une instance de composant avec ```enable()``` et l'objet ```map```  ```PARENT```
- [x] Evenement ```on parent update```
- [x] Possibilité de copier coller un composant depuis l'interface
- [ ] Fonction ```vibrate()```
- [ ] Ajout de la propriété de style correspondant à l'image de fond d'un composant aire
- [ ] Possibilité de créer des clones de composant: lorsque le développeur change le code / style d'un composant, tous ses clones changent aussi le leur
- [ ] Fonction permettant de stocker des données de l'utilisateur sur la base de données de Peps
## Informations techniques
Peps est codé en Javascript avec les frameworks React et React-Native.
Le transpileur de Peps se trouve sur l'application.
Firebase est le service utilisé pour la base de données qui stocke les programmes ainsi que les données des utilisateurs.
