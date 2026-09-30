# pkgbuilds

My Arch Linux PKGBUILDs: AUR packages I maintain and private patched
packages. Used as a [paru](https://github.com/Morganamilo/paru) PKGBUILD
repository by [norisa](https://github.com/noahvogt/norisa):

```ini
# /etc/paru.conf
[pkgbuilds]
Url = https://github.com/noahvogt/pkgbuilds.git
SkipReview
```

## Packages

| package | description |
| --- | --- |
| fluffychat-color-emoji | fluffychat with Noto Color Emoji in flutter's font fallback list (not on the AUR) |
| openconnect-ms-auth | fetches an openconnect webvpn cookie from an MFA enabled Microsoft account ([fork](https://github.com/noahvogt/openconnect-ms-auth)) |

## Updates

A daily workflow (`.github/workflows/check-updates.yml`) opens a PR when

- upstream releases a new version (sources in `nvchecker.toml`): bumps
  `pkgver`, checksums and `.SRCINFO`, and checks that `prepare()` still
  applies all patches
- the AUR package a PKGBUILD is forked from (`<pkg>/.aur-upstream`) gets new
  commits: the PR shows the diff to port by hand

## Scripts

- `scripts/import-aur <pkg>`: import an AUR package with its history
- `scripts/publish-aur <pkg>`: push a package directory to its AUR repo
- `scripts/bump <pkg> <version>`: bump a package to a new version
