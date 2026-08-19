# Duckout — Privacy Policy

**Last updated: 2026-08-19 · Applies to Duckout v1.x (panic-hide)**

## The short version

Duckout collects nothing, sends nothing, and has no servers. It moves your tabs
around inside your own browser. That is all it does.

## What Duckout collects

**No personal data of any kind.** Specifically, Duckout does not collect,
transmit, sell, share, or retain:

- browsing history, URLs, or page titles
- the content of any page you visit
- personal or financial information
- authentication details, cookies, or credentials
- location, device identifiers, or usage analytics

There is no account, no sign-in, and no telemetry.

## Why Duckout cannot read your pages

Duckout requests exactly two permissions:

| Permission | Why it is needed |
|---|---|
| `tabs` | To move a tab into a background window and move it back. Hiding a tab *is* a tab operation, so this permission is the feature. |
| `storage` | To remember your two settings, and to remember which tabs are currently hidden so they can be restored. |

Duckout requests **no host permissions and registers no content scripts**. Under
Chrome's extension model that means it has no ability to read or modify the
contents of the pages you visit — not as a policy promise, but as a limit of what
it is installed with. You can verify this yourself on `chrome://extensions`: the
permission list shows tab and storage access and nothing about site data.

## What is stored, and where

Everything stays on your device, in Chrome's own extension storage:

- **Your settings** (two on/off preferences: mute-while-hidden, show-decoy) are
  kept in `chrome.storage.sync`. **Honest caveat:** if you have Chrome Sync
  enabled, Chrome itself syncs this storage area across your signed-in Chrome
  installations via your Google Account. That transfer is performed by Chrome, not
  by Duckout, and it carries only those two on/off values — never URLs, titles, or
  page content. Turn off Chrome Sync, or use `chrome.storage.local` builds, if you
  would rather it stayed on one machine.
- **Which tabs are currently hidden** is kept in `chrome.storage.session`, which
  Chrome clears when you quit the browser. It holds tab IDs and positions so a
  hidden tab can be put back; it is never transmitted anywhere.

Uninstalling Duckout removes both.

## Third parties

None. No analytics provider, no crash reporter, no ad network, no CDN, no
external fonts, no remote code. Duckout makes no network requests at all.

## What Duckout protects you from — and what it does not

Duckout is designed for **shoulder-surfing**: someone glancing at your screen in
an office, a café, a classroom, or a shared room.

It does **not** protect you from network monitoring, your employer's IT or device
management, your internet service provider, software installed on your computer,
or your browser history. Duckout has no ability to affect any of those, and you
should not rely on it as though it did.

## Children

Duckout is not directed at children and collects no data from anyone, including
children under 13.

## Changes

Material changes will be published here with a new "Last updated" date before the
build they describe is released.

## Contact

Questions about this policy: open an issue on the project's public repository, or
use the support link on the Chrome Web Store listing.

---
