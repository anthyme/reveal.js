# Akka


## Actor model

![actor model](/slides/rex-akka-cqrs/img/actormodel.png)


## Why?

- Parallelism and linear performance <!-- .element: class="fragment" data-fragment-index="1" -->

- Aggregate consistancy <!-- .element: class="fragment" data-fragment-index="2" -->

- Pre-compute and command priority  <!-- .element: class="fragment" data-fragment-index="3" -->

- Sub commands <!-- .element: class="fragment" data-fragment-index="4" -->


## How?

![cqrs](/slides/rex-akka-cqrs/img/actor.png)


## Not Implemented

- View Event Handler Actors with a Mailbox buffer <!-- .element: class="fragment" data-fragment-index="1" -->

- Aggregate stored in the AggregateActor <!-- .element: class="fragment" data-fragment-index="2" -->

- Cancel old (low) priority command <!-- .element: class="fragment" data-fragment-index="3" -->

- Asynchrone CQRS with reactive architecture and new views pushed <!-- .element: class="fragment" data-fragment-index="4" -->

- Durability with Akka Persistance <!-- .element: class="fragment" data-fragment-index="5" -->