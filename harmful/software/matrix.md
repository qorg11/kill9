>I hosted a matrix server and explored Riot. You can tell they've
>invested a lot into the UI. There's some 'dark pattern design' going
>on too, like their "data collection dialog." They want you to
>consent. Encryption isn't on by default, and when you do turn it on
>the program prompts you to 'backup' your keys where "we'll store an
>encrypted copy of your keys on our server." There is so much push to
>harvet data from you in some way or another. For an apparently "open
>source," "private," and "federated" program there seems to be an
>insidious push to be the polar opposite. The project wants to
>eventually move away from matrix usernames to phone numbers or e-mail
>addresses to identify users.

--- [lainon](https://lainchan.org/sec/res/10513.html#q10557)

# Matrix, Riot, Element, Synapse, Vector... I don't know how it is called anymore

Hey that's first problem! nobody knows how to find your service!

Go to your search engine and look up the following:

* "Matrix"
* "Element matrix"
* "Matrix vector element"
* "Element"

See? no related results of what we're talking about..

# Servers uses HTTP for it

What the hell? Why do a completly separate server use HTTP?

I mean, XMPP uses HTTP only for file upload and that's it (Also, the
HTTP upload file server is started by the XMPP server, not like
matrix, which depends on, let's say, nginx)

# Centralization

Yeah, Matrix is a decentralized protocol in theory, but in practice,
this is different:

* Everyone has their account in matrix.org
* Everyone uses element as their client, because all the others suck

# Client is written in Electron!

What else do I have to say?

# Comparision to XMPP

| blank                | XMPP                     | Matrix                            |
|----------------------|--------------------------|-----------------------------------|
| Open protocol?       | Yes                      | Yes but no                        |
| Commercialn project? | No                       | New Vector develops Element       |
| Encryption           | OMEMO, OTR, PGP          | OLM                               |
| Monopoly Network?    | Many servers and clients | Most users use Element+Matrix.org |

# BTW, how the fuck do I setup a fucking Matrix server?

You literally can't i was trying to setup a Matrix server but i
fucking literally couldn't, why do I have to setup nginx? I mean, yes,
XMPP does also depend on Nginx but is highly optional. (just for HTTP
file upload and nothing else) but Matrix FULLY depends in HTTP
apparently.
