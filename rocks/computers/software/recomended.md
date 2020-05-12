# Kill-9 recommended computer related things

Here's a list of useful software you should install on your computer.

# Operating system

If you got up into kill-9.xyz is because you know how to install an
operating system. If you are using Windows/MacOS Install GNU/Linux.

## Recommended distros

I highly recommend [Debian](https://debian.org),
[Fedora](https://fedoraproject.org), [Gentoo](https://gentoo.org),
[Void](https://voidlinux.org), and any other distro that does not use
systemd (Debian and fedora use systemd. But it's forgivable since
they're the best distros) I do not recommend distros based on other
distros (i.e Ubuntu)

# Software

I'm not a moron. All the software can be installed on your distro's
repos. Try RPM Fusion if using fedora. If you use Gentoo. I guess you
know what's a ./configure

Now that you're using a real operating system there's some software
you should use:

Web browser -> [Firefox](https.//mozilla.org/firefox) Is the browser I
use. Remember to [configure](/guides/firefox/) it.

## Pandoc

Pandoc is an universal any markup language to any markup language
converter (Kill-9 uses Pandoc to convert from Markdown to HTML)

Usage is very simple: ```pandoc input.md -o output.pdf``` And that
converts from markdown to pdf. It can use beamer and other stuff. Be
sure to check the manual. LaTeX options can be passed in yaml at the
top of the document.

## ffmpeg

ffmpeg is just a simple as shit video transcoder

```ffmpeg -i input.mp4 output.mp4```

## Emacs

Emacs is the "text editor" that I use. But it can do much more than
just editing text. It has its own programming language (Emacs lisp) so
you can do mostly anything with it.

## urxvt

Sucks less than gnome-terminal and st. Configured using
Xresources. check out my
[.Xresources](https://git.qorg11.net/dotfiles.git/blob/HEAD:/.Xresources)

## i3wm (or i3-gaps) (or dwm)

It's a tilling window manager (which i use) it is highly
configurable. They say that you shold dwm instead. but they're
basically the same thing. So use which is better for you

# Programming languages

## Perl

Perl is my favorite programming languages. It is the less bad listed
in harmful/software. Pretty nice to use. It rocks for text management
and web stuff (php's father)

## C 

The legendary programming language everyone should know. 

## Any LISP

They're fun to use. Remember to read your SICP.
