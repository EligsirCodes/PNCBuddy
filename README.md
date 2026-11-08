# Smart Campus Companion (PNC Buddy)

## Overview

**Smart Campus Companion (PNC Buddy)** is an Android application that gives university students easy access to essential campus tools and information. It centralizes academic and campus services in one app so students can manage their tasks, stay informed, and personalize their experience.

## Features

- **Campus Information** – Browse important campus details and resources.
- **Task & Schedule Manager** – Add, edit, complete, and delete academic tasks with date and time pickers, plus scheduled reminder notifications.
- **Campus Announcements** – Read official announcements, mark them as read or unread, and filter by read status.
- **User Roles** – Student accounts get standard access to tasks and announcements; admin accounts can post and manage announcements. *(Roles are currently mocked.)*
- **Settings** – Switch between light and dark mode and toggle notifications. Preferences persist between sessions.
- **Polished UX** – Empty states, clear error messages, and loading indicators throughout.

## Tech Stack

| Area | Technology |
|---|---|
| Language | Kotlin |
| UI | Jetpack Compose, Material Design 3 |
| Navigation | Jetpack Compose Navigation with a bottom navigation bar |
| Architecture | MVVM with Clean Architecture layers |
| State Management | ViewModel, StateFlow, Kotlin Coroutines |
| Local Storage | Room Database, SharedPreferences |
| Backend | Firebase Authentication, Cloud Firestore, Cloud Messaging |
| Notifications | Task scheduler with broadcast receiver |

## Architecture

The app separates presentation, domain, and data concerns:

```
app/src/main/java/com/example/itew4_casestudy/
├── data/
│   └── repository/        # Auth, Task, and Announcement repositories
├── domain/
│   └── model/             # UserModel, TaskModel, AnnouncementModel
├── presentation/
│   ├── screens/           # Login, Registration, Dashboard, Tasks,
│   │                      # Announcements, Information, Settings,
│   │                      # and reusable UI components
│   ├── viewmodel/         # Auth, Task, Announcement, and Theme ViewModels
│   └── notifications/     # TaskScheduler and TaskNotificationReceiver
├── navigation/            # NavGraph and NavRoutes
├── ui/theme/              # Color, Type, and Theme (light and dark)
└── MainActivity.kt
```

## Screens

- **Login & Registration** – Account access with client-side input validation.
- **Dashboard** – Central hub for the user.
- **Tasks** – Create and manage academic tasks and deadlines.
- **Announcements** – Read, filter, and (for admins) post announcements.
- **Campus Information** – University details and resources.
- **Settings** – Appearance and notification preferences.

## Getting Started

1. **Clone the repository**
   ```bash
   git clone https://github.com/EligsirCodes/PNCBuddy.git
   ```
2. **Open in Android Studio**
   - Launch Android Studio and select **Open**.
   - Navigate to the cloned project folder.
3. **Set up Firebase**
   - Create a project in the [Firebase Console](https://console.firebase.google.com/).
   - Add an Android app with the package name `com.example.itew4_casestudy`.
   - Enable Authentication and Cloud Firestore for the project.
   - Download `google-services.json` and place it in the `app/` directory.
4. **Build and run**
   - Sync the project with Gradle files.
   - Click **Run** (or press `Shift + F10`) to deploy to an emulator or physical device.

## Release History

| Version | Date | Highlights |
|---|---|---|
| `v2.0-final` | 2026-04-26 | Mock student and admin roles, Firebase integration (Firestore, Auth, Cloud Messaging), settings module with dark mode and notification toggle, UI state improvements, Clean Architecture |
| `v1.0-midterm` | 2026-03-15 | Task and schedule manager, announcements module, Room database, MVVM architecture |
| `v0.1.0` | 2026-02-10 | Initial UI and navigation, core screens (Login, Registration, Dashboard) |
