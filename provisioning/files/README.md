# Files for Vagrant provisioning

Put a file named `awsprivatekey.txt` in this directory, containing your AWS key pair's private key in this format:

```
-----BEGIN RSA PRIVATE KEY-----
<private key contents>
-----END RSA PRIVATE KEY-----
```

This will be configured into the Vagrant instance's SSH config as the default key.

The repo will ignore this file, so it won't be in version control.
