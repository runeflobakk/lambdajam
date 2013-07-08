Data, Visibility, and Abstraction
=====================================
**[Stuart Sierra](http://twitter.com/stuartsierra)**

Memory Lane
----------------
Basic is a very good language for starting to learn programming. POW!!
(take that Dijkstra)
Praising QBasic for its distinction between subroutines and FUNCTIONS.
The functions value is its return value.

**C++** 
- about the mechanics of the program and computer.
- not about the data, about _how_ the program works.

**Perl**
- Abstracted away how the computer works.
- Few generic data structures. Everything can be represented with sequences, maps, and simple values.
- "Tie": using different implementations for data structures. Tie a hashmap to database tables, etc.

**Java** (laughter)
- lots of mechanic code to transform from one type to another.
- writing code yourself to get a view of what the data actually is.

**Common Lisp**
- does not have the "different implementations for common data structures" from Perl.
- Could have written it, but it would not compose with other libraries. Not part of the core of the language.

Ranting on operator overloading, and too much extending and mashing up the language. (Ruby. And Scala?)
Suspicious about libraries that use alot of macros, because it makes it non-transparent to what really happens.

**Clojure**
- started coding "subroutines", then went on to use "state of the world" as input output from functions.
- That state can then be fed to something that carries it out and performs side effects.
- **[pedestal.io](http://pedestal.io)**
- Hexagonal Archtitecture. Core that manipulates data. Ports/adapters to the core to perform IO (GUI, WebServices, Database, tests)

Lookup: Dijkstra quote on abstraction.








(Simile-Free) Monad Recipes
===================================
**[Aditya Siram](http://twitter.com/deech)**

"Cookbook recipees" session. How to emulate imperative typical idioms.

**Monadic code:**
- shuffling stuff in and out of contexts.
- Common "interface" to take values out of an arbitrary monad, and put into an arbitrary monad.
- Haskell: left-arrow (&lt;-) and "return".

**Writer monad use case**: Web forms; get complete list of user's error inputs.

A bit hard to follow for non-Haskellers, at least for me. Lots of code examples, values in an out of monads.
 







Let It Crash: Erland Fault Tolerance
======================================
**[Tristan Sloughter](http://twitter.com/t_sloughter)**











Workshop: Hands-on Intro to Haskell
====================================
**Bartosz Milewski**





Systems that run forever self-heal and scale
**********************************************
**Joe Armstrong**

