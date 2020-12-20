# gitlab(.com) sucks lmao

* website is [cuckflared](https://codeberg.org/qorg11/stop_cloudflare)

The solution to this would be to run your own gitlab instance, buuuuuuuuuuuuut...

>\><https://docs.gitlab.com/charts/installation/>  
>\> 8vCPU and 30GB of RAM is recommended

What in the actual fuck?

* it needs JS to work
* and it is esoteric JS

Still not convinced? Try installing gitlab from source while remaining sane.

Protip: you can't

https://docs.gitlab.com/ee/install/installation.html

If you still manage to get through this hell of a setup then enjoy the 700kB JS that it requires.

```
$ curl --head https://gitlab.example.dom/assets/webpack/main.909b7bb7.chunk.js
HTTP/2 200
content-type: application/javascript
content-length: 692119
```

