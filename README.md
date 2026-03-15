**I/US Official Sequencer**
![DMS Preview](DMS%20Preview01.png)
![DMS Preview](DMS%20Preview02.png)
![DMS Preview](DMS%20Preview03.png)

**Live demo**
  * **[Open in New Page](https://iusmusic.github.io/IUS-DMS/)**


## Revision B Architecture Update

* Reframed the device from a sequencer-first prototype into a sampling-first multitrack workstation

* Kept the system as a 5-track DAW layout with a dedicated master section

* Replaced the oscilloscope-style monitor concept with a DAW-style waveform monitor direction

* Defined the monitor as a fixed shared display with vertically compressing track lanes

* Set monitor lane colors by track number:

  * Track 1 red
  * Track 2 blue
  * Track 3 white
  * Track 4 red
  * Track 5 blue

* Defined silent but engaged tracks to write as flat lines rather than disappearing

* Set the monitor to preserve recorded waveform history after capture for future edit and punch-in workflows

* Clarified that the monitor must support touch interaction for waveform selection, cursor placement, and future edit-from-position recording

* Added the requirement for visible waveform grids to support precise editing

* Added a dedicated right-side scroll / jog control for surgical waveform navigation when touch alone is not precise enough

* Split per-track recording behavior into separate functions:

  * Arm / Sample
  * Track Rec
  * Mic Rec

* Track Rec captures the track behavior/output in stereo

* Mic Rec is a separate hold-to-record sampling path

* uploaded audio can be used as a backing-track

* Added the requirement for a separate Master Mix Rec path in addition to Master Mic Rec

* Defined Master Mix Rec as the stereo capture path for all tracks and master performance output

* Confirmed that the master section remains a controller/master-bus section rather than becoming a normal track lane

* Reworked the hardware direction from a single-DSP-centered prototype into a dual-domain architecture

* Defined a Main Compute / UI subsystem for touch DAW display, themes, storage management, and HDMI output

* Defined a separate real-time audio/control subsystem for deterministic low-latency audio behavior

* Kept the audio design focused on studio-quality recording at 24-bit / 48 kHz minimum, with headroom for higher-quality operation later

* Defined the analog/digital boundary more clearly around codec, preamp, line conditioning, output stage, and digital track engine domains

* Expanded the storage direction to support multiple media paths, including more than one microSD slot and external storage workflows

* Added expanded I/O direction including additional USB-C, USB-A, and HDMI support

* Defined HDMI as an external display path for the recorder screen, sound bank monitor, and piano UI

* Rewrote the hardware plan as an open-source-ready modular board split:

  * Main Compute / UI Board
  * Real-Time Audio and Control Board
  * Audio I/O / Analog Board
  * Control Surface Board
  * Display / Touch Subsystem

* Rewrote the block schematic, hardware architecture, and layout documents around Revision B instead of the earlier Revision A prototype assumptions

* Added dedicated block-diagram and industrial-design briefing documents for future diagramming and hardware drawing work
You’re right. Here it is in the same Markdown style as the Revision B section.

## 14 March 2026

* Kept the app as a 5-track sequencer

* Decoupled the keyboard size from the 31-step sequencer

* Replaced the limited keyboard with a full piano keyboard

* Upgraded the keyboard path to use a soundfont-backed piano with fallback behavior

* Added a new Record Monitor below the master track

* Wired it so it shows only armed or recording tracks

* Made the monitor responsive so multiple armed tracks are visible as needed

* Added track color mapping so recordings are visually tied to their source track

* Moved the Settings inside the Library / Sound Bank monitor

* Reduced the left monitor/bank panel width by about 10%

* Added Skip Back, Play/Pause, and Skip Forward controls

* Wired the new UI so the controls and monitor behavior are connected

* Kept the master track as controller rather than using it as the recording lane

## 13 March 2026

* Added a dedicated master track panel above the regular tracks

* Included:

  * **FX toggle**
  * **Midi/Bank mode**
  * **Reverb**
  * **Delay**
  * **Distortion**
  * **Volume**
  * **Play**
  * **Rec**
  * **Sustain**

* Added a **left-side main monitor** panel

* Added an always-visible **oscilloscope** inside the main monitor

* Wired it to the **master output analyser**

* Added a persistent **Sound Library** view inside the main monitor

* Included sound browsing, file loading, search, and assignment workflow support

* Added functional **Reverb**, **Delay**, and **Distortion** controls on all tracks

* Presented the controls as physical-style knobs and wired them to audio behavior

* Added a **minimal physical EQ section** in the top area

* Wired the EQ section to the **master bus**


## How to use the preview

* Step 1. Open index.html in your browser.

* Step 2. Use the main monitor and top controls to access the current workspace.

* Step 3. Open the Library / Sound Bank panel to browse available sounds.

* Step 4. Load audio files if you want to add custom sounds.

* Step 5. Click a sound in the library to arm or assign it for use.

* Step 6. Click a step on any track to place the selected sound into the sequence.

* Step 7. Use the track Play button to hear that track.

* Step 8. Use Stop to stop playback and reset the position as needed.

* Step 9. Change BPM to alter playback speed.

* Step 10. Use the Loop control to keep playback cycling.

* Step 11. Use the transport controls to move through playback.

* Step 12. Use the track controls to adjust playback and performance behavior.

* Step 13. Use the Library / Sound Bank monitor settings area for available display and sound options.

* Step 14. Use the full piano keyboard to play notes across a wider range.

* Step 15. Use the theme/display controls if available to switch viewing modes.

**Custom sounds**

- Place your own sample files in the soundbank samples folder.

- Supported file types depend on browser audio support. Common examples include:

- wav
- mp3
- ogg

- Custom files placed in the samples folder appear in the Custom category in the sound library.

- Suggested naming rules for automatic grouping

- Files that start with kick, snare, clap, or hihat are treated as drum sounds.

- Files that start with bass are treated as bass sounds.

- Files that start with synth are treated as synth sounds.

- Files that start with fx are treated as effects sounds.

## Notes

* Browser audio behavior may vary slightly depending on the browser.

* Some features may require user interaction before audio playback is allowed.

* Microphone-related features depend on browser permissions.

* Support for custom formats depends on the browser’s built-in audio decoding capabilities.


I can also rewrite this into a cleaner README-style section for your .md file.


## I/US DMS

**I/US-DMS is a browser-based prototype of the I/US Official Sequencer**

## What this project is
**This repository brings together two connected parts of the same idea:**

**Software prototype**:
 * **A browser-based sequencer used to test interface behaviour, playback workflow, sound browsing, track control, and interaction design**

**Hardware concept**:
* **Early notes, layouts, and supporting documents of the future physical I/US device**

The software side is the hands-on prototype you can run now.  
The hardware side shows the broader direction the project is moving toward.

## What this repo contains
- Browser prototype (`index.html`)
- Interface experiments and sequencing workflow development
- Early hardware and layout notes
- Soundbank structure for sample testing
- Concept and planning files tied to the wider I/US system

## Current status
This is an early public prototype shared to organise ideas, test workflows, document progress, and gradually connect the software prototype to the larger hardware vision behind I/US.

## Features
- Multi-track step sequencing
- Sample library and custom sample loading
- BPM control
- Looping
- Theme switching
- Microphone recording where supported

## Roadmap
- I will continue to add features and update the project.
- Clear hardware documentation
- Versioned releases
- Customizable effect plugins


  **3 Stereo In + Master Stereo Out Mixer Display**

  * Added a visual mixer section representing:
    * **3 stereo inputs** (`L/R × 3`)
    * **1 stereo master output** (`L/R`)
  * Gain controls displayed below each stereo pair

### Fixed

  **Layout integration**

  * New monitor, EQ, and mixer elements were added relative to the existing HTML layout system
  * Preserved the original wide/open page behavior instead of turning the UI into a fixed-size app

  **Library / Monitor workflow**

  * Library, oscilloscope, and monitor area now coexist in the same left-side module

  **Master audio routing**

  * Master volume, EQ, and master FX are connected within the audio path
  * Midi/Bank mode and sustain behavior are integrated into the master track workflow


### How to open the prototype

  * Step 1. Extract the zip file.
  * Step 2. Open the IUS Official Sequencer folder.
  * Step 3. Open index.html in a modern browser.
  * Step 4. The prototype will load with the main sequencer view.

### What the prototype does

The prototype provides a multi track step sequencer interface with 31 steps per track. It lets you open the sound library, preview sounds, assign sounds to steps, upload a default track sound, record default track audio from microphone input where supported, start and stop playback, change BPM, use looping, inspect assignments, and switch between dark and light high contrast themes.

### How to use the preview

  * Step 1. Open index.html in your browser.
  * Step 2. Click the library button in the top bar.
  * Step 3. Load audio files if you want to add custom sounds.
  * Step 4. Click a sound in the library to arm it.
  * Step 5. Click a step on any track to assign the armed sound.
  * Step 6. Use the play button on a track to hear the sequence.
  * Step 7. Use stop to reset the track.
  * Step 8. Change BPM on a track to alter playback speed.
  * Step 9. Use the loop control to keep playback cycling.
  * Step 10. Use the theme button in the top bar to switch between dark and light high contrast viewing modes.

  * Place your own sample files in the soundbank samples folder.
  * Supported file types depend on browser audio support. Common examples include wav mp3 and ogg.
  * Custom files placed in the samples folder appear in the custom category in the sound library.
  * Suggested naming rules for automatic grouping are shown below.

  * Files that start with kick or snare or clap or hihat are treated as drum sounds.
  * Files that start with bass are treated as bass sounds.
  * Files that start with synth are treated as synth sounds.
  * Files that start with fx are treated as effects sounds.


### License

MIT LICENSE

**Copyright 2026 Pezhman Farhangi**
**IUS Music**

Permission is hereby granted free of charge to any person obtaining a copy of this software and associated documentation files known as the Software to deal in the Software without restriction including without limitation the rights to use copy modify merge publish distribute sublicense and or sell copies of the Software and to permit persons to whom the Software is furnished to do so subject to the following conditions.

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

The Software is provided as is without warranty of any kind express or implied including but not limited to the warranties of merchantability fitness for a particular purpose and noninfringement. In no event shall the authors or copyright holders be liable for any claim damages or other liability whether in an action of contract tort or otherwise arising from out of or in connection with the Software or the use or other dealings in the Software.


### Trademark and brand notice

**I/US (PRS: IUS) and IUS Music® are protected brand identifiers associated with the official IUS project.**

**The code in this repository is licensed separately under the MIT License. That software license does not grant permission to use the IUS name, the IUS Music name, the official logo, the visual identity, artwork, images, audio branding, or other protected brand assets unless explicit written permission is given by IUS Music.**

**All rights in the IUS, I/US and IUS Music brand identity are reserved.**
