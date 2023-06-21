# Scripts

Various shell scripts.

## copycerts
This script copies the letsencrypt certificates for a particular site from one server to another.
Then restarts nginx on that machine.

Usage:
```
 copycerts (FROM) (TO) (SITE)
   FROM - the ssh alias for the machine that the certs are on
   TO   - the ssh alias for the machine that the certs are to be transferred to
   SITE - the domain name for the site under /etc/letsencrypt/live/
```


Remember to update certs on FROM site first:

```bash
sudo certbot -d $SITE -d *.$SITE --preferred-challenges dns --manual certonly
```
or
```bash
sudo certbot --nginx -d $SITE
```

Run this on a local machine with access to both servers.
