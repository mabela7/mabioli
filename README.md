# Lyrics (Android APK)

Capacitor app. GitHub Actions generates the Android project and builds the APK.

## Files (put them in the repo exactly like this)

```
package.json
capacitor.config.json
.gitignore
README.md
www/index.html
.github/workflows/android.yml
icon.png   (optional: your app icon, square PNG 512px+, repo root)
```

## Upload (phone, GitHub website)

GitHub mobile can't upload folders, so create each file by path:

1. Create a new repo on github.com (empty).
2. Add file -> Create new file.
3. In the name box type the full path, e.g. `www/index.html`
   (typing `/` makes the folder). Paste the file contents. Commit.
4. Repeat for every file above, including
   `.github/workflows/android.yml` (hidden folder in Files app,
   so always create this one by typing the path).

## Build

1. Repo -> Actions tab -> "Android APK" -> Run workflow
   (it also runs on every push to main/master).
2. Wait ~5-8 min for the green check.
3. Open the run -> Artifacts -> `lyrics-apk` -> download, unzip,
   install `app-debug.apk` (allow "install unknown apps").

## Notes

- Needs only INTERNET permission (already in the generated manifest).
- Back button closes an open song, then exits the app.
- App icon: upload `icon.png` to the repo root (Add file -> Upload files).
  No icon.png = default icon.
- To change the app name/ID edit `capacitor.config.json`.
- First launch: tap the gear and paste your Firebase Realtime DB URL
  (blank = local only).
- If the build fails, open the failed step in Actions and send me the
  red error lines.
