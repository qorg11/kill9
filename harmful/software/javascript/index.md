# JavaScript and its consequences have been a disaster for the human race

>The beach is essentially shit of fish, and we humans love it, we
>humans love shit

-- Me, circa 2021

(That's why JS is popular)

OR: Manmade virus infecting the world.
JavaScript is a programming language often used on websites. To create
dynamic content on client end. Some dudes thought that extracting the
V8 (chromium javascript interpreter) and making it a executable file
to run javascript outside the browser was a good idea and now we're
doomed.

JavaScript is not only stupid (javascript returns true when) ```true +
true === 2``` Which means that true is literally ```#define true
1```. `null` is `object` for some reason...

At the end that doesn't matters. Because it's a useless fact to be
honest. It only shows how bad designed the shit is. But the pain starts
when you actually use that programming language.

# Developers idiocy

First of all the language is slow as fuck. And websites are BLOATED of
JavaScript nowadays. Adding ***USELESS*** function i'd never like to
use, or functions I already disabled on my browser. Such as smooth
scrolling. I hate smooth scrolling. But some websites force me to use
it because JavaScript.

Not to mention the fucking thing runs like shit because developers
don't really know how to write this abyss programming language. For
example, In a good browser (pale moon), Javascript runs like shit
(IT'S A FEATURE). No I mean, literally, Tweetdeck runs 100 times
better than fucking regular twitter.com.

And remember, if you use a good browser (pale moon), which has slow
javascript interpretation, haha! good luck browsing the web with
javascript enabled! it will be fucking impossible

# Idiocy examples

~~~

<true + true === 2
>true
<true == "1"
>true
<false == 0
>true
<false == "0"
>true

<'0' == 0
>true

<'\t' == 0
>true
<[] == 0
>true
<'\t' == []
>false

<false == undefined
>false
>false == null
<false

<null == undefined
>true

// I specially like this one

<[]+{}
>"[object Object]"
<{}+[]
>0

~~~

# Disabling JavaScript

Unless you only use 1.0 websites. Disabling javascript will broke your
internet experience, but will make it way faster. just install
noscript and have fun with your sane browser.

# NodeJS

Node is what happens when you extract the JavaScript interpreter from
chromium and put it on the desktop. This allows the user to execute
.js files on the desktop without a browser. Which is stupid. A web
programming language shouldn't be on desktop. Just on the web. But
thanks to this great idea we've now worse things

(Node isn't even a JavaScript implementation. It is just the V8 engine
outside the Chromium browser. Meaning that node is just a part of
chromium with marketing)

## Idiotic programmers

As JS standard library wasn't enough pain, you can create modules, as
stated before, JS programmers should not be called programmer as a
sign of respect to other programmers, for example, the
[is-even](https://www.npmjs.com/package/is-even) node module:

![](../is-even.png)

>\>200k weekly downloads

And if you look the `is-even` source code, you see this:

![](../source-code.png)

`is-even` is just a call to the `is-odd` library, okay

And then, if you go to the [module
site](https://www.npmjs.com/package/is-odd) you can see how it has
400K weekly downloads.

![](../is-odd.png)

And if you go to their [GitHub
site](https://github.com/i-voted-for-trump/is-odd). You have the honor
to see this:

![](../dependences.png)


# Syntax

The syntax was written by a gorilla, it uses camelCase, (I don't
like it, but well, i can live with it).

for example, in JS you do `document.getElementById("foobar");` I guess
this is ok, but like I said, this was written by a monkey, becuase
then we have functions: `XMLHttpRequest` <-- What the hell?  Why is
XML capitalized, but Http isn't?  A good language, let's say, C, would
have done it like this: `xml_http_request`; (which is saner)
or `XML_http_request()` if you use the weird OpenSSL functions names lol


# Electron

Electron is what happens when you hire web developers but you gotta
make the program aviable for the desktop. The problem is that
JavaScript can't do graphics (as far as I know, there's no X11 library
for JavaScript, thankfully) So what do they do to use GUIs on
JavaScript? Make every program a mini-chromium browser! So every
program that's running electron is just chromium browser. Which is
truly stupid. And a lazy way to do programming.

Here's what is needed to run a program (Written in a compiled language) in GNU/Linux:

![](C.png)

And this is what is needed to run a program written in electron:

![](Electron.png)

![](/1592614085502.png)

![](/1610633628.png)
