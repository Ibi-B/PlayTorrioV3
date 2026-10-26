# AGENTS.md — PlayTorrio Pet Project

## Project goal

Maintain a personalized, stable Flutter build of PlayTorrio V3.
Gradually add selected features and disable or remove unwanted features without
breaking core movie/TV, Stremio addon, stream, torrent, subtitle, and playback
functionality.

## Non-negotiable rules

1. Do not modify unrelated files.
2. Do not upgrade Flutter, Dart, Gradle, Kotlin, or dependencies unless explicitly requested.
3. Do not delete code in the first change. First disable or hide the feature.
4. Keep every task small: one feature, one concern, one pull request.
5. Preserve GPL-3.0 licensing, copyright notices, and attribution.
6. Do not introduce telemetry, analytics, ads, remote configuration, or external accounts.
7. Do not add code that hosts, downloads, or distributes copyrighted media.
8. Do not modify release signing, package ID, or app-store metadata.
9. Prefer feature flags over hard deletion.
10. If uncertain whether code is used, leave it in place and report it in the PR.

## Required workflow

For every task:

1. Read the relevant files before editing.
2. Produce a short implementation plan.
3. Make the smallest possible change.
4. Run:
   - `flutter analyze`
   - `flutter test`
   - `flutter build apk --debug`
5. Summarize:
   - files changed
   - behavior added or removed
   - potential regressions
   - manual test steps
6. Do not merge or push directly to `main`.

## Architecture rules

- New reusable UI belongs in `lib/features/pet/presentation/`.
- New business logic belongs in `lib/features/pet/domain/`.
- New persistence belongs in `lib/features/pet/data/`.
- New global services belong in `lib/services/` only when tightly integrated with existing services.
- Follow existing project patterns for state management, routing, styling, naming, and error handling.
- Do not create a parallel app architecture.

## Feature removal policy

Removal must occur in separate commits:

1. Hide the UI entry point.
2. Disable navigation and initialization.
3. Leave service code intact.
4. After verification, remove unreachable UI.
5. In a later task, remove service and dependency code.

Never remove an entire subsystem in one pull request.

## Definition of done

- `flutter analyze` introduces no new warnings or errors.
- Existing tests pass.
- The debug APK builds successfully.
- The change is isolated, reversible, and covered by a manual regression checklist.
