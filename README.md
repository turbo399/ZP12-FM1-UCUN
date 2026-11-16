# ZP12-FM1-UCUN
Community compatibility update for ZP12 on newer M‑VAVE FM‑1 hardware.
# ZP12 for newer M-VAVE FM-1 hardware

An unofficial ZP12 2.5 compatibility build for FM-1 units fitted with UCUN UC25HQ80 flash, plus a Linux desktop sample manager with MIDI loop export.

## Downloads

- [Download ZP12 2.5 UCUN firmware, source and patch](./Zp12_test_nopassword.zip)
- [Download Linux Sample Manager v0.3.0 with MIDI export](./ZP12-Desktop-v0.3_nopassword.zip)

Open a link, then click GitHub's download button to save the ZIP. Extract before use.

## Firmware: working save support

This build adds support for UCUN flash ID 0xB36014 while retaining support for Puya flash ID 0x856014.

Saving has been confirmed working by this repository's maintainer on their newer FM-1. This is a report from one device, not validation of every hardware revision.

The original READ-ME-FIRST.txt was written before that successful hardware test and still describes saving as unverified.

The device displays version 2.5. The firmware filename is:

`zp12-2.5-ucun1.fwsc`

### Installation

1. Keep a full-flash backup of your FM-1 before flashing.
2. Extract the firmware ZIP.
3. Read the included READ-ME-FIRST.txt.
4. In M-Flasher, choose FLASH FIRMWARE and select zp12-2.5-ucun1.fwsc.
5. Leave erase-settings and package-stock-bootloader unchecked. Do not select FLASH BOOTLOADER.
6. Wait for completion and restart as instructed.
7. Save a short test pattern while stopped, wait for saving to finish, then power off/on to check it survives.

### Firmware SHA-256

586bcb5fe4988b5438183a60c3c4499a9e1469c838230138f7646f865bf4241f

## Linux Sample Manager v0.3.0

A desktop app for loading and managing samples on an FM-1 running ZP12.

Features include:

- WAV import, trimming, previews and normalization.
- Sample export, deletion and pad assignment.
- Break chopping across pads.
- ZP12 backup and restore.
- Export of saved sequencer loops as MIDI for LMMS or another MIDI sequencer.

### Install on Pop!_OS / Ubuntu

Extract the app ZIP and open a terminal inside the zp12-desktop folder containing install.sh.

Run:

sudo apt install python3-venv libxcb-cursor0 libxkbcommon-x11-0 libegl1
bash install.sh

Run the installer as your normal user, without sudo.

The first installation needs internet access to download dependencies. Afterwards, open ZP12 Sample Manager from your Applications menu.

### Export a loop to LMMS

1. Stop ZP12 playback and save your pattern.
2. In the app, create a fresh backup including ZP12.
3. Choose File → Export loop as MIDI.
4. Open the backup, choose your loop and save the .mid file.
5. Import the MIDI file into LMMS.
6. Set the imported tracks' MIDI outputs to your FM-1 and enable MIDI output.
7. Keep the FM-1's internal sequencer stopped while LMMS plays its pads.

MIDI export contains notes, timing and velocity, not sample audio. Keep the same samples assigned to the same pads on the FM-1.

Full song-chain export, per-hit parameter locks and MULTI PITCH transpositions are not transferred.

## Source, credits and licence

ZP12 is the work of Sven Trogus (@zvenson) and its contributors:

https://github.com/zvenson/zp12

These packages are based on upstream revision:

a7cc3dcf3b59303024dcfb69f34aac98007425c5

The UCUN compatibility change follows the flash-ID acceptance approach used in keremimo/melodee.

This repository shares a community compatibility build and a desktop companion app. It does not claim authorship of the original ZP12 firmware or editor.

Firmware source, the UCUN patch and build validation logs are included in the firmware ZIP. Desktop app source and tests are included in the app ZIP.

Both packages include their GPL v3 licence text and original notices. The desktop package specifies GPL-3.0-only. External dependencies retain their own licences.

This project is not affiliated with or endorsed by M-VAVE or the upstream author.
