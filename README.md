<div align="center">

# 🎮 Game Specific Patches & DLL Wrappers  

***created and maintained by***

[![Chip-Biscuit Website](https://img.shields.io/badge/Chip--Biscuit-Website-blue?style=for-the-badge)](https://chip-biscuit.github.io/)

Reverse Engineering • Programming • Patching • Game Improvements • DLL Creation 

[![Downloads](https://img.shields.io/github/downloads/Chip-Biscuit/Star-Wars-Episode-I-Phantom-Menace-PC-64bit-Installer/phantom/total?label=Total%20Downloads)](https://github.com/Chip-Biscuit/Star-Wars-Episode-I-Phantom-Menace-PC-64bit-Installer/releases/tag/phantom)

<sub>click the Total Downloads button above to take you to the releases page and download the [exe](https://github.com/Chip-Biscuit/Star-Wars-Episode-I-Phantom-Menace-PC-64bit-Installer/releases/download/phantom/Chips64bit_ThePhantomMenaceInstaller.exe) at the bottom</sub>

</div>

# Star Wars: Episode I – The Phantom Menace (PC)
## Modern 64-bit Installer + Fix Pack

![ezgif com-animated-gif-maker (7)](https://github.com/user-attachments/assets/c769f3d3-8260-434f-84ce-11a8193c972e)


The definitive way to play The Phantom Menace on modern Windows systems.

This project provides a fully rebuilt 64-bit installer for the original PC version of Star Wars: Episode I – The Phantom Menace.

The original 16-bit installer no longer works on modern versions of Windows.  
This project recreates the installation process through reverse engineering, ensuring the game remains playable for future generations.

This is a preservation project first, with optional modern enhancements available.

---

## Reverse Engineering Progress

I’ve begun actively reverse engineering the game’s executable to understand how the engine works internally and how far it can be pushed.

So far I’ve successfully:

- Located and patched the camera FOV at runtime
- Analysed frame timing and implemented the 60 FPS modification
- Investigated how the engine handles level loads and why crashes occur with custom FOV
- Begun exploring model and asset file structures

These discoveries are what power the current fixes in this installer.

This is only the beginning. The long-term goal is to properly understand the engine, document its behaviour, and eventually enable full mod support.

---

## Legal Notice

You must legally own an original retail copy of the game.

This installer does NOT include any game data.  
It copies the required files from your original CD or mounted ISO during installation.

No copyrighted game files are distributed.

---

## What’s Included

### Base Installation
- Full game installation on modern 64-bit Windows
- Official 1.1 patch applied
- Folder permission fixes
- Compatibility adjustments
- DPI awareness enabled

### Optional Enhancements (Selectable During Installation)
- Widescreen resolution support (via obi.ini) default 1920x1080
- 60 FPS modification (original game is 30 FPS)
- Adjustable in-game FOV system
- Optional 100% completion save pack  
- ability to play the game past 1920x1080

You may install the base game only if you prefer the original experience.

---

## Resolution / Widescreen Support

If you install the Legacy Resolution option, an obi.ini file will be added to the game folder.

It is preconfigured for 1920x1080.

You can change it to any resolution by editing:
- Game resolution
- Menu resolution

Tested up to 4K.  
Ultrawide and other custom resolutions may also work.

Feedback is welcome.

---

## FPS Patch

The game is patched to run at 60 FPS instead of the original 30 FPS.

This improves smoothness while maintaining original gameplay timing.

---

## FOV System (Work in Progress)

The FOV system allows you to toggle between:
- Original FOV
- Custom FOV value from scripts/chip.ini

Due to engine limitations, FOV changes only apply after the camera state refreshes via the menu.

---

### How to Change FOV

1. While playing in-game, press your configured FOV hotkey  
2. Press ESC to open the menu  
3. Close the menu  

The FOV change will now take effect.

Sequence:

Gameplay → Press Hotkey → Open Menu → Close Menu → FOV Updates

To revert:

Gameplay → Press Hotkey → Open Menu → Close Menu → Original FOV Restored

---

### Important Level-Load Warning

If a level loads while custom FOV is active, the game may crash.

Before finishing a level:
1. Toggle FOV back to original game FOV (60) using the above method
2. Allow the next level to load
3. Reapply your custom FOV once gameplay resumes

This limitation will be improved in future updates.

---

## Launching the Game

After installation:
- You can unmount the disc
- Use the desktop shortcut

Run the game using:

WMAIN.exe

Do NOT launch using:

TPM.exe (launcher) although you can use it to change some options.

The installer automatically creates the correct shortcut.

---

## Optional 100% Game Saves

You can optionally install a full set of completion saves.

If enabled:
- All levels will be unlocked
- All progression complete

This option is off by default.

---

## Modding Community

If you love this game, consider joining the community:

https://discord.gg/KX7R4quSQw

Goals:
- Help players get the game running
- Reverse engineer systems and file formats
- Develop modding tools
- Enable custom maps, textures, and models
- Preserve the game long-term

Long-term goal: full reverse engineering and complete mod support.

Reverse engineers welcome.

---

## Why This Exists

I have played this game since I was 4 years old.

This project exists purely out of passion and preservation.

Everything is released for free to:
- Keep the game alive
- Improve compatibility
- Help the community
- Preserve PC gaming history

If you try it, feedback is always appreciated.

“Creating compatibility fixes and enhancements for legacy PC games.”

# Chip
- reverse engineer
- programmer
- developer
- Game Preservationist
  
<img width="250" height="500" alt="my logoo" src="https://github.com/user-attachments/assets/9bb13d3f-0734-4f1d-b68f-14114b13744a" />

