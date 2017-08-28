# Group Variables for Vagrant build

Put a file named `all` in this directory, containing your AWS credentials in this format:

```
---
AWS_ACCESS_KEY_ID:     <your AWS access key ID>
AWS_SECRET_ACCESS_KEY: <your AWS secret key>
```

These will be configured into the Vagrant instance's Boto config.

The repo will ignore this file, so it won't be in version control.
