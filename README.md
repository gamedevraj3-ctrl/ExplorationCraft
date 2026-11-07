# ExplorationCraft Unity Build

This repository contains the AssetRipper-reconstructed Unity project in `ExplorationCraft_FlightMode_Updated.zip` and GitHub Actions workflows for an Android ARM64 build.

## Required Unity license setup

The repository does not store a Unity license file. To authorize GitHub Actions:

1. Open **Actions → Acquire activation request (.alf)** and run it with **Run workflow**.
2. Download the workflow artifact named `Unity-2022.3.62f1-activation-request`.
3. Extract the `.alf` file and submit it at [Unity manual activation](https://license.unity3d.com/manual).
4. Download the returned `.ulf` file.
5. In **Settings → Secrets and variables → Actions**, create a repository secret named `UNITY_LICENSE` and paste the complete `.ulf` file contents into it. Do not commit `.ulf`, `.alf`, Unity passwords, or serials to the repository.
6. Run **Build Android APK (arm64-v8a)** manually from the Actions tab.

The build workflow unpacks the project ZIP, verifies Unity **2022.3.62f1**, builds an ARM64 APK with IL2CPP, and uploads the APK as a workflow artifact. `UNITY_EMAIL` and `UNITY_PASSWORD` are optional fallback secrets for the Unity builder; the preferred path is the `UNITY_LICENSE` secret.

## Important

This is a reconstructed project, not the original Unity source project. The first build may fail on missing or incompatible recovered assets/scripts and may require Unity console fixes. The original APK and preservation export remain unchanged outside this repository.
