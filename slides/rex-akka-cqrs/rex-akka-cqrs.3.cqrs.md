# CQRS


![cqrs](/slides/rex-akka-cqrs/img/cqrs.png)


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

- Really big Aggregate <!-- .element: class="fragment" data-fragment-index="1" -->

- Sometime a lot of events by command <!-- .element: class="fragment" data-fragment-index="2" -->

- Bad perf on prod dataset at first <!-- .element: class="fragment" data-fragment-index="3" -->

- Synchronous vs Asynchronous <!-- .element: class="fragment" data-fragment-index="4" -->


## Solutions

- Group events by type to batch them (with SqlBulkCopy) <!-- .element: class="fragment" data-fragment-index="1" -->

- Group and map events to "batch events" by storage destination <!-- .element: class="fragment" data-fragment-index="2" -->

- Cache Ref and State data <!-- .element: class="fragment" data-fragment-index="3" -->