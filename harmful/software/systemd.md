# It is actually systemd/Linux!

## Privacy issues

There are a **lot** of conspiracy theories about systemd being spyware.

* [systemd fallbacks to G\*\*gle/Cloudflare
DNS](https://github.com/systemd/systemd/issues/12499) Which,
obviosuly, don't respect privacy.  systemd also use g\*\*gle's ntp
server to get the time. Meaning that systemd will phone g\*\*gle if it
can't access to the default server.

## UNIX philosophy 

>\>Make each program do one thing well. To do a new job, build afresh
>rather than complicate old programs by adding new "features".

According to
[this](https://linux.slashdot.org/story/19/05/25/0538206/systemd-now-has-more-than-12-million-lines-of-code)
systemd has 1.2 million lines:


![What in the actuall hell](/systemd.png)

There's also systemd-boot, systemd-cryptsetup and probably much others
than **we** haven't discovered yet.

Here's a list of what systemd manages:

* [Gnome](https://blogs.gnome.org/benzea/2019/10/01/gnome-3-34-is-now-managed-using-systemd/)
  [Extra](https://github.com/dantrell/gentoo-project-gnome-without-systemd)
* [Home directories](https://www.howtogeek.com/673018/systemd-will-change-how-your-linux-home-directory-works/)
* [Encrypted disks](https://manpages.debian.org/jessie/systemd/systemd-cryptsetup-generator.8.en.html)


Being systemd so fucking big, it could crash in any second. And since
systemd is PID 1, if it crashes, the kernel would panic.

GNU's not UNIX! so why would it have to follow the UNIX philosophy?

Because it is UNIX like!

## Logs

**systemctl** uses its own format (binary btw) to logs the shit, and you have to
use **journalctl** (can't use less/more/cat/whatever) to see what's going on. 

At least, there's /var/log. But not all software use that
