# Verifying PGP Key Fingerprint
Installing arch-linux, when I ran the command: `gpg --keyserver-options auto-key-retrieve --verify archlinux-2023.03.01-x86_64.iso.sig`
I got a response like:
```
michael@zeus:Downloads$ gpg --keyserver-options auto-key-retrieve --verify archlinux-2023.03.01-x86_64.iso.sig
gpg: assuming signed data in 'archlinux-2023.03.01-x86_64.iso'
gpg: Signature made Wed 01 Mar 2023 04:55:51 AM PST
gpg:                using EDDSA key 3E80CA1A8B89F69CBA57D98A76A5EF9054449A5C
gpg:                issuer "pierre@archlinux.org"
gpg: Good signature from "Pierre Schmitz <pierre@archlinux.org>" [unknown]
gpg: WARNING: This key is not certified with a trusted signature!
gpg:          There is no indication that the signature belongs to the owner.
Primary key fingerprint: 3E80 CA1A 8B89 F69C BA57  D98A 76A5 EF90 5444 9A5C
```
Still, I am kind of a newb when it comes to security so I wanted to take extra
measures to verify. On https://archlinux.org/download/#checksums, I was able to
see the following verification command:
```
gpg --auto-key-locate clear,wkd -v --locate-external-key pierre@archlinux.org
```
Which, when run yields:
```
gpg: using pgp trust model
gpg: pub  rsa2048/7F2D434B9741E8AC 2011-04-10  Pierre Schmitz <pierre@archlinux.de>
gpg: key 7F2D434B9741E8AC: "Pierre Schmitz <pierre@archlinux.org>" not changed
gpg: pub  ed25519/76A5EF9054449A5C 2022-10-31  Pierre Schmitz <pierre@archlinux.de>
gpg: key 76A5EF9054449A5C: "Pierre Schmitz <pierre@archlinux.org>" not changed
gpg: Total number processed: 2
gpg:              unchanged: 2
gpg: auto-key-locate found fingerprint 4AA4767BBC9C4B1D18AE28B77F2D434B9741E8AC
gpg: automatically retrieved 'pierre@archlinux.org' via WKD
pub   rsa2048 2011-04-10 [SC]
      4AA4767BBC9C4B1D18AE28B77F2D434B9741E8AC
uid           [ unknown] Pierre Schmitz <pierre@archlinux.org>
sub   rsa2048 2011-04-10 [E]
```
You can see there are two key IDs here: "7F2D434B9741E8AC" and "76A5EF9054449A5C"

Now you can run:
```
for i in 7F2D434B9741E8AC 76A5EF9054449A5C;do echo $i && gpg --fingerprint $i;done
```

Which yields:
```
7F2D434B9741E8AC
pub   rsa2048 2011-04-10 [SC]
      4AA4 767B BC9C 4B1D 18AE  28B7 7F2D 434B 9741 E8AC
uid           [ unknown] Pierre Schmitz <pierre@archlinux.org>
sub   rsa2048 2011-04-10 [E]

76A5EF9054449A5C
pub   ed25519 2022-10-31 [SC] [expires: 2037-10-27]
      3E80 CA1A 8B89 F69C BA57  D98A 76A5 EF90 5444 9A5C
uid           [ unknown] Pierre Schmitz <pierre@archlinux.org>
sub   ed25519 2022-10-31 [A] [expires: 2037-10-27]
sub   cv25519 2022-10-31 [E] [expires: 2037-10-27]
```

You can see that one of the verified keys "76A5EF9054449A5C" has a matching
fingerprint from the first command:
```
76A5EF9054449A5C
pub   ed25519 2022-10-31 [SC] [expires: 2037-10-27]
      3E80 CA1A 8B89 F69C BA57  D98A 76A5 EF90 5444 9A5C

...
...
Primary key fingerprint: 3E80 CA1A 8B89 F69C BA57  D98A 76A5 EF90 5444 9A5C
```


## Tags
#pgp
