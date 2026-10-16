# LumiROM Builder

A Windows 11 app that builds LumiROM for you, so you do not have to live in a terminal. It sets up
WSL, clones the repository, runs the build and hands you the ZIP.

This repository only holds the downloads. The source is private, and every release here is built from
it automatically.

## Download

The newest version is always at these two links:

- **Installer** — [LumiROM.Builder-Setup.exe](https://github.com/LumiROM/WinBuilder-App/releases/latest/download/LumiROM.Builder-Setup.exe)
- **Portable ZIP** — [LumiROM.Builder-win-x64.zip](https://github.com/LumiROM/WinBuilder-App/releases/latest/download/LumiROM.Builder-win-x64.zip)

The installer is per user: no administrator rights, no certificate to install, nothing to trust
first. Take the ZIP if you would rather not install anything.

You need **Windows 11** (build 22000 or newer) and **WSL**. If WSL is missing, the app installs it
for you.

## Using it

**1. Open the app and go to Environment.** It checks what is missing and says it in plain language. On
a fresh machine it is usually two clicks:

- **Install WSL** — a console opens and does it. Restart Windows when it asks, then come back.
- **Install Ubuntu** — after the restart. It will ask for a UNIX username and password: that part is
  yours.

**2. Press "Clone LumiROM in WSL".** The button only appears once Ubuntu has answered, because cloning
into something that cannot build is half an hour wasted. You can watch the progress in the console.

**3. Fill in the Build page.** Stock device, CSC, the IMEI of the base device, and your name. Tick
what you want: mods, Galaxy AI, an image-only build, an incremental OTA.

**4. Press "Start build".** The Console shows it as it happens, stage by stage. If sudo asks for a
password, type it right there — the app tells you when.

**5. Take your ROM from Artifacts.** Copy the ZIP straight over to Windows from there.

Three things worth knowing:

- **Firmware is downloaded once.** The Firmware cache page shows what is stored, and a cache hit skips
  a multi-gigabyte download. Do not clear it without a reason.
- **The app updates itself.** About has an Updates section: it tells you when a newer version is out
  and installs it for you. Nothing is downloaded without its hash being checked first.
- **If the build scripts have moved on**, Home says so and updates them in one click.

## When something breaks

Go to **Settings → Run diagnostics**. It writes a report of everything the app can see — WSL, the
terminal, the environment, the build — and lets you copy it. Paste it into a message:

**https://t.me/LumiROMs**

That saves a round of guessing, and it is usually enough to spot the problem straight away.

## Licence

MIT. Use it, change it, ship it, sell it — just keep the copyright notice with it.

Copyright (c) 2026 LumiROM. Provided as is, without warranty of any kind: the full text, the
one that actually counts, is in [LICENSE](LICENSE).
