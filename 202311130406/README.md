# PGP Basics

Encrypt a message:
```
gpg --armor --encrypt --recipient <Recipient's Email> <File>
```
Please note that the `--armor` flag will encrypt the message in ASCII format, 
which I somehow prefer for no real reason.

Decrypt a message:
```
gpg -d <File>
```
Usually it will ask you for your passphrase associated with your PGP private key
to decrypt the message.

## Related
[202303080639](../202303080639) - Verifying PGP Key Fingerprint

## Tags
#pgp #encryption
