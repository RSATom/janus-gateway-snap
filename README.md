
[![Get it from the Snap Store](https://snapcraft.io/static/images/badges/en/snap-store-white.svg)](https://snapcraft.io/janus-gateway)

# janus-gateway-snap
Helper repo for build Janus WebRTC Server on build.snapcraft.io

## Directories mappings
* `/opt/janus/lib/janus` -> `$SNAP/opt/janus/lib/janus`
* `/opt/janus/share/janus/streams`-> `$SNAP/opt/janus/share/janus/streams`
* `/opt/janus/etc/janus` -> `$SNAP_COMMON/etc`
* `/opt/janus/share/janus/recordings` -> `$SNAP_COMMON/share/recordings`
* `/opt/janus/share/janus/demos/voicemail` -> `$SNAP_COMMON/share/voicemail`

So you can find:
* Configs in `/var/snap/janus-gateway/common/etc` (i.e. `$SNAP_COMMON/etc`)
* Recordings in `/var/snap/janus-gateway/common/share/recordings` (i.e. `$SNAP_COMMON/share/recordings`)
* Voicemail in `/var/snap/janus-gateway/common/share/voicemail` (i.e. `$SNAP_COMMON/share/voicemail`)

## Some hints
* To install Janus latest stable snap: `sudo snap install janus-gateway`;
* To install Janus edge snap (i.e. built from latest `master`): `sudo snap install janus-gateway --edge`;
* To view Janus log: `sudo snap logs janus-gateway`;
* To view Janus log and wait for new lines: `sudo snap logs janus-gateway -f`;
* For Janus snap restart (required after configs edit): `sudo snap restart janus-gateway`;
* To resolve ["Too many open files"](https://github.com/RSATom/janus-gateway-snap/issues/7) run `systemctl edit snap.janus-gateway.janus-gateway.service` and put there something like:
```
[Service]
LimitNOFILE=65536
```


## Getting Started Guide
1. `sudo apt update`
2. `sudo apt install snapd`
4. Use logs to check if it's running. Many options:
 - `snap list janus-gateway`
 - `sudo snap logs janus-gateway`
 - `sudo snap logs janus-gateway -f`
 - `sudo snap logs janus-gateway -n=all`
 - `sudo systemctl status snap.janus-gateway.janus-gateway.service`
5. Use `sudo lsof -i -P -n | grep janus` to check ports being listened to
6. Open `/var/snap/janus-gateway/common/etc` to view/modify configs
7. Run the demos locally: `cd /snap/janus-gateway/current/opt/janus/share/janus/demos && python -m SimpleHTTPServer 8000`
8. Then visit http://localhost:8000 in your browser.
