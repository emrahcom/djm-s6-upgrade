# djm-s6-upgrade

Test repository for upgrading
[s6-overlay](https://github.com/just-containers/s6-overlay) in
[docker-jitsi-meet](https://github.com/jitsi/docker-jitsi-meet).

## Running

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
