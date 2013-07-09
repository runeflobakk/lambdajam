Functional I/O in Scala
===============================
**[Nilanjan Raychaudhuri](http://twitter.com/nraychaudhuri)**

I/O is the problem child of functional programming.

Treating files as collections?
- Wrap it in an Iterable
- lazy
- when is the file closed?

**What is needed:**
Composability, scalability and resource-safety

Solution: good old fold left
IOC: producer pushes data instead of consumer pulls + futures & promises.

```Produces  ->  Transformer  -> Consumer```

The gist: chaining up stacks of functions which is executed at the end. (with what's essentially an IO monad: ```LazyContext.eval```)
Lots of coding, making Iteratees and stuff, more here [github.com/nraychaudhuri/iteratee-exercies](https://github.com/nraychaudhuri/iteratee-exercies)







Functional Async Without the Pain
====================================
**[Jim Powers](http://twitter.com/corruptmemory)**













Functional composition
==========================
**[Chris Ford](http://twitter.com/ctford)**




Workshop: Functional Web Development with Clojure
===========================================
**[Clinton N Dreisbach](http://twitter.com/cndreisbach)**







Keynote: Programming for the Expression of Ideas
====================================================
**Gerald Jay Sussman - [Massachusetts Institute of Technology](http://www.eecs.mit.edu/)**






