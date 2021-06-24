# Cloudflare and its consequences have been a disaster for the cyberspace

Cloudflare is a MITM

Cloudflare stays between you and the server you're going to.

Cloudflare claims this is for "DDoS" protection and CDN.

Which is all good, until cloudflare thinks you're a bot.

Why can cloudflare think you're a bot? here are some reasons

* You use a browser cloudflare don't like
* you care about your privacy, so you use something like tor
* you want sane browser so you disable JS

If cloudflare thinks you're a bot, you'll have to enable JS and ~train
their AI~ solve a captcha to enter the website

If you don't mind click squares for 5 minutes (I once tried to solve
one of these captchas using tor+pale moon and i shit you not, i was
clicking squares for 5 minutes) you should know how this "DDoS
protection" works.

There is no DDoS protection actually, they just have a lot of
servers. So if a server is overloaded, they will just point your
website to another server.

Now, on the "bot" detection. Cloudflare claims to only block "bad
bots" and "attackers". how does this thing work?

Easy. via the **user-agent**. I believe it follows something like this

* Normal IP, most browsers user-agent -> pass
* Tor exit node IP, -> tor browser user-agent pass
* Tor exit node/VPN, -> any user agent but tor browser's -> captcha

Inmidiatly, people who knows how the HyperText Transfer Protocol
Secure works will say "How does Cloudflare know my user agent, the
user agent its passed in the request!"

This is because, despite having the green lock in the browser,
cloudflare **decrypts** all your traffic. All the usernames,
passwords, have passed in plain text through cloudflare's server.


You should [distrust cloudflare from your browser](/guides/distrust_cloudflare)

more info [here](https://git.fuwafuwa.moe/you/stop_cloudflare)
