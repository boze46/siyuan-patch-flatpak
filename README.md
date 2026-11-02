# siyuan-patch-flatpak

Flatpak packaging for the community-patched SiYuan build
([MohamedElashri/siyuan-patch](https://github.com/MohamedElashri/siyuan-patch)),
built and published automatically by GitHub Actions.

Manifest adapted from [flathub/org.b3log.siyuan](https://github.com/flathub/org.b3log.siyuan).
App ID `io.github.MohamedElashri.SiYuan` so it can coexist with the official Flathub build.

## Install (flatpak remote — recommended, gets auto-updates)

```sh
flatpak remote-add --user siyuan-patch https://boze46.github.io/siyuan-patch-flatpak/siyuan-patch.flatpakrepo
flatpak install --user siyuan-patch io.github.MohamedElashri.SiYuan
```

Requires the `flathub` remote to be configured (for the freedesktop runtime and
the Electron base app). Afterwards `flatpak update` picks up new builds
automatically; daily checks against the fork's latest release at 21:17 UTC.

## Install (single-file bundle, no remote)

Grab `siyuan-patch-<version>-x86_64.flatpak` from
[Releases](https://github.com/boze46/siyuan-patch-flatpak/releases), then:

```sh
flatpak install --user ./siyuan-patch-<version>-x86_64.flatpak
```

Updating means installing the newer bundle file over the old one.

## Notes

- The published OSTree repo is **not GPG-signed**; integrity relies on HTTPS
  transport plus OSTree content checksums. Fine for personal use.
- The fork occasionally re-publishes the same version tag with rebuilt assets,
  so CI compares content hashes, not just the version number.
- Scheduled workflows on GitHub are auto-disabled after ~60 days without repo
  activity; re-enable in the Actions tab if that happens.
