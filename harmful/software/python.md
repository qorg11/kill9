# Python is the worst programming language used nowadays

# Lacks everything

* No pointers.
* [No true multithreading](https://kill-9.xyz/thread.png)
* No ternary operators (no, ifes in one line are not ternary operators)
* No switch (if else if else if else if else if else if...)
* No constants
* It is a true miracle that Python has lambdas. (BTW you cannot give statements to a lambda. Which makes them very useless.)
* no goto (a well used goto is better than a horrible code)

# Versions hell

Python (Not these days) have two main versions 2.7 and 3.x. Syntax are quite different, for example:

~~~
print "Hello, I'm using a stupid programming language\n" # Python 2.7
print ("Hello, I'm using a stupid programming language\n") # Python 3.x
~~~

That means a python 2.7 code don't run on a python3 interpreter, and
python 3.0 don't run on a python2.7 interpreter.

Which is fine, but Python mantained python 2.7 for so long. It ended
support on 2020 and should not be used anymore. But [some
programmers](https://bugs.launchpad.net/calibre/+bug/1714107) do not
want to make the change.

Once, i removed python2.7 from my system (as it is obselete and should
never be used) and some python3 libraries stopped working for some
reason i don't understand.

# Mess in the filesystem

~~~
qorg@satania:/home/qorg $ xbps-query -l | grep python | wc -l
4
qorg@satania:/home/qorg $ ls -1 /usr/lib/python3.9/|wc -l
203
~~~

# Dependence hell

~~~
xbps-install poezio

python3-ply               install   -                 3.11_4                 - 
python3-pycparser         install   -                 2.20_1                 - 
python3-cffi              install   -                 1.14.5_1               - 
python3-pycares           install   -                 3.1.1_3                - 
python3-aiodns            install   -                 2.0.0_2                - 
python3-pyasn1            install   -                 0.4.8_3                - 
python3-pyasn1-modules    install   -                 0.2.8_4                - 
python3-async-timeout     install   -                 3.0.1_3                - 
python3-attrs             install   -                 20.3.0_1               - 
python3-chardet           install   -                 4.0.0_1                - 
python3-idna              install   -                 2.10_1                 - 
python3-idna-ssl          install   -                 1.1.0_3                - 
python3-multidict         install   -                 5.1.0_1                - 
python3-yarl              install   -                 1.6.3_1                - 
python3-typing_extensions install   -                 3.7.4.3_1              - 
python3-aiohttp           install   -                 3.7.4_1                - 
python3-slixmpp           install   -                 1.5.2_2                - 
poezio                    install   -                 0.13.1_3               - 

~~~ 

# Other stuff

What the hell is a \_\_main\_\_?

Python is the slowest programming language I've ever seen. It takes one second to print a help message in youtube-dl
