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
