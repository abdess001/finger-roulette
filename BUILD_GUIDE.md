# Quick Build & Test Guide 🚀

## Prerequisites

You need to install Flutter SDK first. Here's how:

### 1. Install Flutter SDK

**Download Flutter:**
1. Go to: https://docs.flutter.dev/get-started/install/windows
2. Download the Flutter SDK ZIP file (latest stable version)
3. Extract to `C:\src\flutter` (or any location you prefer)

**Add to PATH:**
1. Search for "Environment Variables" in Windows
2. Click "Environment Variables"
3. Under "User variables", find "Path" and click "Edit"
4. Click "New" and add: `C:\src\flutter\bin`
5. Click "OK" on all dialogs

**Verify Installation:**
```bash
# Open a NEW Command Prompt or PowerShell
flutter doctor
```

This will check your setup and show what's missing.

### 2. Install Android Studio (if not installed)

1. Download from: https://developer.android.com/studio
2. Install with default settings
3. Open Android Studio
4. Go to: Tools → SDK Manager
5. Install:
   - Android SDK Platform (API 34)
   - Android SDK Build-Tools
   - Android SDK Command-line Tools

**Accept Android Licenses:**
```bash
flutter doctor --android-licenses
```
Type `y` to accept all licenses.

---

## Building the APK

### Step 1: Navigate to Project

```bash
cd C:\Users\ASUS\Desktop\2026\finger_roulette
```

### Step 2: Get Dependencies

```bash
flutter pub get
```

This downloads all required packages (google_mobile_ads, vibration, etc.)

### Step 3: Build APK

**For Testing (Debug APK):**
```bash
flutter build apk --debug
```

**For Release (Optimized APK):**
```bash
flutter build apk --release
```

**APK Location:**
- Debug: `build\app\outputs\flutter-apk\app-debug.apk`
- Release: `build\app\outputs\flutter-apk\app-release.apk`

---

## Testing on Android Device

### Method 1: USB Connection (Recommended)

**Enable Developer Options on Phone:**
1. Go to Settings → About Phone
2. Tap "Build Number" 7 times
3. Go back → Developer Options
4. Enable "USB Debugging"

**Connect & Install:**
1. Connect phone via USB cable
2. Allow USB debugging on phone (popup will appear)
3. Verify connection:
   ```bash
   flutter devices
   ```
   You should see your device listed

4. **Install APK directly:**
   ```bash
   flutter install
   ```
   
   OR run the app:
   ```bash
   flutter run
   ```

### Method 2: Transfer APK File

**Transfer via USB:**
1. Connect phone to PC
2. Copy APK from `build\app\outputs\flutter-apk\app-release.apk`
3. Paste to phone's Downloads folder
4. On phone: Open "Files" app → Downloads
5. Tap the APK file
6. Allow "Install from unknown sources" if prompted
7. Tap "Install"

**Transfer via Cloud/Email:**
1. Upload APK to Google Drive / Dropbox
2. Download on phone
3. Install as above

---

## Quick Commands Summary

```bash
# 1. Check Flutter installation
flutter doctor

# 2. Navigate to project
cd C:\Users\ASUS\Desktop\2026\finger_roulette

# 3. Get dependencies
flutter pub get

# 4. Build release APK
flutter build apk --release

# 5. Install on connected device
flutter install

# OR run directly on device
flutter run
```

---

## Troubleshooting

### "flutter: command not found"
- Flutter not in PATH. Restart Command Prompt after adding to PATH
- Or use full path: `C:\src\flutter\bin\flutter doctor`

### "No devices found"
- Enable USB debugging on phone
- Try different USB cable
- Install phone drivers (usually automatic on Windows)

### "Gradle build failed"
- Run: `flutter clean` then `flutter pub get`
- Check internet connection (Gradle downloads dependencies)

### APK won't install on phone
- Enable "Install from unknown sources" in Settings → Security
- Make sure Android version is 5.0+ (API 21+)

---

## Testing the Game

Once installed:
1. Open "Finger Roulette" app
2. Place 2+ fingers on screen
3. Hold for 2 seconds
4. Watch countdown: 3... 2... 1...
5. One finger selected as "loser" (red pulse + vibration)
6. Tap anywhere to reset

**Expected behavior:**
- ✅ Neon circles appear on each finger touch
- ✅ Countdown starts after 2-second hold
- ✅ Random selection with flash animation
- ✅ Phone vibrates on selection
- ✅ Banner ad at bottom (may take few seconds to load)

---

## File Size

- Debug APK: ~40-50 MB
- Release APK: ~20-25 MB (optimized)

---

## Need Help?

If you encounter issues:
1. Run `flutter doctor -v` and check for errors
2. Make sure all licenses are accepted
3. Try `flutter clean` and rebuild
4. Check that phone is Android 5.0+ (API 21+)
