# 🎵 My Spotify Clone (Android - Media3 + ExoPlayer)

Downlode From Repo Use this Repo For The Songs Downlode https://github.com/kriss2012/spotify/tree/main/songs

A modern Spotify-style music player built using **Kotlin**, **Jetpack Compose**, and **Media3 (ExoPlayer)**.

This app loads songs from device storage and plays them in the background using a proper MediaSessionService.


## 🚀 Features

- 🎶 Load songs from device (MediaStore)
- ▶️ Play / Pause / Resume audio
- ⏭️ Next / Previous support
- 🔊 Proper Audio Focus handling
- 🎧 Auto pause on headphone unplug
- 🔔 Background playback with notification
- 📱 Modern Jetpack Compose UI
- ⚡ Media3 + ExoPlayer powered playback engine

---

## 🏗️ Tech Stack

- Kotlin
- Jetpack Compose
- Media3 (ExoPlayer)
- MediaSessionService
- Android 13+ compatible
- Material 3 UI

---

## 📂 Project Structure

```

com.example.myapplication
│
├── PlaybackService.kt      # Background playback service
├── MainActivity.kt         # Entry point
├── MusicViewModel.kt       # Handles playback logic
├── Song.kt                 # Data model
├── ui/                     # Compose UI screens

````

---

## ⚙️ Setup Instructions

### 1️⃣ Clone Project

```bash
git clone <your-repository-url>
````

Open in Android Studio.

---

### 2️⃣ Required Permissions

Add this in `AndroidManifest.xml`:

For Android 13+:

```xml
<uses-permission android:name="android.permission.READ_MEDIA_AUDIO"/>
```

For Android 12 and below:

```xml
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE"/>
```

---

### 3️⃣ Make Sure MediaItem Is Created Correctly

Playback MUST use:

```kotlin
val mediaItem = MediaItem.fromUri(song.uri)

controller.setMediaItem(mediaItem)
controller.prepare()
controller.play()
```

❌ Do NOT use:

```kotlin
MediaItem.Builder().setMediaId(...)
```

---

## 🎧 Playback Service

Playback runs inside:

```
PlaybackService : MediaSessionService
```

Key features:

* Audio Focus handling
* Background playback
* Notification channel
* Auto stop when not playing

---

## 🛠️ Common Issues & Fix

### ❌ Songs load but don't play

Cause:

* Wrong URI passed to ExoPlayer
* MediaItem built using mediaId instead of URI

Fix:

* Always use `MediaItem.fromUri()`
* Do not override URI in MediaSession callback

---

### ❌ No sound on Android 13+

Make sure:

* Runtime permission is granted
* Audio file URI is valid
* Device volume is not muted

---

## 🧠 How Playback Works

1. Songs loaded from MediaStore
2. User taps play
3. MediaItem created using real URI
4. Controller sends item to PlaybackService
5. ExoPlayer prepares
6. Audio plays in background

---

## 📸 Future Improvements

* 🎨 Dynamic theme colors
* 📀 Album artwork support
* 📑 Playlist creation
* 🔍 Search functionality
* 🌙 Dark mode improvements
* 📡 Streaming support

---

## 📦 Build APK

Inside project folder:

```bash
./gradlew assembleDebug
```

APK location:

```
app/build/outputs/apk/debug/app-debug.apk
```

---

## 👨‍💻 Author

Krishna Patil

---

## 📜 License

This project is for educational purposes only.

Not affiliated with Spotify.

# Offline Music Player for Android

This is a simple yet powerful offline music player application for Android, built with modern, native technologies. The app scans your device's local storage for audio files, organizes them by folder, and provides a clean, intuitive interface for playback.

## Features

*   **Local Music Scanning:** Automatically finds and catalogs all `.mp3`, `.wav`, and other audio files on your device.
*   **Playlist by Folder:** Your music is automatically organized into playlists based on the folder it's stored in.
*   **Modern UI:** A clean, responsive user interface built with Jetpack Compose, inspired by popular music streaming apps.
*   **Full Playback Control:** The player includes all the essential features:
    *   Play and Pause
    *   Skip to Next / Previous Track
    *   Seek Bar
    *   Shuffle and Repeat Modes
    *   Volume Slider
*   **Background Playback:** Your music keeps playing even when the app is minimized or the screen is off, thanks to a robust foreground service.
*   **Media Notification:** Control playback directly from a rich media notification, just like you would with Spotify or other major music apps.
*   **Album Art:** The app automatically fetches and displays embedded album art for your songs.
*   **Navigation:** A simple navigation drawer allows for easy browsing between different parts of the app.

## How to Build and Run

1.  **Clone the repository** or open the project folder in Android Studio.
2.  **Sync Gradle:** Wait for Android Studio to download and sync all the project dependencies.
3.  **Run the App:** Select the `app` run configuration and deploy it to an Android emulator or a physical device.
4.  **Grant Permission:** On first launch, the app will request permission to access your audio files. You must grant this permission for the app to find your music.

## Technologies Used

*   **Kotlin:** The official language for Android development.
*   **Jetpack Compose:** The modern toolkit for building native Android UI.
*   **Media3 (ExoPlayer & MediaSession):** The latest library from Google for powerful and reliable audio playback and background session management.
*   **Jetpack Navigation:** For navigating between different screens within the app.
*   **Jetpack ViewModel:** To manage UI-related data and state in a lifecycle-conscious way.
*   **Coil:** A fast and efficient image loading library for displaying album art.
*   **Kotlin Coroutines:** For managing background threads and asynchronous operations.
