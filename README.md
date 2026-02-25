<div align="center">

# 🎮 Game Specific Patches & DLL Wrappers  

***created and maintained by***

[![Chip-Biscuit Website](https://img.shields.io/badge/Chip--Biscuit-Website-blue?style=for-the-badge)](https://chip-biscuit.github.io/)

Reverse Engineering • Programming • Patching • Game Improvements • DLL Creation 

[![Downloads](https://img.shields.io/github/downloads/Chip-Biscuit/Star-Wars-Episode-I-Phantom-Menace-PC-64bit-Installer/phantom/total?label=Total%20Downloads)](https://github.com/Chip-Biscuit/Star-Wars-Episode-I-Phantom-Menace-PC-64bit-Installer/releases/tag/phantom)

<sub>click the Total Downloads button above to take you to the releases page with the instructions and download Chips64bit_ThePhantomMenaceInstaller.exe at the bottom  of the page</sub>

</div>

# Star Wars: Episode I – The Phantom Menace (PC)
## Modern 64-bit Installer + Fix Pack

The definitive way to play The Phantom Menace on modern Windows systems.

This project provides a fully rebuilt 64-bit installer for the original PC version of Star Wars: Episode I – The Phantom Menace.

The original 16-bit installer no longer works on modern versions of Windows.  
This project recreates the installation process through reverse engineering, ensuring the game remains playable for future generations.

This is a preservation project first, with optional modern enhancements available.

![ezgif com-animated-gif-maker (7)](https://github.com/user-attachments/assets/c769f3d3-8260-434f-84ce-11a8193c972e)

<br>

## Video: Installer + Modern Enhancements in Action

Gameplay recorded using the modern 64-bit installer with widescreen, FOV, and 60 FPS enabled.

[![Watch the video](https://github.com/user-attachments/assets/101939cb-90b6-43f9-9145-78e1b7abcc24)](https://youtu.be/zAeQpJcd5-Q)

###### <i>Click the image above to watch the video</i>
<br>

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

#### Gameplay & Engine
- Widescreen resolution support (via obi.ini) — default 1920×1080
- Greater-than-1080p resolution support
- 60 FPS modification (original game is 30 FPS)
- Adjustable in-game FOV system
- Optional 100% completion save pack

#### Graphics
- LegacyD3D Resolution Hack (extended resolution handling)
- DirectX 7 → DirectX 9 wrapper (dxwrapper)
  - Anti-aliasing
  - Anisotropic filtering
  - Borderless windowed mode
  - Improved compatibility on modern GPUs

#### Audio
- DSOAL (restores EAX environmental audio on modern Windows)

#### Controller Support
- Xidi input wrapper
  - Modern controller compatibility
  - Xbox controller support
  - Remapping via Xidi.ini

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

The FOV hotkey by default is F1 and you can change this to any keyboard or mouse key you like using the folder scripts -> chip.ini

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

## Graphics Issue: "Could Not Initialize Graphics Hardware"

In rare cases (primarily certain AMD driver versions), the game may fail to initialise legacy DirectDraw / Direct3D and display:

> "Could not initialize graphics hardware"

This is a driver compatibility issue.

---

### Default Installer Configuration (Recommended)

The installer enables the following compatibility components **by default**:

- DirectX 7 → DirectX 9 wrapper (dxwrapper)
- Anti-aliasing
- Anisotropic filtering
- Borderless windowed mode
- Modern GPU compatibility improvements
- DSOAL (restores EAX audio)
- Xidi (modern controller support)

For the vast majority of systems, no additional configuration is required.

Install normally and launch the game.

---

### dgVoodoo2 — Use Only If the Error Persists

If the game still fails to initialise graphics after installation, dgVoodoo2 can be used as a fallback compatibility layer.

This is mainly required for certain AMD GPUs. NVIDIA systems typically do not need this.

⚠ IMPORTANT:

If you plan to use dgVoodoo2, you must install the game **WITHOUT** the Elisha DirectX wrapper enabled.

During installation:

- Untick: **Elisha wrapper (DirectX 7 → DirectX 9)**

Do NOT use dxwrapper and dgVoodoo together.

---

### dgVoodoo2 Installation Steps

1. Download dgVoodoo2 from the official site:  
   https://dege.freeweb.hu/dgVoodoo2/dgVoodoo2/
2. Extract the archive.
3. Copy the following files from the `MS` folder into the game directory (where `WMAIN.exe` is located):
   - `DDraw.dll`
   - `D3DImm.dll`
4. Run `dgVoodooCpl.exe`.
5. Under the **DirectX** tab:
   - Ensure *"Disable and passthru to real DirectX"* is **unchecked**
   - Select **dgVoodoo Virtual 3D Accelerated Card**
6. Click Apply and close.
7. Launch the game again.

---

### Important — Resolution Handling

Do **NOT** use dgVoodoo2 to force resolution scaling.

Resolution should be configured natively using:

```
obi.ini
```

The installer already patches the game for modern resolutions.

Using dgVoodoo scaling together with the installer’s widescreen enhancements may cause:

- Incorrect aspect ratio
- Double scaling
- UI distortion
- Unintended behaviour

dgVoodoo2 should only be used as a last-resort compatibility layer.

---

## Audio: EAX Restoration (DSOAL)

Enabled by default in the installer.

Restores environmental audio support removed from modern Windows versions.

---

## Controller Support (Xidi)

Enabled by default in the installer.

Provides:

- Modern XInput controller compatibility
- Xbox controller support
- Full remapping via `Xidi.ini`
- press the start button to open the menu in game on the controller

No manual setup required unless creating a custom controller configuration.

---

## Source Code Availability

The installer and patching framework are currently closed-source while active reverse engineering work is ongoing.

This is intentional to avoid fragmentation, duplicate builds, and large volumes of pull requests while core systems are still being explored and stabilised.

The long-term plan is for the source code to be released once the project reaches a more mature and stable state.

In the meantime:

If you are a reverse engineer, developer, or technical contributor interested in the project, feel free to join the Discord community. I am happy to share progress, findings, and technical details with others working in this space.

Collaboration is welcome — the goal is preservation and understanding of the game’s engine.

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

