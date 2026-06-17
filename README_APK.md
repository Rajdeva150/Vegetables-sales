# Vegetable Sales Tracker - Android APK Build Guide

## Overview
This Android application wraps your Tamil vegetable sales tracking HTML application into a native Android app.

## Prerequisites
1. **Android Studio** (Latest version) - [Download](https://developer.android.com/studio)
2. **Java Development Kit (JDK)** 8 or higher
3. **Android SDK** (API 21 and above)

## Project Structure
```
Vegetables-sales/
├── android/
│   ├── app/
│   │   ├── src/
│   │   │   ├── main/
│   │   │   │   ├── assets/
│   │   │   │   │   └── vegetable_sales.html     (Your HTML file)
│   │   │   │   ├── java/com/vegiesales/app/
│   │   │   │   │   └── MainActivity.java
│   │   │   │   └── res/
│   │   │   │       ├── layout/
│   │   │   │       │   └── activity_main.xml
│   │   │   │       └── values/
│   │   │   │           ├── strings.xml
│   │   │   │           └── styles.xml
│   │   │   └── AndroidManifest.xml
│   │   ├── build.gradle
│   │   └── proguard-rules.pro
│   └── gradle.properties
├── build.gradle
└── settings.gradle
```

## Setup Instructions

### Step 1: Clone and Setup
```bash
git clone https://github.com/Rajdeva150/Vegetables-sales.git
cd Vegetables-sales
```

### Step 2: Place HTML File
1. Copy `vegetable_sales-5.html` to `android/app/src/main/assets/`
2. Rename it to `vegetable_sales.html`

### Step 3: Open in Android Studio
1. Open Android Studio
2. Click **File → Open**
3. Navigate to the `Vegetables-sales` folder
4. Select and open the project

### Step 4: Configure Android SDK
1. Go to **File → Settings → Appearance & Behavior → System Settings → Android SDK**
2. Install the following:
   - **SDK Platforms**: Android 12.0 (API 33) or higher
   - **SDK Tools**: 
     - Android SDK Build-Tools (latest)
     - Android Gradle Plugin

### Step 5: Sync Gradle
- Android Studio will prompt you to sync Gradle. Click **Sync Now**
- Or manually: **File → Sync Project with Gradle Files**

## Building the APK

### Debug APK (For Testing)
```bash
cd Vegetables-sales
./gradlew assembleDebug
```
Output: `android/app/build/outputs/apk/debug/app-debug.apk`

### Release APK (For Distribution)
```bash
./gradlew assembleRelease
```
Output: `android/app/build/outputs/apk/release/app-release.apk`

### Using Android Studio GUI
1. Click **Build → Build Bundle(s)/APK(s) → Build APK(s)**
2. Wait for the build to complete
3. A notification will appear with options to locate or analyze the APK

## App Features
✅ **Stock Management** - Add and track vegetable stock
✅ **Customer Billing** - Create and share bills via WhatsApp
✅ **Profit Tracking** - View daily/date-range profit analysis
✅ **Expense Tracking** - Record expenses and waste
✅ **Customer History** - Track all customer transactions
✅ **Data Persistence** - All data saved locally using localStorage

## Key Permissions
- `INTERNET` - For WhatsApp sharing
- `WRITE_EXTERNAL_STORAGE` - For file operations
- `READ_EXTERNAL_STORAGE` - For file access

## Customization

### Change App Icon
1. Create your icon (512x512 PNG)
2. Place it in `android/app/src/main/res/mipmap-xxxhdpi/`
3. Rename as `ic_launcher.png`

### Change App Name
Edit `android/app/src/main/res/values/strings.xml`
```xml
<string name="app_name">Your App Name</string>
```

### Change Colors
Edit `android/app/src/main/res/values/styles.xml`
```xml
<item name="colorPrimary">#1a4a2e</item>
<item name="colorPrimaryDark">#0d2818</item>
<item name="colorAccent">#4caf7d</item>
```

## Installing on Device

### Via USB
```bash
./gradlew installDebug
```

### Via File
1. Download the APK to your Android device
2. Enable "Unknown Sources" in Settings
3. Open the APK file and install

## Troubleshooting

### Build Fails
- Run `./gradlew clean` then rebuild
- Ensure Android SDK is installed correctly
- Check Java version: `java -version`

### HTML Not Loading
- Verify `vegetable_sales.html` is in `android/app/src/main/assets/`
- Check file name matches in `MainActivity.java`
- Ensure internet permission is granted

### Storage Issues
- App data is stored in device's internal storage
- No external storage required for basic functionality
- Data persists between app sessions

## Release Checklist
- [ ] Update version in `android/app/build.gradle`
- [ ] Update app name and description
- [ ] Create app icon in all sizes
- [ ] Test on multiple Android versions
- [ ] Verify all features work offline
- [ ] Sign the APK with your keystore

## Support
For issues, create an issue on GitHub: [Issues](https://github.com/Rajdeva150/Vegetables-sales/issues)

## License
This project is open source and available under the MIT License.
