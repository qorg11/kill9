# Lisp in emacs

### This page is subdivided into 2 sections, as there are 2 lisps which really shine when developing in Emacs [^1]

# Pre-everything else:

Install [Paredit](https://www.emacswiki.org/emacs/ParEdit), [Smartparens](https://github.com/Fuco1/smartparens), or [Lispy](https://github.com/abo-abo/lispy). You can find documentation for these somewhere on the internet[^2], or some other place.


# Scheme

Install geiser and run it with the Scheme implementation of your choice. If you cannot eval a file, press C-c C-s inside of that file and choose the Scheme implementation you chose.

# Common Lisp

Install [SLIME](https://github.com/slime/slime) or [SLY](https://github.com/joaotavora/sly)[^3] and configure them.

Configuring SLIME:

Add this to your config file
```
(load (expand-file-name "~/quicklisp/slime-helper.el")) ;; If you're using quicklisp
(setq inferior-lisp-program "your-lisp-implementation") ;; Probably Clozure CL or SBCL
```

Configuring SLY:

Literally just add your inferior lisp program into your config file:
`(setq inferior-lisp-program "your-lisp-implementation")`



[^1]: The other lisp which is commonly pointed to as a good development experience in emacs, and which shall not be named, is on the JVM, and we will not be covering it here.
[^2]: Except for paredit, which I linked the documentation for as the main link.
[^3]: The creator of this article recommends SLY more than SLIME as it is a lot more modern and simpler to use.
