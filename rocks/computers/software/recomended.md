# Kill-9 recommended computer related things

Here's a list of useful software you should install on your computer.

# Operating system

If you got up into kill-9.xyz is because you know how to install an
operating system. If you are using Windows/MacOS Install GNU/Linux or a *BSD operating system.

## Recommended distros/BSD flavors

* Linux:

I highly recommend [Debian](https://debian.org),
[Fedora](https://fedoraproject.org), [Gentoo](https://gentoo.org),
[Void](https://voidlinux.org), and any other distro that does not use
systemd (Debian and fedora use systemd. But it's forgivable since
they're the best distros) I do not recommend distros based on other
distros (i.e Ubuntu)

* BSD:

The main 4 BSD flavors recomended by kill9 are [FreeBSD](https://www.freebsd.org), [OpenBSD](https://www.openbsd.org), [NetBSD](https://www.netbsd.org), and [DragonflyBSD](https://www.dragonflybsd.org)

They are all good for different people, but I will give a quick explanation of what they all are.

FreeBSD/DragonflyBSD: Good, reliable desktop operating systems. DragonflyBSD has lots of interesting features that make it different from FreeBSD but the best thing to do when picking out FreeBSD or DragonflyBSD is trying both to see which one is for you.

OpenBSD: Good, minimalist, secure software. OpenBSD is good if you want a suckless and very secure operating system.

NetBSD: NetBSD runs on anything. I haven't used it much but it seems like a very nice operating system and a good BSD derivative. 

I use FreeBSD and DragonflyBSD as my daily driver, because imo they are the most practical operating systems for daily use within this list, but with BSD you sort of need to try them all to find a good operating system for you. 

The only BSDs I do not recommend are BSDs such as (The now-no longer developed) TrueOS, FuryBSD, etc, as they come very bloated out of the box. Using BSDs based on others is okay (OpenBSD is technically based on NetBSD, and DragonflyBSD was a fork of FreeBSD 4.x), but do not use a BSD that is bloated as soon as you install it.

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

## Window Managers

### i3wm (or i3-gaps) (or dwm)

It's a tiling window manager (which i use) it is highly
configurable. They say that you shold dwm instead. but they're
basically the same thing. So use which is better for you

### berry, 2bwm, wmutils

The other main contributor to kill-9 (the person writing this) uses keyboard-driven floating window managers, and I recommend using 2bwm, berry, or wmutils (which isn't technically a window manager, but it's a very good way of managing windows). They are highly configurable and very good. kill-9 recommends berry, 2bwm, and wmutils for this.

# Programming languages

## Perl

Perl is my favorite programming languages. It is the less bad listed
in harmful/software. Pretty nice to use. It rocks for text management
and web stuff (php's father)

## C 

The legendary programming language everyone should know. 

## Any LISP

They're fun to use and very good languages. Remember to read your SICP.
