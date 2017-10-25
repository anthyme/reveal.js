# Software Craftsmanship

*la bou&eacute;e de sauvetage du d&eacute;veloppement agile*


## Agile Manifesto

> Individuals and interactions over processes and tools <!-- .element: class="fragment highlight-current-blue" data-fragment-index="1" -->

> Working software over comprehensive documentation <!-- .element: class="fragment highlight-current-blue" data-fragment-index="2" -->

> Customer collaboration over contract negotiation <!-- .element: class="fragment highlight-current-blue" data-fragment-index="3" -->

> Responding to change over following a plan <!-- .element: class="fragment highlight-current-blue" data-fragment-index="4" -->

Note: 

En **2001**, 17 experts ont fig&eacute; les **4 valeurs** & **12 principes** de l'agilit&eacute;.

1. Le client et le produit au centre
1. Processus it&eacute;ratif &eacute;vite l'effet tunnel & valorise la r&eacute;activit&eacute;
1. Casser les longues chaines de d&eacute;cision et rapprocher les intervenants 

Forc&eacute;ment d'accord apr&agrave;s un projet en V rat&eacute;. 
Cependant la r&eacute;alit&eacute; du terrain ne correspond pas.


## La gueule de bois Agile

![Post it nightmare](/slides/init-software-craftsmanship/img/postItNightmare.jpg)

Note: 

Mirage de l'eldorado des post-its: Les projets IT &eacute;chouent toujours!

Le probl&agrave;me c’est que le « Working Software » a &eacute;t&eacute; pris au pied de la lettre

Pas mal de projet et d’&eacute;quipe utilisant souvent SCRUM et qui se sont trop concentr&eacute; sur la vitesse de d&eacute;veloppement et le working software 
se sont r&eacute;veill&eacute; avec une sacr&eacute; gueule de bois

Car sans s’investir sur la qualit&eacute;, le code a les m&ecirc;mes probl&agrave;mes qu’avant l’agilit&eacute;
Un code peu maintenable, compliqu&eacute;, on sait pas quoi en faire voir m&ecirc;me comment vivre avec

Changement de m&eacute;thodologie sans changement de culture:
- Rythme insoutenable 
- Qualit&eacute; m&eacute;diocre des projets 

Effet de mode nuisibles:
- Business des coachs et certifications agiles


## Temps

![Spirale infernale](/slides/init-software-craftsmanship/img/time.jpg)

Note:

Le probleme est que nous avons une mauvaise relation au temps.

Le nombre de fois o&ugrave; j'ai entendu : "on a pas le temps de faire des tests".
MAIS on a le temps de faire des semaines de test pour trouver tous les bugs avant la livraison ? 
ET on a le temps de debugger pendant des heures pour trouver un commit oublier ?

Le probl&agrave;me est que nous n'avons 
- pas de trace pr&eacute;cise du temps de correction des bugs.
- pas de m&eacute;triques comparatives d'un bug &agrave; l'autre.
- Les d&eacute;veloppeurs sont des perfectionnistes suceptibles : minimise le temps de r&eacute;solution, et r&eacute;solve sur temps perso ou cacher 

=> Essayez de tracer le nb de bugs pour constater une tendance! 


## Le principe agile oubli&eacute;

> Continuous attention to technical excellence and good design
**enhances** <!-- .element: class="fragment highlight-red" data-fragment-index="1" -->
agility.  

Note:

Ce principe n'est pas assez fort : **enhances** -> **am&eacute;liore**

Continuellement l'excellence technique et le bon design sont n&eacute;cessaire  


## Une proposition alternative... 

> Continuous attention to technical excellence and good design
**saves** <!-- .element: class="fragment highlight-green" data-fragment-index="2" -->
agility.  

Note:

Il n'y a pas d'agilit&eacute; possible dans la dur&eacute;e si l'objet 


## La menace cach&eacute;e

![Invisible threat](/slides/init-software-craftsmanship/img/hiddenThreat.png)

Note: 

1. Le time to market, force du mod&agrave;le agile, explose quand la qualit&eacute; du code devient trop mauvaise. 
1. Les imperfections du code freinent l'ajout ou la modification de fonctionnalit&eacute;s
1. Mais pourquoi &eacute;crit-on du mauvais code ? et pourquoi autant ?! 


## Crazy Coder

![Crazy Coder](/slides/init-software-craftsmanship/img/Fotolia_56962791_M.jpg)

Note:

1. Est-ce que les d&eacute;veloppeurs sont insconscients ?
1. On se fait du tort &agrave; &eacute;crire du mauvais code, car il viendra nous hanter
1. On entend, c'est ce que me demande mon cdp... => Pas satisfaisant ? Sommes nous de simples ex&eacute;cutants ?


## Le code est partout

1. Le code est partout.
1. Demain tout sera code.
1. Le nombre de d&eacute;veloppeurs croit de moiti&eacute; tous les 10 ans
1. Confierez-vous votre vie &agrave; une voiture automatique? 
1. Confierez-vous votre op&eacute;ration &agrave; coeur ouvert &agrave; un programme ?


## Nos Valeurs ?

![Lost](/slides/init-software-craftsmanship/img/Land-Of-Confusion.jpg)

Note: 

1. Est-ce que le d&eacute;veloppeur est un ing&eacute;nieur au m&ecirc;me titre qu'un autre ? Ou un simple ex&eacute;cutant ?
1. Le r&ocirc;le de d&eacute;veloppeur porte encore une connotation p&eacute;jorative. => Geek introverti incapable de travailler en &eacute;quipe
1. Faut-il l&eacute;gif&eacute;rer et normer les taches du d&eacute;veloppeur ? 
1. Faut-il des certifications de qualit&eacute; pour les d&eacute;veloppeurs ?


## Take back control 

![Uncle Bob Needs You](/slides/init-software-craftsmanship/img/uncle-bob.jpg)

**Become a Craftsman!**

Note:

Les devs doivent prendre le controle de leur destin&eacute;e ! (uncle bob)

T&ecirc;te de ligne du mouvement software craftsmanship, uncle bob faisait parti des signataire du manifeste agile.

1. Une catastrophe informatique nous pend au nez. Et ce jour l&agrave;, les politiques et les juges viendront l&eacute;gif&eacute;rer sur comment on doit d&eacute;velopper.
1. Seule alternative: les d&eacute;veloppeurs doivent se prendre en main et am&eacute;liorer leurs pratiques pour plus de qualit&eacute;.
1. Craftsman = Artisan. Un professionnel passionn&eacute; par son travail, cherchant sans cesse &agrave; perfectionner son art.

Il propose des principes de dev du Clean Code et certains autre pour am&eacute;liorer la qualit&eacute; de notre code. ce sont devenus des standards du swc.   


## Software Craftsmanship Manifesto

> Not only working software, but also well-crafted software <!-- .element: class="fragment highlight-current-blue" data-fragment-index="1" -->

> Not only responding to change, but also steadily adding value <!-- .element: class="fragment highlight-current-blue" data-fragment-index="2" -->

> Not only individuals and interactions, but also a community of professionals <!-- .element: class="fragment highlight-current-blue" data-fragment-index="3" -->

> Not only customer collaboration, but also productive partnerships <!-- .element: class="fragment highlight-current-blue" data-fragment-index="4" -->

Note:

le manifeste du SWC vient en compl&eacute;ment du manifeste Agile. Ne remet pas en cause l'agilit&eacute; !

On mets l'accent sur les &eacute;l&eacute;ments oubli&eacute;s ou pas suffisamment mis en avant, et on promeut un nouvel &eacute;tat d'esprit du d&eacute;veloppeur.

1. Une voiture qui roule aujourd'hui n'est pas suffisant, il faut qu'elle roule demain. Sa long&eacute; vit&eacute;  passe par la qualit&eacute;  de fabrication.
1. Pas uniquement en r&eacute;action, mais une v&eacute;ritable vision sur le long terme. Non aux rustines et on continue de s'am&eacute; liorer. 
1. Communaut&eacute; de professionnels &eacute;changeant les bonnes pratiques et propageant la culture de l'apprentissage
1. Collaboration bi-directionnelle: m&ecirc;me si le client est primordial, il n'est pas roi. (au mieux pr&eacute;sident ?)


## L'h&eacute;ritage XP 

- Communication
- Simplicity
- Feedback
- Courage
- Respect

Note:

- Tout probl&agrave; me est avant tout un probl&agrave; me de communication
- Quelle est la chose la plus simple qui pourrait possiblement fonctionner?
- Saisir rapidement les changements &agrave; l'oeuvre et comprendre ou on s'est tromp&eacute; 
- Un biais menant &agrave; l'action
- Prenez soin des membres de l'&eacute; quipe et du projet


##

<!-- .slide: data-background-image="/slides/init-software-craftsmanship/img/xp_practices.jpg" data-background-size="contain" data-background-repeat="no-repeat" -->


## d'autres pratiques 

- Clean Code, SOLID
- La pratique d&eacute;lib&eacute;r&eacute;e
- Mob Programming
- Domain Driven Design


## Les bonnes pratiques...

...ne sont bonnes que jusqu'au jour o&ugrave; l'on en trouve de meilleurs.

Note: 

Ne soyez pas dogmatique! Un jour il y aura de meilleures pratiques que les votres.
Meme le TDD & pair progamming seront pe jeter au buchet un jour


##   

Le but du Software Craftmanship n'est pas de suivre les pratiques, ou d'avoir du beau code, 
mais de d&eacute;livrer continuellement de la valeur au travers d'applications bien con&ccedil;ues


## Profil d'un Software Craftsman

- professionnel
- responsable
- pragmatique
- r&eacute;solu
- mentee 
- mentor 

Note:

- prof : soucieux de la valeur d&eacute;livrer &agrave; son client. Et se gardant &agrave; jour dans son domaine
- resp : ne livrera pas un produit en deça du niveau de qualit&eacute; acceptable
- prag : conscient que chaque contexte dicte le niveau d'acceptabilit&eacute;
- r&eacute;solu : capable de d&eacute;fendre sa position dans l'adversit&eacute;
- mentee (humble): je sais que je ne sais rien
- mentor (g&eacute;n&eacute;reux): &agrave; mon tour je participe &agrave; v&eacute; hiculer ce que j'ai appris

Ca fait beaucoup. Certains trouvent &eacute;litiste ce mouvement.
Ce n'est pas vrai ! Il faut viser une perfection  C'est simplement un appel aux d&eacute;veloppeurs soucieux de progresser et de bien faire leur travail.
Un phare au milieu de la nuit...
