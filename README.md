# djm-s6-upgrade

Test repository for upgrading
[s6-overlay](https://github.com/just-containers/s6-overlay) in
[docker-jitsi-meet](https://github.com/jitsi/docker-jitsi-meet).

### Configuring

Create the locale folders on the host machine:

```bash
mkdir -p ~/.jitsi-meet-cfg/prosody/{config,prosody-plugins-custom}
mkdir -p ~/.jitsi-meet-cfg/{jibri,jicofo,jigasi,jvb,web}

mkdir -p ~/.jitsi-meet-cfg/storage/{jibri,transcripts}
chmod 777 ~/.jitsi-meet-cfg/storage/jibri
chmod 777 ~/.jitsi-meet-cfg/storage/transcripts

mkdir -p ~/.jitsi-meet-cfg/tmp/{web-crontabs,web-load-test}
chmod 777 ~/.jitsi-meet-cfg/tmp/web-crontabs
chmod 777 ~/.jitsi-meet-cfg/tmp/web-load-test
```

Create and update `.env`:

```bash
cp env.example .env
./gen-passwords.sh
```

Add some additional values into `.env` depending on the environment:

```bash
PUBLIC_URL=https://172.18.18.1:8443
JVB_ADVERTISE_IPS=172.18.18.1
```

Pull images:

```bash
docker compose -f docker-compose.yml -f jigasi.yml -f jibri.yml pull
```

### Running

```bash
docker compose -f docker-compose.yml up
```

### Stopping

```bash
docker compose -f docker-compose.yml down --remove-orphans
```
