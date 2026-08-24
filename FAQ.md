# DeskRipple — FAQ, Known Limitations & Install Notes

The frequently asked questions for DeskRipple: cost and license, install and uninstall,
updates, privacy, and known limitations.

> This file replaced [BETA-FAQ.md](BETA-FAQ.md) when DeskRipple 1.0 went on sale; the old file
> stays as a pointer so links to it keep resolving.

---

## What is DeskRipple?

DeskRipple is a Windows 10 and 11 desktop utility that lets you create folder-like **docks** directly
on your desktop. Each dock sits behind your normal windows, like a native desktop icon. When
you hover over or click it, it expands into a grid (or fan, column, row, or ring) of shortcuts to
your apps, files, and folders.

It's for people who want a cleaner desktop without giving up quick access to the things they
use most — especially on multi-monitor setups.

## How much does DeskRipple cost?

DeskRipple is a **one-time purchase, not a subscription** — pay once and it's done, with no
recurring charge and nothing to cancel. The price is shown at checkout before you pay, in your
local currency where supported. Every purchase can be refunded within **14 days, no questions
asked**. The readable purchase summary is the
[terms of sale & refunds](https://deskripple.com/terms.html) page.

<!-- FOUNDER-OFFER: retire with the founder window (PAID-LAUNCH-CHECKLIST section 7). -->
**Tested the beta?** Beta testers get 50% off — the founder code is on the app's license screen
and in the founder email.

## What are the license terms?

The governing text is the [EULA](https://github.com/DeskRipple/deskripple/blob/main/EULA.md),
which you accept on first launch. The headlines: the license is **perpetual** and belongs to you,
one person — use it on the Windows PCs you personally use (a desktop and a laptop don't need
separate licenses). For **at least two years from your purchase date** the license includes the
updates DeskRipple needs to keep working on supported versions of Windows 10 and 11, and the app
itself has **no expiry date**. The software is provided as-is, without affecting the statutory
rights consumer law gives you.

## Where's my license key?

Your key arrives with your receipt: the checkout confirmation and the receipt email both link to
the **key page**, which shows your key from the order number and the email address used at
checkout. Enter it in DeskRipple under **Manager → About** and the app is licensed from then on.

The key is verified by the app itself, offline — there is **no account to create, no activation
server, and no internet connection needed to stay licensed**.

Lost the key later? The link in your receipt keeps working, and
[support@deskripple.com](mailto:support@deskripple.com) can look an order up from the order
number or the checkout email address.

## What happens on September 1, 2026?

Without a license key, DeskRipple stops working on that date — enter a key and there's no
expiry. (Installs made before that date ran free until it, as promised during the public beta.)
If you stop using DeskRipple instead, removing entries or uninstalling restores your archived
desktop shortcuts, so nothing is lost either way.

## What are the system requirements?

- **Windows 10 (22H2) or Windows 11**, 64-bit (x64)
- No separate .NET install needed — the app is self-contained
- No account, no login

See [SYSTEM_REQUIREMENTS.md](https://github.com/DeskRipple/deskripple/blob/main/SYSTEM_REQUIREMENTS.md) for the full list.

## How do I install it?

1. Download **`DeskRipple-beta-Setup.exe`** from [the latest release](https://github.com/DeskRipple/deskripple/releases/latest).
   (The `beta` in the file name is the update channel's name, kept so existing installs keep
   updating — the file installs the current version.)
2. Double-click it. That's it — DeskRipple installs per-user (no admin prompt), adds a Start
   Menu entry, and starts automatically.

It installs to `%LocalAppData%\DeskRipple\` and shows up in **Settings → Apps → Installed
apps** like any normal program. No desktop shortcut is created — a desktop-decluttering app
shouldn't add desktop clutter.

> On first launch of the installer you may see a Windows SmartScreen warning — see the
> next question.

## Why does Windows SmartScreen show a warning?

DeskRipple is **code-signed** (Microsoft Trusted Signing), so Windows can verify the publisher.
Even so, because it's a relatively new app, Windows SmartScreen may still show "Windows protected
your PC" when you run the installer, until the download builds up reputation.

This happens because SmartScreen relies on reputation, and a new download starts with little or
no download history. The prompt is milder than for unsigned software — it shows a verified
publisher rather than "Unknown publisher" — and it fades as more people download it. It does
**not** mean the app is malware.

If the prompt appears, click **More info → Run anyway** to continue.

## How do updates work?

Automatically — updates are **on by default**. DeskRipple checks its GitHub releases in the
background every few hours, downloads new versions (small delta downloads, not the full app),
and applies them at a quiet moment — it waits until you're not mid-drag, mid-menu, or working in
an open dock panel, then restarts the docks silently. A small tray notification tells you when a
new version has landed; your folders, settings, and license always carry over.

Prefer to update on your own schedule? Turn off **Manager → About → "Install updates
automatically."** The only update traffic that remains is a single tiny check at launch, which
exists so a seriously broken build can be flagged as "must update before running."

What the license promises about updates — at least two years of Windows-compatibility updates
from purchase, with no expiry on the app when that window ends — is on the
[terms of sale & refunds](https://deskripple.com/terms.html) page.

## What happens to shortcuts I drag in from my desktop?

By default, DeskRipple **moves** them. Drag a `.lnk` or `.url` shortcut in from your desktop
and the original file is tucked into `%APPDATA%\DeskRipple\Desktop Shortcuts\` instead of
staying behind as a duplicate — a tidier desktop is the whole point. Nothing is deleted, and
the original comes back automatically: remove the shortcut from DeskRipple (or uninstall the
app) and it returns to your desktop.

Prefer to keep originals where they are? Pick **"Copy it (keep the original on my desktop)"**
under **Settings → "When I add a shortcut from my desktop."** And you can browse the
archived originals anytime — **Open Shortcuts Folder** (in the tray menu and in Settings) opens
the archive in Explorer; it's a normal folder, so the shortcuts in it keep working even while
DeskRipple isn't running.

This applies only to `.lnk`/`.url` shortcuts dragged in straight **from the desktop** — files
and shortcuts dragged from anywhere else (an Explorer window, the Start menu) are never moved.

## Does DeskRipple collect my data?

DeskRipple is **local-first**. All of its data lives on your PC under
`%APPDATA%\DeskRipple\` — your folders, the shortcuts you add (including any desktop originals
it has moved for you — see the previous question), your license key, an icon cache, and logs.
The only network requests the app makes are **update checks against GitHub** (no identifier,
nothing about you or your setup — see "How do updates work?"), and those can be turned off in
Settings. The license key is checked on your PC — the app doesn't phone home to validate it.

Purchases are handled by Lemon Squeezy as the merchant of record, and the small purchase record
behind license keys is described in the privacy policy's "Purchases and license keys" section.

There are **no ads, no third-party trackers, and your data is never sold or shared.** See the
full [privacy policy](https://github.com/DeskRipple/deskripple/blob/main/PRIVACY.md).

## Is telemetry required?

No. Anonymous usage diagnostics are **opt-in and off by default.** If you choose to turn them
on (from the welcome screen or **Settings → Privacy & diagnostics**), DeskRipple sends at most
one small anonymous daily summary — app version, Windows version, monitor/DPI setup, and
coarse feature-usage counts. It never includes your folder names, shortcut names/paths, file
contents, or anything personal, and you can turn it off anytime. DeskRipple works fully with it
left off.

## How do I send feedback or report a bug?

Use the built-in **Send feedback** option — it's in the tray menu, the Manager window,
and the About panel, and it pre-fills your app version, Windows version, and display scale.
Or go directly to [the feedback form](https://tally.so/r/eqzJZx).

Helpful things to include:
- What you expected vs. what actually happened
- Your number of monitors and display scaling (%), if it's a visual issue
- A screenshot or short screen recording if you can

## How do I report a crash?

If DeskRipple crashes, it writes a **local** crash report under
`%APPDATA%\DeskRipple\crashes\`. These stay on your machine unless you choose to send one.

The easiest way: open the **About** panel and click **Send last crash report** — it reveals the
report file and opens the feedback channel so you can attach it. Nothing is uploaded
automatically.

## How do I uninstall DeskRipple?

Uninstall it like any app: **Settings → Apps → Installed apps → DeskRipple → Uninstall**.

That's a clean, complete removal — it exits a running DeskRipple, puts any archived desktop
shortcuts back on your desktop (see "What happens to shortcuts I drag in from my desktop?"),
removes the **`DeskRipple AutoStart`** scheduled task (if you enabled "Start with Windows"),
and deletes both the program files (`%LocalAppData%\DeskRipple\`) and the data folder
(`%APPDATA%\DeskRipple\` — your dock layout, settings, icon cache, and logs). Nothing else is
left behind.

> **Your license key is part of that data folder, so uninstalling removes it from the PC too.**
> That's deliberate — a clean uninstall leaves no residue — and it never costs you the license:
> keep your receipt, and the key page shows your key again from the order number and checkout
> email whenever you reinstall.

*Manual fallback* (if you'd rather do it by hand, or Apps & Features misbehaves):
1. Run `DeskRipple.App.exe --uninstall` from `%LocalAppData%\DeskRipple\current\` — it does
   the same shortcut-restore + scheduled-task + data cleanup.
2. Then delete `%LocalAppData%\DeskRipple\` if it's still there.

---

## Known Limitations

- **Newer app** — DeskRipple is code-signed, but SmartScreen may still warn on first run until the download builds reputation (see above).
- **Windows 10 and 11, 64-bit only.** No 32-bit or ARM64 build.
- **A license key is needed from September 1, 2026** — without one, DeskRipple stops working on
  that date. With a key there's no expiry.
- Behavior may vary across unusual **multi-monitor / mixed-DPI** setups; if something looks
  off at a particular display scale, that's exactly the kind of feedback that helps.
- DeskRipple is code-signed, but some **antivirus tools** may still be cautious with a newer app until it's more widely seen.

---

## A note on SmartScreen (for the download page)

Place this near the download button:

> **Heads up:** DeskRipple is code-signed (Microsoft Trusted Signing), but because it's a
> relatively new app, Windows SmartScreen may still warn you the first time you run it — Windows
> hasn't built up much download reputation for it yet. If the prompt appears, click **More info →
> Run anyway**. The warning fades as more people download it.

---

*Questions about a purchase, a key, or privacy: support@deskripple.com.*
