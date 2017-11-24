# Code Smells

![Trousse](/slides/init-software-craftsmanship/img/smelly.jpg) <!-- .element style="width: 80%;" -->

Note:

Avez-vous déja eu un  senti contrari a la vu un code?


## Comme une odeur... 

> A code smell is a surface indication that usually corresponds to a deeper problem in the system. Martin Fowler

Note:

Descriptions vagues car il revient aux équipes et développeurs de décider quand un code semble suffisamment odorant pour nécessiter une revue de code.

Des outils de qualimetrie permettent de fixer des seuils pour identifier le code odorant => Sonarqube


### Code Smells

![Trousse](/slides/init-software-craftsmanship/img/cleancode/codesmells.png) 


## Duplication

```csharp
public void CalculateFinalPrice()
{
    switch (item.Country)
    {
        case "France": 
            item.Price = item.BasePrice * FrenchTaxes; 
            break;
        case "USA": 
            item.Price = item.BasePrice * USATaxes; 
            break;
                    ...
        default : item.Price = item.BasePrice;
    }
}
```

Note:

* Polymorphisme pour injecter du comportement 
* plutôt que l'énumération de tous les comportements a un endroit


### Extraire le comportement et le parametrer 

```csharp

Dictionary<string,float> Taxes;

public void CalculateFinalPrice()
{
    item.Price = item.BasePrice * Taxes[item.Country]; 
}
```


> Je n'ai fait celle-ci plus longue que parce que je n'ai pas eu le loisir de la faire plus courte. <br/> Blaise Pascal

Note:
- Expressivité
- Concision


## Concision

Profiter des avantages des languages
- Ternaires (x ? y : z)  
- Lambdas : Linq / Lambdaj / jLinq / Pynq
- Etc


### Conditions non-non-positives 

```javascript
function doSomething(entity) {
    if (!entity.isNotSelected && client != null) {
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


## Grosses conditions

```javascript
function doSomething(date) {
    if ((date > new Date(.year, 11, 01) 
            && date < new Date(new Date().year, 12, 01)) 
        || (date > new Date(new Date().year, 12, 15) 
            && date < new Date(new Date().year + 1, 01, 01))) {
        ...
    }
    else {
        ...
    }   
}
```


### Extraire des variables d'intention

```javascript
function doSomething(date) {
    let year = new Date().year
    let inNovember = date > new Date(year, 11, 01) 
            && date < new Date(year, 12, 01)
    let inSecondHalfDecember = date > new Date(year, 12, 15) 
            && date < new Date(year + 1, 01, 01)
    if (inNovember || inSecondHalfDecember) {
        ...
    }
    else {
        ...
    }   
}
```


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
* Quel est ce 6 ?
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


## Primitive Obsession

```cs
// N'utilisez pas les primitives ...
public void SaveUser(int id, string nom, string prénom, 
    string adresse, string téléphone);

// Quand un objet peut aisément les représenter !
public void SaveUser(User user);
``` 


# R&eacute;f&eacute;rences

- [sourcemaking.com/refactoring/smells](https://sourcemaking.com/refactoring/smells)
- [martinfowler.com/bliki/CodeSmell.html](http://martinfowler.com/bliki/CodeSmell.html)
- Livres :
    - Refactoring, improving the design of existing code, Martin Fowler 
    - Clean Code, Robert C Martin
- [app.pluralsight.com/library/courses/refactoring-fundamentals](https://app.pluralsight.com/library/courses/refactoring-fundamentals/table-of-contents)