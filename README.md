# wavelink-macropad-ahk
A lightweight AHK v2 script to control Elgato Wave Link channels (or any Windows audio device) using a budget macro pad

# Wave Link Macro Pad Controller

A lightweight script to control Elgato Wave Link channels (or any Windows audio device) using a budget macro pad. Written in AutoHotkey v2.

## The Problem
Basic software for budget macro pads can only control the main Windows volume. It cannot control individual Wave Link channels like Discord, Browser, or Music.

This script uses AutoHotkey v2 to talk directly to Windows. It changes the volume of specific channels instantly. You do not need heavy background software.

**Important note:** Because this script talks directly to the Windows audio system, it works not just for Wave Link, but for ANY audio playback or recording device (like your main headphones or microphone).

## What You Need
* Windows 10 or 11
* [AutoHotkey v2](https://www.autohotkey.com/) installed
* Elgato Wave Link (or any other audio device)
* Any macro pad with knobs (encoders)


## How to Setup

### 1. Macro Pad Setup
Open your macro pad software. Change the knob actions to use keys F13 to F24. These keys do not exist on normal keyboards, so they will not interfere with your typing.

Example for one knob:
* Turn Left: F13
* Turn Right: F14
* Press (Click): F15

### 2. Script Setup 
1. Download the `volume_control.ahk` file from this repository.
2. Open it in Notepad.
3. Find the exact names of your Wave Link channels. Press `Win + R`, type `mmsys.cpl`, and hit Enter. Look at the names in the list.
4. **WARNING:** You must use the EXACT name from the Windows list in the script. For example, if your channel is named "Music", the script must say "Music". If the names do not match exactly, the script will not work.
5. Replace the names "Discord", "Browser", and "Music" in the script with your exact channel names.

### The Code
```autohotkey
#Requires AutoHotkey v2.0

; DISCORD
F13::SoundSetVolume("-5", , "Discord")
F14::SoundSetVolume("+5", , "Discord")
F15::SoundSetMute(-1, , "Discord")

; BROWSER
F16::SoundSetVolume("-5", , "Browser")
F17::SoundSetVolume("+5", , "Browser")
F18::SoundSetMute(-1, , "Browser")

; MUSIC
F19::SoundSetVolume("-5", , "Music")
F20::SoundSetVolume("+5", , "Music")
F21::SoundSetMute(-1, , "Music")
