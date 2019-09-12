## How to become a better programmer

This post contains some advice of how to become a better programmer. Over the past few years I have seriously gotten into programming and accumulated a bunch of knowledge from various sources. The purpose of this post is to share links to resources that I believe are the most relevant or insightful in helping you become a better programmer.

### What does the word *programmer* mean?

I like Alexander Stepanov's<sup>1</sup> definition of programmer and the discipline of programming, which he describes in (excruciating) detail in this [video](https://youtu.be/k-meLQaYP5Y). Simply, a programmer is someone who creates or designs computer programs. Programming is a distinct discipline from computer science, but equally important and "glorious". It should the goal of every "software engineer" to become a better programmer, because at the end of the day the product of our labour is code and learning how to make it high quality should be a worthy goal.


#### Disclaimer

This post is just going to be a brain dump for now - without much organization in terms of the topics. I might come back and organize this better in the future.

As you'll notice, all the notes here are just links to resources, because I definitely don't have anything interesting to say on top of what these wonderful people have already said. The choice of resources and advice expressed here are my opinions and I am far from an expert on these topics - if you disagree with certain things, you're probably right. 

### Topics to learn (in no particular order)

#### Software design
* [Out of the tar pit paper](https://github.com/papers-we-love/papers-we-love/blob/master/design/out-of-the-tar-pit.pdf)
**Summary**: This paper describes the problem of *complexity* in modern software (and by modern, they mean anything written after the 60s). They claim that none of the current major paradigms of programming (object-oriented, functional, logic etc.) address this problem head-on. They propose a new paradigm of programming which they call "functional relational programming (FRP)". This paradigm combines the benefits of the relational model for managing data with functional programming for implementing logic. 
**Major takeaway**: Describes in (probably too much) detail the major problems with how programs are written today and how to avoid these problems by minimizing *accidental complexity* through a very principled and structured approach to writing programs.
**Skippable**: No
* Rich Hickey's<sup>2</sup> talks 
["Are We There Yet?" (w/ slides) - Rich Hickey (2009)](https://youtu.be/E4RarTAZ2AY)
Start by watching this talk where Rich outlines the major problems he has with the current major (object-oriented) way of programming. It has a lot of ideas similiar to the Out of the tar pit paper, but presented in a much more concise way. Plus he makes great references to Alfred North Whitehead's books throughout this talk.
[The Language of the System - Rich Hickey](https://www.youtube.com/watch?v=ROor6_NGIWU)
In this talk he describes Clojure in more detail.
[Simple made easy](https://www.youtube.com/watch?v=oytL881p-nQ)
He describes what role simplicity plays in designing programs and how to make programs simpler (presumably by using Clojure).
[The Value of Values with Rich Hickey](https://youtu.be/-6BsiVyC1kM)
Small little talk on why you should be using values in your programs. (To understand what values are, watch the previously mentioned talks)
**Major takeaway**: Programming can be a **lot** simpler than how people normally do it. Eschewing state, mutability, static typing (this is a highly contentious claim) allows us to focus on actually solving our problems rather than constructing grand edifices of complexity that, while being marvelous, are completely counterproductive. These talks contain a lot of wisdom that can be applied to your programming life even if you have no intention of using Clojure.
**Skippable**: Yes
* [Alexander Stepanov: STL and Its Design Principles](https://www.youtube.com/watch?v=COuHLky7E2Q)
In this talk, Stepanov describes his approach to designing programs using generic programming. He says that he created the STL as a shining example of an example of this approach, but unfortunately it never really took off (outside of being directly used by tons of people).
**Major takeaway**: Build large software using small, generic, re-usable, well-tested, performant components. Use concepts to define what types these components operate on. This approach of building software is recursive: larger pieces of software can be generic and re-usable too, we don't need to simply stop at the level of `std::sort`. Of course achieving this in practice is much harder.
**Skippable**: No

### Programming fundamentals

* [SICP Book](https://mitpress.mit.edu/sites/default/files/sicp/index.html) and [SICP Lectures](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-001-structure-and-interpretation-of-computer-programs-spring-2005/)
This book might appear simple or beginner level to you if you are a professional programmer, but it contains wisdom that is not found in most other resources. The book contains ideas that are barely mainstream in 2019 - for example [Lecture 6](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-001-structure-and-interpretation-of-computer-programs-spring-2005/video-lectures/6a-streams-part-1/) describes Streams, a concept that isn't found in most modern programs yet is extremely useful if building interactive software (as can be seen by the increasing popularity of libraries like RxJS.
**Major takeaway**: Constructing programs can be a systematic task, rather than brute-force or ad hoc mishmash of ideas. If we learn the principles behind programming (e.g. primitive expression, means of combination, means of abstraction), we can apply them to construct complex programs in a systematic way.
**Skippable**: At your own peril.
* [Elements of programming](http://elementsofprogramming.com)
This book tries to do for programming what Euclid for mathematics in [Elements](https://en.wikipedia.org/wiki/Euclid%27s_Elements). The goal of this book is to create a mathematical foundation for programming (built on abstract algebra) that is at the same time very practical and described through a(n almost) real programming langage (pseudo C++20).
**Major takeaway**: If you think you know how to write the algorithm for generating fibonacci numbers, you should read this book. It breaks down algorithms to their very fundamentals, giving deep insights on how to construct programs by composing generic algorithms. It implements in detail the philosophy in talk mentioned above by Alex Stepanov.
**Skippable**: At your own peril.
* [Bret Victor - Inventing on Principle](https://vimeo.com/36579366)
I'm putting this this talk under fundamentals, but it's really a talk about seeing the discipline of programming in a different light. The talk is hard to describe, so just watch it!
**Major takeaway**: A lot of people's reactions to Bret's talks is something like "Visual programming sucks and this will never work". I never really saw his talks as being about visual programming at all. His main message is that the way we do programming currently isn't the end state and there is huge room for improvement. For example, computers are excellent are running programs - so why do we simulate computers in our heads while we are writing programs when we could just command the computer to do it for us?
**Skippable**: Yes

#### Practical programming advice

* [CppCon 2014: Mike Acton "Data-Oriented Design and C++" ](https://www.youtube.com/watch?v=rX0ItVEVjHc)
The thesis of this talk is that programming is all about manipulating data, therefore programs should focus on that as their highest priority and try to minimize everything else that gets in the way of achieving that goal. This talk has the added charm that Mike Acton shows utter contempt for C++ while being a keynote speaker at CppCon (the main C++ conference).
**Major takeaway**: Focus on designing your programs around datastructures and how those datastructures are accessed. Achieving ultimate performance is only possible if you (re)orient your thinking around data, rather than algorithms or program "architecture".
**Skippable**: Yes

* [GoingNative 2013 C++ Seasoning - Sean Parent](https://channel9.msdn.com/Events/GoingNative/2013/Cpp-Seasoning)
In this talk Sean Parents describes his goals when writing programs. These goals include No Raw Loops, No Synchronization Primitives, No Incidental Datastructures and others. Sean illustrates beautifully how to take unstructured, ad hoc code and convert it to something that's semantically more meaningful, easier to read and is more performant.
**Major takeaway**: Commit all standard library algorithms and containers to memory. Practice writing code where you minimize control flow and custom algorithms and use precanned algorithms found in either the standard library or other libraries. Most of your programs should be composed standard algorithms acting on simple datastructures.
**Skippable**: Absolutely not

* [Transforming Code into Beautiful, Idiomatic Python - Raymond Hettinger](https://www.youtube.com/watch?v=OSGv2VnC0go)
This is a very easy to follow talk in which Raymond goes through example after example of unpythonic (bad) code and refactors it to make it pythonic. Even if you don't use python, the principles that Raymond uses are crucial to  learn.
**Major takeaway**: There are usually multiple ways of doing a task in your program. Don't always go with the most obvious or easy (greedy) approach. Always take the time to step back and think of how you can simplify a piece of code. Learn techniques like the ones presented in this talk and try to always be on the lookout for when you can apply them in appropriate situations.
**Skippable**: No

* [Stop Writing Classes - Jack Diederich](https://youtu.be/o9pEzgHorH0)
A small little talk that shows examples of overuse of the object-oriented style with frivolous classes and how to refactor them into functions.
**Major takeaway**: About to write a new class or method? Think about if you really need that level of abstraction and what you are trying to acheive with it. Maybe a function is enough. Note: we are not talking about dataclasses in python or structs in C.
**Skippable**: Yes if you've already seen all the other talks.

* [The Fun of Reinvention (Screencast) - David Beazley](https://youtu.be/js_0wjzuMfc)
In this talk David uses python's many metaprogramming techniques to create wonderful datastructures and program generation tools. 
**Major takeaway**: The point of this talk is to remember to lighten up and have fun with programming, while also learning some seriously cool tricks. This talk shows the under-appreciated side of python and why it has been so successful as a DSL for datascience/machine learning. It is wonderfully pliable while still being pretty readable.
**Skippable**: Yes.
 
* [The next big Thing - Andrei Alexandrescu - Meeting C++ 2018 Opening Keynote](https://youtu.be/tcyb1lpEHm0)
In this talk Andrei describes what he calls "Design by introspection". What's being introspected here is the program itself. To give a concrete example, imagine the following implementation of `std::vector` in a pseudo C++:
  ```cpp
  struct vector<T, MAX_SIZE=INFINITY> {
    static if (MAX_SIZE < THRESHOLD) {
      // allocate vector on stack
      T m_buffer[MAX_SIZE];
    else 
      std::size_t m_size;
      T* m_buffer;
      T* m_end;
      // allocate vector on heap
  }
  ```
  This little piece of code lets the user specify a max size for their vector, and if it happens that the user just wants a small vector, we allocate it on the stack, saving a potential slow system call to allocate memory on the heap and keeping pointers around (this is done in many C++ libraries, known as *small vector optimization*). Note the `static if` is a compile time decision - allowing the compiler to generate essentially a new type of vector, opaque to the user.
  **Major takeaway**: Designing generic algorithms and containers can be done locally if the language gives you good metaprogramming support. Baking design decisions into the type system can make performant and less error-prone code.
  **Skippable**: Yes.

#### Functional programming
* [Category Theory for Programmers](https://bartoszmilewski.com/2014/10/28/category-theory-for-programmers-the-preface/)
In this series of blog posts (published later as a book), Bartosz gives an introduction to category theory and how it can be applied to programming in general. Category theory gives really nice primitives for design patterns that can be applied for writing well-structured datastructures and algorithms. A lot of this material is covered in Elements of Programming, so it might be a bit redundant here, but getting a more theoretical picture can be useful for some people. If you don't have the time to read everything, just read Part One.
**Major takeaway**: Building programs from precanned design patterns like monoids, semigroups or monads can be very useful if you want to build generic, reusable components who have certain guaranteed properties that mathematicians have already derived for you. The terminology used in this area can be daunting at first (maybe some weird obscurantism fetish?), but the ideas are really simple once you learn the basics.
**Skippable**: Yes


* [CppCon 2017: Juan Pedro Bolivar Puente “Postmodern immutable data structures](https://www.youtube.com/watch?v=sPhpelUfu8Q)
In this talk Juan describes the implementation and application of persistent datastructures in C++. It's a wonderful example of taking ideas used by Clojure (where all stdlib datastructures are persistent) and bringing them to a *mainstream* language. Juan builds and shows off an extremely elegant text editor implementation which uses his persistent datastrcuture library.
**Major takeaway**: Safety, security and clear reasoning enabled by functional concepts does not have to be orthogonal to performance. In fact, in certain cases it helps us disentangle messes caused by mutability, letting us write simple code which often turns out to be fast. Try to start off by writing functional, immutable code and only demote it to imperative, mutable code when you've proven that you absolutely need to.
**Skippable**: No

#### Tools

* vim
You should probably learn this editor. It will definitely pay off...eventually.
* gdb
Learn how to debug programs effectively.
* sqlite
Learn how to effectively use the relational data model (as implemented by sqlite) in your programs. Every mildly complicated program either contains sqlite or a crappy implementation of it.

#### Languages/Programming environments
Try to learn a few different languages, ideally from different paradigms. For example pick a language from each of these areas: garbage collected (like Python), compiled (like Rust), interpreted (like Clojure), in the browser (like Elm), array-like (like J or Q), managed (like Microsoft Access), pure functional (like Haskell), on the phone (like Kotlin). Obviously you shouldn't start learning all these languages at the same time, but it's good to try to "forget" what you know about programming and get a different perspective by trying different things.


##### Footnotes
<sup>1</sup> [Alexander Stepanov](https://en.wikipedia.org/wiki/Alexander_Stepanov) is a Russian mathematician/programmer known for generic programming and implementing C++ STL. 
<sup>2</sup> [Rich Hickey](https://github.com/richhickey) is an American programmer known for creating the Clojure language (Lisp+JVM). Funnily enough, he's not important enough to have a Wikipedia page.

