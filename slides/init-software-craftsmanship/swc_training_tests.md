# La boite &agrave; outil du Craftsman

![Toolbox](/slides/init-software-craftsmanship/img/Fotolia_93525027_S.jpg)


## Tests 

> Optimism is an occupational hazard of programming: feedback is the treament.
 Kent Beck


### Cout d'un bug au fil du temps

![Cout des bugs](/slides/init-software-craftsmanship/img/cost_of_bugs_over_time.jpg)

Note: 

Le cout d'un bug est d'autant plus grand qu'il est d&eacute;couvert tardivement
- http://blog.celerity.com/the-true-cost-of-a-software-bug 
- https://www.isixsigma.com/industries/software-it/defect-prevention-reducing-costs-and-enhancing-quality/
- http://xbsoftware.com/blog/cost-bugs-software-testing/
- http://superwebdeveloper.com/2009/11/25/the-incredible-rate-of-diminishing-returns-of-fixing-software-bugs/


### Typologie

1. Tests unitaires <!-- .element: class="fragment" data-fragment-index="1" --> 
2. Tests d'int&eacute;gration <!-- .element: class="fragment" data-fragment-index="2" -->
3. Tests fonctionnels <!-- .element: class="fragment" data-fragment-index="3" -->
4. Tests de non-r&eacute;gression <!-- .element: class="fragment" data-fragment-index="4" -->
5. Tests d'acceptance <!-- .element: class="fragment" data-fragment-index="5" -->
6. Tests de performance <!-- .element: class="fragment" data-fragment-index="6" -->

Note: 

- unitaires: &eacute;l&eacute;ment fonctionne correctement seul
- int&eacute;gration: &eacute;l&eacute;ments fonctionnent correctement ensembles
- fonctionnels: &eacute;l&eacute;ments r&eacute;pondent aux sp&eacute;cifications &eacute;tablies pr&eacute;alablement
- non-regression: syst&agrave;me valide selon les jeux de tests pr&eacute;-&eacute;tablis 
- acceptance: syst&agrave;me r&eacute;pond aux attentes des utilisateurs finaux
- performance: &eacute;l&eacute;ment, ou syst&agrave;me entier, r&eacute;pond aux contraintes de performances d&eacute;finies  


### Propri&eacute;t&eacute;s d'un test unitaire

S&eacute;quence de code _**ex&eacute;cutable**_ et **automatisable** mesurant de mani&egrave;re **reproductible** le r&eacute;sultat d'un code **atomique** et **isol&eacute;**


### B&eacute;n&eacute;fices attendus

- D&eacute;tection rapide d'erreurs
- Maintenance s&eacute;curis&eacute;e
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
- Classe de test => &eacute;l&eacute;ment ou comportement à tester  
- M&eacute;thode => Comportement attendu
- Ne pas utiliser le mot *TEST* <!-- .element: class="fragment highlight-red" data-fragment-index="1"--> 


### Organiser ses tests 

|  |             |           |
|--|-------------|-----------|
|1.|   Arrange   |   Given   |
|2.|   Act       |   When    |
|3.|   Assert    |   Then    |


### Dummy, Stub, Fakes & Mock

- Dummy: Objet par d&eacute;faut. 	<!-- .element: class="fragment highlight-current-blue" data-fragment-index="1" -->
- Fake: Impl&eacute;mentation limit&eacute;e 	<!-- .element: class="fragment highlight-current-blue" data-fragment-index="2"--> 
- Stub: R&eacute;ponses pr&eacute;d&eacute;dfinies &agrave; l'appel de ses m&eacute;thodes 	<!-- .element: class="fragment highlight-current-blue" data-fragment-index="3"--> 
- Mock: Trace le comportement  	<!-- .element: class="fragment highlight-current-blue" data-fragment-index="4"--> 

Note: 
- Fake: Version appauvrie d'un objet permettant d'ex&eacute;cuter le test (sans framework)
- Stub: Renvoyer la m&ecirc;me valeur à chaque appel pour &eacute;liminer un aspect al&eacute;atoire, ou un acc&agrave;s base de donn&eacute;es
- Mock: D&eacute;tecter un &eacute;v&eacute;nement ou un changement d'&eacute;tat au sein d'un objet 


### Confusion

Test Double == Mock ? 

**Same Same...**  <!-- .element: class="fragment" data-fragment-index="1" -->

Note: Il y a confusion sur les objets doublures de test, on les appelle tous Mock... 
Les frameworks participent à cette confusion, car ils m&eacute;langent Stub & Mock al&eacute;grement.


### Soignez vos tests!

Le **code de test** est aussi important que le **code de production** 

Il doit &ecirc;tre _aussi propre_ que le code qu'il valide!

Note: 

Meme quand il y a une volont&eacute; de faire des tests, ils peuvent devenir:
- Obsoletes, (&eacute;tat changeant -> tester le comportement et non l'&eacute;tat ?)
- Inmaintenables. (les r&agrave;gles de code propre s'appliquent &eacute;galement au code de test)


### F.I.R.S.T

- Fast
- Isolated
- Repeatable 
- Self-Validating 
- Timely 

Note: 

- Fast => Rapide (car ex&eacute;cuter souvent. Les interruptions nuisent au flux naturel du travail)
- Isolated => Ind&eacute;pendant (pour ex&eacute;cuter des sous ensembles, ou en parall&agrave;le, ind&eacute;pendemment de l'ordre)
- Repeatable => Admettant d'&ecirc;tre rejouer (Sans conserver d'&eacute;tat)
- Self-Validating => Auto-Validant (pas de validation humaine)
- Timely => &eacute;crit avec le code, voir avant (TDD) (En g&eacute;n&eacute;ral, les tests sont meilleurs quand ils sont proche de la conception ou à l'origine du code applicatif). 
https://github.com/ghsukumar/SFDC_Best_Practices/wiki/F.I.R.S.T-Principles-of-Unit-Testing


## Test-Driven Development (TDD)

> If we continue to develop our technology without wisdom or prudence, our servant may prove to be our executioner.
 Omar N. Bradley

Note:

Pratique de d&eacute;veloppement pilot&eacute; par les tests popularis&eacute; par Kent Beck et l'XP visant &agrave; am&eacute;liorer la couverture et la qualit&eacute; du code.
Les praticiens lui reconnaissent m&ecirc;me des vertues de design &eacute;mergent ! 
Alors que ses d&eacute;tracteurs trouvent que l'id&eacute;e est int&eacute;ressante mais la technique fait perdre beaucoup de temps.  


### Forces du TDD 

- 100% de couverture
- Orient&eacute; conception

Note:
- Le code est test&eacute; avant meme d'etre &eacute;crit
- Il faut imaginer l'utilisation des éléments avant leur implémentation comme une api
- On passe beaucoup de temps &agrave; se poser des questions et refactorer. 


### 

<!-- .slide: data-background-image="/slides/init-software-craftsmanship/img/redgreenrefacor.png" data-background-size="contain" data-background-repeat="no-repeat" -->


### Baby Steps

Tests et impl&eacute;mentations les plus simples possibles !

Note:
- Rigueur difficile a tenir pour les developpeurs aguerris 
- Cela fait reellement emerger les algorithmes les plus simples


### Strat&eacute;gies

- Fake it
- Use Obvious Implementation
- Triangulation

Note: 
- Fake it (Doublure temporaire, le temps de faire passer le test)
- Use Obvious Implementation (Solution &eacute;vidente)
- Triangulation (généralisation à la 3eme occurence)
	Avant 3 occurences, on ne g&eacute;n&eacute;ralise pas un comportement !


### Aller plus loin 

- Double Loop TDD
- Mockist vs Classicist
- Outside-In vs Inside-Out TDD 
- Transformation Priority Premise


## 

<!-- .slide: data-background-image="/slides/init-software-craftsmanship/img/Fotolia_121049964_M.jpg" data-background-size="contain" data-background-repeat="no-repeat" -->


## R&eacute;f&eacute;rences 

- The Art of Unit Testing, Roy Osherove
- TDD by Example, Kent Beck
- Growing Object-Oriented Software Guided by Tests, Steve Freeman & Nat Pryce
 