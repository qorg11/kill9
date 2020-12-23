# free(malloc(sizeof("C is a great programming language")));

* C is a great progr.... segmentation fault
* Who wrote the functions? I mean: fprintf, sscanf, isalnum...
* Lack of lambdas
* The preprocessor
* Thank you for making me understand why I got a segfault![^1]

~~~
int sum(int a, int b) {
 return a + b;
}
~~~

That causes overflow

# But remember

~~~
When I find my code in tons of trouble
Friends and colleagues come to me
Speaking words of wisdom
Write in C

As the deadline fast approaches
And bugs are all I can see
Somewhere someone whispers
Write in C

Write in C
Write in C
Write in C
Write in C

LISP is dead and buried
Write in C

I used to write a lot of FORTRAN
For science it worked flawlessly
Try using it for graphics
Write in C

If you just spent nearly 30 hours
Debugging some assembly
Soon you'll be glad to
Write in C

Write in C
Write in C
Write in C, yeah
Write in C

Only wimps use BASIC
Write in C

Write in C
Write in C
Write in C
Write in C

Pascal won't quite cut it
Write in C

Write in C
Write in C
Write in C
Write in C

Don't even mention COBOL
Write in C

And when the screen is fuzzing
And the editor is bugging me
I'm sick of ones and zeroes
Write in C

A thousand people swear that
TP7 is the one for me
I hate the word "procedure"
Write in C

Write in C
Write in C
Write in C
Write in C

PL/1 is '80s
Write in C

Write in C
Write in C
Write in C
Write in C

The government loves Ada
Write in C
~~~

[^1]: gcc10 -fanalyzer can explain why you got a segfault. But this is
    product of the C implementation. Not of the C standard.
