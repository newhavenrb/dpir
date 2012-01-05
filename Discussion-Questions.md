# Discussion Questions

See also: [Russ Olsen interview on Ruby Rogues](http://rubyrogues.com/033-rr-book-club-eloquent-ruby/) (there were some questions about DPiR, from the beginning until about 6-7 minutes in, and perhaps later)

## Preface

* Regarding the C OOP analogy, Linus Torvalds is an OOP naysayer, but has made highly reliable (and maintainable?) code.  What does this say about OOP? _benjaminoakes_
* Is it bad to use patterns as more than a vocabulary?  Should they only be "rediscovered"? _benjaminoakes_
* Is DRY an antipattern?  Is it over-applied or often prematurely applied? _benjaminoakes_
* Does Ruby hide too much complexity?  Is there too much magic in, say, how mixins work?  For example, the equivalent in JavaScript is as expressive, but less "magical". _benjaminoakes_
* As an engineer, shouldn't you know how your plumbing works? _benjaminoakes_
* How does the problem domain affect the use of patterns?  How about culture of an organization? _benjaminoakes_
* How does your organization's culture view pattern use?  Do they have a bad name (e.g. from being over-applied)? _benjaminoakes_

## Chapter 1: Intro

## Chapter 2: Overview of the Ruby language

This chapter is Ruby basics.  If anyone has any clarifying questions, we'll be happy to clear things up.

## Chapter 3: Template Methods

* One thing I find tricky about the Template Method pattern is picking
  methods to "punch out" of the template, in a way that makes
  sense. If you pick strictly the things that vary, it's an effective
  solution, but it might not be the clearest; and as the code ages &amp;
  changes, you might need to refactor the lines of the template
  methods. Maybe this is an argument for keeping use of the template
  method small. I'll try to think up a good example. _Dan_
