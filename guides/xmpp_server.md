# How to setup a prosody server

In this guide i'm going to show how to make a prosody (XMPP)
server, this guide will only cover the bare minimum (no extensions)
+ the http upload mod, so you can send files.

# Requirements

1. A domain (you can use something like <http://afraid.org> or
   <http://duckdns.org> if you don't have any. My domain in this thing
   is flatline.fr.to. I got it in afraid.org
2. A server running a good operating system (Debian, FreeBSD...) I'm
   using a FreeBSD machine in this guide.

# Dependences

1. prosody
2. nginx
3. something that enables the `mod_perl` in nginx, in FreeBSD, it is in
   the `nginx-full` package, or you can choose to install it while
   building nginx using the ports. In Debian you can install the 
   `libnginx-mod-http-perl` package
4. [Certificates](/harmful/software/CA), we are going to use certbot
   here.

# Installation

In FreeBSD, you simply run `pkg install prosody prosody-modules nginx-full` or you can
choose to build it from ports. 

# Configuration

Here is where the """hard part""" comes, in Debian and other good
operating systems, the configuration files are located in
`/etc/prosody`, in FreeBSD they're located at
`/usr/local/etc/prosody`. The main configuration file is
`prosody.cfg.lua` but you can add multiple configurations file in the
.conf.d folder.

The configuration file has a lot of comments so use them as
guide. First of all is to add admins to the server:

`admins = {wintermute@flatline.fr.to}`

The next line is the modules_enabled, if you want to enable some
modules, add them here, some modules can be smacks, for example. but,
again, this guide only covers the minimum.

Next thing you should check is the `allow_registration` parameter,
should be false unless you're going to make a public server.

Next, you can configure prosody to use sql as user storage, but in
this case we are just going to do the internal thing. Make sure that
it is internal_hashed.

Now, skip until the "VirtualHost" Here you will configure the XMPP
VirtualHost for the JID.

Note that configuration bellow "VirtualHost" will only affect that
VirtualHost, until there's a next VirtualHost or "Component". Single
domain servers should have only one "VirtualHost"

By default VirtualHost value is "localhost" change it to your domain:
`VirtualHost "flatline.to.fr"`

Next, you have to add the ssl certificates to it. to use we are going
to generate them using `certbot`

To generate the certificates, run `certbot certonly
--rsa-key-size=4096 -d your-domain`, if you have nginx running, stop
it, so you can use the temporary server option, which has never failed
me. Your certificate will be in
(usr/local)/etc/letsencrypt/youtdomain/fullchain.pem.

prosody includes a command to import certbot certs so you don't have
to bother with permissions, to do this simply run prosodyctl --root
cert import /usr/local/etc/letsencrypt/live/ 

Now, you have to give prosody that certificate, you have to put it
twice for some reason, like this:

<pre class="hl">ssl <span class="hl opt">= {</span> key <span
	class="hl opt">=</span> <span class="hl
	sng">&quot;certs/flatline.fr.to.key&quot;</span><span class="hl
	opt">;</span> certificate <span class="hl opt">=</span> <span
	class="hl sng">&quot;certs/flatline.fr.to.crt&quot;</span><span
	class="hl opt">;</span> <span class="hl opt">}</span>

VirtualHost <span class="hl sng">&quot;flatline.fr.to&quot;</span>

ssl <span class="hl opt">= {</span> key <span class="hl opt">=</span>
	<span class="hl
	sng">&quot;certs/flatline.fr.to.key&quot;</span><span class="hl
	opt">;</span> certificate <span class="hl opt">=</span> <span
	class="hl sng">&quot;certs/flatline.fr.to.crt&quot;</span><span
	class="hl opt">;</span> <span class="hl opt">}</span> </pre>



now, run `prosodyctl check`, you should get an output like this

~~~


Checking config...
Done.

Checking DNS for host flatline.fr.to...
    Host flatline.fr.to does not seem to resolve to this server (IPv6)

Checking certificates...
Checking certificate for flatline.fr.to
  Certificate: /usr/local/etc/prosody/certs/flatline.fr.to.crt

All checks passed, congratulations!
~~~

Which means everything is working! now you have to create an user to
test it, to do this, run something like this `prosodyctl adduser
wintermute@flatline.fr.to`, maybe you should create first the admin's
account. So I created the Wintermute account. 

It will ask for a password, so enter it. Now it's time to test it, you
can use any client. I recommend poezio/gajim/dino/profanity

Before testing, you have to, obviously, start the server, in freebsd
you'd do something like `service prosody start`, probably the same in
Debian.

If you can log in, probably everything works.

# Uploading files

Now you have the bare-bones XMPP server, but you probably want it to
upload files, you can use one of these:

* `mod_http_upload`
* `mod_http_upload_external`

We are going to use `mod_http_upload_external` because it's more
stable and have more benefits over the regular one. There are bunch of
implementations of `mod_http_upload_external` but we are going to use
the perl one because it's the one that worked for me.

## Requirements

* A subdomain (I created up.flatline.fr.to for this)
* nginx
* the perl mod

## Installation

You have to add this to the bottom of the prosody config file 

~~~
Component "up.flatline.fr.to" "http_upload_external"
http_upload_external_base_url = "https://up.flatline.fr.to/"
http_upload_external_secret = "BURDOBORDO:DDDD:DDD:--"
~~~

Please note the "/" at the end of the URL

Create a new site under sites-enabled in nginx configuration folder
with something like this.

~~~
server {
    # Specify directives such as "listen", "server_name", and TLS-related
    # settings for the "server" that handles the uploads.
	server_name up.flatline.fr.to;
    # Uploaded files will be stored below the "root" directory. To minimize
    # disk I/O, make sure the specified path is on the same file system as
    # the directory used by Nginx to store temporary files holding request
    # bodies ("client_body_temp_path", often some directory below /var).
    root /usr/local/var/www/upload;

    # Specify this "location" block (if you don't use "/", see below):
    location / {
        perl upload::handle;
    }

    # Upload file size limit (default: 1m), also specified in your XMPP
    # server's upload module configuration (see below):
    client_max_body_size 100m;
}
~~~

now, in your nginx.conf add something like this in the http section 

~~~
load_module modules/ngx_http_perl_module.so;
http {
perl_modules /usr/local/lib/perl; # Path to upload.pm.
perl_require upload.pm;
...
}
~~~

Run these commands

~~~
mkdir -p /usr/local/lib/perl
wget -O /usr/local/lib/perl/upload.pm https://git.io/fNZgL
~~~

Now you have to edit /usr/local/lib/perl/upload.pm to change the
password for the one you put in prosody configuration.

`my $external_secret = 'BURDOBORDO:DDDD:DDD:--';`

Make the directory for uploaded files `mkdir
/usr/local/var/www/upload` and use chown to give it ownership to nginx
user, in debian is www-data and in freebsd is www, but in others like
arch is nginx.

## SSL for the upload site

We used https:// in the prosody configuration, you can use http:// if
you want, but it's not recommended. We are going to simply use the
`--nginx` certbot flag for this. So you have to install the certbot
nginx plugin. Simply run `certbot --nginx --rsa-key-size=4096 -d
up.flatline.fr.to`. Process shold be automatic.

Try uploading a file in dino, it shold work.

The next step will be adding other modules to your XMPP server, such
as MUC or some others, these are very obvious to install. Only RTFM
:). If you are going to make it compatible with more extensions,
create a tester account (tester@flatline.fr.to) and add it to
<https://compliance.conversations.im>. If you click on the squares of
why the thing isn't working, it will give you a guide of how to
install that. Most modules are simply adding the modules to the
modules_enabled section. You should install smacks and bookmarks!

# References

* [prosody website](https://prosody.im)
* [prosody basic guide](https://prosody.im/doc/configure)
* [using let's encrypt with prosody](https://prosody.im/doc/letsencrypt)
* [prosody modules](https://modules.prosody.im)
* [mod\_http\_upload\_external](https://modules.prosody.im/mod_http_upload_external.html)
* [ngx\_http\_upload](https://github.com/weiss/ngx_http_upload)

