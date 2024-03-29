Based on Peter Oliver's auto.cifs, modified to authenticate only using Kerberos.

## Usage

```
# /etc/auto.master

/cifs      /etc/auto.krb5.cifs
```

where `/etc/auto.krb5.cifs` is the file from this repo.

Access to e.g. `/cifs/earth:arthur$:arthur` will mount CIFS share `arthur$` from fileserver `earth` as user `arthur`,
provided the user holds a Kerberos ticket that grants access.  See `kinit`.

Creating symlinks into `/cifs` makes this easier.

Various paths are supported:

```
host:share
host:share:user
host:share:localuser:remoteuser
host:share:localuser:remoteuser:extra_mount_options
```
