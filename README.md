# Lane-Level GPS (grokgps)

Repo: https://github.com/xz64uj777/grokgps

## Status (2026-09-17)

Scaffold is on `main`: Gradle project files, Android manifest, backend bootstrap, APK workflow.

Kotlin app/engine sources from `grokgps-best.zip` are **not** fully on GitHub yet. The GitHub file API used here cannot bulk-push ~100 source files in one shot. No APK was produced in this pass (no Android SDK in the agent environment; Actions cannot build until sources land).

## Finish the push from your machine

```bash
unzip grokgps-best.zip
cd grokgps-work
# drop Gradle caches if present
rm -rf android/.gradle android/**/build
git init
git remote add origin https://github.com/xz64uj777/grokgps.git
git fetch origin
git checkout -B main
git add -A
git commit -m "Add full GrokGPS source from grokgps-best"
git push -u origin main --force
```

After that push, GitHub Action **Build Android APK** runs on `main`. Download artifact `lane-gps-debug-apk` (`app-debug.apk`).
