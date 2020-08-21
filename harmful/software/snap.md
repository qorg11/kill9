# >what's gcc --static

Why do you mean "Universal packages"?

You don't know how to run a binary file?

GNU/Linux (like every other operating system) has binary files. So you
can just run them, without having to use a "Universal package manager"

## Decentralization of packages.

Decentralization is not okay in package management, they have made
repositories and package manager to have order on the system. Having
more than one package manager breaks that order.

If you **REALLY** need to share an "universal package", just use the
`--static` CFLAG, this will bundle the used libraries in the binary,
it's stupid but well, isn't that what .AppImage does?
