# Distrust Cloudflare's certs from browser's Certificate Authority

The only good thing about the evil [certificate
authority](/harmful/software/CA) is that you can manually edit it in
your browser, in this guide i'll show how to distrust Cloudflare's
certs in Pale Moon, but these steps should be similar in other
browsers.

Why cloudflare's certificates? well, they're useless since
cloudflare's MITM will decrypt the HTTPS request automatically. You
can learn more about the crimes of cloudflare here:
<https://codeberg.org/qorg11/stop_cloudflare>

1. Open the settings (`tools>preferences`)

2. Go to `advanced>certificates`

![](/.img/1609264022.png)

3. Click "View Certificates"

4. Click "Baltimore CyberTrust Root and click edit trust

![](/.img/1609264076.png)

5. Uncheck everything

6. ![](/.img/1609264080.png)

7. Click "Cloudflare Inc ECC CA-3" and click in "Delete or distrust"

![](/.img/1609264086.png)

8. Click "okay"

9. Go to any cloudflared website

10. There!

	<img src="/.img/1609264118.png" width="500"/>
