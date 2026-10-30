# YouTube Cobalt Plus (webOS)

Community fork of [RF1705/youtube-webos-cobalt-adfree](https://github.com/RF1705/youtube-webos-cobalt-adfree), maintained as a separate app variant for testing on LG webOS 25.

> Unofficial community build. Not affiliated with YouTube, Google, LG, or the upstream project.

## Variant identity

- Display name: **YouTube Cobalt Plus**
- Application ID: `com.alison.youtube.cobaltplus`
- Package version: `2.0.3`
- Target test device: **LG 50NANO77SRA**, firmware **33.31.75**, webOS **25**
- Upstream code base: this fork's `main` snapshot at the time this branch was created. The Cobalt engine and web app sources are retained; only the package identity and this documentation are customized in this branch.

## Important coexistence and casting note

This variant uses a different application ID from the stock YouTube app (`youtube.leanback.v4`). It is intended to install side-by-side and must not replace the stock app.

A custom application ID may prevent the YouTube mobile app from detecting this app as the built-in YouTube receiver for ordinary Cast / phone pairing. Do not assume phone casting, account transfer, or sign-in continuity with the stock app. Test sign-in and playback on the TV itself first. The original app remains available as a fallback.

## Features inherited from upstream

- Cobalt-based YouTube TV application
- Ad blocking
- SponsorBlock
- Return YouTube Dislike
- Automatic account selection
- Playback speed controls (remote keys **1** and **3** during playback)
- Optional Shorts visibility and autostart integration

Feature availability and playback quality depend on the TV platform, firmware, Cobalt runtime and YouTube stream selection. 4K/HDR while playback is accelerated has not been verified on the target TV.

## Build

The repository includes manual GitHub Actions workflows:

1. **Actions → Build starterless Cobalt**: build the Cobalt runtime for the selected Cobalt ref and build type.
2. **Actions → Package starterless Cobalt IPK**: enter the successful runtime workflow run ID to package the app using the identity in `starterless-cobalt/appinfo.json`.

Use the same fork branch for both workflows. Keep debug options disabled for a normal test build. Verify the resulting IPK metadata and SHA-256 before installing.

## Safety and testing

- Do not install an IPK whose app ID is `youtube.leanback.v4` if the goal is side-by-side coexistence.
- Do not uninstall or overwrite the stock YouTube app as part of this test.
- Verify package contents, app ID, executable permissions, runtime libraries and checksum before installation.
- No claim is made that the build is malware-free solely because it compiles or passes CI; review dependencies and generated artifacts separately.

## Upstream

- Source: https://github.com/RF1705/youtube-webos-cobalt-adfree
- Upstream license files in this repository continue to apply. Preserve upstream attribution and license notices.
