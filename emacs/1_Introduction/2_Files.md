# Editing files on Emacs

Emacs is a text editor. So its main function is to edit text. You can
open a file with C-x C-f ```(find-file)``` and type the name of the
file you want to open, for example:

C-x C-f myfile

That will create a buffer[^1] which your file's contents.

There is another ways to visit a file in Emacs. for example:

C-x C-r `(file-find-read-only)`: This will open a file but won't allow
you to make changes on it.

C-x 4 f `(find-file-other-window)`: This splits your Emacs window
vertically and puts the selected file you gave on the buffer bellow

C-x 5 f `(find-file-other-frame)`: This opens another Emacs window[^2]
and puts the selected file on a new buffer.

# Opening remote files

Emacs comes with TRAMP which can be used to open remote files. To open
a remote file. Press C-x C-f ```(find-file)``` and follow this syntax:

~~~
/method:host:filename
/method:user@host:filename
/method:user@host#port:filename
~~~

If you don't gave a method (put - as method) Emacs do the following:

1. If `host` starts with ftp, Emacs will use ftp
2. If `user` is "*ftp*" or "*anonymous*" Emacs will use ftp.
3. If the variable `tramp-default-method` is ftp, Emacs will use ftp.
4. If ssh-agent is running, Emacs will use ftp.
5. Otherwise, Emacs will use ssh.

Try opening this remote file: `ftp://test.rebex.net/readme.txt`

To do this, press C-x C-f ```(find-file)``` and type this
/ftp:demo@test.rebex.net:/readme.txt

Emacs will ask for a password. This password is `password`

This is a read only ftp server, but if it allowed write, you could
write the remote file with C-x C-s `(save-buffer)`

## Writing text

To add text to a buffer, you just type what you want to add on the
buffer, unlike Vi/Vim Emacs do not have an "INSERT" mode.

When you finish typing and want to save what you have done press C-x C-s `(save-buffer)`

## Reverting edits on Emacs

Emacs, like every other text editor, allows to undo what you've done. 

If you have done massive changes to a file and want to revert it, type
`M-x revert-buffer` Emacs will ask confirmation. Since this reverts to
the saved version of the buffer. If you saved the file after some
changes, this method will not work. You can undo your last change to
the file with some shorcuts: C-x u, C-/ and C-_ `(undo)`

[^1]: A buffer is where the text resides on your Emacs window,
everything in Emacs is a buffer. In other words, a buffer holds
your text file.
[^2]: This is not a new Emacs run, it is called a "frame" These
two emacs window shares the opened buffers.
