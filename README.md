# Le Tiroir Admin releases

Download and auto-update artifacts for Le Tiroir Admin, the macOS editor for the
Le Tiroir capsule site. The app source stays private; this repository only holds
what an installed copy needs.

## Download

Grab the DMG from the [latest release](https://github.com/stunti/le-tiroir-admin/releases/latest).

## How updates work

On launch the app reads
`https://github.com/stunti/le-tiroir-admin/releases/latest/download/latest.json`,
compares the version with its own, and if a newer one exists it downloads the
`.app.tar.gz` bundle, verifies its minisign signature, replaces the app in
`/Applications` and restarts.

Each release contains:

- the DMG, for a fresh install;
- `Le-Tiroir-Admin_<version>_<arch>.app.tar.gz` and its `.sig`, for the updater;
- `latest.json`, the manifest the app reads.

Releases are built and published by `scripts/release.sh` in the app repository.
