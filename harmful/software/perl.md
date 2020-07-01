# Perl has shitty stuff

Perl functions fucking sucks

~~~
sub pile_of_crap
{
	my $x = shift; # $x is 3 if pile\_of\_crap(3)
	# do something with $x
}
~~~
Why can't it be normal?

>\>inb4 bash

~~~
sub pile_of_crap(my $x)
{
	# do shit with $x;
}
~~~

### $ @ % &

Those symbols (altough they aren't confusing) are useless: for example

remember this:

* $: Scalars, numbers or strings (or references)
* @: Arrays
* %: Hashes, associative arrays

~~~
my @array = qw(hello this is an array);

# How would you print the first element? print @array[0]? haha!

print $array[0]; # prints hello
~~~

That's right! you converted from an array to a scalar (it makes sense
though, but it's VERY confusing)

same thing with hashes:

~~~
my %hash = qw(qorg asshole lain cute_hacker);

print $hash{qorg} # prints asshole
~~~

Again, that's right! you converted a motherfucking associative array
into a fucking scalar (again, makes a lot of sense when you think
about it, you're getting only a string, but it can be VERY confusing)

### There is more than one way to do it

And that's based tbh

Before, i defined an array and a hash using qw, because its a lot
easier than do this:

~~~
my @array = ('hello','this','is','an','array');
~~~

That's the most common way to define an array. But you can also
fucking do:

~~~
my @array;
$array[0] = "hello";
$array[1] = "this";
$array[2] = "is";
$array[3] = "an";
$array[4] = "array";
$array[1312312312] = "wtf"; # from 5 to 1312312312, contents are NULL.
~~~

### use strict

really? it should be enabled by default. it shold be ```use
unstrict``` instead

### perl's logo is an onion

visiting code you wrote some weeks ago will make you cry.

# But it is, still, the greatest programming language the world has ever known.
