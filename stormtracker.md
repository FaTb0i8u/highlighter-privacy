# StormTracker Privacy Policy

Last updated: November 15, 2026

This policy covers the StormTracker Chrome extension. It is separate from the
[Highlighter privacy policy](./policy.md).

## Purpose

StormTracker helps you monitor official US weather alerts, forecasts and storm
outlooks for your chosen location and saved places. It has no accounts,
advertising, analytics, tracking pixels or subscription requirement. We do not
sell personal information or use it for advertising.

## Location information

When you select "Use location" or "Update", Chrome's geolocation service provides
coordinates if permission is granted. Coordinates are kept in extension storage
on your device and sent directly to the US National Weather Service
(`api.weather.gov`) for point information, alerts and forecasts.

The extension checks for alerts about every five minutes while Chrome is
running. These checks include your stored location and any saved places, even
when the popup and StormTracker website are closed. They do not continuously
track your movement: a new GPS position is requested only when you use a
location control. If manual coordinates are entered, they are used in the same
way as a position obtained through geolocation.

Storm Prediction Center outlooks are downloaded from `www.spc.noaa.gov`. Risk for
your location is calculated on your device from those outlook files; your
coordinates do not need to be sent to SPC for that calculation.

## Information stored on your device

The extension uses Chrome's local extension storage for:

- The selected coordinates and location label.
- Saved-place labels and coordinates, if configured.
- Theme, temperature units, notification severity and quiet-hour preferences.
- Recent weather alerts, outlook results, successful-check timestamps and
  notification history, so it can display status and avoid duplicate notices.
- Recent notification destinations, to open the corresponding alert details.

The popup may also keep a theme preference in its own local storage to avoid a
flash of the wrong theme. These settings are not uploaded to an application
database, and the extension does not use Chrome's cloud-synced storage.

## Optional website integration

The extension can operate without a deployed StormTracker website. The standard
standalone build does not install a content script on any website.

The "Open dashboard" and "View on dashboard" links open the full website at
`stormtracker-web.vercel.app` in a new tab. They include the selected coordinates
and, for an alert link, its identifier in the URL. Opening these links does not
enable settings sync or grant access to unrelated websites. The extension's
local alerts, notification checks and official NWS forecast links remain
available without the dashboard.

If a build is explicitly configured to integrate with a StormTracker web app,
its content script runs only on that configured website origin. It reads only
the app's saved places, units and theme preferences, and copies them into local
extension storage. It does not collect browsing history, passwords, cookies or
the content of unrelated websites. Synced saved places are then included in
background National Weather Service alert checks.

A separately deployed web dashboard may use additional map, search and weather
providers; consult that website's privacy policy when using it.

## Network requests and external links

Weather providers receive ordinary connection information, including your IP
address. National Weather Service point queries include coordinates. Providers
may retain request logs under their own policies; we do not control those logs.

If you open an official National Weather Service forecast link, its URL contains
the selected coordinates. Dashboard links likewise include coordinates and may
include an alert identifier. The website host receives those values as part of
the page request, and the dashboard has its own website privacy policy.

Privacy, source-code and voluntary-support links open external websites only
when selected. Those websites receive normal request information and apply
their own privacy policies. Opening this policy on GitHub is governed by
[GitHub's privacy statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement).

## Notifications and permissions

- **Location:** obtain a position when you request it.
- **Storage:** remember local preferences, places and weather status.
- **Alarms:** schedule background alert checks while Chrome is running.
- **Notifications:** show alerts meeting your severity and quiet-hour settings.
- **Weather host access:** request weather data from `api.weather.gov` and
  `www.spc.noaa.gov`.

Notification decisions are made on your device; StormTracker does not use a
remote push-notification service. Notifications may appear on your operating
system's notification center or lock screen, depending on your system settings.
Connectivity, browser sleep, provider outages and permissions can delay or
prevent delivery. StormTracker is not an emergency notification system and
should not be your only source of severe-weather warnings.

## Retention and deletion

Local weather caches and notification history are updated during use. Location,
places and preferences remain until replaced or removed, extension storage is
cleared, or the extension is uninstalled. Clearing extension data or uninstalling
removes the extension's local copy; it does not remove a separate website's
saved settings or providers' request logs. You can revoke location access or
disable the extension in Chrome, and control notifications in Chrome and your
operating system.

## Children

StormTracker is not directed at children and does not intentionally collect
personal information from children or maintain user profiles.

## Changes and contact

We will update the date above when this policy changes. Material changes to
permissions or data handling will also be reflected in the extension and its
Chrome Web Store disclosures.

For privacy questions or requests, open an issue titled "StormTracker privacy"
in the [public privacy and support repository](https://github.com/FaTb0i8u/highlighter-privacy/issues).
Do not post precise locations or other private information in a public issue.
