# It is actually systemd/Linux!

Most people who hate systemd can elaborate on why they hate
systemd. But I can.

## Privacy issues

There are a **lot** of conspiracy theories about systemd being spyware.

[systemd fallback to G\*\*gle DNS
servers.](https://isc.sans.edu/forums/diary/Systemd+Could+Fallback+to+Google+DNS/22516/) This is a very serious privacy issue.

This can be modified in the [`configure.ac`](https://github.com/systemd/systemd/blob/a083537e5d11bce68639c492eda33a7fe997d142/configure.ac#L1305) But i don't think you want to recompile systemd

BTW, why does my ***INIT*** software manage my DNS? I thought we had. emm.

* dhcpcd
* NetworkManager
* wicd
* connman

## UNIX philosophy

>\>Make each program do one thing well. To do a new job, build afresh
>rather than complicate old programs by adding new "features".

According to
[this](https://linux.slashdot.org/story/19/05/25/0538206/systemd-now-has-more-than-12-million-lines-of-code)
systemd has 1.2 million lines:


![What in the actual hell](/systemd.png)

There's also systemd-boot, systemd-crypt setup and probably much others
than **we** haven't discovered yet.

Here's a list of what systemd manages:

* [Gnome](https://blogs.gnome.org/benzea/2019/10/01/gnome-3-34-is-now-managed-using-systemd/)  
[Extra](https://github.com/dantrell/gentoo-project-gnome-without-systemd)
* [Home directories](https://www.howtogeek.com/673018/systemd-will-change-how-your-linux-home-directory-works/)
* [Encrypted disks](https://manpages.debian.org/jessie/systemd/systemd-cryptsetup-generator.8.en.html)

### X11 in systemd

Of course, [X11 was **completely**
necessary](https://cgit.freedesktop.org/systemd/systemd/tree/NEWS?id=2d1ca11270e66777c90a449096203afebc37ec9c#n783)
in PID 1

### Ever wanted to connect to a remote systemd machine (using systemd)?

[Now you
can!](https://cgit.freedesktop.org/systemd/systemd/tree/NEWS?id=2d1ca11270e66777c90a449096203afebc37ec9c#n1500)

### /etc/ bullshit

[If you run
systemd](https://cgit.freedesktop.org/systemd/systemd/tree/NEWS?id=2d1ca11270e66777c90a449096203afebc37ec9c#n1401)
with an empty /etc directory, `systemctl preset-all` (whatever that
does) is executed. to ensure a good "factory reset"

Really? I think that if someone is going to remove /etc is because a)
per's stupid or b) per's distro was already broken.

Also, why is this in the fucking init process? 

#### `systemctl` edit command
[systemctl has its own editor, which is `$EDITOR` though, pretty useless since you just removed /etc.](https://cgit.freedesktop.org/systemd/systemd/tree/NEWS?id=2d1ca11270e66777c90a449096203afebc37ec9c#n689) 
	
### systemd-rfkill
It was something really necessary! My init system controlling if my
fucking wifi card is on or off! I don't know what i would do without a
process spawned by my kernel doing this...

### Your init software manages your calendar and cron jobs

[Yeah, completely
necessary.](https://cgit.freedesktop.org/systemd/systemd/tree/NEWS?id=2d1ca11270e66777c90a449096203afebc37ec9c#n1044)

### systemd stores tempfiles in a completely sane directory!
[Literally why?
](https://cgit.freedesktop.org/systemd/systemd/tree/NEWS?id=2d1ca11270e66777c90a449096203afebc37ec9c#n1049)we
literally have /tmp and /dev/shm, fucking `systemd-tmpfiles` was completely unnecessary

### systemd does not know what FastCGI is

[Thank you systemd](https://cgit.freedesktop.org/systemd/systemd/tree/NEWS?id=2d1ca11270e66777c90a449096203afebc37ec9c#n166)

<hr> Being systemd so fucking big, it could crash in any second. And
since systemd is PID 1, if it crashes, the kernel would panic.

GNU's not UNIX! so why would it have to follow the UNIX philosophy?

Because it is UNIX like!

## Serious issues

* [You can accidentally remove /](https://github.com/systemd/systemd/issues/5644)

* [L\*nnart thinks we cannot `useradd 0day`](https://github.com/systemd/systemd/issues/6237)

* [The very necessary cryptsetup repleacement don't work](https://github.com/systemd/systemd/issues/6381)

* [They don't know how to use getopt](https://github.com/systemd/systemd/issues/1596)

## Logs

**systemctl** uses its own format (binary BTW) to logs the shit, and you have to
use **journalctl** (can't use less/more/cat/whatever) to see what's going on.

At least, there's /var/log. But not all software use that
