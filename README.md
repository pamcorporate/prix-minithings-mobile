# Prix & MiniThings - Mobile (iOS + Android)

Native shells that wrap the existing web game and run it fully offline.
The game stays one `index.html`. This folder packages a snapshot of it.

- Bundle ID (permanent once submitted): `com.pamcorporate.prixminithings`
- App name: `Prix & MiniThings`
- Pricing: paid up front, $5. No in-app purchases.
- Wrapper: Capacitor 8.4.1. iOS + Android built in the cloud on Codemagic (no Mac needed).
- Source game: `../app/index.html` (v1.0.45). This `www/` is a packaged copy, not the live file.

## Update model
Web and Steam stay instant-deploy. Mobile is not. Every change means a new
build plus store review, so changes get batched. To refresh: re-run the offline
bundle, bump `version` in package.json, rebuild, resubmit.

## Layout
- `www/` - the offline-bundled game. Built from `app/index.html` with:
  - Supabase SDK vendored to `www/vendor/supabase.js` (was a jsdelivr CDN URL).
  - `SPRITE_BASE` -> `./sprites/` (the 5 Stan PNGs are bundled there).
  - referral fallback URL set to `https://pamcorporate.com`.
  - native polish in the page head: pinch-zoom disabled, and `navigator.vibrate`
    routed through real iOS haptics when running in the app.
- `assets/` - icon (1024) + splash (2732, light/dark) masters. Stan on the
  4-stud brick. The build expands these into every device size.
- `capacitor.config.json` - app id/name, dark status bar, splash, safe-area insets.
- `codemagic.yaml` - cloud build pipeline for both platforms.
- `package.json` - Capacitor 8 + plugins.
- The native `ios/` and `android/` projects are generated during the build
  (`npx cap add`), so they are intentionally not committed.

## Status
- [x] Offline bundle (game + vendored Supabase SDK + 5 sprites). em-dash 0, JS valid.
- [x] App icon + splash masters (Stan on the corporate brick).
- [x] Capacitor 8 scaffold: package.json, capacitor.config.json, .gitignore.
- [x] Native config: dark status bar, notch/home-indicator safe-areas, zoom off, iOS haptics.
- [x] `codemagic.yaml` cloud build pipeline (Android .aab + iOS .ipa).
- [ ] Privacy policy + Data Safety / App Privacy answers + age rating. (drafting next)
- [ ] Store listings (copy + screenshots). (drafting next)
- [ ] GitHub repo + Codemagic + signing (your accounts).
- [ ] Play Console + App Store Connect listings + submit (I drive, you approve).

## Integrity baseline (this packaged copy)
em-dash 0 . CSS braces 632/632 . divs 361/361 . 2 script blocks, both valid.

## Apple compliance notes
- Offline bundling is done, so Apple should not read this as a thin web wrapper (4.2).
- The in-app "Our website" link to pamcorporate.com is flagged: that site advertises
  buying the game on stores, which Apple can read as steering. Default plan: hide it
  in the iOS build. Pending Josh's call.
- Expect a Teen / 12+ age rating (wheel/slots minigames read as simulated gambling;
  premise is fictional theft).

## First-build watch list (verify on device once Codemagic runs)
- App display name with the `&` (Android strings.xml escaping).
- Safe-area framing on a notched device.
- OTP / referral text input not hidden behind the keyboard.
