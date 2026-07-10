# DeskRipple Privacy Policy

**Effective date:** 2026-07-09
**Applies to:** DeskRipple beta (v0.x)

> This is a plain-language privacy policy for the DeskRipple beta. It is a starting point and is **not legal advice** — have it reviewed before the paid launch.

## The short version

DeskRipple runs entirely on your computer. It does **not** collect, transmit, sell, or share any personal data — there are no accounts, no advertising, and no cross-site tracking.

Out of the box, the only network requests DeskRipple makes are **update checks against GitHub** (where its releases are hosted) so the beta can keep itself current. An update check sends no identifier and no data about you or your setup — it is an ordinary web request, which necessarily reveals your IP address to GitHub, like visiting any website. You can turn automatic updates off in the About panel (Manager → About). See "Network activity" below.

DeskRipple has **one** optional feature beyond that: anonymous usage diagnostics, which are **off by default**. If you choose to turn them on, DeskRipple sends a small, anonymous daily summary so we can tell whether the app is useful and stable. It never includes your folder names, the shortcuts or files you add, or any personal data, and you can turn it off at any time. See "Usage diagnostics" below.

## What DeskRipple stores, and where

All of DeskRipple's data lives in a single folder on your machine:

`%APPDATA%\DeskRipple\` (typically `C:\Users\<you>\AppData\Roaming\DeskRipple\`)

| Location | Contents |
|---|---|
| `config.json` (and `config.json.bak`) | Your folders, the shortcuts you've added, and your settings. |
| `logs\` | Local diagnostic logs that help troubleshoot problems. Because they record what the app did, they can include your folder and shortcut names and full file paths (which may contain your Windows username). They stay on your machine unless you choose to send one to us. |
| `iconcache\` | Cached icon images so folders and shortcuts render quickly. |
| `shortcuts\` | DeskRipple's own copies of the `.lnk`/`.url` shortcuts you drag in, so an entry survives you moving or deleting the original. |
| `Desktop Shortcuts\` | Desktop originals DeskRipple has tucked away for you. By default, dragging a `.lnk`/`.url` shortcut in **from your desktop** moves the original file here rather than leaving a duplicate behind; removing that shortcut from DeskRipple puts the original back on your desktop, and right-click → "Restore original to desktop" brings it back anytime. Prefer copies? Switch to "Copy it" under **Settings → "When I add a shortcut from my desktop."** |
| `crashes\` | Local crash reports that stay on your machine; you can send the most recent one from the About panel if you want to. Each report includes the tail end of the diagnostic log, so the same caution about names and paths applies. |
| `telemetry\` | Created **only if you turn on usage diagnostics**: a random install id and any daily summaries not yet sent. Deleted when you turn diagnostics off. |

DeskRipple reads the shortcuts and icons you add so it can display and launch them. That information is used only to make the app work and is never sent anywhere.

## Network activity

DeskRipple makes exactly two kinds of network requests, both to **GitHub** (`github.com` / `api.github.com`), where its releases are hosted:

1. **Automatic update checks** — every few hours, DeskRipple asks GitHub whether a newer version exists and, if so, downloads it in the background. Off switch: **Manager → About → "Install updates automatically."**
2. **A critical-update check at launch** — a single tiny file fetch that lets us flag a seriously broken build as "must update before running." This one runs even when automatic updates are off (a safety switch that could be switched off wouldn't protect anyone), and skips silently when you're offline.

Neither request sends any identifier or any information about you, your folders, or your setup. Like any web request, they necessarily reveal your IP address to the server (GitHub); GitHub's handling of request logs is governed by [GitHub's privacy statement](https://docs.github.com/en/site-policy/privacy-policies/github-privacy-statement). Apart from the optional usage diagnostics described below (off by default), DeskRipple contacts no other server of its own.

With usage diagnostics **on** (they are off by default), DeskRipple additionally sends the anonymous daily summary described under "Usage diagnostics" below.

When you launch a shortcut, DeskRipple hands off to Windows to open that app, file, or web link. Anything that happens after that (for example, your web browser opening a URL) is governed by the privacy policies of those other programs, not DeskRipple.

### The feedback form

The "Send feedback" buttons don't send anything from the app itself — they open your **web browser** on our feedback form, like clicking a link, so the two kinds of requests above remain the only network requests DeskRipple makes on its own.

The form is hosted by **Tally**, a form service based in Belgium that stores form data on servers within the European Union; what you submit there is handled under [Tally's privacy policy](https://tally.so/help/privacy-policy). To save you typing, the link pre-fills three diagnostic values: your DeskRipple version, your Windows version, and your display scale (e.g. 250%). All three are visible in your browser's address bar, and you can edit or remove them there before submitting — nothing is sent to the form unless you choose to submit it.

### The mailing list

The optional "Join the mailing list" buttons (in the About panel and the welcome dialog) work the same way: they open your **web browser** on a signup form — the app itself sends nothing. The form (also embedded on [deskripple.com](https://deskripple.com)) is hosted by **Brevo**, an email service company headquartered in France; the email address you choose to submit there is handled under [Brevo's privacy policy](https://www.brevo.com/legal/privacypolicy/). Signup is double opt-in — nothing is subscribed until you confirm via the email Brevo sends you. Your address is used only for occasional DeskRipple news (such as the beta-tester founder discount) and is never sold or shared with anyone else, and every email includes an unsubscribe link. To have your address deleted entirely rather than just unsubscribed, email the contact address below.

## Your control over your data

- **Delete everything:** uninstall DeskRipple from **Windows Settings → Apps** — that first moves any archived desktop shortcuts (the `Desktop Shortcuts\` folder above) back onto your desktop, then removes the installed program files, the `%APPDATA%\DeskRipple\` data folder, and the `DeskRipple AutoStart` scheduled task. (Running `DeskRipple.App.exe --uninstall` — the portable-build path — does the same shortcut restore and removes the data folder and the scheduled task; delete the program folder yourself.) You can also delete the `%APPDATA%\DeskRipple\` folder manually at any time — just check `Desktop Shortcuts\` first for originals you want back, since a manual delete skips the automatic restore.
- **Turn off automatic updates:** Manager → About → "Install updates automatically." Only the single critical-update check at launch remains (see "Network activity").
- Because all data is stored locally, there is no server-side copy to request or erase.

## Usage diagnostics (optional, off by default)

DeskRipple includes optional, anonymous usage diagnostics so we can understand whether the app is useful and reliable enough to keep developing. This feature is **off by default** and sends nothing unless you explicitly turn it on — from the first-run welcome screen, or in **Settings → Privacy & diagnostics**.

**What it sends.** When enabled, DeskRipple sends at most one summary per day (each summary also carries a data-format version number) containing:

- a random "install id" generated on your device (not derived from your hardware, account, or any personal identifier), and the summary's date;
- how many days you've had DeskRipple installed, and — separately — on how many of the last 7 and 28 days it was *running* vs. on how many you actually *used* it (opened a folder, launched a shortcut, or changed your setup);
- how many days after installing you first created a folder, first added a shortcut, and first launched one;
- the DeskRipple version, your Windows version, your Windows display language (two-letter code, e.g. "en"), and whether your copy is installed or portable;
- your monitor count, each monitor's display scale (e.g. 100%, 250%), and how many of your monitors have DeskRipple folders on them;
- how many folders you have, how many use a custom icon, how many sit on a secondary monitor, how many separate profiles you've set up (a count only — never their names), and the size of your largest folder (as a coarse range);
- your shortcut count, and the mix of shortcut kinds (web link / app / Store app / other file), as coarse ranges (e.g. "11–25"), never exact counts;
- which expand styles your folders are set to use and how often you open each, your expand mode (and, in click mode, whether panels auto-collapse when the mouse leaves), whether automatic updates are on, and which settings you've changed from their defaults — setting *names* only, never their values;
- counts, since the last summary, of: app launches, folders created, shortcuts added (drag-and-drop vs. via the Manager), shortcuts removed, shortcuts dragged back out to the desktop, folder opens, folder opens dismissed within about a second without launching anything (a hover-misfire signal used to tune timing), shortcut launches, Manager window opens, profile switches, failed shortcut launches (by kind — web link / app / Store app / other file), drags DeskRipple couldn't accept (grouped by coarse kind — image / web link / text / Start-menu item / other — never the dragged content), icons that failed to load, and desktop icons it moved aside (or couldn't move aside) to make room for a folder;
- counts, since the last summary, of internal self-checks and recoveries: how often DeskRipple pushed a folder icon back to its place behind your windows, fell back to a default desktop-icon size because it couldn't measure yours, recovered a folder's custom icon after its source file went missing, and re-linked its own files after its data folder was moved or renamed;
- how quickly folders open, as counts in coarse speed buckets (e.g. "under 50 ms");
- counts of errors and crashes since the last summary, with the type names of the most common errors (e.g. "InvalidOperationException") — never error messages, stack traces, or paths;
- counts of automatic-update attempts and how many failed, by stage (check / download / install).

**What it never sends.** It never includes your folder names, the names, paths, or contents of your shortcuts or files, your username or computer name, screenshots, or anything you type. There is no advertising or cross-site tracking, and the data is never sold or shared.

**Where it goes.** The daily summary is sent to DeskRipple's own endpoint at `telemetry.deskripple.com`, which runs on [Cloudflare](https://www.cloudflare.com/)'s network and stores the summaries in a Cloudflare database. **We do not store the IP address the request comes from.** Summaries are kept for up to 24 months and then deleted. The data is not handed to any third-party analytics provider — Cloudflare acts only as our hosting provider (see [Cloudflare's privacy policy](https://www.cloudflare.com/privacypolicy/)) — and is used solely by DeskRipple's maintainer to understand how the app is used and how reliable it is.

**The install id** is random and pseudonymous: it lets us count returning installs (retention) without identifying you, and cannot be tied back to your name or account.

**Your control.** Turn diagnostics off at any time in Settings → Privacy & diagnostics. Doing so immediately stops all sending and erases the local install id and any not-yet-sent summaries from your device. Running `DeskRipple.App.exe --uninstall` removes everything, including these.

**Uninstalling.** If usage diagnostics are **on** when you uninstall DeskRipple, the uninstaller sends one final anonymous "uninstalled" notice, so we can tell uninstalls apart from machines that are simply offline. It contains only the random install id, the date, how many days DeskRipple was installed, and the app version (plus the same data-format version number) — nothing else. If diagnostics are **off** (the default), uninstalling sends nothing.

Local crash reports (in the `crashes\` folder) are separate and always stay on your machine unless you choose to send one from the About panel. Each report contains the technical details of the error plus roughly the last 32 KB of the diagnostic log, for context about what led up to the crash. Like the log itself, that can include your folder and shortcut names and full file paths — which may contain your Windows username. A crash report is a plain text file, so we suggest opening it and reviewing what's in it before you send it.

> **Maintainer note — keep this in sync with `TelemetryService` / `TelemetryPing`.** The endpoint is now live: a self-hosted Cloudflare Worker + D1 (`server/telemetry/`), reached at `telemetry.deskripple.com`. The Worker deliberately does **not** persist the request IP, so there is no third-party analytics processor and no separate DPA to sign — Cloudflare is only the hosting provider. Three ongoing rules: (1) keep the "What it sends" field list above in lockstep with `TelemetryPing` / `UninstallPing`; (2) keep the "Where it goes" host description in sync with `server/telemetry/wrangler.toml`; (3) honor the stated 24-month retention — prune `daily_pings`/`uninstall_pings` rows older than that (a manual `wrangler d1 execute` is fine at beta scale; first rows age out ~mid-2028). If you set a D1 location hint for data residency (e.g. `--location weur` for the EU), you may state that region here. **And remember: this file is published on the public DeskRipple/deskripple repo — every edit here must be pushed there too** (that copy is what the in-app links open; it sat stale for three weeks once).

## Children

DeskRipple is a general-purpose desktop utility, is not directed at children, and does not knowingly collect data from anyone.

## Changes to this policy

If this policy changes, the updated version will be posted with a new effective date.

## Contact

Questions or privacy concerns: **support@deskripple.com**

Because DeskRipple's data lives only on your device, deleting it is in your hands — uninstall the app or delete the `%APPDATA%\DeskRipple\` folder (see "Your control over your data" above). If you've emailed us, submitted feedback, or turned on usage diagnostics, you can use the address above to ask what we hold about you or to request its deletion; if you're in the EU or UK, you also have statutory rights of access and erasure.
