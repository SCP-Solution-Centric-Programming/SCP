# SCP
Solution Centric Programming

A lot of our biases are based on the state of 1960s hardware.

Today, it is much, much cheaper to build syntaxes than it used to be, and, our hardware runs much, much faster. For example, I built a [REPL](https://www.youtube.com/watch?v=YWXIf1Oc13Y) for development using 4 threads with JSON strings as the IPC format. It runs in the blink of an eye. 

The state of our hardware (and our problem spaces) has changed so much that it is time for a re-think / upgrade / upward-abstraction. The workflow we've got is based on old-fashioned ideas about what we need. We no longer need to make incremental improvements to  1960s development workflows, replete with time-sharing, function-based restrictions on thinking, etc.

To explore these ideas, three subdirectories containing mostly markdown files and subdirectories, have been created:
- WHWG/
	- README.md
	- Atoms/
		- Atoms.md
	- Tools/
		- Tools.md
	- Antipatterns/
		- Antipatterns.md
- WDWH/
	- README.md
	- What Don't We Have?
- Combinations/
	- README.md
	- new workflows

I suggest that brainstorming and discussions take place in Discord, in the 'ps' server on the 'solution-centric-programming' channel (invitation: https://discord.gg/65YZUh6Jpq). [I don't know what other options might be better. Suggestions welcome.]

Then, when ideas coalesce, PR's be submitted to this repo in the form of markdown files and/or code.

# Summary
We started out with biases driven by punch-card, teletype, efficiency mentality[^eff].

[^eff]: Slow hardware in the early days of computing produced an overabundance of concern for "efficiency" that continues to this day. Current-day (2025) hardware is much faster, we might expend our brain-power on how to build better tools for ourselves (better tools for developers --> better tools and larger selection of tools for non-programmers).

Over 50+ years we have come up with many interesting techniques that augment and build upon the old biases.

Should we push the reset button and treat our existing tools as substrates for new ways to think about the concepts of programming?

## Step 1
Make a list of the good things / techniques / ratholes that we've learned about in the last 50+ years.

## Step 2
Examine whether an existing language can be used to directly support or implement each of the good parts.

Currently, I'm thinking that Javascript might be a good choice. It is ubiquitous and runs on browsers on everyone's machines. Maybe WASM will come into play. I don't know enough yet and expect to learn as I go down this path - via comments or help from others.

Javascript's drawback is that it is difficult for humans to write code in. But, so is assembler. "*T2t*" techniques[^t2t] make it possible to create many little DSLs - SCNs - that can create Javascript code, without requiring humans to use Javascript directly.

[^t2t]: t2t means "text to text" transpilation. Just raw rewriting of incoming text to some other text. For example inhaling a new language and transpiling it to legal, runnable code in some existing language, like Javascript, Python, Odin, etc. This is a powerful technique, yet it sounds to be "too simple" for practical use. I've been using *t2t* for several years and have found it not to be wanting. Even for big projects. I've written a full-blown version of 0D in a VHLL (called "rt") and transpile the code, simultaneously, to Python, Javascript and Common Lisp. I would make it transpile to WASM, but, I don't know enough about WASM to be comfortable with it. I imagine someone else could build a WASM rewrite spec (.rwr) more quickly/easily than I can. We've generated Odin code in this way, too, so I know that this technique extends to non-GC languages. I just haven't bothered to create a *.rwr* file for rt-to-Odin]

Javascript has the advantage that it comes with a built-in compiler - *eval()*. Programmers are taught not to use *eval()*, yet, they are told to use compilers. A Javascript compilers is *eval()*. *Eval()* is a Javascript compiler. The reason that *eval()* is to be avoided is not that *eval()* itself is bad, but, that the ability to leak the use of  *eval()* to end-users is bad. It's like allowing end-users to recompile any part of your code at whim, and, it allows applications to inhale just about any garbage from the internet or end-users and to try to compile the garbage and to run the garbage. *Eval()* is powerful, but its use needs to be restricted. SCNs can do that kind of thing - there is no need to vanquish *eval()* for legitimate uses.

# What Is Programming?
Programming is the act of creating atomic operations for abstracting automatable solutions to problems and techniques for creating recipes of such atomic operations. 

# Seeding New Approaches
[from a substack article, brainstorming SCP](https://programmingsimplicity.substack.com/p/solution-centric-programming?r=1egdky)
We explored how this principle led us from single-machine programming to **Solution Centric Programming** (SCP), which treats hundreds of small computing devices (Arduinos, sensors, actuators) as **new atomic operations** for automating specific problems, requiring **new recipe techniques** for combining them. Unlike traditional programming that forces all code through one paradigm, SCP enables **computational diversity** by letting each distributed node use the most appropriate programming paradigm (Forth for real-time control, Prolog for logic, FP for data processing, OOP for state management) as specialized atomic operations, while connecting them through pure data flow rather than restrictive function calls that impose control flow protocols. The key architectural insight is **Solution Centric Program Choreography** - a hierarchical tree structure where parent nodes contain the recipe logic for coordinating child atomic operations, eliminating peer-to-peer coupling that destroys scalability. This creates a new abstraction layer where solutions are choreographed through structured data flow between specialized atomic operations, each autonomous in their execution but coordinated through hierarchical recipes rather than lateral negotiation - representing the next evolutionary step in programming's fundamental cycle of creating atoms and recipes.