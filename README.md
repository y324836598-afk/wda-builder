# Build WDA IPA via GitHub Actions

## Steps

1. Create a new public repo on GitHub (e.g. `wda-builder`).
2. Add `.github/workflows/build-wda.yml` (this directory's content) to the repo.
3. Push to GitHub.
4. Go to repo → Actions tab → "Build WebDriverAgent IPA (unsigned)" → "Run workflow".
5. Wait ~5-10 minutes for macOS runner to build.
6. After green check, click the run → scroll to "Artifacts" → download `WebDriverAgentRunner-unsigned-ipa`.
7. Unzip the artifact to get `WebDriverAgentRunner.ipa`.
8. Use Sideloadly to sideload the IPA with Apple ID free signing.

## Notes

- Free GitHub Actions macOS minutes per month: 2000 (private) / unlimited (public).
- Build is unsigned; Sideloadly does the per-device signing with Apple ID.
- IPA bundle id: `com.facebook.WebDriverAgentRunner.xctrunner`.
- 7-day signing lifetime with free Apple ID; just re-sideload to refresh.
