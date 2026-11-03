# AuraWardrobe - Standalone Mobile Application Setup (Android & iOS)

This package contains everything needed to run AuraWardrobe as a standalone mobile application on both **Android** and **Apple iOS (iPhone/iPad)**.

---

## 1. Technical Note on APK vs. iOS

* **APK (`.apk`) is Android-only**: APK files are compiled specifically for Google Android devices and **cannot run on iOS**.
* **iOS (`.ipa`)**: Apple devices do not support APKs. Native iOS applications use `.ipa` packages compiled on macOS with an Apple Developer certificate.
* **The Universal Solution (Instant Standalone App on Both iOS & Android)**:
  AuraWardrobe is built as a **Progressive Web App (PWA)**. It can be installed directly onto both iPhones and Android phones as a native-like standalone app **without needing app store downloads or APK sideloading**.

---

## 2. Instant Standalone Installation (No Coding Required)

### 🍏 On Apple iPhone / iPad (iOS):
1. Open `index.html` (or host it on your personal server/GitHub Pages) in **Safari**.
2. Tap the **Share** button (the square with an arrow pointing up at the bottom).
3. Scroll down and tap **"Add to Home Screen"**.
4. Tap **Add**.
5. The AuraWardrobe icon will appear on your iPhone home screen and launch in **full-screen standalone mode** without Safari address bars or browser buttons!

### 🤖 On Android:
1. Open the app in **Google Chrome** or your phone's browser.
2. Tap the **three vertical dots** (Menu) in the top-right corner.
3. Tap **"Install App"** (or **"Add to Home screen"**).
4. AuraWardrobe is immediately installed in your Android app drawer and home screen as a standalone app!

---

## 3. How to Generate an Installable Android APK File

If you specifically require a compiled `.apk` file for Android devices:

### Option A: 1-Click Cloud APK Generator (Free & Fastest - 2 Minutes)
1. Go to **[PWABuilder](https://www.pwabuilder.com)** (Microsoft's open-source PWA-to-APK packager).
2. Enter the URL of your hosted `index.html` (e.g., your GitHub Pages or private cloud link).
3. Click **"Package for Android"**.
4. Download the ready-to-install **`AuraWardrobe.apk`**!

### Option B: Local Build via Android Studio & Capacitor
1. Extract this zip file.
2. Place `index.html` inside a folder named `www/`.
3. Open terminal in this folder and run:
   ```bash
   npm install @capacitor/core @capacitor/cli @capacitor/android
   npx cap add android
   npx cap copy
   npx cap open android
   ```
4. In Android Studio, go to **Build** -> **Build Bundle(s) / APK(s)** -> **Build APK(s)**.
5. Your standalone APK will be generated under `android/app/build/outputs/apk/debug/app-debug.apk`.

---

## 4. Package Contents

* `index.html`: The complete, self-contained standalone application.
* `manifest.json`: Web app manifest configured for mobile standalone display.
* `sw.js`: Service worker enabling offline usage and caching.
* `capacitor.config.json`: Mobile runtime configuration for Android Studio and Xcode.
* `package.json`: Dependency manifests for Capacitor mobile compilation.
