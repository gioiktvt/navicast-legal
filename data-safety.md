---
layout: default
title: NaviCast Data Safety
permalink: /data-safety.html
lang: en
---

# NaviCast — Data Safety

**App**: NaviCast (`com.gioitv.navicast`)
**Last updated**: 2026-06-20

This page summarizes, for transparency, what NaviCast declares in the Google Play
"Data safety" section. The short version: **NaviCast collects and shares no user data.**

---

## Summary

| Question | Answer |
|---|---|
| Does the app collect or share any of the required user data types? | **No** |
| Is collected data encrypted in transit? | N/A — no data is transmitted |
| Can users request that their data be deleted? | N/A — no data is collected |

NaviCast has no user account, no analytics, and no advertising SDKs. It does not
read location, contacts, SMS, microphone, camera, calendar, or storage. It reads
Google Maps navigation notifications **only on your device**, turns them into a
local notification for your watch, and discards the original content. Nothing is
transmitted to any server (the app has no server).

---

## Data types (Google Play taxonomy)

For every data type Google Play lists, NaviCast's answer is **Not collected / Not shared**:

| Category | Collected? | Shared? |
|---|---|---|
| Personal info (name, email, IDs, address, phone…) | ❌ No | ❌ No |
| Financial info (incl. payment info) | ❌ No | ❌ No |
| Health & fitness | ❌ No | ❌ No |
| Messages (email, SMS, other) | ❌ No | ❌ No |
| Photos & videos | ❌ No | ❌ No |
| Audio files | ❌ No | ❌ No |
| Files & docs | ❌ No | ❌ No |
| Calendar | ❌ No | ❌ No |
| Contacts | ❌ No | ❌ No |
| App activity | ❌ No | ❌ No |
| Web browsing history | ❌ No | ❌ No |
| App info & performance (crash logs, diagnostics) | ❌ No | ❌ No |
| Device or other IDs | ❌ No | ❌ No |
| Location (approximate or precise) | ❌ No | ❌ No |

→ All data types: **not collected, not shared.**

---

## Note on notification access

NaviCast uses the notification-listener permission to read Google Maps' navigation
notification. Under Google Play's Data Safety guidance, "collected" means **data
transmitted off the device**. NaviCast reads the notification only locally, keeps it
briefly in memory to draw a maneuver icon + distance, produces a local notification,
and then discards it. No notification text, title, or content is transmitted to a
server, written to disk, logged in release builds, or shared with other apps. This is
the same posture as other on-device notification mirrors.

---

## Note on in-app purchases

NaviCast offers a one-time in-app purchase (a 7-day free trial, then an unlock).
Payments are processed entirely by **Google Play Billing**. Under Google Play's Data
Safety guidance, data handled by Google Play's billing system is **exempt** from the
developer's declaration — so this does not change any answer above. NaviCast never
receives or stores your card number or any payment information; it only learns whether
the unlock succeeded.

---

## Privacy Policy

Full details: [Privacy Policy](privacy-policy.html) ·
[Tiếng Việt](privacy-policy-vi.html) · [简体中文](privacy-policy-zh.html)
