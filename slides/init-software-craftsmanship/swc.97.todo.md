## Des pratiques partagées !

* Documenter des standards
* Pair Programming / Mob Programming 
* Code Reviews 
* Outils de suivi de la qualité du code

Note:
Suivre les bonnes pratiques seul ne sert à rien. 
Pire c'est dangereux pour la santé mentale !



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






## Nommage

> Names and attributes must be accommodated to the essence of things, and not the essence to the names, since things come first and names afterwards.
 Galileo Galilei, Discoveries and Opinions of Galileo 