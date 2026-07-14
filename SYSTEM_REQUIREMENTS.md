# DeskRipple — System Requirements

DeskRipple is a Windows desktop shortcut organizer built on .NET 8 + WPF, targeting `win-x64`. The .NET runtime, WPF, and Visual C++ runtime all ship inside the download (the managed runtime in the executable, the native WPF/VC++ DLLs alongside it) — running `DeskRipple-beta-Setup.exe` is the whole install: per-user, no admin prompt, no separate runtime downloads.

## Minimum

| Component   | Requirement                                                                 |
|-------------|------------------------------------------------------------------------------|
| OS          | Windows 10 (22H2) or Windows 11, 64-bit                                      |
| CPU         | 64-bit x64 processor, dual-core, 1 GHz+                                      |
| RAM         | 4 GB                                                                          |
| Disk        | 500 MB free (installed app under `%LocalAppData%\DeskRipple\` + update-package cache) |
| Display     | 1024×768, any DPI scale                                                      |
| GPU         | Any GPU supported by Windows 10/11 (DWM composition is required for the translucent panels) |
| .NET        | None — .NET 8 runtime is bundled                                             |
| VC++ runtime| None — `vcruntime140_cor3.dll` is bundled                                    |
| Permissions | Standard user account — no admin rights required                             |
| Network     | None required — works fully offline; when online it checks GitHub for updates (can be turned off in Settings) |

## Recommended

| Component | Recommendation                                                              |
|-----------|------------------------------------------------------------------------------|
| OS        | Windows 11, or Windows 10 22H2                                               |
| CPU       | Modern 64-bit x64 (Intel 8th gen / AMD Ryzen 2000 or newer)                  |
| RAM       | 8 GB                                                                          |
| Disk      | 1 GB free (icon cache and logs grow with the number of folders/shortcuts)    |
| Display   | 1080p or higher; multi-monitor with mixed DPI fully supported (Per-Monitor V2) |
| GPU       | Any dedicated or modern integrated GPU — smoother animations                  |

## Compatibility notes

- **64-bit Windows only.** There is no 32-bit build. This is a non-issue on Windows 11 (which is 64-bit only) but rules out 32-bit Windows 10 installs.
- **No native ARM64 build.** DeskRipple will run on Windows on ARM via Microsoft's x64 emulation layer, but rendering smoothness and startup time suffer. Native ARM64 is not officially supported.
- **Windows 10 and 11 are both supported.** The application manifest permits both, and DeskRipple has been tested on Windows 10 and Windows 11. Desktop icon displacement (via `IFolderView2`) and the translucent panel rendering were originally tuned against Windows 11, but they work on Windows 10 22H2 as well.
- **SmartScreen on first launch.** The binary is code-signed (Microsoft Trusted Signing). Because DeskRipple is a brand-new app, Windows SmartScreen may still show a prompt on first run until the download builds reputation; if it does, click "More info → Run anyway" to launch. The warning fades as more people download it.
- **Per-user installer, no admin rights.** `DeskRipple-beta-Setup.exe` installs to `%LocalAppData%\DeskRipple\` and adds a Start Menu entry + an **Apps & Features** listing; updates download and apply silently in the background (off switch in Settings). Data (config, icon cache, copied shortcuts, logs) lives under `%APPDATA%\DeskRipple\`. To remove, uninstall from **Settings → Apps** — that removes the program files, the `DeskRipple AutoStart` scheduled task, any legacy HKCU Run-key entry, and the `%APPDATA%\DeskRipple\` data folder. (A `DeskRipple-beta-Portable.zip` exists for the extract-and-run case; the installer is the supported path. The portable build removes its data via `DeskRipple.App.exe --uninstall`.)
- **Single instance.** Only one copy of DeskRipple runs at a time per user session, enforced via a named mutex. A second launch sends `open-manager` to the running instance and exits.

## What DeskRipple does *not* require

- No internet connection for normal use — every feature works offline. (When online, it checks GitHub for updates in the background; that's its only network traffic and it can be turned off in Settings. See the [privacy policy](PRIVACY.md).)
- No Microsoft account.
- No Windows Subsystem features (WSL, Hyper-V, Sandbox).
- No separate .NET, WPF, or Visual C++ runtime install.
- No registry changes outside of per-user reads (desktop icon size, default browser, theme) plus a one-time cleanup of any legacy `HKCU\Software\Microsoft\Windows\CurrentVersion\Run\DeskRipple` value during the auto-start migration. When you enable "Start with Windows", DeskRipple registers a per-user Task Scheduler entry (`DeskRipple AutoStart`) — no elevation, no HKLM, no scheduled job for other accounts.
