# Questions

## base

- Is it still needed to overwrite `/etc/localtime` and `/etc/timezone`.
  Isn't it enough to set `TZ`?

## base-java

- Is it needed to create `/usr/share/man/man1` manually?
- Is `unzip` needed? If needed, put it into `base`
- Why `nodejs` in `base-java`? For `sidecar`..?

## web

- jaas-account with /run/web/config/jaas-account-created.txt

## jibri

- /run/jibri/logs instead of /config/logs
  Is this a problem? tmpfs vs mounted folder
- Looks like `CAPS_SYS_ADMIN` is not needed anymore
