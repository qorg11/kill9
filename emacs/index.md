# Kill-9's Emacs things

Emacs (short for Editor MACroS) is a text editor[^1] made by some
weird guy in the late 70s, and had too many implementations, such as
XEmacs, Freemacs, µEmacs (microemacs). in 1984 (lmao), the GNU project ~~stole~~
rewrote the original Emacs code and the most used version of Emacs was
born: GNU Emacs.

# Installation

Windows users: <https://ftp.rediris.es/mirror/GNU/emacs/windows/> (Or their nearly GNU mirror)

Mac Users: brew install emacs, I guess.

GNU/Linux users: probably the "emacs" package on your distro's repos

BSD users:

FreeBSD: Install off of ports tree or "pkg install emacs"

OpenBSD: pkg_add emacs or ports tree

NetBSD: pkgsrc or pkgin install emacs[^2]

Plan 9 users: What are you doing here?

# Other versions of Emacs

As mentioned above, there are other versions of emacs, most of them
are obsolete (XEmacs for example).  µEmacs is the emacs version used
by Linus Torvalds[^3] I do not recommend to use it. If you want to use
a mini Emacs, you should try [Zile](https://gnu.org/software/zile) or
[Jed](http://www.jedsoft.org/jed/). Zile is stupidly minimum while Jed
has syntax highlighting and other kind of programs. But not close to
real GNU Emacs.

You can find more about Emacs on the sidebar.

# Information about Emacs

In Emacs, everything is an Emacs Lisp function, each keybinding, every

M-x function is written in Emacs Lisp, Emacs Lisp is a complete
programming language. So that's why you can see browsers inside Emacs.

In this book, I'll write the name of the function in front of a keybinding. Because they're pretty self explanatory


**Highly work in progress, please [contribute](https://gitlab.com/qorg11/kill9)**

[^1]: Some people call it a "operating system", but I prefer to call it a Emacs Lisp interpreter. 
[^2]: This won't work if you don't have pkgin installed. If you don't, use pkg_add
[^3]: <https://github.com/torvalds/uemacs>
