# `pax(1)` is a well done `tar(1)`

`pax(1)` allows you to create .tar files in a UNIX way:

~~~
# create a tar file of a directory
pax -w directory > directory.tar
# see the contents of a tar file
pax < directory.tar
# extract contents
pax -r < directory.tar
# create a compressed tar file
pax -w directory | gzip > directory.tar.gz
# decompress a file
zcat directory.tar.gz | pax -r
~~~

These are tar files, so they're compatible with `tar(1)`

You can also use `pax(1)` in a cringe, non UNIX way:


~~~
# create a .tar file
pax -w -f dir.tar dir
# create a compressed file
pax -zw -f dir.tar.gz dir
# decompress a file
pax -zr -f dir.tar.gz
~~~

(I think you get the point)
