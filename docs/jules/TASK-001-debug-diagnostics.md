# Task 1: Add debug-only diagnostics page

## Objective

Add a debug-only diagnostics page to help future development and troubleshooting.
This is an additive task: do not remove, disable, or refactor any existing feature.

## Branching

- Base branch: `pet/dev`
- Task branch: `pet/task/debug-diagnostics`
- Pull-request target: `pet/dev`

## Requirements

1. Create `lib/features/pet/presentation/pages/debug_diagnostics_page.dart`.
2. Add a small diagnostics model/controller under `lib/features/pet/` using the project’s existing patterns.
3. Add a debug-only entry point in the existing settings UI or navigation drawer.
4. The entry point and page must only be visible when `kDebugMode` is true.
5. Display, where readily available:
   - App version/build information
   - Flutter/Dart version
   - Current route or screen name
   - A placeholder section for future scraper diagnostics
6. Follow the existing visual style, navigation pattern, and state-management approach.
7. Do not add dependencies.
8. Do not modify streaming, scraper, torrent, Stremio addon, subtitle, Music, Manga, or Audiobook behavior.

## Verification

Run and report results for:

```bash
flutter analyze
flutter test
flutter build apk --debug
```

## Acceptance criteria

- Debug APK builds successfully.
- The diagnostics page appears only in debug builds.
- No existing screen, service, route, or dependency is changed except where strictly necessary for the entry point.
- The pull request includes:
  - Files changed
  - Behavior changes
  - Potential regressions
  - Manual test checklist
- No release signing, package ID, license, or upstream attribution changes.

## Jules prompt

```text
Read AGENTS.md and docs/jules/TASK-001-debug-diagnostics.md.
Implement Task 1 exactly.
Work from pet/dev, create pet/task/debug-diagnostics,
and open a pull request back to pet/dev.
Do not modify unrelated files or existing features.
```
