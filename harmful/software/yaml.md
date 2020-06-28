# YAML makes no sense

There's a lot of ways to say true or false in YAML (21 I think). Some
of them are very inconvinient. For example

~~~
countries:
	- ES
	- DE
	- FR
	- GB
	- US
	- NO <- This isn't Norway, This is false
~~~

If you use YAML instead of literally anything else, is because you
hate the quotes in this kind of stuff. But you literally have to do
this:

~~~
countries:
	- ES
	- DE
	- FR
	- GB
	- US
	- "NO" <- Alright, not false anymore.
~~~

