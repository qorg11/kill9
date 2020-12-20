# Guide and introduction to PGP

OpenPGP is a standard for encryption. It can be used to encrypt and
sign documents, since it is a standard, there are many
implementations, the one we are going to use is gnu privacy guard
(gpg)

# Installing gnupg

This obviously depends for every distro you're using, if you're using
windows, check [gpg4win](https://gpg4win.org).

* **Debian**: `# apt-get install gpg`
* **Arch**: `# pacman -S gnupg`
* **Void**: `# xbps-install gnupg2 && ln /bin/gpg2 /bin/gpg`

This will install gpg on your system, you check you're using at least
gpg 2, with `gpg --version`:

```
> gpg --version  
gpg (GnuPG) 2.2.23
```

# Generating keys

You need a key-pair to encrypt and sign files, this can be made with
`gpg --full-gen-key --expert`

Why --full-gen-key and --expert? instead of --gen-key? --gen-key does
not provide a way to specify which kind of key we weant, (or the size
of said key) but we can specify it with --expert. It will ask for a
name, e-mail and a comment, this can be obviously be fake, the comment
[should be
blank](https://web.archive.org/web/20200604060421/https://debian-administration.org/users/dkg/weblog/97)

You can choose any kind of key you want (as long as you know what
you're doing and know you're going to be as secure as if you were
using the defaults). I only recommend making RSA4096 or cv25519 keys,
they're both extremely secure. First example is generating a cv25519
key and the second is generating a RSA4096 key

```

> gpg --full-generate-key --expert
Please select what kind of key you want:
   (1) RSA and RSA (default)
   (2) DSA and Elgamal
   (3) DSA (sign only)
   (4) RSA (sign only)
   (7) DSA (set your own capabilities)
   (8) RSA (set your own capabilities)
   (9) ECC and ECC
  (10) ECC (sign only)
  (11) ECC (set your own capabilities)
  (13) Existing key
  (14) Existing key from card
Your selection? 9
Please select which elliptic curve you want:
   (1) Curve 25519
   (3) NIST P-256
   (4) NIST P-384
   (5) NIST P-521
   (6) Brainpool P-256
   (7) Brainpool P-384
   (8) Brainpool P-512
   (9) secp256k1
Your selection? 1
Please specify how long the key should be valid.
         0 = key does not expire
      <n>  = key expires in n days
      <n>w = key expires in n weeks
      <n>m = key expires in n months
      <n>y = key expires in n years
Key is valid for? (0) 0
Key does not expire at all
Is this correct? (y/N) y

GnuPG needs to construct a user ID to identify your key.

Real name: Henry Dorsett Case
Email address: case@example.tld
Comment: 
You selected this USER-ID:
    "Henry Dorsett Case <case@example.tld>"

Change (N)ame, (C)omment, (E)mail or (O)kay/(Q)uit? o
We need to generate a lot of random bytes. It is a good idea to perform
some other action (type on the keyboard, move the mouse, utilize the
disks) during the prime generation; this gives the random number
generator a better chance to gain enough entropy.

[...]

pub   ed25519/0xB9F81A68A9323DEC 2020-12-20 [SC]
      Key fingerprint = 95B1 945C 3D0F 8C34 9C0F  2D07 B9F8 1A68 A932 3DEC
uid                              Henry Dorsett Case <case@example.tld>
sub   cv25519/0x91E8295CB0656BF3 2020-12-20 [E]

```

First, it asks for what kind of key we want, in this case, we want a
ECC and ECC key so we input 9, then it ask for which kind of curve we
want, in this case, Curve 25519. Next, it asks for an expiration date,
this is optional, if you don't want your key to expire, just input 0.

Then it asks for the user data, this is only used for making things
easier at encrypting documents to you, but they can be completely
fake.

It will ask for a passphrase, this passphrase will be used to do
sensitive things with your private key, such as signing, decrypting
and exporting the private key itself.

This is a security layer, so if someone with physical access to your
computer wants to steal your private key, they will need the
passphrase.

For generating RSA keys, the process is quite similar:

```
> gpg --full-generate-key --expert
Please select what kind of key you want:
   (1) RSA and RSA (default)
   (2) DSA and Elgamal
   (3) DSA (sign only)
   (4) RSA (sign only)
   (7) DSA (set your own capabilities)
   (8) RSA (set your own capabilities)
   (9) ECC and ECC
  (10) ECC (sign only)
  (11) ECC (set your own capabilities)
  (13) Existing key
  (14) Existing key from card
Your selection? 1
RSA keys may be between 1024 and 4096 bits long.
What keysize do you want? (3072) 4096
Requested keysize is 4096 bits
RSA keys may be between 1024 and 4096 bits long.
What keysize do you want for the subkey? (3072) 4096
Requested keysize is 4096 bits
Please specify how long the key should be valid.
         0 = key does not expire
      <n>  = key expires in n days
      <n>w = key expires in n weeks
      <n>m = key expires in n months
      <n>y = key expires in n years
Key is valid for? (0) 
Key does not expire at all
Is this correct? (y/N) y

GnuPG needs to construct a user ID to identify your key.

Real name: Armitage
Email address: armitage@example.tld
Comment: 
You selected this USER-ID:
    "Armitage <armitage@example.tld>"

Change (N)ame, (C)omment, (E)mail or (O)kay/(Q)uit? o
We need to generate a lot of random bytes. It is a good idea to perform
some other action (type on the keyboard, move the mouse, utilize the
disks) during the prime generation; this gives the random number
generator a better chance to gain enough entropy.
We need to generate a lot of random bytes. It is a good idea to perform
some other action (type on the keyboard, move the mouse, utilize the
disks) during the prime generation; this gives the random number
generator a better chance to gain enough entropy.
gpg: key 0xC3ACA43D3F305D1A marked as ultimately trusted
public and secret key created and signed.

pub   rsa4096/0xC3ACA43D3F305D1A 2020-12-20 [SC]
      Key fingerprint = E9D0 9458 0092 935B 3106  F4DE C3AC A43D 3F30 5D1A
uid                              Armitage <armitage@example.tld>
sub   rsa4096/0xAD836B00A11253F0 2020-12-20 [E]

```

This key will take a long time to generate, because it has to generate
a very large prime number rather than some weird elliptic curve.

# Sharing keys

So now that you have your pgp key pair, you'd to share your public
key, so people can use it to encrypt documents, and verify your
signatures. To get your public key, run `gpg --export --armor <YOUR
EMAIL/NAME/KEYID>`

```
> gpg --export --armor case@example.tld 
-----BEGIN PGP PUBLIC KEY BLOCK-----

mDMEX9+7wBYJKwYBBAHaRw8BAQdABLut6LCIMHReK/K9vq5sTavwgDG1oT1RrEBJ
UF+ECC20JUhlbnJ5IERvcnNldHQgQ2FzZSA8Y2FzZUBleGFtcGxlLnRsZD6IjwQT
FgoANxYhBJWxlFw9D4w0nA8tB7n4GmipMj3sBQJf37vAAhsDBQsJDQgMBRUKCQgL
BBYCAwACHgECF4AACgkQufgaaKkyPewaVwEAnDJMiXSoWU1iMcVnDuYkJJ7hoUM+
/BDx0FTE4Ojo9bABANK5p68s8lUoB+DojfcqLZeC54QlpvL2ihJ6DRp5hgwIuDgE
X9+7wBIKKwYBBAGXVQEFAQEHQLRWg6LC2QhIr+Wc9wFMrbLZxrT885OWGir83dvw
FlMcAwEIB4h4BBgWCgAgFiEElbGUXD0PjDScDy0HufgaaKkyPewFAl/fu8ACGwwA
CgkQufgaaKkyPexVdgEAhqe/3a0vQKUhQrVlb8Aj++znpPt4+/x2YIof7yx/vA4A
/0/aU7DSZUkfmRzEWUPX9DeUJsyq+ZINHhlVYBJenw4L
=qgZB
-----END PGP PUBLIC KEY BLOCK-----
```

You can share that key anywhere, even in an insecure wey because it is
a public key.

To import someone else's key, you have to save it in a file, (for
example, key.asc) and import it: `gpg --import key.asc` and you will
be able to use that key to verify and encrypt documents

# Encrypting documents

Now that you have someone's key, you'd me able to use it to encrypt
files. To do this, simply run `gpg --encrypt --armor -r
someone@example.tld file_to_encrypt`

That will generate an .asc file, which you'll send to the destinatary
any way, even insecure, only the user with the private key will be
able to read it

```
> gpg --encrypt --armor -r case test

> cat test.asc           
-----BEGIN PGP MESSAGE-----

hF4D+BbxzjxcLnUSAQdAbLFYeelDaKxyo+aALCnvI2gEjt6enHjDniw8KBJAjlkw
bp+ZnupC9t04oy3x6bZdEcTIB0yCAnntQflTS/5PqfEfil7rvaimIlG9tcAMR6r2
0k4B53r3wfDg0Zv+0MtJm+XWhBpJgZUa3wgl3g57Z1HeQV1VPhj4usXYp98nGrMf
tkbc337w9t1JfIVIERHYi6Cyn0BkMReiLVJd1bBHUDU=
=qiRX
-----END PGP MESSAGE-----

```

Note that **only** Case will be able to decrypt the file, not even
you.

# Decrypting documents

Now that you've sent Case test.asc (which contents are the text
above), he will just run `gpg --decrypt test.asc`, it will give the
following output

```
> gpg --decrypt test.asc                        
gpg: encrypted with 256-bit ECDH key, ID 0x91E8295CB0656BF3, created 2020-12-20
      "Henry Dorsett Case <case@example.tld>"
this is a test file
```

If you try to run `gpg --decrypt` with the test.asc above, you won't
be able to decrypt it because you don't have Case's private key.

# Signing documents

You've learn how to encrypt documents, but how can we be sure that the
person who sent the file is actually who they claim to be? This is
what signatures are for. To encrypt and sign a document, simply run
`gpg --encrypt --armor --sign -r email file`

```
> gpg --local-user case@example.tld --encrypt --armor --sign -r
armitage testfile

> cat testfile.asc
-----BEGIN PGP MESSAGE-----

hQIMA62DawChElPwAQ//eDW5mc/0Zf6TVp6eNlwqmsTFx7IXQPE40RRTrQqEOEJo
GrpH09QhZGN4gjqKv+ujMVvo8O8D6tr0Cn1EO0X5JEVn2H7bVr18V0HubLDpCOQv
R9OfH3a52YuOI5kgTmdiPWH25dKPqaDfyDux49J2LUZvufO8rPPqKOhM9jSY3vij
JKu+WZ9PbG/iglsxOtwpdE/Fw6DOMxe7BUUKfAWb104j6XL26YZR39JkUFNO9ZxP
ugt0OrPbEH9NKaYSXVrUkl3CN/pUYu/OL4OwNeKWmQPQV5lShyCemy0ZrCQ2DfrU
vaKiX5Yc0qZzz9cTzpQe/r6LFCKYgrnVPhdC0NgwVOcJ0F5odb6x7LPmDRXAevJG
Lko96qFalnOUKxCxU3QK3XlPVtJb+lIkoGFTKDee0/ef8y9JXZVe8Ea3BfgExPEX
nHaWCUSURkpsK4ry24Welgm+Ry4P/G/xY1oqSWpQbvm5igf0KpTNjKV8chfYPGtS
7bvCguOTjiWdFD/9meuHuGyOyAVSe0lieHK7v2BtUI/moe33uFMng7CaY1NeL+z3
mk9M1OEPKas4BFl3JmZfzO8Q238C/sqbYBC1ZSJp24Q2FFS+VZHHA2rRbZDOAgmK
aCvRe0stOJ7cwoXaYliEPDAcpNtwKeIbaLr1eDvODMJeigUQpBHD01X/rYySuRrS
wCYBASYhCkxLyUjEX4/VkhBNdF/IEv4xxfeEmHQ01YNtgzfXhtGEjx1Y6TglRcnY
cHDh5tnzEkejvtrVJ1co2Ba39cPkMDyYrumSv61ydbHsUYDHbTvS2GLzNta0pQCZ
7wuGXhy+kD0tnhvi+OpE5PspihZfWnNjOUdzHjFinWML/YmNzEwddONKkhZ5ULSh
oZKy7c5txMbYti2RocuQ9Zn+edJEZlhx5pCroVKFTjajODJxtQ9KeNJgT0dSf8+r
0vZaTTQsF4qCQvi1vs+wYvYS2fIGkwaJt+eZgKydUYnNEr/0fD7WcQ==
=RJiZ
-----END PGP MESSAGE-----

```

This message is both encrypted and signed, so when Armitage decrypts
it, he will get this:

```
gpg: encrypted with 4096-bit RSA key, ID 0xAD836B00A11253F0, created 2020-12-20
      "Armitage <armitage@example.tld>"
this is another test filegpg: Signature made Sun 20 Dec 2020 10:17:23 PM CET
gpg:                using EDDSA key 95B1945C3D0F8C349C0F2D07B9F81A68A9323DEC
gpg:                issuer "case@example.tld"
gpg: Good signature from "Henry Dorsett Case <case@example.tld>" [ultimate]
Primary key fingerprint: 95B1 945C 3D0F 8C34 9C0F  2D07 B9F8 1A68 A932 3DEC

```
Note the "Good Signature" part.

## Signing text and... that's it

If you want to make a public announcement and want to give the readers
the posibility to know that you're who you claim to be, you use the
--clear-sign flag

```
> gpg --clear-sign file
> cat file.asc
-----BEGIN PGP SIGNED MESSAGE-----
Hash: SHA512

this is a clearsigned file
-----BEGIN PGP SIGNATURE-----

iIcEARYKAC8WIQSVsZRcPQ+MNJwPLQe5+BpoqTI97AUCX9+/+hEcY2FzZUBleGFt
cGxlLnRsZAAKCRC5+BpoqTI97KpjAP9irmPTgqwbxuUDTR6Fxdn2b5HgyC7Z/A1I
LYHxnQ3F6wEArui4nW4vsm95kUO9CRrZOZwHLcj7EKo4cPhTGjw+SQg=
=RAcs
-----END PGP SIGNATURE-----

```

Anyone who wants to know that the message was written for who they
claim to be, would have to simply run `gpg --verify file.asc`:

```
> gpg --verify file.asc                              
gpg: Signature made Sun 20 Dec 2020 10:19:54 PM CET
gpg:                using EDDSA key 95B1945C3D0F8C349C0F2D07B9F81A68A9323DEC
gpg:                issuer "case@example.tld"
gpg: Good signature from "Henry Dorsett Case <case@example.tld>" [ultimate]
Primary key fingerprint: 95B1 945C 3D0F 8C34 9C0F  2D07 B9F8 1A68 A932 3DEC
gpg: WARNING: not a detached signature; file 'file' was NOT verified!

```

## Signing files

This can be useful while distributing software, so the downloader know
that the file hasn't been modified or compromised, software like apt
and xbps do this to check that the file they're downloading hasn't
been modified.

```
gpg --detach-sign --armor file
> cat file.asc
-----BEGIN PGP SIGNATURE-----

iIcEABYKAC8WIQSVsZRcPQ+MNJwPLQe5+BpoqTI97AUCX9/BVhEcY2FzZUBleGFt
cGxlLnRsZAAKCRC5+BpoqTI97HKbAP4mkamBGFMQVd0sPWO1M9iuFKGWH0OiD/s8
PDdCzxt9oAEAo0Y/Z6+2r2XoaiQdk6C4wzOJeheZA8qJf5GNp3PPQg0=
=7yIi
-----END PGP SIGNATURE-----

```

It is verified the same way: `gpg --verify file.asc`

```
> gpg --verify file.asc                                       
gpg: assuming signed data in 'file'
gpg: Signature made Sun 20 Dec 2020 10:25:42 PM CET
gpg:                using EDDSA key 95B1945C3D0F8C349C0F2D07B9F81A68A9323DEC
gpg:                issuer "case@example.tld"
gpg: Good signature from "Henry Dorsett Case <case@example.tld>" [ultimate]
Primary key fingerprint: 95B1 945C 3D0F 8C34 9C0F  2D07 B9F8 1A68 A932 3DEC

```

If you're wondering what's the difference between `--clear-sign` and
`--detach-sign`, the first is mostly used for plain text documents and the
other for binary files. Such as .iso and .tar files.

Anyone who wants to verify a file signed by you, needs your public
key.

# Configuring software to use pgp

TODO

# pgp in android

TODO
