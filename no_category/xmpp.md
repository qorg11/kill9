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

I am **NOT** going to dig into terms of service. Only privacy. 

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
even think on creating an account here. And would give info to feds
**SHIT TIER**

Also, the website is cuckflared

on top of that, <xmpp://nuegia.net> admin sent a text to me:

>404.city has more problems than you specified. For one, choosing an
>account on 404.city is actively harmful to the federation as you are
>unable to send messages or contact 404.city users unless they add you
>to your roster first. Even worse 404.city users are not notified when
>someone trying to contact them has been blocked. The message is just
>dropped from their perspective.

>the operator of 404.city is notoriously hard to contact, in fact his
>domain he used for contact, faceless.city no longer exists. Sometimes
>the operator pops up in the XSF operators chat, other times i have to
>ask around in general for someone who knows him to ping him for me.

>the operator of 404.city is not very responsive to issues, and almost
>always will blame you for making a mistake when you contact them about
>a service or interoperability issue until you explain it 3 times over
>with XML traces what's going on and why it's their problem not mine.

>To top this all off, the service is unreliable, frequently having
>outages and is laggy. Responses to and from the server even if your an
>external user connecting to a muc there are SECONDS behind on transaction

The first paragraph is the most harmful in my opinion, because XMPP is
good because it's a federation. But 404.city breaks the federation by
only allowing contacts to message you **Remember that they keep the
contact list**. So they fucking **literally** know who you talk to. In
other servers you can make the server admins don't know who you talk
to by just texting them, instead of adding them to contacts, but
404.city makes this not possible.

I don't know what he mean by faceless.city does not exist. It exist
but it is cuckflared (and a non-existing website is better than a
cuckflared one)

But when he mentions that the operator is impossible to contact,
that's true, partly because [He](/404fail1.png) [don't
know](/404fail2.png) [English](/404fail3.png)

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
you can always log in using Tor. They also provide a .onion address
for XMPP.

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

# yax.im

Yaxim is a XMPP client for Android, which also gives us a XMPP server:

[Privacy policy](https://yaxim.org/yax.im/privacy/):

**Information Associated with your Account**

>The IP address of your registration and of your last login are stored
>alongside the account. This is required to detect and delete spammer
>accounts (Art. 6.1f). IP addresses and Jabber IDs of identified
>spammer accounts will be shared with other server operators to
>prevent further abuse.

Well, storing the IP address is not a good start. You can use Tor for
this.

**Server logs**

>IP Address and timestamps

Okay, they can see when you log. ehh

Well, the server is OK. but there are better alternatives. Middle tier

# xmpp.jp

Recaptcha for registartion. their privacy policy don't say much. Low
tier.

# e2e.ee

>How can we figure out who you are? We can’t.  
>Will we ever share data about you with others? No! We don’t know who your are.  
>Do you control the chats and data you place on this server? Yes! You can delete them at your discretion.  

Seems nice! 

>e2e.ee uses IP information to ensure that the service is not
>abused. IP addresses are recorded for the following objectives:

>Allow the creation of one account per IP address every 6 hours IP
>Addresses are recorded on the webiste for these reasons only. The
>records expire and are deleted from the server continuously, always
>within 6 hours.

/!\\ IP address are logged /!\\ But at least they're deleted within 6
hours.

Also

>An XMPP ID, also known as a Jabber ID, is never associated with an IP
>address.
Which is good

>Prosody XMPP Server logs IP addresses when a login fails. This
>information is used to keep accounts safe from brute force
>attacks. Prosody XMPP Server never logs IP addresses in association
>with actual XMPP IDs.

Like with trashserver, don't input a bad password. And prosody never
logs IP addresses.

Well, their website could have better IP address logging. Middle-High tier.

Then i realized I cannot register in my IP because "fraud IP address"

Then I tried in Tor, I also couldn't because "Proxy address". What a Joke. Low tier.

# sum7.eu

This is the community which developed conv6ations, thanks guys! But
they also let you use sum7.eu as XMPP server. when you go to
<https://sum7.eu> their privacy policy link says "Privacy policy: we
save nothing!"  

>We do not use external services like GoogleAnalytics, external fonts
>or GoogleMaps.

So far, so good... So what?

But now we have this:

>From your Website request is only saved:
>Address Family: IPv4 or IPv6
>Requested Domain: e.g. chat.sum7.eu
>Duration of delivery: How long a request take time (in histogram cumulated in buckets)

Thought you guys didn't send anything!

>For easy use, there is Message Archiving enabled by
>default. Hopefully you use OMEMO or you should disable MAM. Otherwise
>your messages are stored plain on this server for other clients.

Yeah, use OMEMO and disable MAM, as always

>HTTP-Uploads are stored for 7 days before it will be deleted
>automatically. Accounts after 1 year unused will be deleted.

Good.

I mean, sum7 didn't give a lot of info, although you create an account
directly from the client. Idk if you can create it through Tor
(probably you can). idk, middle/high tier.

# Summary

Most servers have their flaws. Snopyta requires an email to
register. You cannot register in trashserver nowadays. lqdn does not
support http\_upload

The best thing you could do is
Trashserver->Snopyta->sum7->yaxim->e2eee->lqdn

Don't bother with 404.city it is shit tier.

You should ***ALWAYS*** use OMEMO/PGP to protect your messages. And
connet through Tor if possible. Some clients support giving a
hostname. You put the .onion as hostname. But the regular domain as
Jabber ID. Something like this:

![Jabber XMPP onion](/1601114222.png)
