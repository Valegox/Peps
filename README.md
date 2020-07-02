# Peps
Peps est un projet en développement depuis le 16 juin 2020. L'objectif est de permettre à n'importe qui de développer facilement des casual games pour appareils iOS et Android.  
Le code est écrit depuis un site. Le développeur peut essayer simultanément sa création sur son téléphone via l'application Peps.  
On peut publier ses jeux sur la plateforme Peps afin que n'importe qui puisse l'essayer.

Une petite idée de l'interface du site:


![alt website](https://github.com/PastequeBuild/Peps/blob/master/website.png?raw=true)
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
## Fonctions basiques:
### Afficher des valeurs sur la console
```
print(anyType param1,  anyType param2, ..., anyType paramN)
```
- Description: Affiche des valeurs sur la console.
- Paramètres: Autant de paramètres que l’on veut de n’importe quel type.
- Type de valeur retourné par la fonction: ```undefined```.
### Définir une variable
```
setVar(string variableName, anyType variableValue)
```
- Description: Défini une variable.
- Paramètres:
  - ```variableName```: le nom de la variable que l’on veut définir (si ce nom de variable existe déjà l’ancienne valeur sera écrasée),
  - ```variableValue```: la valeur de la variable.
- Type de valeur retourné par la fonction: ```undefined```
### Récupérer une variable
```
getVar(string variableName)
```
- Description: Récupère la valeur d’une variable.
- Paramètres:
  - ```variableName```: le nom de la variable dont on veut récupérer la valeur.
- Type de valeur retournée par la fonction: ```anyType``` (type de la valeur de la variable).
### Attendre avant d'exécuter une fonction
```
wait(number delay, function functionTriggeredAfterWait)
```
- Description: Exécute une fonction après un délai défini.
- Paramètres: 
  - ```delay```: le délai d’attente avant exécution de la fonction en millisecondes,
  - ```functionTriggeredAfterWait```: la fonction exécutée après le délai choisi.
- Type de valeur retournée par la fonction: ```undefined```.
## Types complexes
Les types complexes sont les types qui retournent une ou plusieurs valeurs dont le type est simple.
### function
#### Description
Fonction qui exécute du code et retourne une valeur.
#### Exemples
##### Définition d'une fonction
```
function myFunctionName(myParameter):
  myCode(getVar("myParameter")) //on considère le paramètre myParameter comme une variable interne à la fonction.
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
- == : Vérifier si deux valeurs sont égales;
- != : Vérifier si deux valeurs ne sont pas égales;
- \> : Vérifier si une valeur est plus grande que l’autre;
- < : Vérifier si une valeur est plus petite qu’une autre;
- \>= : Vérifier si une valeur est plus grande ou égale qu’une autre;
- <= : Vérifier si une valeur est plus petite ou égale qu’une autre.
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
- \+ : addition
- \- : soustraction
- \* : multiplication
- / : division
#### Exemples
```
print(2 + 2) //affiche 4 sur la console
```
```
print(5 / 7 * 86 + 42 - 8) //affiche 95.42857142857143 sur la console
```
#### Type de valeur primitif retourné par le type complexe
```number```
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
setVar("count", 0)

print("Le comptage va commencer.")

while (getVar("count") <= 10):
	print(getVar("count"))
	setVar("count", getVar("count")+1)

print("Le comptage est terminé.")
```
## Composants
Un jeu codé en Peps regroupe plusieurs composants. Un composant peut être visible ou invisible. Il existe deux types de composants visibles:
- Les aires
- Les textes


On peut styliser ces composants depuis l'interface du site, mais aussi y inclure du code. Les composants sont structurés hiérarchiquement, on parle de composant parent et de composant enfant.
### Activer et désactiver un composant
Pour qu'un composant vive, il faut que son parent l'active à travers cette fonction basique:
```
enable(string componentName)
```
On peut à tout moment tuer le composant de cette manière:
```
disable(string componentName)
```
Seul le parent d'un composant peut tuer son enfant. Lorsqu'un composant est tué, l'ensemble de ses enfants le sont aussi.
Un composant mort n'exécute plus de code, et devient invisible s'il a été paramétré préalablement comme visible.  
### Le composant Main
```Main``` est un composant défini par défaut au sommet de la chaîne hierarchique des composants. Il n'a donc pas de parent, et tous les composants du jeu sont ses enfants. ```Main``` est activé dès la compilation. Il est impossible de le tuer. C'est à l'intérieur de ce composant que l'on peut afficher la console à l'aide du mot-clé ```CONSOLE```, placé au tout début du code.
## Evenements
Le code d'un bloc événement n'est exécuté que lorsque celui-ci se réalise.
### Forme
```
on myEvent:
	myCode()
```
### Exemple
Dire "Hello" lorsque l'on appuie sur le composant dans lequel le code se trouve.
```
on touch:
	print("Hello")
```
### Liste des types d'événements
- ```touch```
## Styliser ses composants dynamiquement
Il est possible de styliser ses composants de manière statique depuis l'interface de développement. Néanmmoins, il est possible que vous vouliez changer des particularités visuelles depuis le code.
### Forme
```
SetStyle(string property, anyType value)
```
### Exemple
Admettons que vous vouliez définir la couleur de fond en rouge dès que l'on appuie sur le composant.
```
on touch:
	SetStyle("backgroundColor", "red")
```
### Liste des propriétés de style
#### Composants "aire"
- ```backgroundColor```: couleur de fond
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
- ```fontSize```: taille du texte
- ```fontWeight```: épaisseur du texte
- ```textDecorationLine```: soulignage
- ```fontStyle```: italique
- ```fontFamily```: police d'écriture
- ```margin```: marge extérieure aux bordures
## Exemples de code
### Dire bonjour en fonction d'une heure
Ce programme permet de dire bonjour en fonction d'une heure définie sous la variable ```time```.
```
CONSOLE //doit être placé au début du code afin d'afficher la console sur l'application

setVar("time", 17) //définition de la variable time

if (getVar("time") <= 12):
	sayGoodMorning("Patrick")
else:
	if (getVar("time") <= 18):
		sayGoodAfternoon("Jean")
	else:
		sayGoodEvening("Antonio")

//cette fonction permet de dire bonjour le matin
function sayGoodMorning(name):
	print("Good morning", getVar("name"))

//cette fonction permet de dire bonjour l'après midi
function sayGoodAfternoon(name):
	print("Good afternoon", getVar("name"))

//cette fonction permet de dire bonjour le soir
function sayGoodEvening(name):
	print("Good evening", getVar("name"))
```
### Afficher le prix de consoles de jeux
```
CONSOLE //doit être placé au début du code afin d'afficher la console sur l'application

print("Prix de la Xbox One:", getPrice("Xbox One"))
print("Prix de la PS 5:", getPrice("PlayStation 5"))

//cette fonction permet de récupérer le prix d'une console de jeu en fonction de son paramètre article
function getPrice(article):
	if (getVar("article") == "Xbox One"): //on vérifie le nom du paramètre article
		return(200)
	else:
		if (getVar("article") == "PlayStation 5"): //ici aussi
			return(450)
```
### Faire un compte à rebours
```
CONSOLE //doit être placé au début du code afin d'afficher la console sur l'application

print("Début du compte à rebours")

setVar("i", 10)

while (getVar("i") >= 0): //tant que i est supérieur ou égal à 0
	print(getVar("i"))
	setVar("i", getVar("i")-1) //on retire 1 à i

print("BONNE ANNÉE !")
```
# Todolist
### Support
- [x] Initialisation + Interfaces de base + liaison de l'application au site (frontend & database)
- [x] Interface du site
- [ ] Interface de l'application
- [ ] Système d'authentification avec projets et scores dédiés à chaque compte
- [ ] Documentation
### Langage de programmation: bases algorithmiques
- [x] Lecture algorithmique et envoi du futur code Peps sur la base de données
- [x] Affichage de la console lorsque le code commence par le mot-clé CONSOLE
- [x] Initialisation du compileur et des types primitifs
- [x] Fonction basique ```print()```
- [x] Type complexe: ```equality```
- [x] Type complexe: ```operation```
- [x] Fonctions basiques ```setVar()``` et ```getVar()```
- [x] Pouvoir définir une fonction exécutant du code (type complexe: ```function```)
- [x] Permettre de retourner une valeur au sein de la fonction à l'aide de ```return()```
- [x] Accès aux paramètres à l'intérieur d'une fonction définie avec ```getVar()```
- [x] Fonction basique ```wait()```
- [x] Conditions ```if()``` ```else```
- [x] Commentaires ```//```
- [x] Fonction basique de boucle: ```while()```
- [ ] Type ```array``` (tableau) et fonctions basiques associées
- [ ] Type ```map``` (dictionnaire) et fonctions basiques associées
### Compilateur évolué
- [x] Représentation hierarchique et intéractive des composants sur l'interface de programmation
- [x] Séparation du code en plusieurs composants + suite algorithmique des composants
- [x] Possibilité de rendre un composant visible à travers une image ou un objet stylisable
- [x] Evenements associés à l'intéraction de l'utilisateur (lorsqu'on touche l'écran)
- [ ] Pouvoir modifier du contenu textuel et du style depuis le code
- [ ] Fonctions basiques associées au placement / déplacement d'un composant visible
- [ ] Possibilité de créer des variables globales qu'une liste de composant définie peut récupérer / mettre à jour
- [ ] Evenement associé à une mise à jour du composant, causée par la mise à jour du ```state``` du composant ou d'un ```state``` global dont le composant a accès
- [ ] Fonction permettant de stocker le score de l'utilisateur sur la base de donnée de Peps
## Informations techniques
Peps est codé en Javascript avec les frameworks React et React-Native.
Le compileur de Peps se trouve sur l'application.
Firebase est le service utilisé pour la base de données qui stocke les programmes ainsi que les données des utilisateurs.
