# VS2B Open Beta

VS2B (Virtual SIM Button Box) is a Windows app for building a touchscreen control panel and opening it on a phone, tablet, or secondary touchscreen over your local network.

This is an open beta of an amateur side project. I am building it in my spare time because I wanted a flexible virtual button box for simulator-style games. Expect rough edges, unfinished ideas, and the occasional bug. Friendly, specific feedback is very welcome, but please do not expect commercial-product support or guaranteed fixes.

This repository contains downloadable beta builds only. The source code is maintained in a separate private repository.

## Download

Download the current Windows x64 portable build from GitHub Releases:

- [VS2B-Portable-0.2.0-beta-x64.exe](https://github.com/Nes-Apps/VS2B-Beta/releases/download/v0.2.0-beta/VS2B-Portable-0.2.0-beta-x64.exe)

No installer is required. Windows may show a SmartScreen warning because this hobby-project build is not code-signed. Check the SHA-256 value in `SHA256SUMS.txt` before running the file if you want to verify your download.

PowerShell verification example:

```powershell
Get-FileHash .\VS2B-Portable-0.2.0-beta-x64.exe -Algorithm SHA256
```

## Before You Start

- VS2B is designed for Windows and devices on the same trusted local network.
- Do not expose the VS2B screen webpage directly to the public internet.
- Start in **Test Mode**. It logs controls without sending keys to another program.
- **Live Mode** can send keyboard and mouse input to Windows. Choose the correct target application before using it.
- Use **Release All Keys** immediately if a simulated key ever seems stuck.
- Export or copy any important profiles before trying a new beta build.
- VS2B automatically keeps a small rotating diagnostic log in its application-data folder. It keeps the current log and one previous log instead of growing forever.

## Quick Start

1. Download and run the portable `.exe`.
2. In the PC app, select an existing profile or create a new one.
3. Set the profile's **Target Application** to the game or program that should receive Live Mode input.
4. Use **Pages** to create or select a page.
5. Add controls in the page builder, then drag and resize them to arrange your layout.
6. Select each control to edit its label, appearance, shortcut, macro, or control settings.
7. Click **Save Profiles** when the app shows unsaved changes.
8. In the screen webpage section, create an access code and click **Start Screen**.
9. On a phone or tablet connected to the same network, open one of the LAN addresses shown by VS2B.
10. Enter the access code to pair the device, then test the layout in **Test Mode**.
11. When the controls behave correctly, switch to **Live Mode**, bring the chosen target application to the foreground, and test carefully.

The **Info** button in the PC app also contains a short guide to profiles, pages, controls, shortcuts, macros, colors, pairing, and input safety.

## Building A Button Box

### Profiles and pages

A profile is a complete setup, usually for one game. Each profile can contain multiple pages. The three-letter page label becomes the tab shown on the phone or tablet.

Changing the editor page only changes what you are editing. Save when you want layout changes sent to the screen webpage.

### Page builder

- Left-click a control to select it.
- Hold the left mouse button and drag to move it.
- Drag the resize grip to change its size.
- Right-click a control to delete it after confirmation.
- Use the screen preset, orientation, grid, safe-area, background, and bottom-bar settings to match your device.
- The builder preview includes the mobile bottom bar so it should be close to what the paired device displays.

### Control types

- **Push Button:** sends a shortcut, macro, page-navigation action, hold, or toggle.
- **Mouse Wheel:** sends wheel up/down input, with an optional modifier key.
- **Slider:** controls a Windows audio output level.
- **Energy Matrix:** provides a triangular three-way control with configurable commands.
- **2-Position Switch:** moves between two visual positions and can send a command for each.
- **4-Position Switch:** moves between four visual positions and can send a command for each.

Shortcut mode is for one key. Use a macro for combinations such as `RightAlt+F5` or for multi-step actions. `LeftAlt+F4` is blocked as a safety measure.

## What This Open Beta Needs Tested

The most useful testing for this build is real-world use on different Windows PCs, phones, tablets, browsers, networks, and games.

Please pay special attention to:

- Whether the PC builder preview matches the phone/tablet layout.
- Dragging and resizing controls on different page sizes and grid modes.
- Saving, unsaved-change warnings, changing editor pages, and restarting the app.
- Push buttons, holds, toggles, macros, mouse wheels, sliders, energy matrices, and switches.
- Pairing, forgetting a device, reconnecting after sleep, and refreshing the screen webpage.
- Test Mode versus Live Mode.
- Target-application blocking when the wrong program has focus.
- Key release when switching away from a game or pressing **Release All Keys**.
- Older or less common mobile browsers, if you have one available.

## Reporting A Problem

Open a GitHub issue and include as much of the following as you can:

- VS2B version.
- Windows version.
- Phone/tablet model and browser, if the screen webpage is involved.
- Game or target application, if Live Mode is involved.
- What you were trying to do.
- Exact steps that reproduce the problem.
- What you expected and what actually happened.
- A screenshot or short recording, if it helps explain the layout or behavior.
- Relevant messages from the VS2B command log.
- The exported diagnostic log, especially if the problem happened before the app was restarted.

Use **Export Log** in the PC app's Command Log panel to save a copy that can be attached to the issue. The automatic log records the app version, warnings, errors, connection activity, input events, device/session identifiers, and command context. It does not intentionally record the pairing access code, but it may contain target-app names, local file paths, shortcuts, local network information, or profile/control identifiers.

Please open the exported log in a text editor and remove access codes, personal paths, profile data, network details, or anything else private before posting it publicly.

## Project Scope

VS2B is local-first. It does not inspect game memory, modify game files, bypass anti-cheat systems, or provide a hosted remote service. It sends normal configured input from the PC app when Live Mode and its safety checks allow it.

This is a learning project shared in the hope that it is useful and fun. Use beta builds at your own risk, keep backups of layouts you care about, and be patient with the human building it.
