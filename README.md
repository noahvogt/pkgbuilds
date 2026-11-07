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
| chromium-extension-return-youtube-dislike | [Return YouTube Dislike](https://github.com/Anarios/return-youtube-dislike), preinstalled for chromium |
| chromium-extension-rggl | [Remove German Gender Language](https://github.com/motsiw/rggl), preinstalled for chromium |
| fluffychat-color-emoji | fluffychat with Noto Color Emoji in flutter's font fallback list (not on the AUR) |
| issuu-dl | downloader for issuu.com with pdf and cbz output ([own project](https://github.com/noahvogt/issuu-dl)) |
| libva-v4l2_request-asahi | VA-API driver for the Apple Silicon video decoder ([asahi-va-driver](https://github.com/sofus13/libva-v4l2_request)) |
| openconnect-ms-auth | fetches an openconnect webvpn cookie from an MFA enabled Microsoft account ([fork](https://github.com/noahvogt/openconnect-ms-auth)) |
| tibasicc | TI-BASIC (de-)compiler ([own project](https://github.com/noahvogt/tibasicc)) |
| tibasicc-git | tibasicc, git version |
| tilp-xdg | TI calculator link program, patched to follow the XDG Base Directory spec (fork of AUR tilp) |

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
