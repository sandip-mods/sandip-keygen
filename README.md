# ⚡ SANDIP KEYGEN

<p align="center">
  <img src="sandip.png" alt="Sandip Keygen Logo" width="160"/>
</p>


<p align="center">
  <b>High-Performance Key Management Portal & Cloud-Synchronized Android Application</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Version-v1.0.5-00e5ff?style=for-the-badge" alt="Version">
  <img src="https://img.shields.io/badge/Platform-Android_5.0+-3DDC84?style=for-the-badge&logo=android&logoColor=white" alt="Platform">
  <img src="https://img.shields.io/badge/Target_SDK-34-black?style=for-the-badge" alt="Target SDK">
  <img src="https://img.shields.io/badge/Architecture-ARM64--v8a-ff0055?style=for-the-badge" alt="Architecture">

</p>

---

## 📖 Overview

🔑 **SANDIP KEYGEN** — A streamlined key retrieval utility for the Aincrad Client, developed by [@AincradMods](https://t.me/AincradMods).

* 🌐 **Key Generation Portal**: [https://aincradmods.com/getkey](https://aincradmods.com/getkey)
* ⚙️ **Core Functionality**: Simplifies the process of retrieving authentication keys required to access the Aincrad Client.
* 🚀 **Developed & Maintained by**: **SANDIP MOD'S**
* ✨ Designed for a convenient, efficient, and user-friendly key retrieval experience.

---

Built with a deeply optimized native layer, hardware-accelerated haptics, and a pitch-black AMOLED interface, it delivers an ultra-smooth and secure user experience. The app also features a **Real-Time Cloud Synchronization Engine** that enables on-the-fly maintenance scheduling, live estimated duration streaming, and zero-restart instant access restoration.

---

## ✨ Key Features

### 🛠️ Real-Time Cloud Maintenance System
- **Instant Auto-Dismiss**: When `maintenance: false` is updated on GitHub, the app auto-dismisses the maintenance page within **~3.5 seconds** without requiring an app restart.
- **Dynamic Duration Streaming**: Changes to `maintenanceRetryAfter` (e.g. *30 minutes* ➔ *2 hours*) sync live on the screen without closing the dialog.
- **Cache-Busting Polling**: Bypasses GitHub raw CDN caching using dynamic query hashes (`?t=timestamp`) and `no-cache` network headers.
- **Emergency Protection**: Full-screen AMOLED lock screen blocks all underlying functionality while maintenance is active.

### 🔄 In-App OTA Update System
- **Silent Background Check**: Automatically verifies version codes against remote JSON metadata.
- **Seamless Downloader**: Integrated background download manager with real-time download percentage, speed, and file size tracking.
- **Package Integrity Verification**: Pre-validates downloaded APKs using Android package parsers before launching installation to prevent corrupted package errors.

### 🎨 Ultra-Modern AMOLED Interface
- **Pure Black (0x000000)**: Optimized for OLED/AMOLED displays for maximum battery savings and high contrast.
- **Edge-to-Edge Display**: Fully responsive layout with transparent status and navigation bars.
- **Smooth Animations**: High-tech particle backdrop, glow borders, and fluid touch ripples.

### 📳 Next-Gen Tactile Haptic Engine
- **Hardware-Level Precision**: Powered by custom multi-tier haptic profiles (`CLICK`, `HEAVY`, `TICK`, `SUCCESS`, `ERROR`, `WARNING`).
- **Tactile Feedback**: Distinct vibration response for key extractions, connection retries, and button interactions.

### 🔒 Dual-Layer Security & Payload Protection
- **Encrypted DEX Architecture**: Payload bytecode is cryptographically encrypted (`assets/ondev/p`) using HKDF + AES-GCM and loaded dynamically into memory.
- **Native Armor (`libsandip.so`)**: Binary-level protection against unauthorized tampering and reverse engineering.

---

## 📡 Remote Control API (`update.json`)

The application is controlled in real-time via GitHub raw JSON:

```json
{
  "versionCode": 105,
  "versionName": "1.0.5",
  "apkUrl": "https://github.com/sandipff2000-byte/sandip-keygen-updates/releases/download/v1.0.4/SANDIP.KEYGEN.v1.0.4.apk",
  "forceUpdate": false,
  "releaseNotes": "Real-time maintenance auto-sync, dynamic duration updates & AMOLED UI improvements.",
  "maintenance": false,
  "maintenanceTitle": "App Under Maintenance",
  "maintenanceMessage": "We are performing system maintenance. Please check back shortly.",
  "maintenanceRetryAfter": "30 minutes"
}
```

### Remote Field Reference

| Key | Type | Description |
| :--- | :--- | :--- |
| `versionCode` | `Integer` | Remote build version number (triggers OTA update if > local). |
| `versionName` | `String` | Semantic version string displayed to the user. |
| `apkUrl` | `String` | Direct download link for the latest APK package. |
| `forceUpdate` | `Boolean` | When `true`, hides the 'Later' button and requires update. |
| `maintenance` | `Boolean` | When `true`, instantly locks the app in full-screen maintenance mode. |
| `maintenanceTitle` | `String` | Main heading displayed on the maintenance screen. |
| `maintenanceMessage` | `String` | Custom message or instructions for users during downtime. |
| `maintenanceRetryAfter` | `String` | Real-time estimated duration displayed dynamically on-screen. |

---

## 🏗️ Architecture & Tech Stack

```
SANDIP KEYGEN/
├── apk_decompiled/             # Outer Host APK (Decompiled resources & manifest)
│   ├── assets/                 # App assets & encrypted payload (assets/ondev/p)
│   ├── lib/arm64-v8a/          # Native libraries (libsandip.so)
│   └── smali/                  # Entry-point smali classes & FileProvider
├── payload_decompiled/         # Core Payload Logic (Protected Dex source)
│   └── smali/akatsuki/zxixghost/
│       ├── AkUpdateManager.smali   # Cloud Update & Real-Time Maintenance Engine
│       └── MainActivity.smali      # Main portal logic & UI
├── scratch/build_update/       # Java source code for update & maintenance modules
│   ├── AkUpdateManager.java    # Pure Java implementation for compile pipeline
│   └── compile_update.py       # Java -> Javac -> D8 -> Smali deployment script
└── package_and_build.ps1       # Master build script: Payload repack -> DEX encrypt -> Outer build -> Sign
```

- **Languages**: Java (OpenJDK 17/8), Smali, C++ (ARM64), Python, PowerShell
- **Tools**: Apktool 3.0.3, D8 Dexer, Android SDK 34 Platform, ZipAlign, Apksigner

---

## 🚀 Build & Compilation

### Prerequisites
- [Java Development Kit (JDK 17+)](https://www.oracle.com/java/technologies/downloads/)
- [Android SDK Build-Tools](https://developer.android.com/studio) (Includes `d8.jar`, `zipalign`, `apksigner`)
- [Python 3.8+](https://www.python.org/)
- [Apktool 3.0.3+](https://apktool.org/)

### 1. Compile Java Modules to Smali
Recompiles `AkUpdateManager.java`, translates to Dalvik bytecode with D8, and injects freshly generated smali into payload classes:
```powershell
python scratch/build_update/compile_update.py
```

### 2. Package, Encrypt & Sign APK
Builds the payload APK, extracts DEXes, encrypts them into `assets/ondev/p`, recompiles the outer APK, zipaligns, and signs the release binary:
```powershell
powershell -ExecutionPolicy Bypass -File .\package_and_build.ps1
```

**Output**:
```
SANDIP KEYGEN.apk (Release signed, ready for deployment)
```

---

## 📝 Changelog

### Version 1.0.5
- ⚡ **Real-Time Maintenance Engine**: Added live auto-polling loop with zero-restart auto-dismiss on maintenance completion.
- ⏱️ **Dynamic Duration Updates**: Real-time on-screen duration sync when remote `maintenanceRetryAfter` changes.
- 📳 **Key Extracted Haptic Feedback**: Integrated custom haptic cues for success, errors, warnings, and button taps.
- 📱 **Edge-to-Edge System Bar**: Perfected transparent AMOLED status bar visibility across Android 10, 11, 12, 13, and 14+.
- 🚀 **Cache-Busting HTTP Pipeline**: Eliminated CDN stale data caching using timestamp hash parameters.

---

## 👤 Developer & Credits

- **Developer & Maintainer**: **SANDIP MOD'S**
- **Client / Development Partner**: [@AincradMods](https://t.me/AincradMods)
- **Key Generation Portal**: [https://aincradmods.com/getkey](https://aincradmods.com/getkey)
- **Telegram Channel**: [@sandipmods](https://t.me/whoes_mee)
- **GitHub Repository**: [sandip-keygen-updates](https://github.com/sandipff2000-byte/sandip-keygen-updates)

---

<p align="center">
  <sub>Made with ❤️ by <b>SANDIP MOD'S</b> • All Rights Reserved</sub>
</p>
