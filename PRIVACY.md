# Privacy Policy

**Zabbix NOC Alerter** (the "extension") alerts you to new problems in your own
Zabbix instance. This policy explains how it handles data.

## Summary

The extension does **not** collect, store, or transmit any personal data to the
developer or to any third party. It communicates only with the Zabbix server URL
that **you** configure, using your existing browser session or an optional API
token that you provide.

## What the extension accesses

- **Your settings** (Zabbix URL, optional API token, sound and filter preferences,
  language, mute state): stored locally on your device via `chrome.storage.local`.
  They never leave your device except as part of a request to your own Zabbix.
- **Your Zabbix session cookie**: read locally to authenticate requests to the
  Zabbix URL you configured, so you do not need to enter a token. It is sent only
  to your Zabbix server, never to the developer or any third party.
- **Problem data from your Zabbix**: fetched from your Zabbix API to show active
  problems in the popup and notifications. It stays on your device.

## What the extension does NOT do

- No analytics, no telemetry, no tracking of any kind.
- No selling or sharing of data with third parties.
- No remote code: all logic is bundled in the extension; alarm sounds are
  generated locally with the Web Audio API (no external files).
- It contacts no server other than the single Zabbix URL you set.

## Permissions and why they are needed

- **storage**: save your settings locally.
- **cookies**: read your Zabbix session cookie to authenticate to your Zabbix.
- **notifications**: show a desktop notification for new or resolved problems.
- **offscreen**: play the alarm sound (Manifest V3 service workers cannot play audio).
- **alarms**: wake the background worker periodically to check your Zabbix.
- **host permissions (`<all_urls>`)**: required because your Zabbix can be on any
  domain, IP, or port that only you know; the extension only ever contacts the
  single URL you configure in the options.

## Contact

Questions or issues: https://github.com/opastorello/zabbix-noc-alerter/issues

_Last updated: June 2026._
