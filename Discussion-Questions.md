# Discussion Questions

[Meetup event](http://www.meetup.com/newhavenrb/events/46434952/)

See also: [Russ Olsen interview on Ruby Rogues](http://rubyrogues.com/033-rr-book-club-eloquent-ruby/) (there were some questions about DPiR, from the beginning until about 6-7 minutes in, and perhaps later)

## Preface

* Regarding the C OOP analogy, Linus Torvalds is an OOP naysayer, but has made highly reliable (and maintainable?) code.  What does this say about OOP? _benjaminoakes_
  * I think it means OOP is not the only way to do it. You can write poetry in French _or_ English. _danbernier_
  * For the curious: [Panel: Objects on Trial](http://www.infoq.com/presentations/Panel-Objects-On-Trial) is supposed to be a funny but serious look at oop in general. Best point made for me is that you don't need O.O. based language to create an O.O. system. _diego_
* Is it bad to use patterns as more than a vocabulary?  Should they only be "rediscovered"? _benjaminoakes_
* Is DRY an antipattern?  Is it over-applied or often prematurely applied? _benjaminoakes_
* Is YAGNI an antipattern?  Is it over-applied or often prematurely applied? _danbernier_
* Does Ruby hide too much complexity?  Is there too much magic in, say, how mixins work?  For example, the equivalent in JavaScript is as expressive, but less "magical". _benjaminoakes_
 * What's the equivalent in JavaScript? Something like `a.extend(b)`? or do you mean the prototype object model? _danbernier_
* As an engineer, shouldn't you know how your plumbing works? _benjaminoakes_
 * Yes, but how far down? Do engineers need to understand quarks? _danbernier_
* How does the problem domain affect the use of patterns?  How about culture of an organization? _benjaminoakes_
 * I think the architecture affects it more than the problem domain. Web apps have similar patterns regardless of problem domain, and same goes for rich-client 3D simulations, rich-client GUI apps, web service layers, and language parsers. _danbernier_
* How does your organization's culture view pattern use?  Do they have a bad name (e.g. from being over-applied)? _benjaminoakes_

## Chapter 1: Intro

## Chapter 2: Overview of the Ruby language

This chapter is Ruby basics.  If anyone has any clarifying questions, we'll be happy to clear things up.

* Coming from statically typed languages like Java and C, I still don't fully understand how the ruby interpreter handles all `@instance_variable`'s.  How exactly does the interpreter pick up all of them? _Zach_
 * I'm not sure what part is unclear to you, but basically, the syntax (something like `/\b@[a-z_]+\b/`) makes them easy enough to recognize. The main difference is that Ruby lets you add new instance variables at run-time (see https://gist.github.com/1579738: first, `f` has no `@bonk`, then later, it does). Think of it like a hash, where the key is the instance variable's name, and you can add new keys. _danbernier_
  * To expand on @danbernier's explanation:  are you familiar with how `this` is bound in JavaScript?  How about `this.variable = 'value'`?  The latter is **essentially** the same idea as `@variable = 'value'` in Ruby.

## Chapter 3: Template Methods

From Wikipedia:

> The control structure (inversion of control) that is the result of the application of a template pattern is often referred to as the Hollywood Principle: "Don't call us, we'll call you."

* When have you found yourself using **Template** before? _benjaminoakes_
* When have you wished you _hadn't_ used **Template** before? _benjaminoakes_
* One thing I find tricky about the Template Method pattern is picking
  methods to "punch out" of the template, in a way that makes
  sense. If you pick strictly the things that vary, it's an effective
  solution, but it might not be the clearest; and as the code ages &amp;
  changes, you might need to refactor the lines of the template
  methods. Maybe this is an argument for keeping use of the template
  method small. I'll try to think up a good example. _danbernier_
* Is **Template** limited in its usefulness?  As @danbernier points out, it's more useful when there are fewer things that vary.  The example of `initialize` in Ruby being a hook method is one example (only one method, but look at how much you can do with it).  _benjaminoakes_
* Is Ruby's `Object` a good example of when inheritance makes sense (in conjunction with the `initialize` hook)?  If so, what does that mean for `BasicObject`?