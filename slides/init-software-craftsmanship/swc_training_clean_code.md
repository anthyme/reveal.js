# Clean & Simple Code #

![Clean](/slides/init-software-craftsmanship/img/CleanCode.jpg)

Note: 

1. Uncle Bob a popularis&eacute; la pratique du Clean Code au travers de ces deux livres Clean Code et Clean Coder. 
1. D&eacute;veloppeur am&eacute;ricain n&eacute; en 1952  
1. Parmis les cr&eacute;ateurs du manifeste Agile
1. SmallTalk & Java
1. Kent Beck <-> Simple Design : essentiel des pratiques dev XP 


## A venir...

1. Clean Code
1. Simple Design
1. SOLID Principles
1. Yahtzee Kata


## Du code propre ?

- Du code structur&eacute;, rang&eacute;, coh&eacute;rent & expressif
- Du code qui facilite la compr&eacute;hension et l'utilisation

Note:

- Exemple de la paillasse du cuisinier

Ensemble de r&egrave;gles: 

- de programmation (objet)
- de nommage
- de documentation


## Pourquoi c'est important ?

- D&eacute;veloppeur: 80% lecture / 20% &eacute;criture 
- La documentation est souvent incompl&egrave;te, p&eacute;rim&eacute;e, voir inexistente
- Code est partag&eacute; par les &eacute;quipes
- En agile, il faut être pr&eacute;parer au changement

Note: 

- Je ne parle même pas du support et des testeurs 


## Ratio Signal/Bruit 

- Cerveau humain peut traiter nombre limit&eacute; de signaux 
- Trop d'informations se transforment en bruit
- Le bruit du code s'amplifie au fil du temps

Note:

1. Homme conserve seulement 7 &eacute;l&eacute;ments (+-2) dans sa m&eacute;moire &agrave; un moment donn&eacute;
1. Un code avec une complexit&eacute; cyclomatique trop importante renvoit trop de possibilit&eacute;s
1. Une fois sur cette voie on ne peut que rajouter dela complexit&eacute; (un if / case de plus) 


## Clean Code 

> Clean code always looks like it was written by someone who cares. Michael Feathers @mfeathers

Note:

1. Extrait du chapitre &eacute;crit par Michael Feathers dans le livre Clean Code


# Nommage #

> Names and attributes must be accommodated to the essence of things, and not the essence to the names, since things come first and names afterwards.
 Galileo Galilei, Discoveries and Opinions of Galileo 


## Quel nom ?

![Trousse](/slides/init-software-craftsmanship/img/trousse_africaine.jpg)

- X  <!-- .element: class="fragment" data-fragment-index="1" -->
- Conteneur  <!-- .element: class="fragment" data-fragment-index="2" -->
- StyloCrayonsRegles&GommeManager  <!-- .element: class="fragment" data-fragment-index="3" -->
- **Trousse**   <!-- .element: class="fragment" data-fragment-index="4" -->

Note:

- Difficile de nommer sans comprendre
- Plusieurs noms possibles


## Et maintenant ?

![Trousse](/slides/init-software-craftsmanship/img/trousse_cuir.png)

Note: 

Même fonction mais fabrication et format diff&eacute;rents


## Ou encore ?

![Trousse](/slides/init-software-craftsmanship/img/trousse_de_secours.png)

Note:

- Meme famille mais contenu tr&egrave; s diff&eacute;rent
- Le contexte est important pour trouver le nom ad&eacute;quat
- **Il n'est jamais trop tard pour renommer son enfant!**


## Nommer une classe

1. Un nom
2. Aussi sp&eacute;cifique que possible 
3. Responsabilit&eacute; claire
4. Pas de suffixes superflus

Note:

Pb de nommage => smell de responsabilit&eacute; peu claire ou de mauvaise utilisation?


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

Les suffixe trop g&eacute;n&eacute;riques ou superflus constituent du bruit.


## Nommer une m&eacute;thode

- Le nom doit suffire !
- Pas de nom g&eacute;n&eacute;rique (Do, Process, Execute) 

=> ex: DocumentConverter.HtmlFromText(textFile);


## Appel &agrave; un ami !

Dans le doute, demandez &agrave; un coll&egrave;gue 


# Conditions

> Je n'ai fait celle-ci plus longue que parce que je n'ai pas eu le loisir de la faire plus courte. Blaise Pascal

Note:

- Expressivit&eacute;
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

* Pr&eacute;f&eacute;rez les formulations positives
* Impr&eacute;cision des ensembles flous (tous sauf a)


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

* Fragilit&eacute; au changement
* Aucune protection &agrave; la compilation


## R&eacute;duire la complexit&eacute; 

```python
if date.before(SUMMER_START) and date.after(SUMMER_END):
    charge = quantity * winterRate + winterServiceCharge
    if WINTER_SALE_START < date < WINTER_SALES_END:
        charge = charge * 0.7    
else:
    charge = quantity * summerRate
```

Note:

* Favoriser une m&eacute;thode
* Extraire m&eacute;thode


## Comportement vs Enum&eacute;ration

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
* plutôt que l'&eacute;num&eacute;ration de tous les comportements &agrave; un endroit


## Dictionaires

* D&eacute;placer une liste de conditions dans une structure de donn&eacute;es

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
 Robert C. Martin @unclebob


## Pourquoi cr&eacute;er une fonction?

* Eviter la duplication
* R&eacute;duire l'indentation du code
* Clarifier l'intention d'un code 
* S&eacute;parer diff&eacute;rentes op&eacute;rations

Note:

* dup: Mutualiser pour r&eacute;utiliser & &eacute;viter les disparit&eacute;s
* ind: R&eacute;duire la complexit&eacute; cyclomatique
* int: Introduire des concepts de plus haut niveau, r&eacute;duire le nombre d'&eacute;l&eacute;ments locaux.
* sep: Diviser pour mieux r&egrave;gner - &eacute;viter les effets de vase communicants


## M&eacute;triques

Uncle Bob, dit qu'une fonction ne devrait :
- rarement faire plus de **20 lignes**
- quasi jamais plus de **100 lignes**,
- pas avoir plus de **3 param&egrave;tres**. 


# Exceptions

3 types d'exceptions:
* Fatale
* G&eacute;rable
* N&eacute;gligeable

Note:

- fat: ressources obligatoires dysfonctionnant. Incapacit&eacute; de l'app &agrave; se rattraper gracieusement.
- ger: une ou plusieurs solutions existent : rejeu, operation alternative
- neg: pas d'incidence sur l'application. (code in&eacute;l&eacute;gant dans une api de plus bas niveau)


## Je ne veux rien trouver sous le tapis!

![Mamie](/slides/init-software-craftsmanship/img/Fotolia_75067118_M.jpg)

Note:

* Bubble exceptions to competent level
* Don't handle exception if you can't revert to stable state
* Last resort, handle at topmost level and shutdown app or abort web call 


# Classes

> Classes should do one thing. They should do it well. They should do it only.
 Robert C. Martin @unclebob


## <New Class>

* Nouveau concept
* Coh&eacute;sion faible
* R&eacute;utilisation
* R&eacute;duire la complexit&eacute;

Note:

**r&eacute;duire complexit&eacute;**: 
- diminuer le nombre d'&eacute;l&eacute;ments (coh&eacute;sion) 
- encapsuler des variables dans une structure coh&eacute;rente


## Coh&eacute;sion & Couplage 

* Coh&eacute;sion *forte*
    - Regroupement fonctionnel
    - Même niveau de d&eacute;tail

* Couplage *faible*
    - Minimiser d&eacute;pendances 


## Soyez protecteur 

Exposez le minimum n&eacute;cessaire !


## Primitive Obsession

```cs
// N'utilisez pas les primitives ...
public void SaveUser(int id, string nom, string pr&eacute;nom, string adresse, string t&eacute;l&eacute;phone);

// Quand un objet peut ais&eacute;ment les repr&eacute;senter !
public void SaveUser(User user);
``` 


## Principe de proximit&eacute;

Conserver les &eacute;l&eacute;ments li&eacute;s &agrave; proximit&eacute;


## Table des mati&egrave; res

Le code collapsed se lit comme un r&eacute;sum&eacute;


# Commentaires

- redondance 
- &eacute;vidence 
- p&eacute;remption 

=> inutile


## To comment or not to comment

* R&eacute;sum&eacute;
* Code d&eacute;sactiv&eacute;
* Avertissement
* Clarification

Note: 

* R&eacute;sum&eacute;
    - Duplication  
    - Approximation
    - Vision erron&eacute;e/p&eacute;rim&eacute;e
* Code d&eacute;sactiv&eacute;
    - Zombie code => Delete
* Avertissement : Todo/Warning
    - Dette technique
* Clarification
    - Signe de code trop long ?


## Questions &agrave; se poser

- Arrivez-vous &agrave; exprimer l'intention dans le code?
- Est-ce que le commentaire est un d&eacute;odorant ?
- Est-ce que sa place est dans le code source?


# Simple Design

> Make it work, make it right, make it fast.
― Kent Beck


## 4 rules of Simple Design

* Valide les tests
* Exprime clairement son intention 
* Contient aucune duplication
* Minimise le nombre d'&eacute;l&eacute;ments

Note:

- Ordre d'importance descendant
**ATTENTION**: Minimiser tant qu'on n'enfreint pas la seconde r&egrave;gle ! 


## Principe de surprise minimum

Fais ce que tu dis, et dis (clairement) ce que tu fais!

Void GetItem();
Item GetItem(int id);

Note:

Une m&eacute;thode GetItem() on s'attend qu'elle requ&ecirc;te un dataprovider pour r&eacute;cup&eacute;rer l'&eacute;l&eacute;ment et &eacute;ventuellement le remettre en formeet le renvoie en sortie

=> notions de Standard et de Coh&eacute;rence au sein de l'application

Faites votre code comme une API, pensez &agrave; l'usage d'un autre d&eacute;veloppeur ne connaissant pas la tuyauterie interne.
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


## La v&eacute;rit&eacute; est dans le code

* Le code est majoritairement lu
* Le code est la seule documentation &agrave; jour
* Le bruit est l'origine de mauvaises impl&eacute;mentations & bugs


## Un investissement durable 

Ces principes fonctionnent quelque soit
* le langage (objet)
* l'architecture
* les librairies


## Des pratiques partag&eacute;es !

* Documenter des standards
* Pair Programming / Mob Programming 
* Code Reviews 
* Outils de suivi de la qualit&eacute; du code

Note:

Suivre les bonnes pratiques seul ne sert à rien. 
Pire c'est dangereux pour la santé mentale !


## R&eacute;f&eacute;rences 

- Clean Code, Robert C Martin
- Extreme Programming Explained, Kent Beck