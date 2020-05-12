<style>
li {color:white;}
</style>
# Scheme sucks (but less)

* Scheme standard is really minimalist and specific

This implies that an scheme implementation implements it as the
creator wants. They include libraries and extensions which can make an
implementation incompatible with another. They need "
Scheme Requests for Implementation" to solve that problem.

### Variables and procedures

Scheme uses the same namespace for variables and procedures. So you
can't give the name "list" to a variable. Instead you can see ```xs``` or ```lst```

