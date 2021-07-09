## Introduction

If you care about the upmost security, you should probably be using the
LibreSSL TLS crypto stack. 

This is an SSL library forked from OpenSSL by the OpenBSD team around 2014
with improving the codebase, improving security, and applying the best
development practices. 

This guide focuses on Gentoo GNU/Linux, as it needs a few more steps to get
working than other distros.

# Getting started

You will need Gentoo installed on your computer obvoiously, and some
patience, espesially if you have a bunch of applications installed. 

Keep in mind if you have a bunch of packages, be prepared to recompile, and
debug any of them along the way if they fail to work or compile. 

# Adding the overlay

First thing you will NEED TO DO is add the LibreSSL ebuild overlay to your
system. 

This supplies the LibreSSL ebuild itself and patches for other applications
to get working under LibreSSL. Please do the following in a terminal:

~~~ emerge eselect-repository eselect repository enable libressl emaint
sync -r libressl ~~~

After doing this, you should have the overlay synced and installed, you can
check this by running

~~~ ls /var/db/repos/libressl ~~~

If files appear, you have it installed.

# make.conf settings

You will have to set some flags in your make.conf for specific apps to use
LibreSSL instaid of OpenSSL. 

In your make.conf please find the USE="" paramater and put in the
following:

~~~ USE="-openssl -system-ssl" ~~~

For apps with these USE flags, they will ignore specific OpenSSL support.
**system-ssl** is known to cause problems for nodejs users, so I reccomend
disabiling it here.

Another thing that the migration does is installs and OpenSSL dummy
package. Due to gentoo removing LibreSSL from their overlay. 

This package is needed for packages to build correctly, dont worry, they
still bind to LibreSSL. 

To be sure this dummy package is the only one allowed to be merged, please
open this file in a text editor

**/etc/portage/package/package.mask**. 

If this is a directory, not a file, then do 

**/etc/portage/package/package.mask/openssl**. 

And insert the following

~~~
# OpenSSL mask
dev-libs/openssl::gentoo

# OpenSSL package mask
app-crypt/qca::gentoo dev-lang/python::gentoo ~~~

This will mask OpenSSL from being merged, and cause the other packages
listed to only build from the LibreSSL overlay.  

# Migration time

Time for the big thing, we are going to migrate from OpenSSL to Libressl.
The first part is removing OpenSSL from your system, and fetcing needed
packages for the migration. please run:

~~~ emerge -f wget curl python libressl emerge -Cq dev-libs/openssl ~~~

After doing this, please merge LibreSSL, this will take a minute so please
be patient.

~~~ emerge -1q dev-libs/libressl::libressl ~~~

You're almost done! To test that you are actually using LibreSSL, you can
run somthing like 

**openssl version** 

and if it returns somthing like 

**LibreSSL x.x.x**

you're using LibreSSL.

# Finishing touches

Time to update and rebind everything to use LibreSSL, you may have noticed
emerge will complain about libraries needing to be rebuilt, this will fix
that.  Please run:

~~~ emerge -vquDN @world emerge @preserved-rebuild ~~~

And if everything compiles fine, congratulations! You are now using a
LibreSSL based Gentoo system. I hope you enjoyed this guide. -itZzenXX
