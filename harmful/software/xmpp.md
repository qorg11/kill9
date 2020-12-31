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

## File encryption

When you upload something using http_upload using omemo, the file is
encrypted, but using AES *symmetric* cryptography, rather than
recipient's public key and your public key. As it is symmetric
cryptography the passphrase is stored somewhere else, in this case, it
is stored **in the URI**. Meaning that if an attacker could get the
URI you've sent, they could get the file.

Obviously, this is not likely to happen because the message with the
URI is encrypted with TLS and OMEMO, but I think the file should've be
encrypted with recipient's public key.

The reason of this (i think) is that so you can use another tools to
download omemo files. Like omemo-wget.

Anyways, if you want to share files and get encrypted on-the-go you
can always use pgp.
