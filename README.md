# Peps
Peps est un projet en développement depuis le 16 avril 2020. L'objectif est de permettre à n'importe qui de développer facilement des jeux casual sur smartphone.
Le code est écrit depuis un site, et le développeur peut essayer simultanément sa création sur son téléphone, depuis l'application Peps.
Une fois qu'une première version du jeu est terminée, il est possible de la publier sur la plateforme Peps afin que n'importe qui puisse l'essayer et la commenter. Les joueurs n'ont pas besoin de les installer, les jeux se jouent en ligne.
## Informations techniques
Peps est codé en Javascript avec les frameworks React et React-Native.
Le compileur de Peps se trouve sur l'application.
Firebase est le service utilisé pour la base de données qui stocke les programmes ainsi que les données des utilisateurs.
## Todolist
### Support
- [x] Initialisation + Interfaces de base + liaison de l'application au site (frontend & database)
- [ ] Interface du site
- [ ] Interface de l'application
- [ ] Système d'authentification avec projets et scores dédiés à chaque compte
### Langage de programmation: bases algorithmiques
- [x] Lecture algorithmique et envoi du futur code Peps sur la base de données
- [x] Affichage de la console lorsque le code commence par le mot-clé CONSOLE
- [x] Initialisation du compileur et des types primitifs et complexes
- [x] Fonction basique ```print()```
- [x] Type complexe: ```equality```
- [x] Type complexe: ```operation```
- [x] Fonctions basiques ```setVar()``` et ```getVar()```
- [x] Pouvoir définir une fonction exécutant du code (type complexe: ```function```)
- [x] Permettre de retourner une valeur au sein de la fonction à l'aide de ```return```
- [x] Accès aux paramètres à l'intérieur d'une fonction définie avec ```getVar()```
- [x] Fonction basique ```wait()```
- [x] Conditions ```if()``` ```else```
- [ ] Commentaires ```//```
- [ ] Fonction basique de boucle: ```for()```
- [ ] Type ```array``` (tableau) et fonctions basiques associées
- [ ] Type ```map``` (dictionnaire) et fonctions basiques associées
### Compilateur évolué
- [ ] Séparation du code en plusieurs composants + suite algorithmique des composants
- [ ] Représentation hierarchique et intéractive des composants sur l'interface de programmation
- [ ] Interface de la side bar
- [ ] Possibilité de rendre un composant visible à travers une image ou un objet stylisable en CSS
- [ ] Fonctions basiques associées au placement / déplacement d'un composant visible
- [ ] Evenements associés au cycle de vie d'un composant (apparition / disparition)
- [ ] Evenements associés à l'intéraction de l'utilisateur (lorsqu'on touche l'écran, etc)
- [ ] Mise en place d'un ```state``` (état) associé à chaque composant
- [ ] Possibilité de créer des ```state``` globaux qu'une liste de composant définie peut récupérer / mettre à jour
- [ ] Evenement associé à une mise à jour du composant, causée par la mise à jour du ```state``` du composant ou d'un ```state``` global dont le composant a accès
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
## Types complexes
Les types complexes sont les types qui retournent une valeur dont le type est simple.
### function
#### Description
Fonction qui exécute du code et retourne une valeur.
#### Exemples
##### Définition d'une fonction
```
function myFunctionName(myParameter):
  myCode(getVar("myParameter")) //on considère le paramètre myParameter comme une variable interne à la fonction.
  return "my value"
  
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
## Exemples de code
```
setVar("time", 17)

if (getVar("time") <= 12):
	sayGoodMorning("Patrick")
else:
	if (getVar("time") <= 18):
		sayGoodAfternoon("Jean")
	else:
		sayGoodEvening("Antonio")

function sayGoodMorning(name):
	print("Good morning", getVar("name"))

function sayGoodAfternoon(name):
	print("Good afternoon", getVar("name"))

function sayGoodEvening(name):
	print("Good evening", getVar("name"))
```
