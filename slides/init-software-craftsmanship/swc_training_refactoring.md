
<!-- .slide: data-background-image="/slides/init-software-craftsmanship/img/keep_calm_and_refactor.png" data-background-size="contain" data-background-repeat="no-repeat" -->


## D&eacute;finition

> Refactoring is the process of changing a software system in such a way that it does not alter the external behavior of the code yet improves its internal structure. 
Martin Fowler


## Implications

- Le refactoring ne comprend aucune modification du syst&egrave;me (global)
- Le refactoring n'est pas une r&eacute;ecriture 
- Un refactoring am&eacute;liore le code dans un but pr&eacute;cis.

Note:

- L'art d'am&eacute;liorer sans risque la structure de code existant.
- Touche pas aux fonctionnalit&eacute;s existantes => &eacute;viter les r&eacute;gressions
- Part du code existant => La v&eacute;rit&eacute; est dans le code ! 
- Le refactoring a vocation a pr&eacute;par&eacute; le code pour accueillir de nouvelles fonctionnalit&eacute;s plus facilement, ou bien, atteindre un niveau de qualit&eacute; manquant.  


## Enjeu

Le refactoring nous permet de mettre le code dans un &eacute;tat satisfaisant pour affronter sereinement les demandes d'&eacute;volution

Note: 

- Car la perfection n'est pas de ce monde, 	
- et les contraintes externes peuvent avoir raison des meilleures intentions.
- Car le futur ne peut &ecirc;tre anticiper  


## Quand doit-on refactorer ?

Le poids du code existant nous emp&ecirc;che d'avancer dans de bonnes conditions! 


### Code est difficile &agrave; modifier

- Personne ne le comprend
- Les impacts d’une modification ricochent &agrave; travers l’application 

Note:

- Lorsque vous vous dites : "Je ferai mieux de cr&eacute;er un nouveau module &agrave; côt&eacute; du code existant." 
- Am&eacute;liorer un code qui n'a pas besoin de changer => Perte de temps 


### Qualit&eacute; est difficile &agrave; garantir
- Code difficilement testable
- D&eacute;tection de Code Smells


## Minimiser

> Premature optimization is the root of all evil.
Donald Knuth

- La solution la plus simple r&eacute;pondant au besoin connu aujourd’hui
- Cultivez la capacit&eacute; de r&eacute;agir au changement, sans l'anticiper

Note:

Rendez vous service: minimiser la comeplexit&eacute;! Vos refactorings n'en seront que plus faciles. 

1. Une solution simple... pouvant &ecirc;tre am&eacute;liorer (refactorer) par la suite !
1. M&eacute;fiez vous de early optimisation


## TDD

![Red Green REFACTOR](/slides/init-software-craftsmanship/img/Red_Green_Refactor_text.JPG)

Note:

- Refactoring = &eacute;tape r&eacute;currente dans le TDD !
- Le code marche enfin, on a une vision clair du probl&egrave;me, on refactor vers une solution plus simple & pereine


## Code Legacy

Quelques d&eacute;finitions:
1. Code sans tests unitaires (Michael Feathers) 
1. Code d&egrave;s qu'il est &eacute;crit.
1. Du code en production
1. Code dont les cr&eacute;ateurs ne font pas parti de l'&eacute;quipe.


## Refactoring du Code Legacy

1. Identifier les points de changement
1. Identifier les points de test associ&eacute;s
1. Casser les d&eacute;pendances
1. Mise en place du harnais de tests
1. On applique des transformations et le refactoring
1. On valide nos modifications


## 1) Identifier les points de changement

- Code Smell
- Evolution du design


## Faire &eacute;voluer son design 

- Choix technique 
- Changement impr&eacute;vu 
- Nouvelle strat&eacute;gie

Note: 

- Nouvel ORM, ajout du Cache, …
- Modification d’une r&eacute;glementation
- Expansion &agrave; l'International -> multi-langue, r&egrave;glementations locales


## 2) Identifier les points &agrave; tester

- En tests unitaires, fonctionnels ?
- Quelle couverture ?


## Tests = Feedback

Qu’est ce que je veux savoir pour garantir la solidit&eacute; de mon code ?


## 3) Casser Les D&eacute;pendances

- Identifier les “Seams”, fronti&egrave;res entre les &eacute;l&eacute;ments du code

=> Crucial pour rendre les syst&egrave;mes testables!


## Cr&eacute;er des doubles

Sale -> Display 		

Sale -> Interface <- Display
				  <- Fake Display


## 4) Ecrire les tests

Retour au TDD : 

 RED - GREEN - REFACTOR


## 5) Transformations 

[Transformations](http://refactoring.com/catalog/): 
- Extract Method
- Extract Class
- Extract Interface
- Hide Method
- Remove Middle Man
- Replace Conditional with Polymorphism
- Replace Constructor with Factory Method
- Change Value to Reference


## N'oubliez pas les tests !

Refactoring des tests si n&eacute;cessaire.

> Test Code is just as important as Production Code 


## Pas d'ajout durant le refactoring !

Pas de nouvelles fonctionnalit&eacute;s durant un refactoring ! 

Note:

- Source de r&eacute;gression
- Pas couvert par les tests existant
- Trop de modifications simultan&eacute;es obscurcissent la source d'&eacute;ventuelles r&eacute;gressions


## Rappel: Baby Steps


## Rappel : Use Tests


## R&eacute;f&eacute;rences

 Refactorings : 

- Catalogue
	- [Martin Fowler's Catalog](http://refactoring.com/catalog)
	- [Sourcemaking](https://sourcemaking.com/refactoring/)

- Livres
    - Refactoring, improving the design of existing code, Martin Fowler 
    - Working with Legacy Code, Michael Feathers

- Pluralsight
    [Refactoring Code](https://app.pluralsight.com/library/courses/refactoring-fundamentals/table-of-contents), Steve Smith
