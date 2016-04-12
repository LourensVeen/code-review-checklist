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

## Providing feedback


## References

Atwood, Jeff (2006) [Code Reviews: Just Do It](http://blog.codinghorror.com/code-reviews-just-do-it/)

Burke, Kevin (2011) [Why code review beats testing: evidence from decades of programming research.](https://kev.inburke.com/kevin/the-best-ways-to-find-bugs-in-your-code/)

McConnell, Steve (2004) Code Complete: A Practical Handbook of Software Construction, Second Edition. Microsoft Press. ISBN-13: 978-0735619678

SMARTBEAR [Best practices for code review.](https://smartbear.com/learn/code-review/best-practices-for-peer-code-review/)


