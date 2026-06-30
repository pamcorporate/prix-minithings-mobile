# Store compliance answers - Prix & MiniThings

Use these when filling the console forms. They reflect what the game actually does:
no ads, no third party analytics or tracking SDKs, backend is Supabase only.
Data collected: email (sign in, optional), game save, referral code, user-submitted bug reports.

Privacy policy URL (host first): https://prix-minithings.vercel.app/privacy.html

---

## Google Play - Data Safety form

- Does your app collect or share user data? **Yes, collects. Does not share.**
  (Supabase is our processor/infrastructure, not a third party we "share" data with.)
- Is all data encrypted in transit? **Yes.**
- Do you provide a way to request data deletion? **Yes** (email josh@pamcorporate.com; in-app Wipe clears local data).

Data types to declare as **Collected** (not shared):

| Category | Data type | Collected | Purpose | Optional? |
|---|---|---|---|---|
| Personal info | Email address | Yes | Account management, App functionality | Optional (only if you sign in) |
| App activity | App interactions (game save / progress) | Yes | App functionality | Optional |
| App info & performance | Diagnostics (user-submitted bug report logs) | Yes | App functionality | Optional |

Declare **NOT collected**: location, financial info, health, photos/videos, audio, contacts,
calendar, messages, browsing history, device or advertising IDs.

---

## Apple - App Privacy (nutrition label)

- Used to track you? **No.** (No cross-app/website tracking, no ad identifier.)
- Data **linked to you** (only when signed in), all for **App Functionality**:
  - Contact Info -> Email Address
  - User Content -> game save / other user content
  - Diagnostics -> other diagnostic data (bug reports)
- Data **not linked to you**: none beyond the above.
- Declare nothing under Tracking.
- Everything else (location, identifiers, purchases, browsing, financial, health, contacts): **Not Collected.**
  Purchases are handled by Apple, not collected by the app.

---

## Age rating questionnaire

Answer the questionnaire with the facts below; the store computes the final tier.

Key facts about the content:
- **Simulated gambling: YES.** The wheel and slot-style minigames are gambling-themed
  but use no real money and pay only in-game currency. This is the main rating driver.
- Violence: none.
- Sexual content / nudity: none.
- Profanity / crude humor: mild (satirical).
- Mature/suggestive themes: mild (dark comedy about corporate greed and fictional theft).
- Controlled substances: none.
- Real-money gambling: none.
- User-generated content / social: none (no chat, no sharing of user content).

Expected outcome: **Google Play Teen**; **Apple 12+ or higher** (simulated gambling can push
Apple's tier up). The questionnaire sets the final number, this is just the ballpark.

Note: keep the satire clearly fictional in all metadata. The game already states it is satire
and that all characters are invented.

---

## Other declarations
- Ads: **No ads.**
- In-app purchases: **None.** (Paid up front, $5.)
- Account creation: optional; the game is fully playable without an account.
- Account deletion: supported by email (required by both stores when accounts exist).
- Export compliance (Apple): uses only standard HTTPS encryption -> answer "No" to the
  question about non-exempt/custom encryption (standard exemption applies).
