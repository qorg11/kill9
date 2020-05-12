# ANSI Common Lisp is a mess

Function names were written by a monkey

(terpri) <- meaning terminate print line

(princ) <- why not (print)?

## Variables

In [Scheme](https://kill-9.xyz/harmful/software/scheme) you can declare functions and variables with (define)
In common lisp. You can use (defparameter) (defvar) (defun) and probably much more.

~~~
;; scheme
(define x 3)
< x
> 3
(define x 4)
< x
> 3
;; ANSI Common Lisp

(defvar *x* 3) ;; * are optional though
< *x*
> 3
(defvar *x* 4)
< *x*
> 3
(defparameter *x* 4)
< *x*
> 4
~~~

Common Lisp (and any other LISP programming language) is fun to use. But can get easily confusing.
