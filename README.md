# Flat 11 Electric Bill — Android-ready project

## Requirements
- Node.js 20+
- Android Studio
- Android SDK / platform tools
- JDK 17

## Run in browser
npm install
npm run dev

## Create Android project
npm install
npm run build
npx cap add android
npx cap sync android
npx cap open android

Then in Android Studio:
Build > Build Bundle(s) / APK(s) > Build APK(s)

The app is designed to work offline. Room/resident data and payment settings are stored locally on the device.

## Notes
- PDF generation is implemented with jsPDF.
- The original `window.storage` dependency was replaced with browser/device local storage.
- Payment details are editable under Settings instead of being hard-coded.
- The generated APK package ID is `com.flat11.electricbill`.

## Build the APK online with GitHub Actions

This project includes a GitHub Actions workflow at `.github/workflows/build-android.yml`.

### Steps

1. Create a GitHub repository and upload all files from this project.
2. Make sure the default branch is named `main`.
3. Open the repository on GitHub.
4. Select **Actions**.
5. Select **Build Android APK**.
6. Click **Run workflow**.
7. Wait for the build to finish.
8. Open the completed workflow run.
9. Under **Artifacts**, download **flat11-electric-bill-apk**.
10. Extract the downloaded ZIP. Inside is `app-debug.apk`.
11. Transfer/install the APK on your Android phone.

This produces a **debug APK for direct installation**. It is not a Play Store-signed release. A signed release/AAB can be added later if you want to publish the app on Google Play.

### Important

The GitHub Actions build creates the Capacitor Android project during the cloud build, so you do not need Android Studio on your computer.
