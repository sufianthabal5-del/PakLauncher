# PakLauncher Android source

- Product name: **PakLauncher**
- Android application ID: `com.pak.launcher` (debug variant adds `.debug`)
- Android namespace retained as `net.kdt.pojavlaunch` to preserve existing Java/resource references.
- Visual direction: near-black surfaces, neon green highlights, white primary text.
- Branding artwork: `PakLauncher-Branding.png`; launcher mark: `app_pojavlauncher/src/main/res/drawable-nodpi/paklauncher_logo.png`.
- GitHub Actions workflow: `.github/workflows/paklauncher-apk.yml` (`workflow_dispatch` or pushes to main/master).

## Build

Run `./gradlew :app_pojavlauncher:assembleRelease`. GitHub Actions downloads the project's external Java 8 runtime artifact and builds the release APK. The workflow uploads `PakLauncher-release.apk` as an Actions artifact.

## Microsoft sign-in configuration

The registered Microsoft Application (client) ID must be added to the native MSAL configuration only after the Android package name and signing-certificate hash are verified. No client secret belongs in this Android app. The ID supplied by the owner is intentionally not duplicated into source until the MSAL redirect/platform settings are confirmed.

## Important

This source tree contains third-party open-source components. Preserve the included license and NOTICE files and comply with each dependency's terms. An APK is not considered tested until the GitHub Actions workflow completes successfully on the owner's repository.
