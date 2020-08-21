# Signal considered harmful

Signal claims to be a ultra private instant messenger. It encrypts the
messages and there's no central server. Or is there?

Let's find out!

# Distribution

Signal always struggled with which should be the most easy thing (and
mandatory if you want users to use your thing) the distribution.

Being Signal Android/The Apple Garbage software, it should be
distributed in their respective stores. In Android, you can use
F-Droid. But Signal discourages getting Signal from F-Droid.

G\*\*gle Play Services are literally botnet. They allow software to
run in the background (for things like notifications). They also allow
the software to update in the background. Basically, G\*\*gle play
services is a rootkit, that allows \<thing\> to do anything with your
phone. Without you knowing!

For the longest time, **Signal would not work without *G\*\*gle Play
Services*** Thankfully, this is fixed since 2017, and Google Play
services are not longer needed.

**BUT** if you go to signal.org->get signal->Android **will redirect
you to G\*\*gle Play**

## F-Droid

F-Droid is a repository that only gives you Free (as in freedom (and
as free beer)) software for Android.

Moxie [Don't want to use F-Droid as official way of
distribution](https://github.com/signalapp/Signal-Android/issues/127#issuecomment-13335689)
because it does not allow auto-updating. Auto-upgrades are
harmful. And we all know that.

F-Droid supports upgrades. They're just manual. Android sucks and you
cannot do like `xbps-install -Su` to verify and upgrade all your
packages. You have to install the APKs one by one.

But the thing here is that F-Droid **supports** upgrades!

Moxie also claims that APKs could not be verified in another
store. This is [not
true](https://f-droid.org/en/docs/Signing_Process/).

Moxie could setup his own F-Droid repository (it's easy as crap). But
Signal cared more about important features that security-wanting
users. Such as [Emoji
reactions](https://signal.org/blog/more-reactions/) or [Animated gif
search, using 3rd party
websites](https://signal.org/blog/signal-and-giphy-update/)

## Direct APK download

Anyways, You can [Download the apk from the official signal website
](https://signal.org/android/apk/) but I had to use my search engine
to find this. So this is hidden as shit. Also, **it encourages to
download signal from G\*\*gle Play**

And the way to verify it is using `keytool` (whatever that is (I also
had to use my search engine to see that the hell that is))

To verify the file. I had to unzip the apk (what?), get to the
META-INF folder, and use keytool to verify.

Why don't just use `.sig` files to verify things? (Like any other Free
Software does with their binaries and source packages? (Also, every
sane repository does this with RSA))

Also: A checksum **IS NOT** a signature. Your local fed can break onto
your server, put a backdoored APK, and change the signatures. What a
fed cannot do though is to sign that backdoored APK with your PGP key,
because you need the private key to sign. Also the passphrase in any
sane implementation of OpenPGP, BTW F-Droid signs the packages
automatically.

## Centralization

Signal claims to be a P2P messenger, this is true I guess. But what is
not true is that the whole system is P2P. It has **centralized
servers**

Where does Signal stores your phone number, so you can use your
account in multiple clients? How do i get information about my
contact? Yup, they're stored in Moxie's servers!

Signal should be federated. Basically a federation are like email,
Lain can send an email from lainswebsite to qorg, whose email is at
vxempire.xyz, and nothing says you cannot do that.

I should be able to setup my own Signal server, in my own hardware. So
I'm in control of the logs and data. I can also let my friends to use
my server. And this server should be able to communicate to the
official signal servers.

BUT Moxie forbids this. Your fork of Signal cannot use the official
Signal servers. Because servers are not federated. This means that
Signal Fork's users cannot talk to official Signal users. No fork of
Signal will ever have any large user base.

Your Signal fork, also, can't have the name "Signal" on it. Because
that makes [Moxie
angry](https://github.com/LibreSignal/LibreSignal/issues/37#issuecomment-217211165)

# Why is Signal recommended by security experts then?

Because they're trying to convince computer novices to use a secure
IM, you know, I don't expect my grandmother to setup her own XMPP
server. But I can expect her to use Signal since it is made for novices.

# Conclusion

XMPP does not have any of these problems.

Okay, Signal is good, but the things we have talked about here is not
what you expect from a "security focused" program. The chat itself is
P2P, and that's good. Also it is encrypted. So if you have to choose
between \<big corporate owned IM\> and Signal, choose Signal.

Did I mention it needs phone number to work?
