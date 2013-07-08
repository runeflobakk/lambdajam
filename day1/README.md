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

_"The purpose of abstraction is not to be vague, but to create a new semantic level in which one can be absolutely precise."_ - Edsger Dijkstra








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
 







Let it Crash: Erland Fault Tolerance
======================================
**[Tristan Sloughter](http://twitter.com/t_sloughter)**

http://thisotplife.tumblr.com
http://learnyousomeerlang.com

Erlang created in 1986 by Joe Armstrong, with concurrency and error recovery built-in

Erlang enables coding "happy path", and if bad things happen, it's OK.
Keep working to a level of satisfaction in the presence of failure. Degradation is better than "no response".
Graceful degardation: black knight from Knights of the Round Table (Monty Python)

1/132 bugs are _NOT_ Heisenbugs
(Heisenbugs are bugs you cannot reproduce)

Coding happy paths:
- less code, less ifs and spaghetti
- less bugs
- easier to reason

So Erlang is fault tolerant, but what you _need_ to think about is
- how processes should behave in an event of failure
- how other processes behave (continue as before, or restart), and the hierarchy of that behavior
- restarting process(es) in a consistent initial state

The correct semantics for

**OTP:** The JEE of Erlang. It does what JEE promisses, but fails to provide.


Jim Gray: Why do computers stop and what can be done about it
http://www.hpl.hp.com/techreports/tandem/TR-85.7.pdf












Workshop: Hands-on Intro to Haskell
====================================
**Bartosz Milewski**

**Conceptual model:**
Your program is a tree of pure functions. Since Haskell is lazy, to get something actually done, this tree is triggered by IO, and any side effects produced by the tree is done "outside" of the pure functions of your program.

Turning top level design into types.
---------------------------------------

https://www.fpcomplete.com/user/bartosz/boh-code

Worked through a simple expression calculator with assignement capability:
- tokenizer String -> [Token]
- parser [Token] -> Tree
- evaluator Tree -> Double

To be able to support assignments, the use of a symbol table was modelled into the types, and passed to and returned from all the functions. From there the code was refactored into monads, in particular the Maybe, Either, and State monad, the latter being used for transparently passing the symbol table, i.e. "the world" as far as the calculator program is concerned. The key point was, that if one does not know monads, one will invent them when abstracting the common code patterns.

Very nice workshop. Although most of the concepts covered in the first part of the workshop should be known to functional programmers, I like that we do not rush through things. The syntax is new, and to really grasp what is going on, one need to process the code mentally.




