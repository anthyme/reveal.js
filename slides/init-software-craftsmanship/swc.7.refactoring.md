
![Trousse](/slides/init-software-craftsmanship/img/keep_calm_and_refactor.png) <!-- .element style="width: 80%;" -->


## Définition

> Refactoring is the process of changing a software system in such a way that it does not alter the external behavior of the code yet improves its internal structure. <br/>Martin Fowler


## Implications

- Le refactoring ne comprend aucune modification du systeme (global)
- Le refactoring n'est pas une réecriture 
- Un refactoring améliore le code dans un but précis.

Note:

- L'art d'améliorer sans risque la structure de code existant.
- Touche pas aux fonctionnalités existantes => éviter les régressions
- Part du code existant => La vérité est dans le code ! 
- Le refactoring a vocation a préparé le code pour accueillir de nouvelles fonctionnalités plus facilement, ou bien, atteindre un niveau de qualité manquant.  


## Enjeu

Le refactoring nous permet de mettre le code dans un état satisfaisant pour affronter sereinement les demandes d'évolution

Note: 

- Car la perfection n'est pas de ce monde, 	
- et les contraintes externes peuvent avoir raison des meilleures intentions.
- Car le futur ne peut etre anticiper  


## Quand doit-on refactorer ?

Le poids du code existant nous empeche d'avancer dans de bonnes conditions! 


### Code est difficile a modifier

- Personne ne le comprend
- Les impacts d’une modification ricochent a travers l’application 

Note:

- Lorsque vous vous dites : "Je ferai mieux de créer un nouveau module a côté du code existant." 
- Améliorer un code qui n'a pas besoin de changer => Perte de temps 


### Qualité est difficile a garantir

- Code difficilement testable
- Détection de Code Smells


## Minimiser

> Premature optimization is the root of all evil. <br/>Donald Knuth

- La solution la plus simple répondant au besoin connu aujourd’hui
- Cultivez la capacité de réagir au changement, sans l'anticiper

Note:

Rendez vous service: minimiser la comeplexité! Vos refactorings n'en seront que plus faciles. 

1. Une solution simple... pouvant etre amélioré (refactorer) par la suite !
1. Méfiez vous de early optimisation


![Red Green REFACTOR](/slides/init-software-craftsmanship/img/refactoring/tdd.gif)

Note:
- Refactoring = étape récurrente dans le TDD !
- Le code marche enfin, on a une vision clair du probleme, on refactor vers une solution plus simple & pereine


## Code Legacy

Quelques définitions:
1. Code sans tests unitaires (Michael Feathers) 
1. Code des qu'il est écrit.
1. Du code en production
1. Code dont les créateurs ne font pas parti de l'équipe.


## Refactoring du Code Legacy

1. Identifier les points de changement
1. Identifier les points de test associés
1. Casser les dépendances
1. Mise en place du harnais de tests
1. On applique des transformations et le refactoring
1. On valide nos modifications


## 1) Identifier les points de changement

- Code Smell
- Evolution du design


## Faire évoluer son design 

- Choix technique 
- Changement imprévu 
- Nouvelle stratégie

Note: 

- Nouvel ORM, ajout du Cache, …
- Modification d’une réglementation
- Expansion a l'International -> multi-langue, reglementations locales


## 2) Identifier les points a tester

- En tests unitaires, fonctionnels ?
- Quelle couverture ?


## Tests = Feedback

Qu’est ce que je veux savoir pour garantir la solidité de mon code ?


## 3) Casser Les Dépendances

- Identifier les “Seams”, frontieres entre les éléments du code

=> Crucial pour rendre les systemes testables!


## Créer des doubles

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

Refactoring des tests si nécessaire.

> Test Code is just as important as Production Code 


## Pas d'ajout durant le refactoring !

Pas de nouvelles fonctionnalités durant un refactoring ! 

Note:

- Source de régression
- Pas couvert par les tests existant
- Trop de modifications simultanées obscurcissent la source d'éventuelles régressions


## Rappel: Baby Steps


## Rappel : Use Tests


## Références

- [refactoring.com/catalog](http://refactoring.com/catalog), Martin Fowler
- [sourcemaking.com/refactoring/](https://sourcemaking.com/refactoring/)
- Refactoring, improving the design of existing code, Martin Fowler 
- Working with Legacy Code, Michael Feathers
- [app.pluralsight.com/library/courses/refactoring-fundamentals](https://app.pluralsight.com/library/courses/refactoring-fundamentals/table-of-contents), Steve Smith
