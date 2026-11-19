# Tadbir — Android developer APK

This repository contains the **build pipeline**, but the complete Android source has **not yet been pushed**.

The source snapshot is the clean Tadbir Aegis V3 developer archive dated 2026-11-19 (SHA-256 of the source ZIP: `863b90cd622ccf8aa4a6f6bbca8e555d22c31d32f548afda15b2aa124d58b508`). The source package is provided in the associated ChatGPT conversation. Do not substitute an older archive.

## Import and build

1. Download `Tadbir_Aegis_V3_GitHub_Ready_Complete_Source_2026-11-19.zip` from the conversation and extract it.
2. Install Git and Git LFS and authenticate to GitHub as the repository owner.
3. From the extracted directory run `bash PUBLISH_TO_GITHUB.sh` (Linux/macOS) or `./PUBLISH_TO_GITHUB.ps1` (PowerShell).
4. The push to `main` starts [Android APK — Tadbir (developer build)](../../actions/workflows/android-apk.yml) automatically. Download the artifact `tadbir-android-development-signed-apk` after a successful run.

Build parameters: Java 17, Gradle 8.11.1, AGP 8.10.1, compileSdk 36, uber-apk-signer 1.3.0. The workflow verifies signature, zip alignment, manifest package `ma.tadbir.web`, minimum SDK 26, ZIP integrity and SHA-256.

The APK is **development signed**. It will not update an installed APK signed with a different certificate. Do not uninstall a version holding user data unless it has been backed up.

### Status

The presence of this workflow does not prove a successful APK build; check the run logs and artifacts. The upstream source does not include GGUF weights or the separately stored original legal PDFs.
