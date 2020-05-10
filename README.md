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

<br>

[![Get it from the Snap Store](https://snapcraft.io/static/images/badges/en/snap-store-white.svg)](https://snapcraft.io/janus-gateway)
