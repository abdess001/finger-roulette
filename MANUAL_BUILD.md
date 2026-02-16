# Flutter Build Instructions

Since Flutter is not detected in the system PATH, please follow these steps:

## Option 1: Build Using Command Line

1. **Open a NEW PowerShell or Command Prompt window** (this is important - the PATH may not be updated in old windows)

2. **Verify Flutter is working:**
   ```bash
   flutter doctor
   ```

3. **Navigate to project:**
   ```bash
   cd C:\Users\ASUS\Desktop\2026\finger_roulette
   ```

4. **Install dependencies:**
   ```bash
   flutter pub get
   ```

5. **Build the APK:**
   ```bash
   flutter build apk --release
   ```

6. **Find your APK:**
   - Location: `C:\Users\ASUS\Desktop\2026\finger_roulette\build\app\outputs\flutter-apk\app-release.apk`

7. **Copy to new folder:**
   ```bash
   mkdir C:\Users\ASUS\Desktop\2026\FingerRouletteAPK
   copy build\app\outputs\flutter-apk\app-release.apk C:\Users\ASUS\Desktop\2026\FingerRouletteAPK\
   ```

## Option 2: If Flutter Command Not Found

If `flutter` command still doesn't work, you need to:

1. **Find where Flutter is installed** (common locations):
   - `C:\flutter`
   - `C:\src\flutter`
   - `C:\Users\ASUS\flutter`
   - Check your Downloads folder

2. **Add Flutter to PATH:**
   - Search "Environment Variables" in Windows
   - Edit "Path" variable
   - Add: `C:\[your-flutter-location]\bin`
   - Click OK
   - **Restart PowerShell/Command Prompt**

3. **Then run the commands above**

## Quick Test

After building, the APK will be ready to install on your Android device!
