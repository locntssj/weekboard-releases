# WeekBoard Releases

**Public download repository** for [WeekBoard](https://weekboard.teacher-aid.org) — a floating weekly timetable for Windows.

> This repo hosts **installers and release notes only**.  
> Application source code is **not** published here.

---

## Download

| | |
|---|---|
| **Website** | [weekboard.teacher-aid.org](https://weekboard.teacher-aid.org) |
| **Releases** | [GitHub Releases](https://github.com/locntssj/weekboard-releases/releases) |
| **Latest setup (Windows x64)** | See [latest release](https://github.com/locntssj/weekboard-releases/releases/latest) |

### Recommended installer

After each release is published, prefer:

- **NSIS setup:** `WeekBoard_x.y.z_x64-setup.exe`
- **MSI (optional):** `WeekBoard_x.y.z_x64_en-US.msi`

Direct asset URLs look like:

```text
https://github.com/locntssj/weekboard-releases/releases/download/v0.1.0/WeekBoard_0.1.0_x64-setup.exe
```

---

## What is WeekBoard?

Desktop widget for your **weekly schedule**:

- Period / class board, week grid, split view  
- Floating · Sidebar · Overlay window modes  
- Google Calendar two-way sync (~30 days)  
- Optional Gemini AI Chat (your own API key)  
- Themes, reminders, system tray, start with Windows  
- Privacy-first: data stays on your PC by default  

**Platform:** Windows 10 / 11 (x64)

---

## Latest: v0.1.0 (2026-07-17)

First public release.

### Highlights
- Weekly timetable UI (period board, grid, split)
- Google Calendar OAuth + two-way sync (next 30 days)
- AI Chat FAB (optional Gemini)
- Auto check for updates
- Themes, fonts, Windows toast reminders
- In-app Privacy Policy & Terms

### Notes
- Fresh install starts with an **empty board**
- AI requires a personal [Gemini API key](https://aistudio.google.com/)
- Full notes: attach `RELEASE_NOTES` on the GitHub Release page

---

## Install

1. Open the [latest release](https://github.com/locntssj/weekboard-releases/releases/latest)
2. Download `WeekBoard_*_x64-setup.exe`
3. Run the installer (current-user install)
4. Launch **WeekBoard** from the Start menu or system tray

If Windows SmartScreen appears: *More info* → *Run anyway* (unsigned builds until a code-signing cert is used).

---

## Update check

The app can check for updates against the product site.  
When a new version ships, also publish a GitHub Release **here** so this repo stays the canonical download mirror.

Suggested `downloadUrl` for the app / landing:

```text
https://github.com/locntssj/weekboard-releases/releases/download/vX.Y.Z/WeekBoard_X.Y.Z_x64-setup.exe
```

---

## Privacy & legal

- [Privacy Policy](https://weekboard.teacher-aid.org/privacy/)
- [Terms of Service](https://weekboard.teacher-aid.org/terms/)
- Contact: [locnt.ssj@gmail.com](mailto:locnt.ssj@gmail.com)

---

## Support

- Email: **locnt.ssj@gmail.com**
- Product site: **https://weekboard.teacher-aid.org**

---

## For maintainers (publish a release)

```powershell
# From the private app build machine (example paths)
$ver = "0.1.0"
$nsis = "E:\WeekBoard\src-tauri\target\release\bundle\nsis\WeekBoard_${ver}_x64-setup.exe"
$msi  = "E:\WeekBoard\src-tauri\target\release\bundle\msi\WeekBoard_${ver}_x64_en-US.msi"

gh release create "v$ver" $nsis $msi `
  --repo locntssj/weekboard-releases `
  --title "WeekBoard v$ver" `
  --notes-file "E:\WeekBoard\RELEASE_NOTES.md"
```

Do **not** upload source trees, `.env`, or `client_secret_*.json` to this repository.

---

## License

Installer binaries are provided for end users under the product Terms of Service.  
See [LICENSE](./LICENSE) in this repository for the license text that applies to materials published here.
