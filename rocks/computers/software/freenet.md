# Freenet rocks!

Freenet is a content-based anonymous network, this means, that unlike
tor, it is based only in content rather than services, you don't
need. a webserver to host a website in freenet. You only have to
insert it.

Then, when you have that website uploaded in freenet, you'll be
seeding it, other people will visit and they'll become seeders as
well! So you can turn off your computer, and the website will be still
accessible!

Any content you download will be kept in the datastore, a encrypted
file that has every content you've visited in freenet. This file is
encrypted and can be only decrypted with the keys. There are 4 types
of keys but the most important are:

* SSK: Signed Subspace Keys. For content that will change, like a website
* USK: Updateable Subspace Keys. Useful for getting the latest version of a SSK key
* CHK: Content Hash Keys, Used for static content, such as pdfs, images...



This is a freenet URL: <http://127.0.0.1:8888/USK@wA57L-2IJYwx6wOrLyKEpS6NHXRrSUXNWJNfu9T5gc4,twOe8gGJw~8~p-ICxazYTVduvS4RJZfiLUKRmRzo3so,AQACAAE/qorg/34/>

It has it scheme: http://FPROXYADDRESS:/KEYTYPE@DECRYPTIONKEY/DOCUMENT/VERSION/

Notice how freenet has "versions" this in freesites are some kind of
wayback machine. You can go to *any* version of a freesite by
modifying the URL, for example: http://127.0.0.1:8888/SSK@wA57L-2IJYwx6wOrLyKEpS6NHXRrSUXNWJNfu9T5gc4,twOe8gGJw~8~p-ICxazYTVduvS4RJZfiLUKRmRzo3so,AQACAAE/qorg-1/ 

That will take you to the first version of my freesite

There are some plugins to Freenet, like Frost or Sore, which enables
social media over freenet.
