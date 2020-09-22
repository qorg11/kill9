XMPP servers comparision
========================

Well, here I am going to compare XMPP servers. As we all know XMPP is a
descentralizeted protocol. So you can have an account in servera.tld and
your friend can have an account in serverb.tld and communicate without
problem.

The best thing to do is to setup your own XMPP server. But, obviously,
not everyone can do this. So public servers exists for some reason. In
this article I am going to compare all the XMPP public servers I\'ve
seen. What they recollect, how to register to them and stuff like that.

Trashserver.net
===============

Let\'s dig onto their [privacy
policy](https://trashserver.net/en/privacy/)!

>IP addresses of users are not logged by default. Exception: In case of
>incorrect login attempts, the IP address is logged to prevent attacks on
>accounts.

Awesome! Just be sure to type your password correctly and no IP will be
logged. Also, some clients, like Gajim, Conversations and ChatSecure
supports connecting from Tor. (By the program\'s settings. For another
client just use torsocks or something like that)

>No personal data is required for registration.

Registration is closed. So I cannot test this now.

>To keep messages synchronized across multiple devices and exchange
>messages even when two subscribers are not online at the same time,
>messages are cached on the server for up to 4 weeks.

Well, understandable. If you don\'t want to do this. You have two
options:

1.  Use OMEMO/OpenPGP/OTR
2.  Disable the logging feature in your client.

>Contents uploaded via http~upload~ remain stored on the server for 4
>weeks

If you don\'t want content to be in trashserver\'s. Don\'t upload files
to it. Or use OMEMO/PGP/OTR

Awesome! This server seems good!

>If I am required to cooperate with law enforcement authorities under
>any applicable law, information will be disclosed in accordance with the
>applicable law.

Aw, shit.

Good server. But be sure to always use OMEMO/PGP/OTR so this last point
is less harmful. Middle tier.

404.city
========

Alright what the fuck? I have to solve a ReCraptcha to create an
account? in the absolute trash it goes!

[Privacy policy](https://wiki.404.city/en/404.city:_Privacy_Policy):

>We store your contact list, connection time and current session IP
>address. To prevent spam from 02/12/2020 we save account registration
>information. We are not located on the surface of Mars and we will be
>obliged (as anyone else) to provide this data by officially confirmed
>government request in the United States or the European Union.

Alright, they store, your **IP Address** and when you connected. Don\'t
even think on creating an account here. And would give info to feds.html
**SHIT TIER**

Snopyta
=======

You have to create to enable JS to create an account. Err.

Well, but nothing else is needed! No Craptchas!

Now, in their [privacy
policy](https://snopyta.org/service/xmpp/xmpp_privacy_policy.html):

> Login credentials are stored in encrypted form and never shared with
>other parties.

Good.

>No IP adresses are stored by default on our servers. We may temporary
>enable logs which contain IP addresses if needed for debugging. These
>logs are deleted immediately after action has been taken and are kept
>for a maximum of 24 hours.

Well, you have to be out of luck for Snopyta to log your IP. Anyways,
you can always log in using Tor. I don\'t know if Snopyta gives .onion
services for their XMPP.

>Messages sent to you while you are offline are stored until you
>connect or your account is deleted.

Yeah, use OMEMO or PGP

The rest of the privacy policy is just XMPP basic stuff. High tier.

Riseup
======

Ah, the old reliable. Right?

**NO!**

Riseup has a good privacy policy. XMPP is not the exception but their
XMPP server sucks!

You cannot even [Upload
files](https://compliance.conversations.im/server/riseup.net/) to it!
Altought it does not support **A LOT** of XEPs. That all the previous
server supports. Low tier. If you con\'t care about it. Riseup has a
good privacy policy (they literally would rather to [nuke the
server](https://riseup.net/en/about-us/policy/government-faq) than
surrender to the goverment) then it is high tier.

Wait what? You're telling me that Riseup accepts non-trusted
connections?  WHAT? ABORT EVERYTHING. NEVER USE THIS

jabber.lqdn.fr
==============

Literally who XMPP server. Yes, but Digdeeper uses it.

In the registration. E-mail is optionan. Which is good, and no craptchas
are needed.

[Privacy policy](https://jabber.lqdn.fr/frequently-asked-questions/):

Messages in the server sent to someone offline are logged until sent.
Alright, as always, use OMEMO/blah blah/

>Your list of contacts (that's how xmpp/jabber protocol is working)

Well, I guess.

>The date of last connection for each account, so that we can delete
>account when they are unused for 6 months. (But we don't keep the IP
>address from where you connect.)

Well, that\'s ok.

Well, the privacy policy is ok. High tier


# Creep.im

Oh, okay! first thing we see when accessing the website is "IPs are
not logged" Good start!

You can create an account directly in the client! Awesome!

You can connect to a .onion link!

This is too good to be true.

And indeed it is. If you want to talk to someone in a creep.im
account. You'll have to solve a craptcha. Don't use creep.im if you
don't want your contacts to become your enemies. Shit tier. just for
this.

# xmpp.jp

Recaptcha for registartion. their privacy policy don't say much. Low
tier.

# Summary

Use trashserver, snopyta or lqdn.
