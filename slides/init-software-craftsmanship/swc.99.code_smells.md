
## Type de Code Smells

|                   |
|:------------------|
| Bloaters          |
| OO Abusers        |
| Change Preventers |
| Dispensables      |
| Couplers          |
| ...               |


## Les Encombrants

| Bloaters            |
|:--------------------|
| Long Method         |
| Large Class         |
| Primitive Obsession |
| Long Parameter List |
| Data Clumps         |
|                     |

Note: 

Font grossir le code dans des proportions diminuant la lisibilit&eacute; et la flexibilit&eacute;.  

**Action**: Diminuer le nombre d'&eacute;l&eacute;ments (Extract Method, Values to Object)


## Les Casseurs

| Object-Oriented Abusers         |
|:--------------------------------|
| Switch Statements               |
| Temporary Field                 |
| Refused Bequest                 |         
| Alt. Classes w/ dif. Interfaces |
|                                 |

Note:

Contraires aux valeurs de l'orient&eacute; objet
- encapsulation
- polymorphisme
- h&eacute;ritage

**Action**: Re-mod&eacute;liser notre domaine en tenant compte de cette r&eacute;alit&eacute;


## Les Bureaucrates

| Change Preventers                |
|:---------------------------------|
| Divergent Change                 |
| Shotgun Surgery                  |         
| Solution Sprawl                  |
| Parallel Inheritance Hierarchies |
|                                  |

Note: 

Responsabilit&eacute;s r&eacute;pandu &agrave; travers le code g&ecirc;nant la modification

**Action**: Mutualiser la logique au sein d'une methode/classe


## Les Superflus

| Dispensables           |
|:-----------------------|
| Lazy Class             |
| Data Class             |
| Duplicate Code         |
| Dead Code              |
| Speculative Generality |
|                        |

Note: 

Signe de code inutile
- Enrichir les &eacute;l&eacute;ments  
- ou supprimer le code (middle man)  

**Action**: Se d&eacute;barasser des éléments nuisibles
ex: Data classes doivent se responsabiliser pour justifier leur existence. 


## Les Pots de Colle 1/2

| Couplers                  |
|:--------------------------|
| Artificial Coupling       |
| Feature Envy              |
| Inappropriate Intimacy    |
| Incomplete Library Class  |
|                           |

Note: 

Classes difficiles &agrave; modifier individuellement du &agrave; des d&eacute;pendances non n&eacute;cessaires.


## Les Pots de Colle 2/2

| Couplers                  |
|:--------------------------|
| Indecent Exposure         |
| Hidden Dependencies       |
| Message Chains            |
| Middle Man                |
| Tramp Data                |
|                           |

Note:

> Hidden Dependencies : Couplage, Nuit &agrave; la testabilit&eacute; -> Injection de d&eacute;pendances ! 


# R&eacute;f&eacute;rences

- Catalogue
	- [Sourcemaking](https://sourcemaking.com/refactoring/smells)

- Article
    - [Code Smell](http://martinfowler.com/bliki/CodeSmell.html), Martin Fowler

- Livres
    - Refactoring, improving the design of existing code, Martin Fowler 
    - Clean Code, Robert C Martin

- Pluralsight
    [Refactoring Code](https://app.pluralsight.com/library/courses/refactoring-fundamentals/table-of-contents), Steve Smith