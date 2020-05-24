# Moving in Emacs

The Emacs cursor just says where the next character will be printed,
and such things like that, like in Vim, you can move it with the arrow
keys, but this is a bad idea since you have to move your hands to do
that.

Do this: put your hands on the keyboard in the most comfortable way
possible, they don't have to be on the home row, just comfortable
position.

Very likely, one of your fingers is near the F key, other in the P
key, and other near the B key, this are the keys you will use to move
the cursor in Emacs. But since Emacs don't have an insert mode "like
vim" you have to use a modifier key. The most common are C (Control)
and M (Meta)[^1]

The movement keys have a meaning: F meanings forward (Next character),
P previous (Previous line), B backward (Previous character) and N next
(Next line)

You can see it this way[^2]:

~~~
               C-p
				:
				:
C-b   ....   The cursor .... C-f
				:
				:
			   C-n
~~~

This is hard to use at first. but keep using it for a while and you'll
love it more than "comfortable" Vim key bindings.

If moving character by character is too slow, you can try using the
M-f and M-b to move word by word. M-p and M-n don't do anything. So
don't try it.
## Moving even faster

Sometimes you just have to go to the end or beginning of the
line. Obviously Emacs supports this. with the C-a and C-e shortcuts.

C-a goes to the beginning of the line and C-e goes to the end of the
line.

You can also go to the end or beginning of a sentence with Meta. M-e
goes to the end of the sentence and M-a goes to the beginning

Most desktop keyboards have a Page Up and previous Page Down, this
keys do work on Emacs, but they're far from the keys we normally
use. So we Emacs has it shortcut for it: C-v and M-v. C-v means next
page and M-v previous page.

While editing configuration files. You probably want to go the end of
the file and start typing, M-> will put the cursor on the last
character of the file. And M-< will put the cursor in the first
character of the file (This behaviour is the same as the Home and End
key in a website for example. In Emacs, these keys just move the
cursor to the end or beginning of the line (Like C-e and C-a)

There's a weird keybinding: C-u (Universal argument) which gives a
numeric value to the next keybinding you'll use. For example. C-u 8 C-b will do C-b 8 times.

## Exercises

Open [this](https://kill-9.xyz/emacs/introduction/.lorem) file in
Emacs and move across it (Try C-b, C-F- C-n, C-p, C-e, C-a, M-a,
M-e...)

[^1]: Meta key was a key present on very (very) old keyboards. Since
    the Meta key is missing on newer keyboards. We use left Alt
    instead. But if your keyboard (Sun Type 7 for example) has a meta
    key, you can use it instead of Alt. You can also use ESC instead
    of alt

[^2]: While reading Emacs documentation, you'll find a lot of M-* and
    C-*, M-f for example, means Meta + F, and C-f means Control + f
