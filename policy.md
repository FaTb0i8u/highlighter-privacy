# Privacy Policy

<!--
  The published copy of this policy, and the URL the Chrome Web Store listing
  points at, is:
  https://github.com/FaTb0i8u/highlighter-privacy/blob/main/policy.md
  The two copies must stay identical. A mismatch between the published policy,
  the dashboard disclosures and the extension's behaviour is itself a Chrome
  Web Store policy violation.
-->

**Last updated: 11 November 2026**

Highlighter is a local-only browser extension. It is built so that the
question "where did my data go?" has exactly one answer: *nowhere*.

## What leaves your device

**Your annotations are never uploaded.** The extension has no
analytics, no telemetry, no crash reporting, no user accounts and no
advertising identifiers. When you open a PDF in Highlighter, it downloads that
document from its original site, which receives the usual document request
(including authentication cookies where the browser permits). There is no
annotation data in that request. The
developer never receives your data, because there is no server to receive it.
Optional settings sync is limited to settings — see
[Chrome sync](#chrome-sync) below.

The extension does, however, *handle* data on your own machine in order to
work. That is disclosed in full below and in the Chrome Web Store listing, as
"website content" and "web history".

## What is stored, and where

The extension stores the following in `chrome.storage.local`, which lives on
your own computer inside your Chrome profile:

| Data | Why it exists |
| --- | --- |
| The highlighted text and its surrounding context | To re-locate the passage the next time you open the page |
| Your notes and tags, and any note you write about a whole page | To show them next to the highlight or page |
| The page URL, hostname and title | To group highlights by page in the library |
| The highlight colour and creation time | To render and sort your highlights |
| Freehand strokes, pen colour/width and PDF page coordinates | To restore drawings on webpages and PDF pages |
| Your settings (theme, panel width, disabled sites, …) | To keep the extension configured the way you like it |

Tracking parameters (`utm_*`, `fbclid`, `gclid` and similar) are stripped from
URLs before they are stored, so the same article saved from two different
campaign links resolves to one entry.

## What is never stored

- Page content you did not explicitly highlight. PDF bytes are processed in
  memory for viewing, not saved in extension storage.
- Passwords, form input, cookies or browsing history.
- Anything you type into an editable field — the extension refuses to
  highlight inside inputs, textareas and `contenteditable` regions.

## Network activity

The PDF viewer requests the document URL you explicitly open from its original
site. A downloaded copy you choose with the file picker is read locally and
never uploaded. Annotated-PDF exports are created entirely on your device and
saved as a separate file with highlights and drawings embedded. The original
is unchanged; notes and tags remain in extension storage/JSON backups.
PDF.js, pdf-lib, fonts, character maps and rendering assets are bundled
with the extension, not fetched from a CDN. There is no backend, analytics
service or remotely loaded script. Normal webpage highlighting makes no network
requests. Site icons in the library are drawn locally as letter
avatars rather than fetched from a favicon service, precisely so that browsing
your own library does not leak the list of sites you read to anyone.

The one link in the interface — the optional "Buy me a coffee" link in the side
panel, popup and settings page — is an ordinary link. Nothing is loaded from
Buy Me a Coffee unless you deliberately click it, at which point your browser
opens `buymeacoffee.com` in a new tab and that site's own privacy policy
applies. The coffee cup icon is drawn locally, for the same reason as the site
icons above: an image hosted by Buy Me a Coffee would tell them that you use
this extension even if you never clicked. The extension is free, nothing is
gated behind a payment, and the developer receives no information about who
clicked or who donated beyond what Buy Me a Coffee shows any creator.

## Site access

The extension **does** request access to all `http` and `https` sites
(`host_permissions`, shown by Chrome as "Read and change all your data on all
websites"). That warning is broad because Chrome has no narrower way to say
"any page the user chooses to highlight on" — highlights can be made anywhere,
so access cannot be limited to a fixed list of sites in advance.

What that access is actually used for:

- Running the content script that paints your highlights back onto a page.
- Reading the current tab's URL, so the toolbar badge can show how many
  annotations that page has and whether highlighting or drawing is enabled.
- Downloading a PDF from its original site when you choose to open it in
  Highlighter.

What it is **not** used for: collecting or uploading your annotations or page
content to the developer. If you would rather it not run on a particular site, add that hostname to
the disabled list in the options page.

## Chrome sync

Highlights and notes are stored with `chrome.storage.local` and therefore stay
on this device. They are never uploaded to Google's sync servers.

Settings sync is **off by default**. If you turn on *Sync settings across your
Chrome devices* in the options page, your settings — theme, colour names,
disabled sites and behaviour preferences — are written to
`chrome.storage.sync`. Chrome then stores them in your Google account and
copies them to your other signed-in Chrome browsers, under
[Google's privacy policy](https://policies.google.com/privacy). The extension
does not upload settings itself; Chrome does the syncing. Turning the
option off stops further syncing.

## Your control over your data

- **Export** — download every highlight as JSON, Markdown, CSV or plain text
  from the extension's options page or side panel. Full JSON backups also
  preserve drawing geometry; text exports contain drawing labels and notes.
- **Import** — restore a JSON backup, merging with or replacing what is there.
- **Delete** — remove a single highlight, everything on one page, or all
  highlights and notes at once from the options page.
- **Disable per site** — add any hostname to the disabled list and the
  extension will not run there.
- **Uninstall** — removing the extension deletes all of its stored data.

## Permissions

| Permission | Reason |
| --- | --- |
| `storage` | Save highlights and settings locally |
| `unlimitedStorage` | Avoid the 10 MB `storage.local` cap for users with large libraries |
| `contextMenus` | Add "Highlight selection", "Open highlights panel" and "Open library" to the right-click menu |
| `scripting` | Start the extension in tabs that were already open when it was installed or updated, so they do not need reloading |
| `host_permissions` (`http://*/*`, `https://*/*`) | Render highlights, read the current tab's URL for annotation state/counts, and download PDFs explicitly opened in Highlighter from their original sites |

No `tabs`, `history`, `cookies`, `webRequest` or remote-code permissions are
requested.

## Changes

Any change to this policy is published at
<https://github.com/FaTb0i8u/highlighter-privacy>, where the full commit
history is publicly auditable, and the date at the top of this document is
updated to match.

## Contact

Questions about this policy, bug reports and feature requests:
<fatb0i8u@gmail.com>
