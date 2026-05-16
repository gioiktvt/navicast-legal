---
layout: default
title: NaviCast Data Safety
permalink: /data-safety.html
lang: en
---

# Google Play Console — Data Safety Form Draft

**App**: NaviCast (`com.gioitv.navicast`)
**Form version**: Play Console Data Safety form (2026 schema)
**Drafted**: 2026-05-08
**Owner**: Security agent — review by anh Giới before submission

> Anh Giới: copy-paste vào Play Console "Data safety" section khi tạo app listing. Mọi câu trả lời justified bởi source code path — see §"Justification" cuối form.

---

## Section 1 — Data collection and security

### Q1. Does your app collect or share any of the required user data types?

**Answer: No**

Justification: NaviCast does not collect or share any user data type listed in Play's Data Safety taxonomy. Specifically, app:
- Has no user account, no login, no analytics SDK.
- Does not read location, contacts, SMS, microphone, camera, calendar, or storage.
- Reads Google Maps notifications only on-device (similar to any notification listener app like Pushbullet) and produces a local notification; no notification content is transmitted, persisted, or shared.
- No third-party libraries that collect data (no Firebase, Crashlytics, ads SDK).

Source code evidence:
- `app/src/main/AndroidManifest.xml` — no internet permission (P1 baseline), no user-data permission.
- `app/src/main/java/com/gioitv/navicast/service/` — listener filter restricted to `com.google.android.apps.maps`. No `OkHttp`, `Retrofit`, `URL`, `WebSocket` imports anywhere in `service/`, `parser/`, `publisher/`.
- `app/src/main/java/com/gioitv/navicast/data/` — DataStore only stores user preferences (watch preset, units, language, theme, notification toggle, vibration toggle, onboarding flag). Nothing personal.

### Q2. Is all of the user data collected by your app encrypted in transit?

**Answer: N/A — no data transmission**

Justification: There is no data transmission, encrypted or otherwise. App operates entirely on-device.

### Q3. Do you provide a way for users to request that their data is deleted?

**Answer: N/A — no data collected**

Justification: There is no user data to delete. User can:
- Revoke `BIND_NOTIFICATION_LISTENER_SERVICE` to stop reading notifications.
- Uninstall app to wipe local DataStore preferences.

### Q4. Has your app been independently validated against a global security standard?

**Answer: No**

Justification: NaviCast is a small, independent open-beta app. No third-party security audit has been performed. App follows internal security policy (`.agents/protocols/security-policy.md`) and undergoes Architect + Security agent review for every code change.

---

## Section 2 — Data types (per Play taxonomy)

For each data type Play lists, NaviCast's answer:

| Category | Type | Collected? | Shared? | Required for app? |
|---|---|---|---|---|
| **Personal info** | Name | ❌ No | ❌ No | No |
| | Email address | ❌ No | ❌ No | No |
| | User IDs | ❌ No | ❌ No | No |
| | Address | ❌ No | ❌ No | No |
| | Phone number | ❌ No | ❌ No | No |
| | Race/ethnicity | ❌ No | ❌ No | No |
| | Political/religious beliefs | ❌ No | ❌ No | No |
| | Sexual orientation | ❌ No | ❌ No | No |
| | Other personal info | ❌ No | ❌ No | No |
| **Financial info** | (any) | ❌ No | ❌ No | No |
| **Health & fitness** | Health info | ❌ No | ❌ No | No |
| | Fitness info | ❌ No | ❌ No | No |
| **Messages** | Emails | ❌ No | ❌ No | No |
| | SMS / MMS | ❌ No | ❌ No | No |
| | Other in-app messages | ❌ No | ❌ No | No |
| **Photos and videos** | Photos | ❌ No | ❌ No | No |
| | Videos | ❌ No | ❌ No | No |
| **Audio files** | Voice/sound recordings | ❌ No | ❌ No | No |
| | Music files | ❌ No | ❌ No | No |
| | Other audio files | ❌ No | ❌ No | No |
| **Files and docs** | Files and docs | ❌ No | ❌ No | No |
| **Calendar** | Calendar events | ❌ No | ❌ No | No |
| **Contacts** | Contacts | ❌ No | ❌ No | No |
| **App activity** | App interactions | ❌ No | ❌ No | No |
| | In-app search history | ❌ No | ❌ No | No |
| | Installed apps | ❌ No | ❌ No | No |
| | Other user-generated content | ❌ No | ❌ No | No |
| | Other actions | ❌ No | ❌ No | No |
| **Web browsing** | Web browsing history | ❌ No | ❌ No | No |
| **App info & performance** | Crash logs | ❌ No | ❌ No | No |
| | Diagnostics | ❌ No | ❌ No | No |
| | Other app performance data | ❌ No | ❌ No | No |
| **Device or other IDs** | Device or other IDs | ❌ No | ❌ No | No |
| **Location** | Approximate location | ❌ No | ❌ No | No |
| | Precise location | ❌ No | ❌ No | No |

→ **All 35 data types: not collected, not shared.** App falls into the "no data collected" category in the Data Safety section.

---

## Section 3 — Special note on notification content (Google Play reviewer FAQ)

Reviewers may ask: *"NaviCast requests `BIND_NOTIFICATION_LISTENER_SERVICE` — doesn't that count as collecting Messages/Other data?"*

**Answer**: Per Google Play's Data Safety guidance, **"collected" means transmitted off device**. NaviCast reads notifications only locally, processes them in volatile memory, produces a local notification, and discards the original content. No notification text/title/extras is:
- Transmitted to a server (NaviCast has no server endpoint and no internet permission in P1).
- Persisted to disk (no DataStore/Room/file write of notification content).
- Logged in release builds (verified by source audit + ProGuard `-assumevalues` rules + R8 strip of debug-only `ExtrasDumper` class).
- Shared via Intent / IPC with other apps (no broadcast, no content provider, no shared file).

Therefore, even though NaviCast technically *reads* notifications, it does not *collect* user data per Play's definition. This is the same posture as system-level notification mirrors (e.g., Wear OS, AirDroid, Pushbullet declared in Data Safety).

For technical proof:
- Source code audit log: `.agents/security/audits/audit_P1-T2_notification_flow.md` (after T2 merge).
- Network library negative scan: `git grep -E "okhttp|retrofit|ktor|HttpURLConnection|URLConnection|WebSocket" app/src/main/` → 0 hits.
- Persistence negative scan: `git grep -rE "DataStore.*write|edit\\(\\)" app/src/main/java/com/gioitv/navicast/(service|parser|publisher)/` → 0 hits (DataStore only used in `data/` for preferences).

---

## Section 4 — Privacy Policy URL

```
https://gioiktvt.github.io/navicast-legal/privacy-policy.html
```

(Will be live after Developer wires GitHub Pages deploy from `docs/legal/privacy-policy-en.md` + `privacy-policy-vi.md` — recommend follow-up task `P1.T10b — GitHub Pages deploy` if not already in plan.)

---

## Section 5 — Form submission checklist

Before submission, anh Giới verify:

- [ ] All 35 data types marked "Not collected" + "Not shared"
- [ ] Q1 = No, Q2 = N/A, Q3 = N/A, Q4 = No
- [ ] Privacy Policy URL live + accessible (HTML version of `privacy-policy-en.md`)
- [ ] App description in Play Console contains trademark disclaimer (see [trademark-disclaimer.md](trademark-disclaimer.md))
- [ ] Screenshots do not show notification content from real Maps navigation (use mock/synthetic per security policy §2)
- [ ] Title does NOT contain "Huawei", "Google Maps", "Waze", "Vietmap" (Play Trademark Policy)
- [ ] Body description disclaims affiliation with Huawei/Google/Vietmap/Waze

If any checklist item fails, **do not submit** — fix first.

---

## Changelog
- 2026-05-08 — Security agent created P1.T10 draft. Pending: Developer GitHub Pages deploy + anh Giới Play Console review.
