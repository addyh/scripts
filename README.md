This script copies the letsencrypt certificates for a particular site from one server to another.
Then restarts nginx on that machine.

Remember to update certs on FROM site first:

```sh
sudo certbot -d $SITE -d *.$SITE --preferred-challenges dns --manual certonly
```
or
```sh
sudo certbot --nginx -d $SITE
```

Run this on a local machine with access to both servers.
