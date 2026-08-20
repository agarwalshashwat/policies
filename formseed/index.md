# Formseed — Privacy Policy

**Last updated: 2026-08-20 · Applies to Formseed v1.x**

## The short version

Formseed reads the form on the tab you are looking at, works out what each field
means, makes up realistic test data, and types it in. All of that happens inside
your browser. Nothing about the page is sent anywhere, because Formseed has
nowhere to send it: it makes no network requests at all.

## What Formseed collects

**No personal data of any kind.** Specifically, Formseed does not collect,
transmit, sell, share, or retain:

- browsing history, URLs, or page titles
- the content of any page you visit
- anything you have typed into a form
- personal or financial information
- authentication details, cookies, or credentials
- location, device identifiers, or usage analytics

There is no account, no sign-in, and no telemetry.

## Permissions, and why each one exists

Formseed requests exactly three permissions and **no host permissions**.

| Permission | Why it is needed |
|---|---|
| `activeTab` | To read and fill the form on the tab you are looking at. This is granted **only when you click the Formseed toolbar button**, applies **only to that one tab**, and expires as soon as that tab navigates elsewhere. |
| `scripting` | To run the analyze-and-fill code inside that tab once `activeTab` has granted access to it. Without a host permission it cannot reach any tab you have not clicked on. |
| `storage` | To remember your own settings: scenario, locale, record count, the two toggles, and whether you have dismissed the welcome message. |

**Formseed requests no host permissions and registers no content scripts.** It
has no standing ability to read the pages you visit — not as a policy promise,
but as a limit of what it is installed with. Nothing runs on any page until you
click the button. You can verify this on `chrome://extensions`: Chrome does not
show the "read and change all your data on all websites" warning for Formseed,
because it never asks for it.

## What is stored, and where

Only your settings, in `chrome.storage.local` on your own device. That is a
handful of preferences — which scenario you picked, which locale, how many
records, and two on/off toggles.

Formseed deliberately does **not** use `chrome.storage.sync`, which Chrome would
upload to your Google Account. Nothing Formseed stores ever leaves your machine.

**Page content is never stored at all** — not the fields it found, not the values
it generated, not the address of the page. Analysis results live in memory only,
for as long as the popup is open, and are gone when you close it.

## What Formseed writes to the page

It fills form fields, and only form fields. It will not:

- submit a form, click a button, or navigate anywhere
- touch a password, payment-card, or one-time-code field
- put a value into a dropdown or radio group that was not already one of its own
  options
- overwrite something you typed yourself, unless you turn on the overwrite
  toggle

Anything it decides not to fill is listed in the popup with the reason.

## Third parties

None. No analytics provider, no crash reporter, no ad network, no CDN, no
external fonts, no remote code. Formseed makes no network requests at all, and
its source contains no networking code — this is enforced automatically at build
time, so a change that introduced one would fail the build rather than ship.

## Known limitation: fields inside other sites' frames

Some pages embed forms from another domain inside a frame — payment-card fields
and some embedded form widgets work this way. **Formseed cannot fill those**, and
equally **cannot read them**.

This is a direct consequence of holding no host permissions: `activeTab` grants
access to the site you are on, and not to third-party frames inside it. Reaching
them would require the permanent "all your data on all websites" access this
extension is deliberately built without. Those fields are listed as skipped
rather than silently ignored.

## Artificial intelligence

The version covered by this policy uses **no AI or machine learning of any kind**.
Field detection is entirely rule-based and runs on your device.

A future version may optionally use Chrome's built-in on-device AI, which would
also run locally and send nothing anywhere. If a version is ever released that
can send data to an external AI provider, it will be **off by default**, will
require you to turn it on explicitly and supply your own API key, and this policy
will be updated to describe it before that version ships. No such feature exists
today.

## Children

Formseed is a tool for software developers and is not directed at children. It
collects no data from anyone, of any age.

## Changes to this policy

Material changes will be published here with an updated date, before or alongside
the release they describe.

## Contact

Questions about this policy: **shashwat@ideaclan.com**
