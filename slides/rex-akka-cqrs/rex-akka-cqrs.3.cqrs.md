# CQRS


![cqrs](/slides/rex-akka-cqrs/img/cqrs.png)


## Why CQRS ?

- Domain complexity encapsulation in the command side

- View materialization


## Architecture

![cqrs architecture](/slides/rex-akka-cqrs/img/cqrs-architecture.png)


## Command side

- (State + Ref) * Builder = Aggregate <!-- .element: class="fragment" data-fragment-index="1" -->

- Aggregate + command = (Domain) Events <!-- .element: class="fragment" data-fragment-index="2" -->

- State + Events = NewState <!-- .element: class="fragment" data-fragment-index="3" -->

- Then: Save NewState & Publish Events <!-- .element: class="fragment" data-fragment-index="4" -->


## View side

- Foreach event

- Upsert view database


## Challenges

- Big Aggregate <!-- .element: class="fragment" data-fragment-index="1" -->

- A lot of data displayed to the user <!-- .element: class="fragment" data-fragment-index="2" -->

- Sometime a lot of created events <!-- .element: class="fragment" data-fragment-index="3" -->

- Bad perfs on prod dataset at first <!-- .element: class="fragment" data-fragment-index="4" -->

- Synchronous vs Asynchronous <!-- .element: class="fragment" data-fragment-index="5" -->
<br/> => Eventual consistancy danger !!!


## Solutions

- Group events by type and do batchs <!-- .element: class="fragment" data-fragment-index="1" -->

- Group and map domain events by storage destination to "batch events"  <!-- .element: class="fragment" data-fragment-index="2" -->

- Cache Ref and State data <!-- .element: class="fragment" data-fragment-index="3" -->

- Compute and store less with <br/>"business tricks" <!-- .element: class="fragment" data-fragment-index="4" -->