### Clean Code

![Clean](/slides/init-software-craftsmanship/img/CleanCode.jpg)

Note: 

1. Uncle Bob a popularisé la pratique du Clean Code au travers de ces deux livres Clean Code et Clean Coder. 
1. Développeur américain né en 1952  
1. Parmis les créateurs du manifeste Agile
1. SmallTalk & Java
1. Kent Beck <-> Simple Design : essentiel des pratiques dev XP 


### Stupid code !

- Singleton
- Tight coupling
- Untestable
- Premature optimization
- Indescriptive naming 
- Duplication


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
- Le code EST la documentation et seule source de vérité
- Etre agile, c'est pouvoir changer

Note: 

- Je ne parle même pas du support et des testeurs 


## Ratio Signal/Bruit 

- Cerveau humain peut traiter nombre limité de signaux 
- Trop d'informations se transforment en bruit
- Le bruit du code s'amplifie au fil du temps

Note:

1. Homme conserve seulement 7 éléments (+-2) dans sa mémoire a un moment donné
1. Un code avec une complexité cyclomatique trop importante renvoit trop de possibilités
1. Une fois sur cette voie on ne peut que rajouter dela complexité (un if / case de plus) 


## Clean Code 

> Clean code always looks like it was written by someone who cares. <br/> Michael Feathers

Note:

1. Extrait du chapitre écrit par Michael Feathers dans le livre Clean Code


> There are only two hard things in Computer Science: cache invalidation and <br/> naming things. <br/> Phil Karlton


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


## Appel a un ami !

Dans le doute, demandez a un collegue 


# Classes

> Classes should do one thing. They should do it well. They should do it only.
 <br/>Robert C. Martin


## Ajouter une Classe ?

* Nouveau concept
* Cohésion faible
* Réutilisation
* Réduire la complexité

Note:
**réduire complexité**: 
- diminuer le nombre d'éléments (cohésion) 
- encapsuler des variables dans une structure cohérente


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


# Functions

> Functions should do one thing. They should do it well. They should do it only. <br/>Robert C. Martin


## Nommer une méthode

- Le nom doit suffire !
- Pas de nom générique (Do, Process, Execute, ...) 

=> ex: DocumentConverter.HtmlFromText(textFile);


## Pourquoi créer une fonction?

* Eviter la duplication
* Réduire l'indentation du code
* Clarifier l'intention d'un code 
* Séparer différentes opérations et abstractions

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


## Cohésion & Couplage 

- Cohésion *forte*
    - Regroupement fonctionnel
    - Meme niveau de détail

- Couplage *faible*
    - Minimiser dépendances 


## Soyez protecteur 

Exposez le minimum nécessaire !


## Principe de proximité

Conserver les éléments liés a proximité

# Commentaires

- redondance 
- évidence 
- péremption 

=> inutile ou presque


## To comment or not to comment

* Résumé ?
* Code désactivé ?
* Clarification ?
* Avertissement ?

Note: 
* Résumé
    - Duplication  
    - Approximation
    - Vision erronée/périmée
* Code désactivé
    - Zombie code => Delete
* Clarification
    - Signe de code trop long ?
* Avertissement : Todo/Warning
    - Dette technique


## Questions a se poser

- Arrivez-vous a exprimer l'intention dans le code?
- Est-ce que le commentaire est un déodorant ?
- Est-ce que sa place est dans le code source?


# Simple Design

> Make it work, <br/>make it right, <br/>make it fast.<br/>Kent Beck


## 4 regles

* Valide les tests
* Exprime clairement son intention 
* Contient aucune duplication
* Minimise le nombre d'éléments

Note:
- Ordre d'importance descendant
**ATTENTION**: Minimiser tant qu'on n'enfreint pas la seconde regle ! 


### Principe de surprise minimum

Fais ce que tu dis, <br/>et dis (clairement) ce que tu fais!

```csharp
void GetItem();
//vs
Item GetItem(int id);
```

Note:
Une méthode GetItem() on s'attend qu'elle requete un dataprovider pour récupérer l'élément et éventuellement le remettre en forme et le renvoie en sortie

=> notions de Standard et  Cohérence au sein de l'application
de
Faites votre code comme une API, pensez a l'usage d'un autre développeur ne connaissant pas la tuyauterie interne.
Le TDD peut aider!


# Conclusion

> Simplicity is a great virtue but it requires hard work to achieve it and education to appreciate it. And to make matters worse: complexity sells better. <br/>Edsger W. Dijkstra


### La vérité est dans le code

* Le code est majoritairement lu
* Le code est la seule documentation a jour
* Le bruit est l'origine de mauvaises implémentations & bugs


### Un investissement durable 

Ces principes fonctionnent quelque soit
* le langage (objet)
* l'architecture
* les librairies


## Références 

- Clean Code, Robert C Martin (@unclebob)
- Extreme Programming Explained, Kent Beck