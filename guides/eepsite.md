# How to setup an Eepsite in most linux distros

An eepsite is a website in I2P, there are 2 main I2P clients (Java I2P
and i2pd). So i'll cover both programs here

# nginx configuration

Implying you use nginx, you should use a configuration like this:

~~~
server {
	listen 127.0.0.1:8080;
	root /home/eepsite/www_data;
	# any of your custom configuration goes here
}
~~~
Now, explaining the not-so-normal things on the configuration:

* We listen to 127.0.0.1 because we want only that computer to access
  that server (if it was just `listen 8080;` it will bind the port to
  every available IP address. Allowing external access and we don't
  want that.)
* We listen to port 8080 so we can have less errors later. The i2p
  client will pick the port 8080 in 127.0.0.1 and then use it as port
  80 in the I2P address. As there's only one HTTP server in
  port 8080. You don't have to do any of these weird `server_name`
  hacks. So you should bind to another port each eepiste you want.
  
# i2pd configuration

1. Create the ~/.i2pd/tunnels.conf file
2. put these contents

~~~
[website]
type = http
host = 127.0.0.1
port = 8080
keys = website.dat
enableuniquelocal = false
~~~

## Explanation

* `type = http` so it forwards the given port to 80 automatically
* `host = 127.0.0.1` the host to make the request (can be anything)
* `port = 8080` where it will get the port (change this for further eepsites)
* `keys = website.dat` the file which will hold the eepiste private
  key
* `enaleuniquelocal = false` gives the 127.0.0.1 IP address to each
  visitor. (by default i2pd will give addresses like 127.32.23.12)

Now start i2pd, you can get the b32 address of the site you just
created with this command:

`printf "%s.b32.i2p\n" $(head -c 391 website.dat|sha256sum|xxd -r -p | base32 |sed  s/=//g | tr A-Z a-z)`

(Or you can go to http://127.0.0.1:7070/?page=i2p_tunnels)

That's it!

# Java I2P

Java I2P is better in my opinion because it is faster and it's easier
to create an eepiste then. By default Java ships with Jetty (A simple
HTTP server that does it job very well). So you can just drop the
files you want to serve in ~/.i2p/eepsite/docroot and they'll be
served once you start the first thing in
<http://127.0.0.1:7657/i2ptunnelmgr> (the one that points to
127.0.0.1:7658, which is the jetty instance)

Jetty does it work pretty well, but you can obviously use nginx (or
any other HTTP server, obviously). To do this just scroll to the
bottom in <http://127.0.0.1:7657/i2ptunnelmgr> and create an HTTP
hidden service.

Enter whatever you want in the name. And in the description. You can
set a website hostname if you want (foobar.i2p) and edit the private
key file if you want. 

Just enter whatever you need in the target section:

![The target section mentioned above](/i2p.png)

Then click save. click start and it should give you the b32
address. And if you gave it a host. a addresshelper.

That's it!
