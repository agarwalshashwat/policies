# Resume My Journey — Privacy Policy

**Last updated: 2026-08-20 · Applies to Resume My Journey v1.x**

## The short version

Resume My Journey remembers where you were on a page so it can offer to put you
back. To do that it has to look at the page you are reading. Everything it
learns stays on your own device, is never transmitted anywhere, and you can
erase all of it in one click.

There is no account, no sign-in, no server, and no analytics.

## What it reads, and why

Being straight about this matters more than sounding reassuring: **this
extension does read the pages you visit.** That is the feature, not a
side-effect.

To resume you to an exact spot rather than the top of a page, it records *what
you were looking at* instead of a pixel measurement — because a pixel
measurement is wrong the moment a page renders at a different height. So when
you scroll, it looks at the block of content at the top of your screen and notes
enough to find it again later.

## What is stored on your device

For each page where you scrolled far enough to be worth remembering:

| Stored | Example |
|---|---|
| The page address and title | `en.wikipedia.org/wiki/…`, "Transmission Control Protocol" |
| A short excerpt of the text at the top of your screen | up to 72 characters, plus a short numeric fingerprint of that text |
| A way to find that element again | an element id or a structural path, e.g. `#history` |
| Your scroll offset and how far down the page you were | `9600px`, `41%` |
| A video or audio timestamp, if one was playing | `1:35` of `3:33` |
| The nearest section heading, so the offer can name where you'd land | "Congestion control" |

That is the whole record. It does **not** store the page's full text, images,
form input, passwords, or anything you typed.

All of it is kept in Chrome's local extension storage (`chrome.storage.local`)
on the machine where it was captured. Uninstalling the extension deletes it.

**Storage is capped** at roughly 4 MB and 2,000 pages. When it fills, the oldest
places are dropped automatically. You never have to prune anything, and it
cannot grow without bound.

## What is never collected or sent

- Nothing is transmitted anywhere. **The extension makes no network requests at
  all** — not to us, not to anyone.
- No browsing history is uploaded, sold, or shared.
- No analytics, no telemetry, no crash reporting, no advertising identifiers.
- No passwords, cookies, credentials, or payment details are read or stored.
- Chrome's own cross-device sync is **not** used, so your saved places do not
  travel to your other computers via your Google Account.

This is enforced by the build, not just by policy: the project's build fails if
any source file so much as references `fetch`, `XMLHttpRequest`, `WebSocket`,
`sendBeacon`, or Chrome's sync storage. A version that phoned home could not be
compiled.

## Pages it deliberately ignores

The extension does not record positions on sign-in, sign-up, logout, OAuth,
checkout, or account-authentication pages, or on any non-web page
(`chrome://`, local files, the extension's own pages). Resuming into a
half-finished login or payment flow would be useless at best.

## Permissions, and why each is needed

| Permission | Why |
|---|---|
| `storage` | To keep your saved places and your two settings on your device. |
| `tabs` | To know when the page in a tab changed, so the toolbar marker can show whether a saved position exists for the page you are on. |
| Access to websites (`<all_urls>`) | The extension has to run on whatever page you are reading in order to notice where you are in it. It resumes on any site rather than a hand-picked list, which means it needs access to all of them. |

Broad site access is a real trust ask, and it is the honest cost of a feature
that works everywhere instead of on ten approved domains. What limits the risk
is that nothing it reads can leave your machine.

## Third parties

None. No analytics provider, no error reporter, no ad network, no CDN, no
external fonts, no remote code.

## Your control

- **Pause saving** at any time from the toolbar popup.
- **Erase everything** with one click in the toolbar popup ("Forget everything").
- **Turn off the offer** so the extension stays silent, or turn on automatic
  resume so it does not ask.
- **Uninstall** removes all stored data along with the extension.

## Children

Resume My Journey is not directed at children and collects no data from anyone,
including children under 13.

## Changes

Material changes will be published here with a new "Last updated" date before
the build they describe is released.

## Contact

Questions about this policy: use the support link on the Chrome Web Store
listing.

---
