# Emacs isn't bloat. (n)vim is.

Remember, Nobody knows what's Emacs is, I just say it is a Lisp
machine emulator. But the GNU Project says it is a text editor. Which
is true.

Emacs is written in (src/ directory in the Emacs source tree) C and in
Lisp (lisp directory in the source tree). The C part contains the
Emacs core. Which is what Emacs need to work. The Lisp directory has
the "bloated" things. The basic functionality of the text editor (such
as (forward-char) and that kind of functions are written in C). If
thing a Emacs' feature (M-x tetris) is bloat. You can remove
lisp/play/tetris.el. And the bloat is gone.

>\>But I have to recompile to remove a feature from Emacs.

Nope. Most .el(c) files are in /usr/emacs/*/lisp. You can remove
whatever you want from there. Emacs will work without them.

Unbloating Emacs is easy, just rm -r some .el files. How easy is it to
unbloat (n)vim?

Since it is fully written in C, you have to learn it to figure out
what to delete. So Vim doesn't stop working. Then you gotta recompile.

Nvim is a (fork) of vim written in Vimscript, C and extensible in Lua.
Using an external programming language for extensions is bloat. Emacs
fixed that using its own programming language.
