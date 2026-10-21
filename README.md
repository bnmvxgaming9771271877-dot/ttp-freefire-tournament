# TTP Free Fire Tournament — Android Starter v2

Dark gaming-style native Android starter app with a GitHub Actions workflow to build and upload a debug APK.

## Included app screens
- Dark gaming home screen
- Free Fire player/team name + UID registration form
- Registration status saved for the current app process
- Room ID and password screen
- Local demo admin panel to publish room details
- Bottom navigation for Home, Register, Room and Admin

## GitHub APK build
1. Create a GitHub repository.
2. Extract this ZIP and upload all files and folders to the repository root.
3. Use `main` as the branch name (or keep `master`).
4. Open **Actions** and enable workflows if prompted.
5. Run **Build TTP Free Fire APK** using **Run workflow**, or push a commit.
6. Open the completed run and download the `TTP-FreeFire-debug-apk` artifact.
7. Extract the artifact ZIP to get `app-debug.apk`.

## Build configuration
- JDK 17
- Gradle 8.9
- Android Gradle Plugin 8.7.3
- Kotlin Android plugin 2.0.21
- Android SDK / build tools 35
- No third-party runtime libraries

## Local build
With JDK 17, Android SDK and Gradle installed:

```bash
gradle --no-daemon :app:assembleDebug
```

APK output: `app/build/outputs/apk/debug/app-debug.apk`

## Demo admin PIN
The local prototype uses `2026` to reveal admin controls. This is only a demo gate, not secure authentication.

## Production limitations — read before publishing
This ZIP is a functional UI prototype, not a production-ready tournament service:
- Data is local to the app/device and is not a shared online database.
- Registration approval, multi-player roster, live tournament listing and results are not connected to a backend.
- The admin PIN is hardcoded for demonstration. Do not publish a real app with this gate as its security.
- Room credentials should only be served to eligible players by a secure backend with admin authentication and authorization.
- No payment, wallet, or prize distribution system is included.
- A debug APK is for testing; Play Store distribution needs a signed release build and privacy/legal review.

The workflow is configured with compatible toolchain versions, but should be run in GitHub Actions to verify the build in the target environment.
