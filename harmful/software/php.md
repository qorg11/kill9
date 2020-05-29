# PHP

Main references:

* [https://www.php.net/](https://www.php.net/)

Rasmus Lerdorf made PHP in 1994. He didnt know the mess he was in for.

PHP has had a rocky history since its inception. As of writing we are at stable release 7.4.6

PHP has a reputation as a language with shitty code, mostly because its so easy to write that beginners pick it up.

Owing to this is that WordPress is a super-popular easy to set up, free PHP framework for blogs. It's super customizeable because you can easily write themes and plugins using the codex reference they provide. But the whole framework is functional, not object-oriented, which makes it an absolute right pain to manage from the perspective of including modules from multiple developers. So all these plugins and themes are some-what kind of hackily written by beginners and go out of support easily. Plus there's not usually VC for them, they are just .zips uploaded to wordpress.org

So what kind of happened is that early on in history shitty (new) developers who didn't have the benefit of standards to work with went out and build like thousands of these spaghetti sites and then disappeared and left them to be maintained by people with less experience. So they all got hacked, and anyone with any brains who has to deal with it fucking hates it.

But thats not PHPs fault!! nginx and Apache come with almost out of the box support for PHP, of course people will write some really shitty code for it... and leave it for someone else to deal with. Problem since time immemorial.

And actually I think PHP didnt really support (I mean it did, support classes) object-oriented approaches early on, but since 7 support for namespacing and prefixes have really improved.

PHP has been through lots of distinct periods. I know that Zend is probably the oldest PHP framework I am familiar with - Rasmus is related to it. Zend is still getting releases! But all my experiences with it have been kind of shitty.

Symfony is another popular one, newer than Zend. They might share some packages, I'm not sure. Symfony is pretty good in my opinion - they're up to date with the latest standards.

## Standards in PHP

For a long time there weren't really standards. PHP was a pretty simple language, method names did what they said on the tin, stuff was added cause it was useful. Now we have https://www.php-fig.org/psr/ the PSR, the holy grail of PHP developers who dont want to fuck things up for the people coming after.

PSR-0 was the first (deprecated in 2014 in favour of the PSR-4) - its a standard for organizing your namespaces for classes so that with a simple script you can autoload an entire directory of classes into an application. Incredibly handy. People didnt (and some still dont) see PHP as an OO language, but it totally can be! And the benefits for treating it as such are impressive.

PSR-1 is a basic coding standard and is still in effect. Its simple stuff, like only using `<?php` to start files, use UTF-8, separate classes from code actually running in different files, StudlyCaps for classnames, etc. PSR-1 is extended with more recommendations in PSR-2 and PSR-12.

Other standards concern themselves withselves with specifying interfaces for common web developement operations - caching, HTTP request/response structures, containers, etc.

## Anyways

With standards PHP is very manageable. Symfony has written a number of packages that comply with the PSR standards, so you can get quick and easy caching and HTTP support with no trouble.

WordPress is actually manageable if you use it vanilla and manage your own themes and plugins - dont use someone elses unless you OK the source yourself.

Laravel is a popular MVC framework that is all the rage today but its really just a chunky symfony.

People have done some crazy stuff with PHP since its been around so long. Want to write your UI in PHP? http://gtk.php.net/

If you are interested in learning PHP the best tutorial is probably just the one they host on their site: https://www.php.net/manual/en/getting-started.php

and here is a simple PHP script to make an array with "Hello", "world" and loop over it and output it with spaces:

    <?php
        $my_string_array = ["hello", "world"];
        foreach ($my_string_array as $word)
            echo $word." "; // or echo "{$word} " with interpolation
    ?>

