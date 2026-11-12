# CICT Org Fair

**Live site:** https://yna21.github.io/org-fair/

A Flutter app for the CICT Org Fair: browse the orgs and their officers,
see what's on today, and check the booth schedule. The events are written by
org officers in a headless CMS (Contentful), so changing an event does not
need a new release.

## Releases

| Part | How it ships |
|---|---|
| Web | GitHub Actions tests, builds and deploys to GitHub Pages on every push to `main` |
| Android | `flutter build apk --release --dart-define-from-file=cms.json` |

Current version: **1.1.0 (build 2)**

## Run it locally

1. Copy `cms.example.json` to `cms.json` and fill in your CMS values
   (`cms.json` is in `.gitignore`, so it is never committed).
2. Run:

```
flutter pub get
flutter run -d chrome --dart-define-from-file=cms.json
```

## Tests

```
flutter test
```

## CI/CD

- `.github/workflows/ci.yml`: analyze, test and build on every pull request and push.
- `.github/workflows/deploy.yml`: test, build and publish to GitHub Pages on every push to `main`.
- Repository variables: `CMS`, `CMS_SPACE`. Repository secret: `CMS_TOKEN`.