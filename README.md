# Study OS

Study OS is a browser-based, local-first study command centre. It uses plain HTML, CSS, and JavaScript so it runs without a build step or third-party runtime dependencies.

## Run locally

Open `index.html` in a modern browser, or serve this directory over HTTP:

```powershell
python -m http.server 5173
```

Then visit `http://localhost:5173`.

## Included features

- Responsive dark dashboard, sidebar navigation, global search, and quick-add menu.
- Persistent daily goals, tasks, backlogs, weekly timetable, revision schedule, exam dates, notes, and daily journal.
- Pomodoro focus timer with pause/resume, browser refresh recovery, session history, and tracked focus analytics.
- Browser-generated ambient audio and playback for audio files selected from the device. Audio files are not uploaded.
- Local JSON backup export and import, study settings, and subject list.
- Rule-based next-step suggestions using stored task, backlog, and revision dates.

## Storage and cloud sync

Records live in this browser's `localStorage`. Export a JSON backup before clearing browser data or moving devices. User-selected audio file URLs are session-only; select those files again after restarting the browser.

Cloud sync and authentication are not configured. No Supabase credentials or server-side components are present. To add cloud sync, create a Supabase project, implement email authentication and per-user tables with row-level security, then supply only the public project URL and anon key through the app's deployment configuration. Never put a service-role key in browser code. Until that backend is implemented, the app accurately shows cloud sync as disconnected.

## Deploy

Deploy `index.html`, `styles.css`, and `app.js` as static files to any static web host. No environment variables are required for the local-first app. The Google Fonts import is optional; system sans-serif fallbacks are used when fonts cannot load.

## Limitations

- Study data is stored per browser and does not sync between devices.
- Ambient sounds are generated locally with Web Audio; their timbre is intentionally simple.
- The weekly timetable is edited one entry at a time. A session's day indicates its weekly recurrence.
- Notes accept markdown-friendly plain text and resource URLs; file attachments are not stored.
- Study duration analytics distinguish completed tracked focus sessions from planned goal duration.
