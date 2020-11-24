# YAML makes no sense

There's a lot of ways to say true or false in YAML (21 I think). Some
of them are very inconvinient. For example

~~~
countries:
    - ES
    - DE
    - FR
    - GB
    - US
    - NO <- This isn't Norway, This is false
~~~

If you use YAML instead of literally anything else, is because you
hate the quotes in this kind of stuff. But you literally have to do
this:

~~~
countries:
    - ES
    - DE
    - FR
    - GB
    - US
    - "NO" <- Alright, not false anymore.
~~~

YAML can understand both tabs and spaces as indentation methods. It depends
on the implementation if they are supported and many don't support it. So
you're usually stuck working with spaces in YAML files instead of tabs.

~~~
editors:
    - vi
    - emacs
    - ed

functions:
  - read <- Here's where the parsers will get confused
  - write
~~~

If you thought indentation is a problem, you will have a bigger problem
with complex structures. Here's array colors that contains two elements.

~~~
colors:
    -
      red: valid
      hex: "FF000000"
    - cow:
      hex: none
~~~

This roughly translates to:

~~~
colors = { 
	{ red: "valid", hex: "FF000000"},
	cow = { hex: "none" }
}
~~~

YAML also decided to be special and add includes. How they work depends on
the implementation. Here's a good example on how to abuse it:

~~~
users:
    - name: Chris
      repositories: &chrisrepos
          - emacsconf
	  - dotfiles
    - name: Marie
      repositories: *chrisrepos
	  - emacsconf-improved
    - name: John
      repositories: *chrisrepos
~~~

One would guess that John has access to Chris' repositories and Marie
too with the added -improved repository but this is invalid. You need to
use <<: \*chrisrepos on the next line to append/override values. Wasted
reserved keynames for things that already exist.

YAML doesn't require you to quote your strings which should result in
simpler writing for humans. But here's some weird cases where this results
in parsing problems. Try to guess how many of these are strings and how
many are integers.

~~~
value1: 42423
value2: +0x_324_bad
value3: -9_90_99_0:39:1
value4: -0_
value5: 0_0_0_0_0
~~~

If you guessed all, you are right. YAML allows all kinds of things in
integers to make it more readable to humans and to make implementations
more complicated.
