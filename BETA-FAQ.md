# DeskRipple Beta — FAQ, Known Limitations & Install Notes

Publishable help content for the DeskRipple public beta. Drop it onto the landing page and/or
paste the relevant parts into the GitHub Release description.

> All placeholders are filled (2026-06-09) — ready to publish. Install/uninstall/update
> sections rewritten for the Velopack installer (B20, 2026-06-10). Desktop Shortcuts archive
> Q&A added 2026-06-12 (proposal 14). The feedback link mirrors `AppInfo.FeedbackUrl` and the
> landing-page link — keep all three in sync if the form URL ever changes.

---

## What is DeskRipple?

DeskRipple is a Windows 10 and 11 desktop utility that lets you create folder-like **docks** directly
on your desktop. Each dock sits behind your normal windows, like a native desktop icon. When
you hover over or click it, it expands into a grid (or fan, column, row, or ring) of shortcuts to
your apps, files, and folders.

It's for people who want a cleaner desktop without giving up quick access to the things they
use most — especially on multi-monitor setups.

## Is DeskRipple free?

Yes — DeskRipple is currently a **free public beta**. A one-time paid release will
come later (the price isn't final yet); the beta is free while the app is being tested and
improved. Beta testers will be offered a founder discount when the paid version ships.

## What are the license terms?

The beta is covered by a short beta license — the
[EULA](https://github.com/DeskRipple/deskripple/blob/main/EULA.md). By downloading and using
DeskRipple you agree to it. The headlines: the beta is provided **as-is** while in testing, it
keeps itself updated automatically (see "How do updates work?" below), and this build stops
working after **September 1, 2026** (see "Known Limitations").

## What are the system requirements?

- **Windows 10 (22H2) or Windows 11**, 64-bit (x64)
- No separate .NET install needed — the app is self-contained
- No account, no login

See [SYSTEM_REQUIREMENTS.md](https://github.com/DeskRipple/deskripple/blob/main/SYSTEM_REQUIREMENTS.md) for the full list.

## How do I install it?

1. Download **`DeskRipple-beta-Setup.exe`** from [the latest release](https://github.com/DeskRipple/deskripple/releases/latest).
2. Double-click it. That's it — DeskRipple installs per-user (no admin prompt), adds a Start
   Menu entry, and starts automatically.

It installs to `%LocalAppData%\DeskRipple\` and shows up in **Settings → Apps → Installed
apps** like any normal program. No desktop shortcut is created — a desktop-decluttering app
shouldn't add desktop clutter.

> On first launch of the installer you'll likely see a Windows SmartScreen warning — see the
> next question.

## Why does Windows SmartScreen show a warning?

DeskRipple is **code-signed** (Microsoft Trusted Signing), so Windows can verify the publisher.
Even so, because it's a brand-new app, Windows SmartScreen may still show "Windows protected
your PC" when you run the installer, until the download builds up reputation.

This happens because SmartScreen relies on reputation, and a new download starts with little or
no download history. The prompt is milder than for unsigned software — it shows a verified
publisher rather than "Unknown publisher" — and it fades as more people download it. It does
**not** mean the app is malware.

If the prompt appears, click **More info → Run anyway** to continue.

## How do updates work?

Automatically — updates are **on by default**. DeskRipple checks its GitHub releases in the
background every few hours,
downloads new beta builds (small delta downloads, not the full app), and applies them at a
quiet moment — it waits until you're not mid-drag, mid-menu, or working in an open dock panel,
then restarts the docks silently. A small tray notification tells you when a new version has
landed; your folders and settings always carry over.

Prefer to update on your own schedule? Turn off **Manager → About → "Install updates
automatically."** The only update traffic that remains is a single tiny check at launch, which
exists so a seriously broken build can be flagged as "must update before running."

## Is DeskRipple finished?

No — it's an early beta. Expect rough edges, the occasional bug, and details that change
between versions. The whole point of this phase is to find out what works, what breaks, and
what to improve before the paid release. Please send feedback (see below).

## What happens to shortcuts I drag in from my desktop?

By default, DeskRipple **moves** them. Drag a `.lnk` or `.url` shortcut in from your desktop
and the original file is tucked into `%APPDATA%\DeskRipple\Desktop Shortcuts\` instead of
staying behind as a duplicate — a tidier desktop is the whole point. Nothing is deleted, and
the original comes back automatically: remove the shortcut from DeskRipple (or uninstall the
app) and it returns to your desktop. You can also right-click a shortcut in a dock and choose
**Restore original to desktop** to bring the file back while keeping the dock entry.

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
it has moved for you — see the previous question), an icon cache, and logs. The
only network requests it makes are **update checks against GitHub** (no identifier, nothing
about you or your setup — see "How do updates work?"), and those can be turned off in
Settings.

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

*Manual fallback* (if you'd rather do it by hand, or Apps & Features misbehaves):
1. Run `DeskRipple.App.exe --uninstall` from `%LocalAppData%\DeskRipple\current\` — it does
   the same shortcut-restore + scheduled-task + data cleanup.
2. Then delete `%LocalAppData%\DeskRipple\` if it's still there.

---

## Known Limitations

DeskRipple is an early beta, so these are expected:

- **Brand-new app** — DeskRipple is code-signed, but SmartScreen may still warn on first run until the download builds reputation (see above).
- **Windows 10 and 11, 64-bit only.** No 32-bit or ARM64 build.
- **Time-limited beta build** — this beta expires on **September 1, 2026**; after that you'll
  need a newer build. With automatic updates on you'll always have the newest one anyway.
- Behavior may vary across unusual **multi-monitor / mixed-DPI** setups; if something looks
  off at a particular display scale, that's exactly the kind of feedback that helps.
- DeskRipple is code-signed, but some **antivirus tools** may still be cautious with a brand-new app until it's more widely seen.
- Settings, layouts, and interaction details may still change between versions.

### Should I run it on my main PC?

Your call. DeskRipple is meant for everyday desktop use, but it's still beta software. If you
rely on your PC for critical work and don't enjoy troubleshooting, you may prefer to wait for a
later stable release. If you like trying new Windows utilities and giving feedback, now's a
great time.

---

## A note on SmartScreen (for the download page)

Place this near the download button:

> **Heads up:** DeskRipple is code-signed (Microsoft Trusted Signing), but because it's a
> brand-new app, Windows SmartScreen may still warn you the first time you run it — Windows
> hasn't built up download reputation for it yet. If the prompt appears, click **More info →
> Run anyway**. The warning fades as more people download it.

---

*Questions or privacy concerns: support@deskripple.com.*
