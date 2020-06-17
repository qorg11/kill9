<style>
pre {
overflow:auto;
table-layout:fixed;
width: 75%;
max-width:75%;
}
</style>
# C++ sucks

>C makes it easy to shoot yourself in the foot; C++ makes it harder,
>but when you do, it blows away your whole leg. 

--- Bjarne Stroustrup

>If you like C++, you don’t know C++. There’s a mutual exclusion going
>on here, and I’ve yet to see a counter-example other than possibly a
>few of the members of the standards committee.

--- ssylvan

## Object oriented

So automatically sucks.

## Ugly syntax

The only non-ugly part of C++ is the headers' name: iostream, cmath,
ctime, thread, etc. Unlike in C, where they are ugly as shit: stdio.h,
unistd.h, stdlib.h, pthreads.h...

But the rest of the language has the ugliest syntax that I've ever seen:

Hello world in C++

~~~
#include <iostream>

int main(void)
{
	std::cout << "Hello world!" << std:endl;
}
~~~

### What the FUCK was Bjarne smoking when he did this:

In C:

`printf("0x%04x\n", 0x424);`

In C++:

`std::cout << "0x" << std::hex << std::setfill('0') << std::setw(4) << 0x424 << std::endl;`

Now what the fuck is std:: and why do I have to write << just to print some shit.

Note: you can skip the std:: part with ```using namespace std``` but this is a [bad practice](https://stackoverflow.com/questions/1452721/why-is-using-namespace-std-considered-bad-practice)

## Error messages

in the following code:



~~~
#include <iostream>

int main(void)
{
	std::cout < "Hello world!" < std:endl;
}
~~~

You get this error message:

<p class="code">

~~~
a.cc: In function ‘int main()’:
a.cc:5:13: error: no match for ‘operator<’ (operand types are ‘std::ostream’ {aka ‘std::basic_ostream<char>’} and ‘const char [13]’)
    5 |   std::cout < "Hello world!" < std:endl;
      |   ~~~~~~~~~ ^ ~~~~~~~~~~~~~~
      |        |      |
      |        |      const char [13]
      |        std::ostream {aka std::basic_ostream<char>}
In file included from /usr/local/include/c++/10.0.1/bits/stl_algobase.h:64,
                 from /usr/local/include/c++/10.0.1/bits/char_traits.h:39,
                 from /usr/local/include/c++/10.0.1/ios:40,
                 from /usr/local/include/c++/10.0.1/ostream:38,
                 from /usr/local/include/c++/10.0.1/iostream:39,
                 from a.cc:1:
/usr/local/include/c++/10.0.1/bits/stl_pair.h:489:5: note: candidate: ‘template<class _T1, class _T2> constexpr bool std::operator<(const std::pair<_T1, _T2>&, const std::pair<_T1, _T2>&)’
  489 |     operator<(const pair<_T1, _T2>& __x, const pair<_T1, _T2>& __y)
      |     ^~~~~~~~
/usr/local/include/c++/10.0.1/bits/stl_pair.h:489:5: note:   template argument deduction/substitution failed:
a.cc:5:15: note:   ‘std::ostream’ {aka ‘std::basic_ostream<char>’} is not derived from ‘const std::pair<_T1, _T2>’
    5 |   std::cout < "Hello world!" < std:endl;
      |               ^~~~~~~~~~~~~~
In file included from /usr/local/include/c++/10.0.1/bits/stl_algobase.h:67,
                 from /usr/local/include/c++/10.0.1/bits/char_traits.h:39,
                 from /usr/local/include/c++/10.0.1/ios:40,
                 from /usr/local/include/c++/10.0.1/ostream:38,
                 from /usr/local/include/c++/10.0.1/iostream:39,
                 from a.cc:1:
/usr/local/include/c++/10.0.1/bits/stl_iterator.h:366:5: note: candidate: ‘template<class _Iterator> bool std::operator<(const std::reverse_iterator<_Iterator>&, const std::reverse_iterator<_Iterator>&)’
  366 |     operator<(const reverse_iterator<_Iterator>& __x,
      |     ^~~~~~~~
/usr/local/include/c++/10.0.1/bits/stl_iterator.h:366:5: note:   template argument deduction/substitution failed:
a.cc:5:15: note:   ‘std::ostream’ {aka ‘std::basic_ostream<char>’} is not derived from ‘const std::reverse_iterator<_Iterator>’
    5 |   std::cout < "Hello world!" < std:endl;
      |               ^~~~~~~~~~~~~~
In file included from /usr/local/include/c++/10.0.1/bits/stl_algobase.h:67,
                 from /usr/local/include/c++/10.0.1/bits/char_traits.h:39,
                 from /usr/local/include/c++/10.0.1/ios:40,
                 from /usr/local/include/c++/10.0.1/ostream:38,
                 from /usr/local/include/c++/10.0.1/iostream:39,
                 from a.cc:1:
/usr/local/include/c++/10.0.1/bits/stl_iterator.h:404:5: note: candidate: ‘template<class _IteratorL, class _IteratorR> bool std::operator<(const std::reverse_iterator<_Iterator>&, const std::reverse_iterator<_IteratorR>&)’
  404 |     operator<(const reverse_iterator<_IteratorL>& __x,
      |     ^~~~~~~~
/usr/local/include/c++/10.0.1/bits/stl_iterator.h:404:5: note:   template argument deduction/substitution failed:
a.cc:5:15: note:   ‘std::ostream’ {aka ‘std::basic_ostream<char>’} is not derived from ‘const std::reverse_iterator<_Iterator>’
    5 |   std::cout < "Hello world!" < std:endl;
      |               ^~~~~~~~~~~~~~
In file included from /usr/local/include/c++/10.0.1/bits/stl_algobase.h:67,
                 from /usr/local/include/c++/10.0.1/bits/char_traits.h:39,
                 from /usr/local/include/c++/10.0.1/ios:40,
                 from /usr/local/include/c++/10.0.1/ostream:38,
                 from /usr/local/include/c++/10.0.1/iostream:39,
                 from a.cc:1:
/usr/local/include/c++/10.0.1/bits/stl_iterator.h:1451:5: note: candidate: ‘template<class _IteratorL, class _IteratorR> bool std::operator<(const std::move_iterator<_IteratorL>&, const std::move_iterator<_IteratorR>&)’
 1451 |     operator<(const move_iterator<_IteratorL>& __x,
      |     ^~~~~~~~
/usr/local/include/c++/10.0.1/bits/stl_iterator.h:1451:5: note:   template argument deduction/substitution failed:
a.cc:5:15: note:   ‘std::ostream’ {aka ‘std::basic_ostream<char>’} is not derived from ‘const std::move_iterator<_IteratorL>’
    5 |   std::cout < "Hello world!" < std:endl;
      |               ^~~~~~~~~~~~~~
In file included from /usr/local/include/c++/10.0.1/bits/stl_algobase.h:67,
                 from /usr/local/include/c++/10.0.1/bits/char_traits.h:39,
                 from /usr/local/include/c++/10.0.1/ios:40,
                 from /usr/local/include/c++/10.0.1/ostream:38,
                 from /usr/local/include/c++/10.0.1/iostream:39,
                 from a.cc:1:
/usr/local/include/c++/10.0.1/bits/stl_iterator.h:1507:5: note: candidate: ‘template<class _Iterator> bool std::operator<(const std::move_iterator<_IteratorL>&, const std::move_iterator<_IteratorL>&)’
 1507 |     operator<(const move_iterator<_Iterator>& __x,
      |     ^~~~~~~~
/usr/local/include/c++/10.0.1/bits/stl_iterator.h:1507:5: note:   template argument deduction/substitution failed:
a.cc:5:15: note:   ‘std::ostream’ {aka ‘std::basic_ostream<char>’} is not derived from ‘const std::move_iterator<_IteratorL>’
    5 |   std::cout < "Hello world!" < std:endl;
      |               ^~~~~~~~~~~~~~
In file included from /usr/local/include/c++/10.0.1/string:55,
                 from /usr/local/include/c++/10.0.1/bits/locale_classes.h:40,
                 from /usr/local/include/c++/10.0.1/bits/ios_base.h:41,
                 from /usr/local/include/c++/10.0.1/ios:42,
                 from /usr/local/include/c++/10.0.1/ostream:38,
                 from /usr/local/include/c++/10.0.1/iostream:39,
                 from a.cc:1:
/usr/local/include/c++/10.0.1/bits/basic_string.h:6267:5: note: candidate: ‘template<class _CharT, class _Traits, class _Alloc> bool std::operator<(const std::__cxx11::basic_string<_CharT, _Traits, _Alloc>&, const std::__cxx11::basic_string<_CharT, _Traits, _Alloc>&)’
 6267 |     operator<(const basic_string<_CharT, _Traits, _Alloc>& __lhs,
      |     ^~~~~~~~
/usr/local/include/c++/10.0.1/bits/basic_string.h:6267:5: note:   template argument deduction/substitution failed:
a.cc:5:15: note:   ‘std::ostream’ {aka ‘std::basic_ostream<char>’} is not derived from ‘const std::__cxx11::basic_string<_CharT, _Traits, _Alloc>’
    5 |   std::cout < "Hello world!" < std:endl;
      |               ^~~~~~~~~~~~~~
In file included from /usr/local/include/c++/10.0.1/string:55,
                 from /usr/local/include/c++/10.0.1/bits/locale_classes.h:40,
                 from /usr/local/include/c++/10.0.1/bits/ios_base.h:41,
                 from /usr/local/include/c++/10.0.1/ios:42,
                 from /usr/local/include/c++/10.0.1/ostream:38,
                 from /usr/local/include/c++/10.0.1/iostream:39,
                 from a.cc:1:
/usr/local/include/c++/10.0.1/bits/basic_string.h:6280:5: note: candidate: ‘template<class _CharT, class _Traits, class _Alloc> bool std::operator<(const std::__cxx11::basic_string<_CharT, _Traits, _Alloc>&, const _CharT*)’
 6280 |     operator<(const basic_string<_CharT, _Traits, _Alloc>& __lhs,
      |     ^~~~~~~~
/usr/local/include/c++/10.0.1/bits/basic_string.h:6280:5: note:   template argument deduction/substitution failed:
a.cc:5:15: note:   ‘std::ostream’ {aka ‘std::basic_ostream<char>’} is not derived from ‘const std::__cxx11::basic_string<_CharT, _Traits, _Alloc>’
    5 |   std::cout < "Hello world!" < std:endl;
      |               ^~~~~~~~~~~~~~
In file included from /usr/local/include/c++/10.0.1/string:55,
                 from /usr/local/include/c++/10.0.1/bits/locale_classes.h:40,
                 from /usr/local/include/c++/10.0.1/bits/ios_base.h:41,
                 from /usr/local/include/c++/10.0.1/ios:42,
                 from /usr/local/include/c++/10.0.1/ostream:38,
                 from /usr/local/include/c++/10.0.1/iostream:39,
                 from a.cc:1:
/usr/local/include/c++/10.0.1/bits/basic_string.h:6292:5: note: candidate: ‘template<class _CharT, class _Traits, class _Alloc> bool std::operator<(const _CharT*, const std::__cxx11::basic_string<_CharT, _Traits, _Alloc>&)’
 6292 |     operator<(const _CharT* __lhs,
      |     ^~~~~~~~
/usr/local/include/c++/10.0.1/bits/basic_string.h:6292:5: note:   template argument deduction/substitution failed:
a.cc:5:15: note:   mismatched types ‘const _CharT*’ and ‘std::basic_ostream<char>’
    5 |   std::cout < "Hello world!" < std:endl;
      |               ^~~~~~~~~~~~~~
In file included from /usr/local/include/c++/10.0.1/bits/ios_base.h:46,
                 from /usr/local/include/c++/10.0.1/ios:42,
                 from /usr/local/include/c++/10.0.1/ostream:38,
                 from /usr/local/include/c++/10.0.1/iostream:39,
                 from a.cc:1:
/usr/local/include/c++/10.0.1/system_error:252:3: note: candidate: ‘bool std::operator<(const std::error_code&, const std::error_code&)’
  252 |   operator<(const error_code& __lhs, const error_code& __rhs) noexcept
      |   ^~~~~~~~
/usr/local/include/c++/10.0.1/system_error:252:31: note:   no known conversion for argument 1 from ‘std::ostream’ {aka ‘std::basic_ostream<char>’} to ‘const std::error_code&’
  252 |   operator<(const error_code& __lhs, const error_code& __rhs) noexcept
      |             ~~~~~~~~~~~~~~~~~~^~~~~
/usr/local/include/c++/10.0.1/system_error:379:3: note: candidate: ‘bool std::operator<(const std::error_condition&, const std::error_condition&)’
  379 |   operator<(const error_condition& __lhs,
      |   ^~~~~~~~
/usr/local/include/c++/10.0.1/system_error:379:36: note:   no known conversion for argument 1 from ‘std::ostream’ {aka ‘std::basic_ostream<char>’} to ‘const std::error_condition&’
  379 |   operator<(const error_condition& __lhs,
      |             ~~~~~~~~~~~~~~~~~~~~~~~^~~~~
a.cc:5:35: error: found ‘:’ in nested-name-specifier, expected ‘::’
    5 |   std::cout < "Hello world!" < std:endl;
      |                                   ^
      |                                   ::
~~~
</p>
(In GCC)

## Compatibilty

C++ is "compatible" with C

But this can break most C programs
