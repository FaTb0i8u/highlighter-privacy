# Privacy Policy

**Last updated: 7 August 2026**

Highlighter is a local-only browser extension. It is built so that the
question "where did my data go?" has exactly one answer: *nowhere*.

## What is collected

**Nothing is collected.** The extension has no analytics, no telemetry, no
crash reporting, no user accounts and no advertising identifiers.

## What is stored, and where

The extension stores the following in `chrome.storage.local`, which lives on
your own computer inside your Chrome profile:

| Data | Why it exists |
| --- | --- |
| The highlighted text and its surrounding context | To re-locate the passage the next time you open the page |
| Your notes and tags | To show them next to the highlight |
| The page URL, hostname and title | To group highlights by page in the library |
| The highlight colour and creation time | To render and sort your highlights |
| Your settings (theme, panel width, disabled sites, …) | To keep the extension configured the way you like it |

Tracking parameters (`utm_*`, `fbclid`, `gclid` and similar) are stripped from
URLs before they are stored, so the same article saved from two different
campaign links resolves to one entry.

## What is never stored

- Page content you did not explicitly highlight.
- Passwords, form input, cookies or browsing history.
- Anything you type into an editable field — the extension refuses to
  highlight inside inputs, textareas and `contenteditable` regions.

## Network activity

The extension makes **zero network requests**. There is no backend, no CDN and
no third-party script. Site icons in the library are drawn locally as letter
avatars rather than fetched from a favicon service, precisely so that browsing
your own library does not leak the list of sites you read to anyone.

## Site access

The extension **does** request access to all `http` and `https` sites
(`host_permissions`, shown by Chrome as "Read and change all your data on all
websites"). That warning is broad because Chrome has no narrower way to say
"any page the user chooses to highlight on" — highlights can be made anywhere,
so access cannot be limited to a fixed list of sites in advance.

What that access is actually used for:

- Running the content script that paints your highlights back onto a page.
- Reading the current tab's URL, so the toolbar badge can show how many
  highlights that page has.

What it is **not** used for: reading, collecting or transmitting page content.
Nothing is sent anywhere, because the extension makes no network requests at
all. If you would rather it not run on a particular site, add that hostname to
the disabled list in the options page.

## Chrome sync

Highlights are stored with `chrome.storage.local` and therefore stay on this
device. They are not uploaded to Google's sync servers.

## Your control over your data

- **Export** — download every highlight as JSON, Markdown, CSV or plain text
  from the extension's options page or side panel.
- **Import** — restore a JSON backup, merging with or replacing what is there.
- **Delete** — remove a single highlight, everything on one page, or all data
  at once from the options page.
- **Disable per site** — add any hostname to the disabled list and the
  extension will not run there.
- **Uninstall** — removing the extension deletes all of its stored data.

## Permissions

| Permission | Reason |
| --- | --- |
| `storage` | Save highlights and settings locally |
| `unlimitedStorage` | Avoid a 5 MB cap for users with large libraries |
| `host_permissions` (`http://*/*`, `https://*/*`) | Run the content script that renders your highlights, and read the current tab's URL for the badge count |

No `tabs`, `history`, `cookies`, `webRequest` or remote-code permissions are
requested.

## Changes

Any change to this policy will be published in this file in the repository, so
the full history is auditable.

## Contact

Open an issue in the project repository.
