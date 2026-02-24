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
- Widescreen resolution support (via obi.ini) default 1920x1080
- 60 FPS modification (original game is 30 FPS)
- Adjustable in-game FOV system
- Optional 100% completion save pack  
- ability to play the game past 1920x1080

You may install the base game only if you prefer the original experience.

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

## Fix: "Could Not Initialize Graphics Hardware" (Primarily AMD GPUs) (not included in installer)

Some modern AMD graphics drivers may fail to properly initialize the game's legacy DirectDraw / Direct3D components.

If you receive the error:

> "Could not initialize graphics hardware"

this is typically a driver compatibility issue.

### Recommended Solution – [dgVoodoo2](https://dege.freeweb.hu/dgVoodoo2/dgVoodoo2/) (Compatibility Wrapper)

This is mainly required for certain AMD GPUs. NVIDIA users typically do not need this.

1. Download dgVoodoo2 from the official website.
2. Extract the archive.
3. Copy the following files from the `MS` folder into the game directory (where `WMAIN.exe` is located):
   - `DDraw.dll`
   - `D3DImm.dll`
4. Run `dgVoodooCpl.exe`.
5. Under the **DirectX** tab:
   - Ensure *"Disable and passthru to real DirectX"* is **unchecked**.
   - Select **dgVoodoo Virtual 3D Accelerated Card**.
6. Click Apply and close.

Launch the game again.

This is currently a compatibility workaround. Future updates aim to resolve this without requiring dgVoodoo2.

The installer already provides native widescreen support through obi.ini. Do not use dgVoodoo for resolution scaling, as this may cause UI distortion or double scaling.

a visual aid: 

<img width="298" height="359" alt="Screenshot 2026-02-24 130556" src="https://github.com/user-attachments/assets/14f982c7-9985-42f5-8326-586d8b3bced6" />

<img width="301" height="359" alt="Screenshot 2026-02-24 130622" src="https://github.com/user-attachments/assets/9a264dba-d9f0-4b49-9347-168250d65a84" />

### Important – Resolution Handling

Do **NOT** use dgVoodoo2 to force resolution scaling.

Resolution should be configured natively using:

obi.ini

The installer patches the game to properly support modern resolutions through `obi.ini`.

Using dgVoodoo resolution scaling in combination with the installer’s widescreen enhancements may cause:

- Incorrect aspect ratio
- Double scaling
- UI distortion
- Unintended behaviour

dgVoodoo should only be used as a compatibility wrapper if required.

---

## Restoring EAX Audio (DSOAL) (not included in installer)

The game originally supported EAX environmental audio, which is no longer available on modern Windows systems.

EAX-style audio can be restored using [DSOAL](https://github.com/kcat/dsoal) (DirectSound-to-OpenAL wrapper):

### Installation

1. Download the latest release from the DSOAL GitHub page.
2. Extract the archive.
3. Navigate to:

DSOAL+HRTF → win32

4. Copy **all contents** from this folder into the game installation directory (where `WMAIN.exe` is located).
5. Launch the game.
6. In the in-game sound settings, enable the **EAX** option.

Environmental audio effects should now function again.

### Notes

- This is an optional enhancement and not required to run the game.
- Works alongside the installer and patches without conflict.
- Behaviour may vary depending on audio hardware and OpenAL configuration.
- If audio issues occur, remove the DSOAL files from the game directory.

---


## Controller Support (Xidi) (not included in installer)

Xidi can be used to provide improved controller support and full remapping flexibility.

✔ Works with modern XInput gamepads (Xbox controllers and compatible devices).  
⚠ Always create a backup of `WMAIN.exe` before modifying anything.


### Standard Installation (Recommended)

1. Download the latest release of [Xidi](https://github.com/samuelgr/Xidi)
2. Extract the archive.
3. Open the `Win32` folder inside the extracted files.
4. Copy `winmm.dll` into the game directory (next to `WMAIN.exe`).
5. Create a file named `Xidi.ini` in the same directory (instructions below).
6. Launch the game and test controller input.

If the controller does not respond, use the fallback method below.


### Fallback Method (Required on Some Windows 11 Systems)

Some systems may require redirecting the `winmm.dll` import.

1. Rename `winmm.dll` to `winm2.dll`.
2. Open `WMAIN.exe` in a hex editor.
3. Search for the ASCII string:

```
winmm.dll
```

4. Replace it with:

```
winm2.dll
```

(Do not change the length — it must remain the same.)
5. Save the file.
6. Place `winm2.dll` and `Xidi.ini` in the game directory (next to `WMAIN.exe`).


## Creating Xidi.ini

Create a new text file in the game directory named:

```
Xidi.ini
```

Open it in a text editor and paste the following configuration:

```ini
[Mapper]
Type                = PhantomMenace

[CustomMapper:PhantomMenace]
StickLeftX          = Axis(X)
StickLeftY          = Axis(Y)
StickRightX         = Split( Compound( Keyboard(LAlt), Keyboard(RIGHT) ), Compound( Keyboard(LAlt), Keyboard(LEFT) ) )
StickRightY         = null
ButtonA             = Button(1)
ButtonB             = Button(2)
ButtonX             = Button(3)
ButtonY             = Button(4)
ButtonLB            = Button(5)
ButtonRB            = Button(6)
TriggerLT           = Button(7)
TriggerRT           = Button(8)
ButtonBack          = Button(9)
ButtonStart         = Keyboard(ESCAPE)
ButtonLS            = Button(11)
ButtonRS            = Button(12)
DpadUp              = Keyboard(UP)
DpadDown            = Keyboard(DOWN)
DpadLeft            = Keyboard(LEFT)
DpadRight           = Keyboard(RIGHT)
```

Important:

- Make sure the file is saved as `Xidi.ini`
- Ensure it is not accidentally saved as `Xidi.ini.txt`
- The game is 32-bit — use the **Win32** build of Xidi

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

