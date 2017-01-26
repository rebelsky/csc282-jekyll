---
title: Eboard 01  Introduction
number: 01
section: eboards
held: 2017-01-26
---
CSC 282.01, Class 01:  Introduction
===================================

_Overview_

* Preliminaries
    * Notes and news
    * Upcoming work
    * Questions
* The origins of the course.
* Course policies
* Some principles and practices.
* Example: C from K & R
* Detour: A C memory problem
* Exercise: Some simple tasks

### News / Etc.

* Welcome to "Thinking in C and *nix".
    * The course has had a variety of titles.
    * I'll use at least one more, but I'll explain more later.
* I'm Sam (or SamR)
* I'll take attendance, mostly to make sure that I know everyone's name.
* Please sign up for a Github account and send me your username.
* As seems to be the norm in this department, I'm putting together a series
  of readings for this course.  They are definitely "a work in progress".
  Nonetheless, I'd like you to read the drafts.

### Upcoming Work

* Read: [the introductory material](../readings/intro)
* Read: Raymond, chapter 1
* Do: [Simple tasks](../assignments/simple-tasks)
* Do: [*nix tools](../assignments/unix-tools)

### Good things to do

* Lots of fun dance things this weekend.
* Go to Macalester and watch the swimmers swim and the divers dive.

### Questions

The origins of the course.
--------------------------

* Sam was teaching compilers.
* Students were clueless about key issues in C and Unix, like Macros and
  Make and other things that start with 'Ma'.
* Sam now teaches them.

Course policies and procedures
------------------------------

* S/D/F course
    * Attend at least 11/13 classes
    * Be active in class when you attend
    * Do the readings
    * Try the homework (timebox)
* 1 credit course.  At least three hours per week on the course.
    * 1 hour in class.
    * 30 minutes reading.
    * 90 minutes programming.
    * 2000 minutes dealing with annoying software that doesn't work correctly
      (optional)
* I will often spend class time talking through assignments (and make 
  you talk through them)
* I will generally call on people randomly.

Some principles and practices.
------------------------------

* Testing is important!  Find ways to test.  (Automated.)
* Code style is important!  We will use the GNU C standards.
* Have fun with what you are doing!
* Automate when possible!
* Write general code.

Example: C from K & R
---------------------

```
char *
fun (char *t, char *s)
{
  while (*t++ = *s++)
    ;
  return t;
} // fun
```

What does this do?

* Keeps doing something until some error comes up.  Then returns t.
* It's a lot like `strcpy`
* `*t = *s` assigns a character.
* Issue: What about size.
* The `++` moves on to the next character.  (Use, `++` is pointer increment.)
* We are incrementing before we use it.
* `=` returns the value assigned.  When we hit `'\0'`, it stops.
* That's the end of string character.

Reflections on the world view this code represents 

* You know the underlying representation of data.
* You know about pointers.
* You like to be concise.
* You assume that the client is smart enough to pass in the correct
  parameters (e.g., that there's enough space).

Questions

* Is there a preconditions that `strlen(t) >= strlen(s)`?  
    * No!  We need to know how much data is associated with `t`, not the
      length of the current string associated with `t`.
    * `char *target = malloc(123);`
* Why don't the programmers check the preconditions?
    * It is costly to check, and they want to be efficient.  Let's assume
      our clients are competent, even though that is tradtionally a bad
      assumption.
    * If they are worried about the preconditions, but also being efficient,
      they could use `assert` or put code in a `#ifndef NDEBUG` block.
    * C does not provide a mechanism for checking how much memory is 
      associated with a pointer.
* What would you choose as the preconditions?
    * There is enough memory associated with t (or you want to do some
      stupid array overflow for nefarious means)





Detour: A C memory problem
--------------------------

Exercise: Some simple tasks
---------------------------

