# AGENTS.md

## Scope

These instructions apply to the whole `trvny/WiFi-Automatic` repository.
The default branch is `master`.

## Repository role

This is a maintained fork of `j4velin/WiFi-Automatic`, not a clean upstream
mirror. Read `README.md`, `NOTICE`, and the recent commit history before changing
or synchronizing code.

## Change rules

- Preserve upstream authorship, license notices, package identity, and the
  documented distinction between upstream code and fork modifications.
- Do not replace the repository wholesale with a newer upstream tree. Compare
  changes and retain intentional fork fixes, CI, metadata, and documentation.
- Treat Android background execution, Wi-Fi permissions, alarms, and behavior
  across API levels as compatibility-sensitive.
- Do not change signing, publishing, application IDs, store metadata, or release
  configuration unless the task explicitly requires it.
- Keep changes small and avoid unrelated modernization or mass formatting.

## Before changing anything

- Check current `master`, open pull requests, and recent changes.
- Inspect the relevant Gradle and Android manifest configuration.
- When using upstream as evidence, compare the exact upstream revision rather
  than assuming the latest upstream code is compatible with this fork.

## Validation

Use the same build exercised by CI:

```bash
chmod +x gradlew
./gradlew --no-daemon clean assembleFdroidDebug
```

Run narrower tests or lint when available and relevant. Report anything not
run, especially device or Android-version behavior that cannot be verified in
CI.

## GitHub workflow

Keep one logical change per pull request. Truly trivial low-risk edits may go
directly to `master`. Treat Codex review as advisory only; do not ask it to
implement, commit, or push. Prefer squash merge after relevant checks pass on
the final head commit.
