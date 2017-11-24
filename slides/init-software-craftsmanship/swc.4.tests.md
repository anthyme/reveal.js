### La boite a outil du Craftsman

![Toolbox](/slides/init-software-craftsmanship/img/Fotolia_93525027_S.jpg) <!-- .element style="width: 70%;" -->


## Tests 

> Optimism is an occupational hazard of programming: feedback is the treament.
 Kent Beck


### Cout d'un bug au fil du temps

![Cout des bugs](/slides/init-software-craftsmanship/img/cost_of_bugs_over_time.jpg)

Note: 
Le cout d'un bug est d'autant plus grand qu'il est découvert tardivement
- http://blog.celerity.com/the-true-cost-of-a-software-bug 
- https://www.isixsigma.com/industries/software-it/defect-prevention-reducing-costs-and-enhancing-quality/
- http://xbsoftware.com/blog/cost-bugs-software-testing/
- http://superwebdeveloper.com/2009/11/25/the-incredible-rate-of-diminishing-returns-of-fixing-software-bugs/


### Typologie

1. Tests unitaires <!-- .element: class="fragment" data-fragment-index="1" --> 
2. Tests d'intégration <!-- .element: class="fragment" data-fragment-index="2" -->
3. Tests fonctionnels <!-- .element: class="fragment" data-fragment-index="3" -->
4. Tests de non-régression <!-- .element: class="fragment" data-fragment-index="4" -->
5. Tests d'acceptance <!-- .element: class="fragment" data-fragment-index="5" -->
6. Tests de performance <!-- .element: class="fragment" data-fragment-index="6" -->

Note: 
- unitaires: élément fonctionne correctement seul
- intégration: éléments fonctionnent correctement ensembles
- fonctionnels: éléments répondent aux spécifications établies préalablement
- non-regression: systame valide selon les jeux de tests pré-établis 
- acceptance: systame répond aux attentes des utilisateurs finaux
- performance: élément, ou systame entier, répond aux contraintes de performances définies  


### Propriétés d'un test unitaire

Séquence de code _**exécutable**_ et **automatisable** mesurant de maniere **reproductible** le résultat d'un code **atomique** et **isolé**


### Bénéfices attendus

- Détection rapide d'erreurs
- Maintenance sécurisée
- Documentation technique & fonctionnelle


### Nommer son test

```csharp
public class WhenUserEditsEntry
{
	[Fact]
	public void ValidationShouldSucceedWhenTitleIsNotNullOrWhiteSpace()
	{
		...
	}
}
``` 
<!-- .element: class="fragment" data-fragment-index="1"--> 

Note: 
- Classe de test => élément ou comportement à tester  
- Méthode => Comportement attendu
- Ne pas utiliser le mot *TEST* <!-- .element: class="fragment highlight-red" data-fragment-index="1"--> 


### Organiser ses tests 

|  |             |           |
|--|-------------|-----------|
|1.|   Arrange   |   Given   |
|2.|   Act       |   When    |
|3.|   Assert    |   Then    |


### Dummy, Stub, Fakes & Mock

- Dummy: Objet par défaut. 	<!-- .element: class="fragment highlight-current-blue" data-fragment-index="1" -->
- Fake: Implémentation limitée 	<!-- .element: class="fragment highlight-current-blue" data-fragment-index="2"--> 
- Stub: Réponses prédédfinies a l'appel de ses méthodes 	<!-- .element: class="fragment highlight-current-blue" data-fragment-index="3"--> 
- Mock: Trace le comportement  	<!-- .element: class="fragment highlight-current-blue" data-fragment-index="4"--> 

Note: 
- Fake: Version appauvrie d'un objet permettant d'exécuter le test (sans framework)
- Stub: Renvoyer la même valeur à chaque appel pour éliminer un aspect aléatoire, ou un acces base de données
- Mock: Détecter un événement ou un changement d'état au sein d'un objet 
Il y a confusion sur les objets doublures de test, on les appelle tous Mock... 
Les frameworks participent à cette confusion, car ils mélangent Stub & Mock alégrement.


### Soignez vos tests!

Le **code de test** est aussi important que le **code de production** 

Il doit etre _aussi propre_ que le code qu'il valide!

Note:
Meme quand il y a une volonté de faire des tests, ils peuvent devenir:
- Obsoletes, (état changeant -> tester le comportement et non l'état ?)
- Inmaintenables. (les ragles de code propre s'appliquent également au code de test)


### F.I.R.S.T

- Fast
- Isolated
- Repeatable 
- Self-Validating 
- Timely 

Note: 
- Fast => Rapide (car exécuter souvent. Les interruptions nuisent au flux naturel du travail)
- Isolated => Indépendant (pour exécuter des sous ensembles, ou en parallale, indépendemment de l'ordre)
- Repeatable => Admettant d'etre rejouer (Sans conserver d'état)
- Self-Validating => Auto-Validant (pas de validation humaine)
- Timely => écrit avec le code, voir avant (TDD) (En général, les tests sont meilleurs quand ils sont proche de la conception ou à l'origine du code applicatif). 
https://github.com/ghsukumar/SFDC_Best_Practices/wiki/F.I.R.S.T-Principles-of-Unit-Testing


## Test-Driven Development (TDD)

> If we continue to develop our technology without wisdom or prudence, our servant may prove to be our executioner.
 Omar N. Bradley

Note:
Pratique de développement piloté par les tests popularisé par Kent Beck et l'XP visant a améliorer la couverture et la qualité du code.
Les praticiens lui reconnaissent meme des vertues de design émergent ! 
Alors que ses détracteurs trouvent que l'idée est intéressante mais la technique fait perdre beaucoup de temps.  


### Forces du TDD 

- 100% de couverture
- Orienté conception

Note:
- Le code est testé avant meme d'etre écrit
- Il faut imaginer l'utilisation des éléments avant leur implémentation comme une api
- On passe beaucoup de temps a se poser des questions et refactorer. 


![redgreenrefacor](/slides/init-software-craftsmanship/img/redgreenrefacor.png) <!-- .element style="border: 0; background: None; box-shadow: None;width: 70%;" -->


### Baby Steps

Tests et implémentations les plus simples possibles !

Note:
- Rigueur difficile a tenir pour les developpeurs aguerris 
- Cela fait reellement emerger les algorithmes les plus simples


### Stratégies

- Fake it
- Use Obvious Implementation
- Triangulation

Note: 
- Fake it (Doublure temporaire, le temps de faire passer le test)
- Use Obvious Implementation (Solution évidente)
- Triangulation (généralisation à la 3eme occurence)
	Avant 3 occurences, on ne généralise pas un comportement !


### Aller plus loin 

- Double Loop TDD
- Mockist vs Classicist
- Outside-In vs Inside-Out TDD 
- Transformation Priority Premise


![questions](/slides/init-software-craftsmanship/img/Fotolia_121049964_M.jpg) <!-- .element style="border: 0; background: None; box-shadow: None;width: 130%;" -->


## Références 

- TDD by Example, Kent Beck
- Growing Object-Oriented Software Guided by Tests, Steve Freeman & Nat Pryce
- The Art of Unit Testing, Roy Osherove
 