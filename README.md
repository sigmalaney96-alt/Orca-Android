![Logo](screenshots/app_icon.png?raw=true "Logo")

# Orca for Android

[![Build Status](https://travis-ci.org/kuoruan/Chromium-Android.svg)](https://travis-ci.org/kuoruan/Chromium-Android) [![Release Version](https://img.shields.io/github/release/kuoruan/Chromium-Android.svg)](https://github.com/kuoruan/Chromium-Android/releases/latest) [![Latest Release Download](https://img.shields.io/github/downloads/kuoruan/Chromium-Android/latest/total.svg)](https://github.com/kuoruan/Chromium-Android/releases/latest)

### Introduction

- Orca is a browser built on the Chromium Android source in this repository.
- All files are from (or generate from) the [Chromium project](https://chromium.googlesource.com/ "Chromium source repo").
- This repository helps you review the most popular browser app on Android.
- You can also build your own Android browser with this repository.

The app uses the existing native Chromium browser UI and rendering engine. The current Orca
changes set the application identity to `com.orca.browser`, use the Abyss palette for native
browser surfaces, and add a branded hero to Chromium's native New Tab page while retaining its
search box and site tiles. Tabs, bookmarks, history, and downloads remain native Chromium
features. The project remains on Chromium 73, Android Gradle Plugin 3.3.2, Gradle 4.10.1, and
target SDK 28. The newer Orca settings pages, Ecosia default search, tracker blocking, site
permission manager, and Bit-Swapper game are not implemented.

The `Build Orca APK` GitHub Actions workflow builds debug and release APKs and publishes them as
`Orca-debug-apk` and `Orca-release-apk-unsigned`. The release artifact is unsigned because no
production signing key is configured; it is not ready for Play Store distribution or installation
as a production update until signed with the owner's key. The project remains on target SDK 28 and
only packages 32-bit ARM native libraries, so it is not Play Store-ready and may not run on
64-bit-only devices. The build fetches the archived Google VR SDK AAR from its official upstream
repository at a pinned commit and verifies its SHA-256 checksum; local builds must place the same
AAR under `app/libs/`.

### Start Working

Check out this repository and open the project with [Android Studio](https://developer.android.com/studio/index.html "Download Android Studio").

Now you can build, run, debug as a normal android project.

Notice: If you have something wrong with build, try close instant run in Android Stuido settings.

### Screenshots

![Welcome](screenshots/welcome.png?raw=true "Welcome") ![App Home](screenshots/app_home.png?raw=true "App Home")

![Html5 Score](screenshots/html5_score.png?raw=true "Html5 Score") ![Video Play](screenshots/video_play.png?raw=true "Video Play")

### Source Update

If you want to update Chromium source, these steps may help:

1. [Checking out and building Chromium for Android](https://chromium.googlesource.com/chromium/src/+/master/docs/android_build_instructions.md), to match our build settings, use [tools/args.gn](tools/args.gn)
2. Generate files for Android Studio with offical guide: [Android Studio](https://chromium.googlesource.com/chromium/src/+/master/docs/android_studio.md)

	- After that, you can find some ```build.gradle``` files in ```[BUILD_TARGET]/gradle```, which defines the Java sources for Chromium.

3. Try sync files with script: [tools/sync_chromium.sh](tools/sync_chromium.sh)

	- Replace `BASE_DIR` in script with your Chromium src dir.
	- Replace `RELEASE_DIR` in script with your build dir.
	- `PRO_DIR` is the dir where new files will copied to.
	- **Sync script may out of date that you need modify it yourself**.

4. Finally, replace all files in this project with the new files.

### Thanks

This project is based on:

- [https://github.com/JackyAndroid/AndroidChromium](https://github.com/JackyAndroid/AndroidChromium)
- [https://github.com/mogoweb/365browser](https://github.com/mogoweb/365browser)

### Copyright & License

Please see [LICENSE](https://chromium.googlesource.com/chromium/src/+/master/LICENSE).
