# Discbox

A music player made of spinning CDs, with playlists and notes. Everything you add
(CDs, covers, songs, playlists, notes) is saved on your device and is still there
after you close the app.

## Get the APK (no Android Studio needed)

1. Create a new repository on GitHub and upload everything in this folder
   (keep the `.github` folder).
2. Open the **Actions** tab. The **Build Android APK** workflow starts by itself
   after your upload (or press **Run workflow**).
3. When it turns green (about 5 minutes), open the run and download
   **Discbox-apk** from *Artifacts*. Unzip it and send `Discbox.apk` to your phone.
4. Open the APK on your phone and allow "install unknown apps" when asked.

## Change the app

- The whole app is `www/index.html`.
- The logo comes from `resources/`. Replace `icon-only.png` (1024x1024) to change it,
  `icon-foreground.png` + `icon-background.png` are for round / adaptive icons.
- Push your change and the APK rebuilds.

## Build on your own computer instead

Needs Node 20 and JDK 17 plus the Android SDK.

    npm install
    npx cap add android
    npx capacitor-assets generate --android
    npx cap sync android
    cd android && ./gradlew assembleDebug

The APK is in `android/app/build/outputs/apk/debug/`.

## Run Discbox as a Windows desktop app

Needs Node.js on Windows.

    npm install
    npm run desktop

To create a portable Windows executable:

    npm run desktop:dist

The `.exe` is saved in `dist/` and runs without installation. It uses the same
`www/index.html` as the Android app.
