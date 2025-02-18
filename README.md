# djm-s6-upgrade

Test repository for upgrading
[s6-overlay](https://github.com/just-containers/s6-overlay) in
[docker-jitsi-meet](https://github.com/jitsi/docker-jitsi-meet).

### Configuring

Create the locale folders on the host machine:

```bash
mkdir -p ~/.jitsi-meet-cfg/prosody/{config,prosody-plugins-custom}
mkdir -p ~/.jitsi-meet-cfg/{jicofo,jigasi,jvb,transcripts,web}
chmod 777 ~/.jitsi-meet-cfg/transcripts

mkdir -p ~/.jitsi-meet-cfg/crontabs/web
chmod 777 ~/.jitsi-meet-cfg/crontabs/web

mkdir -p ~/.jitsi-meet-cfg/test/web
chmod 777 ~/.jitsi-meet-cfg/test/web

mkdir -p ~/.jitsi-meet-cfg/jibri/{logs,recordings}
chmod 777 ~/.jitsi-meet-cfg/jibri/{logs,recordings}
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
