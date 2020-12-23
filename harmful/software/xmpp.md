# XMPP considered harmful

* XEPs are a mess
* They're still trying to say "We are better than ICQ"
* [Useless XEPs](https://xmpp.org/extensions/xep-0277.html)
* XML
* All clients could be a LOT better

# OMEMO

OMEMO is the (one of the) encryption thing(s) for XMPP, as any thing
for encryption, you have to verify the other person's you're talking
to keys, most client verify *new* keys **automatically**, and no one
really cares. This means that if a fed (or anyone) breaks into your
friend's account, you'd think that you're talking to your friend, with
encryption, but it's a fed, your client just signed all the new keys
by default

thankfully, new clients are adding some "verified" keys, and it will
warn you when a message was send from an untrusted key, or you'll
simply won't recieve messages from untrusted keys

