# roff is a good typewriter

UNIX is the least bad operating system that i've used. UNIX comes with
lots of tools that can help you to do many things. One of those useful
things is the roff document formatter. There's also the GNU
implementation of roff called "groff". They do basically the same.

Only a mentally deranged person would use roff in its own, so they
created macros to make groff easier, I use ms and mom
macros, depending on what I'm trying to accomplish. ms macros are
mostly used for manpages and mom macros for other stuff.

This is an example of a nroff document:

~~~
.TL
"This is a title"
.AU
qorg11

.NH
This is a numbered heading

.PP
This is a paragraph, lorem ipsum blah blah blah blah blah blah

.SH
This is a subheading

~~~

You can read the document in the terminal like this: `nroff -ms <
file.ms`

Or you can use groff to convert it to ps/pdfs: `groff -ms -Tpdf <
file.ms > output.pdf`

You can change the -T flag to other outputs like html or ps.

# Supports for other things

You can preprocess roff documents to give them support to do more
things, such as Unicode (using `preconv`) and equations supports (using
`eqn`). Here's an example:

~~~
.TL
This is another document
.AU
qorg11

.NH
This is a numbered header

.EQ
4 sup 2 = 16
.EN

.EQ
a sup 2 over 2
.EN
.EQ
x = {
b +- sqrt {-b sup 2 - 4ac}
} over 2a
.EN

.EQ
Spurdo -> N,N-DMT
.EN

.PP 
This thing contais unicode ñññ áéíóú
~~~

If you compile it like the last document, you'll see weird stuff that
has nothing to do with what you have written. So you have to use the
preprocessors. So compile it like this: `preconv <file.ms |eqn | groff
-ms > file.ps`


# TODO

* Talk about mom macros

