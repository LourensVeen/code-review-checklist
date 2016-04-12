# Code reviews

## Introduction
At the eScience Center, we value software quality. Higher quality software has
fewer defects, better security, and better performance, which leads to happier
users who can work more effectively.

Code reviews are an effective method for improving software quality. One
source suggests that unit testing finds approximately 25% of defects, function
testing 35%, integration testing 45%, and code review 55-60% [REF McConnell; ]. While that
means that none of these methods are good enough on their own, and they should
be combined, clearly code review is an essential tool here.

Aside from having fewer angry users, code review also improves the development
process. By reviewing new additions for quality, less technical debt is
accumulated, which helps long-term maintainability of the code. Reviews allow
developers to learn from each other, and spreads knowledge of the code around
the team. It is also a good means of getting new developers up to speed.

The main downside of code reviews is that they take time and effort. In
particular, if someone from outside the project does the reviewing, they'll
have to learn the code, which is a significant investment. Once up to speed,
the burden is reduced significantly however, and the returns include a much
smaller amount of time spent debugging later.



## Approach

It's important to distinguish between semi-formal code *reviews* and formal
code *inspections*. The latter involve "up to six participants and hours of
meetings paging through detailed code printouts" [REF smartbear]. As this
extra formality does not seem to yield better results, we limit ourselves to
light-weight, informal code reviews.



## Process

We haven't yet decided on how to integrate code reviews into our working
process. While that gets hashed out, here is some general advice from various
sources and experience.

- Review everything, nothing is too short or simple

- Try to have something else to do, and spread the load throughout your
working day. Don't review full-time.

- Don't review for more than an hour at a time, after that the success rate
  drops quite quickly
- Don't review more than 400 LOC at a time, less than 200 LOC is better
- Take the time, read carefully, don't review more than 500 LOC / hour


## Prerequisites



## Tools



## Review checklist

This section provides two checklists for code reviews, one for the whole
program, and one for individual files or proposed changes. In all cases, the
goal is to use your brain and your programming experience to figure out how
to make the code better. The lists are intended to be a source of inspiration
and a description of what should be best practices in most circumstances, not
a bureaucratic artifact. Some items on this list may not apply to your project
or programming language, in which case you should disregard them. You may not
agree with some of the items on this list, in which case we'd like to see an
issue or a pull request. Likewise if you have something to add.


### Excluded from this checklist

The following items are part of a software quality check, but are better done
by an automated tool than by a human. As such, they've been excluded from this
checklist. If tools are not available, they should be checked manually.

- Coding conventions (e.g. PEP 8)
- Test coverage


### Program level checklist

Here is a list of things to consider when looking at the program as a whole,
rather than when looking at an individual file or change.

(TODO: look at how this interacts with the eSTeP checklist)

#### Documentation

Documentation is a prerequisite for using, developing and reviewing the
program. Here are some things to check for.

- Is there a description of the purpose of the program or library?
- Are detailed requirements listed?
- Are requirements ranked according to MoSCoW?
- Is the use and function of third-party libraries documented?
- Is the structure/architecture of the program documented? (see below)
- Is there an installation manual?
- Is there a user manual?
- Is there documentation on how to contribute?
  - Including how to submit changes
  - Including how to document your changes

#### Architecture

These items are mainly important for larger programs, but may still be good
to consider for small ones as well.

- Is the program split up into clearly separated modules?
- Is there a clear, hierarchical / layered, dependency structure between
  these modules?
  - If not, modules should be rearranged, or it may make more sense to combine
    heavily independent modules
- Can the design be simplified?

#### Security

If you're making software that is accesible to the outside world (e.g. a web
application), then security becomes important. Security issues are defects,
but not all defects are security issues. A security-conscious design can help
mitigate the security impact of defects.

- Which modules deal with user input?
- Which modules generate output?
- Are input and output compartmentalised?
  - If not, consider making separate modules that manage all input
    and output, so validation can happen in one place
- In which modules is untrusted data present?
  - The fewer the better
- Is untrusted data compartmentalised?
  - Ideally, validate in the input module and pass only
    validated data to other parts

#### Legal

"I'm an engineer, not a lawyer!" is an oft-overheard phrase, but being an
engineer doesn't give you permission to ignore the legal rights of the
creators of the code you're using. Here are some things to check. When in
doubt, ask your licensing person for advice.

- Are the licenses of all modules/libraries that are used documented?
- Are the requirements set by those licenses fulfilled?
  - Are the licenses included where needed?
  - Are copyright statements included in the code where needed?
  - Are copyright statements included in the documentation where needed?
- Are the licenses of all the parts compatible with each other?
- Is the project license compatible with all libraries?


### File/Change level checklist

When you're checking individual changes (e.g. pull requests) or files, the
code itself becomes the subject of scrutiny. Depending on the language, files
may contain interfaces, classes or other type definitions, and functions. All
these should be checked, as well as the file overall:

- Does this file contain a logical grouping of functionality?
- How big is it? Should it be split up?
- Is it easy to understand?
- Can any of the code be replaced by library functions?

#### Interfaces
- Is the interface documented?
- Does the concept it models make sense?
- Can it be split up further? (Interfaces should be as small as possible)

Note that most of the following items assume an object-oriented programming
style, which may not be relevant to the code you're looking at.

#### Classes and types

- Is the class documented?
- Does it have a single responsibility? Can it be split?
- If it's designed to be extended, can it be?
- If it's not designed to be extended, is it protected against that? (e.g. final declarations)
- If it's derived from another class, can you substitute an object of this class for one of its parent class(es)?
- Is the class testable?
    - Are the dependencies clear and explicit?
    - Does it have a small number of dependencies?
    - Does it depend on interfaces, rather than on classes?

#### Function/Method declarations

- Are there comments that describe the intent of the function or method?
- Are input and output documented? Including units?
- Are pre- and postconditions documented?
- Are edge cases and unusual things commented?
    
#### Function/Method definitions

- Are edge cases and unusual things commented?
- Is there incomplete code?
- Could this function be split up (is it not too long)?
- Does it work? Perform intended function, logic correct, ...
- Is it easy to understand?
- Is there redundant or duplicate code? (DRY)
- Do loops have a set length and do they terminate correctly?
- Can debugging or logging code be removed?
- Can any of the code be replaced by library functions?

#### Security

- If you're using a library, do you check errors it returns?
- Are all data inputs checked?
- Are output values checked and encoded properly?
- Are invalid parameters handled correctly?

#### Tests

- Do unit tests actually test what they are supposed to?
- Is bounds checking being done?
- Is a test framework and/or library used?



## Providing feedback



## References

Atwood, Jeff (2006) [Code Reviews: Just Do It](http://blog.codinghorror.com/code-reviews-just-do-it/)

Burke, Kevin (2011) [Why code review beats testing: evidence from decades of programming research.](https://kev.inburke.com/kevin/the-best-ways-to-find-bugs-in-your-code/)

McConnell, Steve (2004) Code Complete: A Practical Handbook of Software Construction, Second Edition. Microsoft Press. ISBN-13: 978-0735619678

SMARTBEAR [Best practices for code review.](https://smartbear.com/learn/code-review/best-practices-for-peer-code-review/)


