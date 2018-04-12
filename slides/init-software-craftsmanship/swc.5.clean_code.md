### Clean & Simple Code #

![Clean](/slides/init-software-craftsmanship/img/CleanCode.jpg)

Note: 

1. Uncle Bob a popularisé la pratique du Clean Code au travers de ces deux livres Clean Code et Clean Coder. 
1. Développeur américain né en 1952  
1. Parmis les créateurs du manifeste Agile
1. SmallTalk & Java
1. Kent Beck <-> Simple Design : essentiel des pratiques dev XP 


## Du code propre ?

- Du code structuré, rangé, cohérent & expressif <!-- .element: class="fragment" data-fragment-index="1" -->
- Du code qui facilite la compréhension et l'utilisation <!-- .element: class="fragment" data-fragment-index="1" -->

Note:

- Exemple de la paillasse du cuisinier

Ensemble de regles: 

- de programmation (objet)
- de nommage
- de documentation


### Pourquoi c'est important ?

- Développeur: 80% lecture / 20% écriture 
- La documentation est souvent incomplete, périmée, voir inexistente
- Code est partagé par les équipes
- Etre agile, c'est embrasser le changement

Note: 
- Je ne parle même pas du support et des testeurs
- le code est la documentation


## Ratio Signal/Bruit 

- Le cerveau humain peut traiter nombre limité de signaux 
- Trop d'informations se transforment en bruit
- Le bruit du code s'amplifie au fil du temps

Note:

Construction mental du code
1. Homme conserve seulement 7 éléments (+-2) dans sa mémoire a un moment donné
1. Un code avec une complexité cyclomatique trop importante renvoit trop de possibilités
1. Une fois sur cette voie on ne peut que rajouter dela complexité (un if / case de plus) 


## Clean Code 

> Clean code always looks like it was written by someone who cares. <br/> Michael Feathers

Note:

1. Extrait du chapitre écrit par Michael Feathers dans le livre Clean Code


## Nommage

> Names and attributes must be accommodated to the essence of things, and not the essence to the names, since things come first and names afterwards.
 Galileo Galilei, Discoveries and Opinions of Galileo 


### Quel nom ?

![Trousse](/slides/init-software-craftsmanship/img/trousse_africaine.jpg) <!-- .element style="width: 50%;" -->

- X  <!-- .element: class="fragment" data-fragment-index="1" -->
- Conteneur  <!-- .element: class="fragment" data-fragment-index="2" -->
- StyloCrayonsRegles&GommeManager  <!-- .element: class="fragment" data-fragment-index="3" -->
- Trousse   <!-- .element: class="fragment" data-fragment-index="4" style="font-weight:bold;color:green" -->

Note:
- Difficile de nommer sans comprendre
- Plusieurs noms possibles


## Et maintenant ?

![Trousse](/slides/init-software-craftsmanship/img/trousse_cuir.png)

Note: 

Même fonction mais fabrication et format différents


## Ou encore ?

![Trousse](/slides/init-software-craftsmanship/img/trousse_de_secours.png)

Note:

- Meme famille mais contenu tre s différent
- Le contexte est important pour trouver le nom adéquat
- **Il n'est jamais trop tard pour renommer son enfant!**


## Nommer une classe

1. Un nom
2. Aussi spécifique que possible 
3. Responsabilité claire
4. Pas de suffixes superflus

Note:

Pb de nommage => smell de responsabilité peu claire ou de mauvaise utilisation?


## Ca suffixe !

* Object
* Manager
* Info
* Helper
* Executor
* Processor
* Utils
* Abstract
* ...

Note:

Les suffixe trop génériques ou superflus constituent du bruit.


## Nommer une méthode

- Le nom doit suffire !
- Pas de nom générique (Do, Process, Execute) 

=> ex: DocumentConverter.HtmlFromText(textFile);


## Appel a un ami !

Dans le doute, demandez a un collegue 


# Conditions

> Je n'ai fait celle-ci plus longue que parce que je n'ai pas eu le loisir de la faire plus courte. Blaise Pascal

Note:
- Expressivité
- Concision


## Conditions non-non-positives 

```javascript
function doSomething(entity) {

    if (!entity.isNotSelected && client!=null) {
        ...
    }

    if (!entity instanceof Person) {
        ...
    }
    else {
        ...
    }   
}
```

Note:

* Préférez les formulations positives
* Imprécision des ensembles flous (tous sauf a)


## Magic Strings & Numbers

```Java
public void Initialize(Person person, int level, Date date) 
{
    if (level != 6)
        person.Title = "Employee";
    else
        person.Title = "Chief Dictator"; 

    if (person.Title == "Employee") {
        ...
    }
}
```

Note:

* Fragilité au changement
* Aucune protection a la compilation


## Réduire la complexité 

```python
if date.before(SUMMER_START) and date.after(SUMMER_END):
    charge = quantity * winterRate + winterServiceCharge
    if WINTER_SALE_START < date < WINTER_SALES_END:
        charge = charge * 0.7    
else:
    charge = quantity * summerRate
```

Note:

* Favoriser une méthode
* Extraire méthode


## Comportement vs Enumération

```csharp
public void CalculateFinalPrice()
{
    switch (item.Country)
    {
        case "France": item.Price = item.BasePrice*FrenchTaxes; 
                    break;
        case "USA": item.Price = item.BasePrice*USATaxes; 
                    break;
                    ...
        default : item.Price = item.BasePrice;
    }
}
```

Note:

* Polymorphisme pour injecter du comportement 
* plutôt que l'énumération de tous les comportements a un endroit


## Dictionaires

Déplacer une liste de conditions dans une structure de données

```csharp

Dictionary<string,float> Taxes;

public void CalculateFinalPrice()
{
     item.Price = item.BasePrice*Taxes[item.Country]; 
}
```


## Concision

Profiter des avantages des
* Ternaires (x ? y : z)  
* Lambdas : Linq / Lambdaj / jLinq / Pynq


# Functions

> Functions should do one thing. They should do it well. They should do it only.
 <br/>Robert C. Martin


## Pourquoi créer une fonction?

* Eviter la duplication
* Réduire l'indentation du code
* Clarifier l'intention d'un code 
* Séparer différentes opérations

Note:

* dup: Mutualiser pour réutiliser & éviter les disparités
* ind: Réduire la complexité cyclomatique
* int: Introduire des concepts de plus haut niveau, réduire le nombre d'éléments locaux.
* sep: Diviser pour mieux regner - éviter les effets de vase communicants


## Métriques

Uncle Bob, dit qu'une fonction ne devrait :
- rarement faire plus de **20 lignes**
- quasi jamais plus de **100 lignes**,
- pas avoir plus de **3 parametres**. 


# Exceptions

3 types d'exceptions:
* Fatale
* Gérable
* Négligeable

Note:
- fat: ressources obligatoires dysfonctionnant. Incapacité de l'app a se rattraper gracieusement.
- ger: une ou plusieurs solutions existent : rejeu, operation alternative
- neg: pas d'incidence sur l'application. (code inélégant dans une api de plus bas niveau)


## Je ne veux rien trouver sous le tapis!

![Mamie](/slides/init-software-craftsmanship/img/Fotolia_75067118_M.jpg) <!-- .element style="width: 60%;" -->

Note:
* Bubble exceptions to competent level
* Don't handle exception if you can't revert to stable state
* Last resort, handle at topmost level and shutdown app or abort web call 


# Classes

> Classes should do one thing. They should do it well. They should do it only.
 <br/>Robert C. Martin


## New Class ?

* Nouveau concept
* Cohésion faible
* Réutilisation
* Réduire la complexité

Note:
**réduire complexité**: 
- diminuer le nombre d'éléments (cohésion) 
- encapsuler des variables dans une structure cohérente


## Cohésion & Couplage 

* Cohésion *forte*
    - Regroupement fonctionnel
    - Meme niveau de détail

* Couplage *faible*
    - Minimiser dépendances 


## Soyez protecteur 

Exposez le minimum nécessaire !


## Primitive Obsession

```cs
// N'utilisez pas les primitives ...
public void SaveUser(int id, string nom, string prénom, 
    string adresse, string téléphone);

// Quand un objet peut aisément les représenter !
public void SaveUser(User user);
``` 


## Principe de proximité

Conserver les éléments liés a proximité


## Table des matieres

Le code collapsed se lit comme un résumé


# Commentaires

- redondance 
- évidence 
- péremption 

=> inutile ou presque


## To comment or not to comment

* Résumé
* Code désactivé
* Avertissement
* Clarification

Note: 
* Résumé
    - Duplication  
    - Approximation
    - Vision erronée/périmée
* Code désactivé
    - Zombie code => Delete
* Avertissement : Todo/Warning
    - Dette technique
* Clarification
    - Signe de code trop long ?


## Questions a se poser

- Arrivez-vous a exprimer l'intention dans le code?
- Est-ce que le commentaire est un déodorant ?
- Est-ce que sa place est dans le code source?


# Simple Design

> Make it work, make it right, make it fast.
― Kent Beck


## 4 rules of Simple Design

* Valide les tests
* Exprime clairement son intention 
* Contient aucune duplication
* Minimise le nombre d'éléments

Note:

- Ordre d'importance descendant
**ATTENTION**: Minimiser tant qu'on n'enfreint pas la seconde regle ! 


## Principe de surprise minimum

Fais ce que tu dis, et dis (clairement) ce que tu fais!

Void GetItem();
Item GetItem(int id);

Note:

Une méthode GetItem() on s'attend qu'elle requ&ecirc;te un dataprovider pour récupérer l'élément et éventuellement le remettre en formeet le renvoie en sortie

=> notions de Standard et de Cohérence au sein de l'application

Faites votre code comme une API, pensez a l'usage d'un autre développeur ne connaissant pas la tuyauterie interne.
Le TDD peut aider!


# SOLID Principles

|     |         |                                 |
|:---:|:-------:|---------------------------------|
| *S* | **SRP** | Single responsibility principle |
| *O* | **OCP** | Open/closed principle           |
| *L* | **LSP** | Liskov substitution principle   |
| *I* | **ISP** | Interface segregation principle |
| *D* | **DIP** | Dependency inversion principle  |
|     |         |                                 |

Note:

- SRP: a class should have only a single responsibility (i.e. only one potential change in the software's specification should be able to affect the specification of the class)
- OCP: “software entities … should be open for extension, but closed for modification.”
- LSP: “objects in a program should be replaceable with instances of their subtypes without altering the correctness of that program.” See also design by contract.
- ISP: “many client-specific interfaces are better than one general-purpose interface.”
- DIP: one should “Depend upon Abstractions. Do not depend upon concretions.”


## SRP : Single Responsability Principle

- Une classe ne devrait avoir qu'une seule responsabilité et donc une seule raison de changer 

Note:


## OCP : Open-Closed Principle

> software entities (classes, modules, functions, etc.) should be open for extension, but closed for modification. Bertrand Meyer


# Conclusion

> Simplicity is a great virtue but it requires hard work to achieve it and education to appreciate it. And to make matters worse: complexity sells better.
― Edsger W. Dijkstra


## La vérité est dans le code

* Le code est majoritairement lu
* Le code est la seule documentation a jour
* Le bruit est l'origine de mauvaises implémentations & bugs


## Un investissement durable 

Ces principes fonctionnent quelque soit
* le langage (objet)
* l'architecture
* les librairies


## Des pratiques partagées !

* Documenter des standards
* Pair Programming / Mob Programming 
* Code Reviews 
* Outils de suivi de la qualité du code

Note:

Suivre les bonnes pratiques seul ne sert à rien. 
Pire c'est dangereux pour la santé mentale !


## Références 

- Clean Code, Robert C Martin @unclebob
- Extreme Programming Explained, Kent Beck