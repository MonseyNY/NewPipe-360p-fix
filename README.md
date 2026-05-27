# NewPipe 360p Fix

**Temporary patched build of [NewPipe](https://github.com/TeamNewPipe/NewPipe) 0.28.7 that fixes YouTube videos being stuck at 360p.**

## The Problem
YouTube started enforcing a new streaming protocol (SABR) on standard clients, which removes traditional stream URLs from adaptive formats. This leaves NewPipe with only the 360p progressive stream — no 720p, 1080p, or higher.

## The Fix
This fork adds an **ANDROID_VR client** (Oculus Quest 3) as a fallback. YouTube still serves traditional stream URLs to this client, restoring all quality options.

Changes made:
- **NewPipeExtractor**: Added ANDROID_VR client with SABR-only detection and automatic fallback
- **NewPipe**: Added AV1 video itags (394-401) and audio itags (599, 600) to the supported list

## Install
Download the APK from the [Releases](https://github.com/MonseyNY/NewPipe-360p-fix/releases) page.

This build uses a different package name (`org.schabi.newpipe.fix360`) and shows as **"NewPipe Fix"** in your app drawer. This means you can install it right alongside the official NewPipe app without uninstalling — both apps will work independently on your device.

## Status
A PR has been submitted to the official repos:
- **Extractor PR**: [NewPipeExtractor#1498](https://github.com/TeamNewPipe/NewPipeExtractor/pull/1498)
- **Tracking issue**: [NewPipe#13320](https://github.com/TeamNewPipe/NewPipe/issues/13320)

Once the official fix is released, uninstall this and switch back to the official NewPipe.
