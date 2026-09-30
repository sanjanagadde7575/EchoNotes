# EchoNotes

# EchoNotes

A voice-first notes and reminders app for Android, built with Kotlin and Jetpack Compose. Speak a task, and EchoNotes turns it into a categorized note with a due-date reminder — no manual date picking required.

This is the first project in a three-part Android portfolio (EchoNotes → SnapSpend → TrustBank), each one building on the last.

## Features

- **Voice-to-note capture** — tap once, speak a task, and EchoNotes converts it to text and sets a reminder automatically.
- **Actionable reminder notifications** — snooze or mark a note done directly from the notification, no need to open the app.
- **Color-coded urgency** — notes flagged as urgent stand out visually in the list.
- **Category organization** — Work, Personal, Home, and Payments, with filter chips on the home screen.
- **Home-screen widget** — an at-a-glance view of upcoming notes without opening the app.
- **Simple onboarding** — collects your name and requests microphone/notification permissions up front; returning users skip straight to the home screen.

## Tech Stack

- **Kotlin**
- **Jetpack Compose** (Material 3) for the UI
- **Navigation Compose** for screen navigation
- Android's built-in **NotificationManager / NotificationCompat** for reminders, with a `BroadcastReceiver` handling snooze/mark-done actions tapped from a notification
- **AppWidgetProvider** for the home-screen widget
- Min SDK 24, Target SDK 37

## Project Structure

| File | Purpose |
|---|---|
| `MainActivity.kt` | App entry point — hosts onboarding, the home note list, add/edit flow, and voice-capture screens |
| `Note.kt` | The note data model (text, category, due label, urgency flag, done state) |
| `NotificationHelper.kt` | Builds and shows the reminder notification, including its snooze/mark-done actions |
| `NoteActionReceiver.kt` | Handles the snooze/mark-done actions tapped from a notification |
| `EchoNotesWidget.kt` | The home-screen widget provider |
| `ui/theme/` | The app's Compose theme (light, warm cream/white with an orange accent) |

## Known Limitations

This is a portfolio/learning project. Notes are currently held in memory only (no local database), so they don't persist between app restarts — that was a deliberate scope choice to keep this first project focused on the voice-capture and notification flow. Persistent storage is exactly what the next project in this series, SnapSpend, added with a Room database.

## Getting Started

1. Clone the repo and open it in Android Studio.
2. Let Gradle sync — it pulls in the Compose BOM and AndroidX libraries, no extra setup needed.
3. Run on an emulator or device running Android 7.0 (API 24) or higher.
4. Grant microphone and notification permissions when prompted, to use voice capture and reminders.
