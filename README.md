mtest
=====

Simple macros for simple testing in (Typed) Racket.

Currently rackunit functions like check-equal?
or check-true in a Typed Racket module (#lang typed/racket)
lose source location when reporting test failures. There
may be some simple fix to the typed/rackunit interface to fix this.
Until that fix is discovered, these macros are useful for work in 
Typed Racket (at least for me).

Example:

```Racket
#lang typed/racket

(require mtest)

(chk (not #f))
(chk 42 (* 2 21)) ; uses equal
(chk-eqv? 42 (* 2 21))
(chk-eq? 42 (* 2 21))
(chk~ (not #t))
```
