# Pro Car Android App

Android client for the Pro Car rental system. It uses the existing PHP/MySQL backend in `car-rental-system`.

## Project structure

- `app/` — Android app module
- `build.gradle.kts` — root Gradle build config
- `settings.gradle.kts` — project settings

## Requirements

- Android Studio
- JDK 17+
- Android SDK with API 34

## Setup

1. Install Android Studio.
2. Open this folder in Android Studio.
3. Let Android Studio install the required SDK and Gradle plugin versions.
4. Run the app on an emulator or physical device.

## Database connection

The Android client connects to `http://10.102.115.214:8081/procar/backend/`, where `10.102.115.214` is this computer's current Wi-Fi address. WAMP Apache serves the project through the `C:\wamp64\www\procar` junction. If the address changes, update `API_BASE_URL` in `app/src/main/java/com/procar/app/data/ProCarApi.kt` and rebuild.

1. Start WAMP MariaDB (this installation uses port `3307`; the project `.env` configures that port).
2. Start WAMP Apache on port `8081`; it serves the project at `http://localhost:8081/procar/`.
3. Keep the phone and computer on the same Wi-Fi network.
4. Build and install the Android app.

The first API request creates the `pro_car` database and tables when MySQL credentials in `.env` are valid. The Android app supports customer registration/login, live car search, booking creation, booking history, cancellation, payment recording, and review submission. Admin and company inventory management remain available through the web dashboard.

