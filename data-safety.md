---
layout: default
title: NaviCast Data Safety
permalink: /data-safety.html
lang: en
---

# NaviCast — Data Safety

**App**: NaviCast
**Last updated**: 2026-11-27

This page summarizes, for transparency, what NaviCast declares in the Google Play
"Data safety" section. The short version: **only what you type into the search box (with an approximate position), and precise location on the Ultimate tier, ever leave your device. Neither is stored.**

---

## Summary

| Question | Answer |
|---|---|
| Does the app collect or share any of the required user data types? | **Yes — location, and search terms when you search for a destination** |
| Is collected data encrypted in transit? | **Yes** |
| Can users request that their data be deleted? | N/A — nothing is stored off-device |

NaviCast has no user account, no analytics, and no advertising. It does not read
contacts, SMS, microphone, camera, calendar, or storage. It reads Google Maps navigation
notifications **only on your device**, turns them into a local notification for your watch,
and discards the original content. **Notification content is never transmitted anywhere.**

**Two kinds of data leave the device, both only for app functionality:**

1. **Search terms and an approximate position** — when you search for a destination (all tiers), the text you type and
   a position rounded to about 100 m are sent to NaviCast's search service so nearby results come first. Nothing is
   stored.
2. **Precise location — Ultimate tier only.** Its live map and standalone navigation read precise location once you
   enable that feature, and send coordinates to map service providers for map tiles, routing and place search. Under
   Google's definition, data transmitted off the device is *collected*; these providers are third parties, so
   *shared* is declared as well. Optional. No background location. The Standard and Pro tiers never request location.

NaviCast keeps no location history and no search history off the device.

---

## Data types (Google Play taxonomy)

For every data type Google Play lists except location and app activity, NaviCast's answer is
**Not collected / Not shared**:

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
| **App activity** (in-app search terms) | ✅ **Yes** — see note below | ❌ No |
| Web browsing history | ❌ No | ❌ No |
| App info & performance (crash logs, diagnostics) | ❌ No | ❌ No |
| Device or other IDs | ❌ No | ❌ No |
| **Location (approximate and precise)** | ✅ **Yes** — see note below | ✅ **Yes** — to the map service providers above |

### Note — what changed in Android 1.0.35

Before 1.0.35 the only collected type was **location**, and only on the Ultimate tier. From 1.0.35
NaviCast looks up places through its own search service, so two entries change
for **all tiers**, not just Ultimate:

| Data type | Purpose | Shared? | Stored? | Optional? |
|---|---|---|---|---|
| **App activity** — the destination you type into the search box | App functionality (finding a destination) | ❌ No | ❌ No — the server keeps no search terms | Yes: searching is a thing you choose to do |
| **Location (approximate)** — rounded to ~100 m, sent with a search so nearby results come first | App functionality | ❌ No | ❌ No | Yes: searching works without it, results are just less local |

Both are **encrypted in transit** and **not stored**. Neither is linked to a user account — NaviCast
has none. Navigation notification content is still **never transmitted anywhere**; this entry covers
only what you yourself type into the search box.

Precise location on the Ultimate tier is unchanged: it goes to the map service providers while you
navigate, as before.

→ Collected: **app activity** (search terms) and **location** — for **App functionality** only, encrypted in transit,
not stored. Shared: **precise location on the Ultimate tier** only, with map service providers. Every other data type:
not collected, not shared.

---

## Note on notification access

NaviCast uses notification access to read Google Maps' navigation
notification. Under Google Play's Data Safety guidance, "collected" means **data
transmitted off the device**. NaviCast reads the notification only locally, keeps it
briefly in memory to draw a turn icon and distance, produces a local notification,
and then discards it. No notification text, title, or content is transmitted to a
server, written to disk, logged in release builds, or shared with other apps.

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
