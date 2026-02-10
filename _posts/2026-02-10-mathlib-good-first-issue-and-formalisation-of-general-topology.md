---
title: "mathlib - good first issue and formalisation of general topology"
categories:
  - Mathematics
tags:
  - Lean
  - mathlib
  - formalisation
  - topology
  - pi-base
---

[Lean](https://lean-lang.org/) is a functional programming language and interactive theorem prover. [mathlib](https://leanprover-community.github.io/mathlib-overview.html) is its main mathematical library, by far the biggest of its kind (with over 700 contributors!). mathlib covers a wide range of mathematics, likely more than an average [undergraduate education](https://leanprover-community.github.io/undergrad.html) has to offer (though the extent of this depends on the field). This is great for several reasons! For example, mathlib thus formally verified much of mathematics and makes a great foundation for independent formalisation efforts in Lean. However there is one caveat attached to this:

There are many different ways and resources to [learn](https://leanprover-community.github.io/learn.html) Lean. However, like with any programming language, at some point any student of formalised mathematics will want to contribute something on their own, ideally to mathlib itself. The size of mathlib makes this increasingly difficult: What to do if all your knowledge of mathematics is already formalised?

- While there are still several undergraduate topics [not yet in mathlib](https://leanprover-community.github.io/undergrad_todo.html), increasingly those topics being not yet formalised is due to them being niche or difficult to formalise (i.e. matrices).
- The mathlib repository on GitHub also has an "[Issues](https://github.com/leanprover-community/mathlib4/issues)" tab. There is, like the title of this post, also a so-called "good first issue" label. However again, there aren't so many of those and most of them are of a rather technical nature and might not be so interesting for newcomers. Similarly, simply searching "TODO" in mathlib will lead to many small tasks. These are however difficult to browse properly and of vastly varying difficulty and level of technicality.
- There are many problem lists. Most famously, there exists [Freek's 100 theorems list](https://www.cs.ru.nl/~freek/100/). All of the theorems there [not yet in mathlib](https://leanprover-community.github.io/100-missing.html) are in fact difficult. More recently, there is also the [1000 theorem list](https://leanprover-community.github.io/1000.html), which is the same as the [Wikipedia list](https://en.wikipedia.org/wiki/List_of_theorems) of theorems. In my opinion, this list does not get as much attention as it should. Nevertheless, searching the list for a suitable theorem (some of the "theorems" listed there are in fact not precisely mathematical) is rather tedious, and many, if not most, of the propositions there first need additional infrastructure.
- Lastly, mathlib is not the only popular Lean repository. Google DeepMind's [formal conjectures repository](https://github.com/google-deepmind/formal-conjectures) is likely the most beginner friendly. Without much Lean experience at all, one can easily find a suitable conjecture (for example an Erdős problem) to formalise. The only downside with this approach is that the formal conjectures repository contains very few proofs, one of the main aspects of Lean.

In the formal conjecture repository, there are selected problem lists, i.e. the [Erdős problems](https://www.erdosproblems.com/) or [Ben Green's 100 open problems list](https://people.maths.ox.ac.uk/greenbj/papers/open-problems.pdf). The vast majority of PRs, especially by newcomers, are concerned with problems from such lists. Similarly, the [equational theories project](https://teorth.github.io/equational_theories/) also had a clear goal in mind.

The above observations lead me to believe a "good" way or project to introduce newcomers to collaborative projects in Lean ought to contain the following features:

- Clear goals and milestones ahead
- Mathematics that is not hard to understand
- Contains both definitions and proofs
- (Some) Easy proofs, possibilities for small PRs
- Easily browsable
- Preferably upstream-able to mathlib

I want to propose one way for this. The [pi-base](https://topology.pi-base.org/) is a database in topology. It was founded in 2014 by James Dabbs. As of writing, it contains 217 spaces, 224 properties and 838 theorems (which are implications between properties). The pi-base implicitly contains most of what general topology has to offer. It is equipped with a deduction engine, with which traits of topological spaces (which can be understood as counterexamples to theorems) are mostly automatically assigned.

I have been contributing to the project recently and by doing that it has become increasingly clear that the pi-base would greatly benefit from formalising its theorems and properties. For example, this could help spot mistakes in theorems (and thus, crucially, in the deduction engine) and help make things more precise in general.

Similarly, a formalisation of the pi-base would be a great candidate for a "good" collaborative project that newcomers can contribute to under the criteria above:

- A formalisation of all properties and theorems (and maybe even spaces) is a big goal with many milestones.
- While most people will be unfamiliar with the majority of the definitions in pi-base, once somebody knows a bit of topology, almost none of them are hard to grasp.
- Formalising properties are clearly nice definitions and implications/theorems contain proofs.
- Many of the 838 theorems are very easy, though there are also tougher ones.
- The pi-base has a good browsable website, which could easily be expanded to show what has been formalised so far.
- Upstreaming theorems and properties from the pi-base would greatly enrich mathlib's topology sublibrary

Possibly, a formalisation of the pi-base could also be aided by AI tools and might be a good way to empirically test and compare their current abilities.
