[![Snap Status](https://build.snapcraft.io/badge/RSATom/janus-gateway-snap.svg)](https://build.snapcraft.io/user/RSATom/janus-gateway-snap)

# janus-gateway-snap
Helper repo for build Janus WebRTC Server on build.snapcraft.io

## Directories mapping
* Configs: `$SNAP_COMMON/etc` (`/var/snap/janus-gateway/common/etc`)
* Recordings: `$SNAP_COMMON/share/recordings` (`/var/snap/janus-gateway/common/share/recordings`)
* Voicemail: `$SNAP_COMMON/share/voicemail` (`/var/snap/janus-gateway/common/share/voicemail`)

## Some hints

* Install Janus latest stable snap: `sudo snap install janus-gateway`;
* Install Janus edge snap (i.e. built from latest `master`): `sudo snap install janus-gateway --edge`;
* View Janus log: `sudo snap logs janus-gateway`;
* View Janus log and wait for new lines: `sudo snap logs janus-gateway -f`;
* Janus snap configs directory: `/var/snap/janus-gateway/common/etc/`;
* Janus snap restart (required after configs edit): `sudo snap restart janus-gateway`;

## Getting Started Guide
1. `sudo apt update`
2. `sudo apt install snapd`

3. Do you need data channel support?
- Y:  stable doesn't have it. See [this discussion](https://github.com/RSATom/janus-gateway-snap/issues/9). If you can deal with daily restarts (e.g., just local testing), then `sudo snap install janus-gateway --edge` will have it. For prod environments, either switch it to dev mode to stop updates, or create your own snap.
- N:  `sudo snap install janus-gateway` 

4. `sudo systemctl status snap.janus-gateway.janus-gateway.service` (verify it's running)
5.  `sudo lsof -i -P -n | grep janus` (check ports being listened to)
6.  `sudo nano /var/snap/janus-gateway/common/etc` to modify config values
7. If you want to run a local demo, clone the original meetecho repo down to get the 'html' folder from there. Then run a simple local server to access the files on localhost. So:
```
cd ~/where_you_keep_your_cloned_repos
git clone https://github.com/meetecho/janus-gateway.git
cd janus-gateway/html
```
Then visit http://localhost:8000/ in your browser.




<br>

[![Get it from the Snap Store](https://snapcraft.io/static/images/badges/en/snap-store-white.svg)](https://snapcraft.io/janus-gateway)
