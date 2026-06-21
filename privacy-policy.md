---
layout: default
title: NaviCast Privacy Policy
permalink: /privacy-policy.html
lang: en
---

# Privacy Policy — NaviCast

**App name**: NaviCast
**Application ID**: `com.gioitv.navicast`
**Developer**: gioitv (gioitv86@gmail.com)
**Effective date**: 2026-05-08
**Last updated**: 2026-06-20

---

## 1. Summary

NaviCast is an Android companion app that forwards turn-by-turn navigation icons from your phone to your Huawei smartwatch via Huawei Health. **NaviCast does not collect, store, or transmit any personal data off your device.** Every operation is performed locally; nothing leaves your phone.

If you read nothing else, read this:
- ❌ No user accounts, no login.
- ❌ No analytics, no tracking, no advertising SDKs.
- ❌ No notification content (text, addresses, ETA, place names) is ever uploaded, stored on a server, or shared with third parties.
- ❌ No location, contacts, microphone, camera, SMS, or storage access.
- ✅ Reads Google Maps notifications (only) on your device, converts them to a watch-friendly notification, posts it locally so Huawei Health can forward to your watch.
- 💳 NaviCast is free to try. After a free trial period, a **one-time in-app purchase** unlocks the app permanently. The purchase is processed entirely by **Google Play Billing** — NaviCast never sees, handles, or stores your payment-card details, and no purchase is tied to any account we hold (we hold none).

---

## 2. Data we collect

**None.** NaviCast does not collect, transmit, or persist any personal data. Specifically:

| Data type | Collected? | Notes |
|---|---|---|
| Personal identifiers (name, email, phone, account ID) | ❌ No | App has no account system |
| Location | ❌ No | Location permission is **not requested** |
| Contacts, SMS, call logs | ❌ No | These permissions are **not requested** |
| Notification content (Google Maps maneuver text, addresses) | ⚠️ Read only on-device | Used only to render an icon + distance label on a local notification. Never persisted, logged, or transmitted. |
| Device identifiers (IMEI, advertising ID) | ❌ No | App does **not** read device IDs |
| Crash reports, analytics, diagnostics | ❌ No | NaviCast ships without Firebase, Crashlytics, Sentry, or any analytics SDK |
| Files, photos, media | ❌ No | Storage permission is **not requested** |
| Payment / card details | ❌ No | One-time purchases are processed by **Google Play Billing**. NaviCast never receives your card number, billing address, or any payment instrument data. |
| Purchase status | ⚠️ On-device only | After you buy, NaviCast stores a local "unlocked" flag and queries Google Play to confirm your entitlement. This flag is not personal data and is not transmitted to us (we run no server). |

**App settings** (watch model preset, distance unit, language, theme, vibration toggle, onboarding completion flag) are stored locally on your device using Android Jetpack DataStore in the app's private storage area. These settings:
- Never leave your device.
- Are wiped on app uninstall.
- Contain no personal data — only your UI preferences.

---

## 3. Permissions we request

NaviCast requests **only** the minimum permissions needed to do its job:

| Permission | Why we need it |
|---|---|
| `BIND_NOTIFICATION_LISTENER_SERVICE` | To read Google Maps' navigation notification on your phone. This is the **only** way to know when a maneuver is coming. The system enforces this via the "Notification access" toggle in Settings — you control when NaviCast can read notifications. |
| `POST_NOTIFICATIONS` (Android 13+) | To create a local notification with the maneuver icon, which Huawei Health forwards to your watch. |
| `FOREGROUND_SERVICE` + `FOREGROUND_SERVICE_SPECIAL_USE` | To keep our notification listener alive during navigation (Android otherwise kills it after a few minutes on some devices). |
| `com.android.vending.BILLING` | To offer the one-time in-app purchase that unlocks the app after the free trial, via Google Play Billing. No payment data is handled by NaviCast. |

We do **not** request: location, contacts, SMS, microphone, camera, storage, Bluetooth, phone state, or "query all packages".

You can revoke `BIND_NOTIFICATION_LISTENER_SERVICE` at any time:
**Settings → Apps → Special access → Notification access → toggle NaviCast off.**

When this is off, NaviCast cannot read any notification, including Google Maps. The forwarding stops immediately.

---

## 4. Third-party services

NaviCast uses only **one** third-party service — Google Play Billing, for purchases. Specifically:
- ❌ No Firebase, Google Analytics, or any Google Play Services SDK beyond standard Android system services and billing.
- ❌ No Crashlytics, Sentry, Bugsnag, or other crash reporters.
- ❌ No advertising SDKs.
- ❌ No social login.
- ✅ **Google Play Billing** — used solely to process the one-time in-app purchase that unlocks the app after the free trial.

**Google Play Billing.** When you choose to buy, NaviCast hands you off to the Google Play Store app, which collects and processes your payment entirely on its side. NaviCast receives back only a purchase token / entitlement state confirming the unlock — never your card number, billing address, or any payment instrument. Google's handling of that payment data is governed by **Google's Privacy Policy** (https://policies.google.com/privacy), not by us.

NaviCast interacts with **Huawei Health** only indirectly: it posts a regular Android notification, and Huawei Health (which you install and configure separately) reads it the same way it reads any other notification. We don't use Huawei Health's APIs directly.

---

## 5. Data sharing

We share **no data with anyone**. There is no data to share — nothing leaves your device.

Specifically:
- We do not sell your data.
- We do not share with advertisers.
- We do not share with analytics providers.
- We do not share with law enforcement (we have no data to provide).

The single exception is **payment processing**: if you make a purchase, your payment is handled directly between you and **Google Play**, under Google's own privacy policy. NaviCast neither receives nor forwards that payment data — we only learn whether the unlock succeeded.

---

## 6. Children's privacy

NaviCast is not directed at children under 13. The app does not knowingly collect any data from anyone, including children. Because nothing is collected, nothing concerning children needs to be stored, deleted, or reported.

---

## 7. Your rights

Because NaviCast collects no data, there is no data to access, delete, or export. However:

- **To stop the app from reading notifications**: revoke notification access (Settings → Apps → Special access → Notification access → NaviCast → off).
- **To stop the app entirely**: uninstall it. All local settings are wiped.
- **To request information**: contact the developer (see §10 below). We will respond within 30 days.

If you live in the EU/UK (GDPR/UK DPA), the EEA, California (CCPA), or similar jurisdictions, your rights to access/rectify/delete personal data are preserved by default — there is simply no personal data being processed.

---

## 8. Security

NaviCast follows defensive security practices:
- All processing is **on-device only**. There is no server.
- Notification content is held in volatile memory (RAM) for the duration of one navigation session, then released.
- No notification content is logged in release builds (verified by source code audit + ProGuard rules).
- The signed release APK is built via an automated CI pipeline; the signing key never leaves the developer's secured environment.
- Source code is closed-source and reviewed before each release.

---

## 9. Changes to this policy

If we ever change this policy, we will:
1. Update the "Last updated" date at the top.
2. Note the change in app's release notes (Play Store).
3. If the change is material (e.g., we ever started collecting any data — which we have no plans to do), we will require explicit user consent before the change takes effect.

You can check the current version at: `https://gioiktvt.github.io/navicast-legal/privacy-policy.html` (English) or `https://gioiktvt.github.io/navicast-legal/privacy-policy-vi.html` (Vietnamese).

---

## 10. Contact

For questions, requests, or concerns about this Privacy Policy:

- **Email**: gioitv86@gmail.com

Please use English or Vietnamese.

---

## 11. Trademark notice

"Google Maps" and the Google Maps logo are trademarks of Google LLC.
"Vietmap" is a trademark of Vietmap Joint Stock Company.
"Waze" is a trademark of Waze Mobile Ltd.
"Huawei", "Huawei Health", "Huawei Watch", "Huawei Band", "Huawei Watch GT", "Huawei Watch Fit" are trademarks of Huawei Technologies Co., Ltd.

NaviCast is an **independent third-party companion app**. It is **not affiliated with, endorsed by, or sponsored by** Google, Vietmap, Waze, or Huawei. NaviCast does not use these companies' APIs (other than reading public Android notifications, which any user-installed app with notification access can do).

---

*This policy is written in plain English. The Vietnamese version is at [privacy-policy-vi.md](privacy-policy-vi.md). Both versions are legally equivalent; in case of disagreement, the Vietnamese version controls for users in Vietnam, the English version controls elsewhere.*
