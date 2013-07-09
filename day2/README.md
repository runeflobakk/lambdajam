Functional I/O in Scala
===============================
**[Nilanjan Raychaudhuri](http://twitter.com/nraychaudhuri)**

I/O is the problem child of functional programming.

**What is needed**
Composability, scalability and resource-safety


Treating files as collections?
- Wrap it in an Iterable
- lazy
- when is the file closed?



Solution: apparently good old fold left
IOC: producer pushes data instead of consumer pulls, with some added futures & promises.

```Produces  ->  Transformer  -> Consumer```

The gist: chaining up stacks of functions which is executed at the end. (with what's essentially an IO monad: ```LazyContext.eval```)

Lots of coding, making Iteratees and stuff, more here [github.com/nraychaudhuri/iteratee-exercies](https://github.com/nraychaudhuri/iteratee-exercies)







Functional Async Without the Pain
====================================
**[Jim Powers](http://twitter.com/corruptmemory)**

**Async, Actors, and IOC**

- Wants to minimize IOC, in contrast to the last talk... More direct style
- Separation between business logic and actor-related plumbling.

**Actors**
- abstraction over message passing
- actors do:
  - send messages
  - respond 
  - create other actors


**[Scatter/Gather](http://www.enterpriseintegrationpatterns.com/BroadcastAggregate.html)**
Problem: scaling a search index

Typical Actor-implementations gets dificult to compose, and reason about the business logic, what gets sent where, and so on.
Callback-code needs mental book keeping on the actual stack of operations.
Composition is tricky. "Return type" of actors is essentially ```Nothing```


**Futures**
- callback oriented
- verbose


**[Async](https://github.com/scala/async)**

```
async {
   await(someFn) + await(someOtherFn) 
}
```

Looks like it is waiting and blocking the thread, but the macro is in fact making it not block.

Async is not a very good match for actor based applications. (Considered an anti-pattern at Typesafe)


**[Machines](https://github.com/runarorama)**

Composable network of stream processors



**Conclusion**

- We need better abstractions for working with actors.
- Direct control, see the flow of computation.
- Composability
- Reasoning
- Separate business and plumbing code.















Workshop: Functional Web Development with Clojure
===========================================
**[Clinton N Dreisbach](http://twitter.com/cndreisbach)**

- many languages (HTML, CSS, JavaScript, server side)
- lots of moving parts, technology

Traditional: frameworks...
Or: same language for client and server (browser then dictates language for backend)

Frameworks means someone takes lots of opinionated choices for you.
Clojure:
- Noir (deprecated)
- Pedestal (new)
- CHP (new)
- Luminus (curated collection of libs) <-- the Clojure way

Clojure way:
- lots of loossely coupled libraries

Why Clojure:
- domain is data manip. or needs concurrency
- acces to all Java libs
- quick dev. with the REPL
- tooling with Leiningen
- deploy WARs
- it is _fast_

Libs:
- Ring
- Compojure
- libnoir (features of now deprecated Noir, as reusable independent parts)
- Hiccup
- Garden (CSS)
- ClojureScript
- Cheshire (JSON)
- Liberator (REST)


Compile JS from ClojureScript
- lein-cljsbuild
- code must not rely on other code that cannot be compiled to JS


FRP with Javelin
- Functional Reactive Programming
- like a spreadsheet, updating one cell, immediately updates depending cells


Lots of libraries. Some frameworks for pulling it all together:
- [Luminus](http://luminusweb.net)
- [Pedestal](http://pedestal.io) - good for JavaScript-heavy single-page apps
- [Hoplon](https://github.com/tailrecursion/hoplon) only client-side, HTML as expressions voodoo magic.





