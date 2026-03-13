## I/US Official Sequencer

**https://iusmusic.github.io/IUS-DMS/**
 * Preview Models
![DMS Preview](DMS%20Preview01.png)
![DMS Preview](DMS%20Preview02.png)

 * Web UI
![DMS Preview](DMS%20Preview.png)


## Changelog

 13 March 2026

**Master Track**

  * Added a dedicated master track panel above the regular tracks
  * Includes **FX toggle**, **Midi/Bank mode**, **Reverb**, **Delay**, **Distortion**, **Volume**, **Play**, **Rec**, and **Sustain**
  * Master track remains visually distinct while preserving the original sequencer row style

  **Persistent Main Monitor**

  * Added a **left-side main monitor** panel
  * Integrated into the layout alongside the sequencer
  * Designed to follow the original `index.html` proportions rather than replacing them

  **Oscilloscope**

  * Added an always-visible **oscilloscope** inside the main monitor
  * Wired to the **master output analyser**

  **Sound Library Monitor**

  * Added a persistent **Sound Library** view inside the main monitor
  * Includes sound browsing, file loading, search, and assignment workflow support

  **Master Effects Controls**

  * Added functional **Reverb**, **Delay**, and **Distortion** controls on the master track
  * Controls are visually presented as physical-style knobs and wired to audio behavior

  **Master EQ**

  * Added a **minimal physical EQ section** in the top area
  * Wired to the **master bus**

  **Top Status Area**

  * Added master status / armed-sound display elements in the top bar

  **3 Stereo In + Master Stereo Out Mixer Display**

  * Added a visual mixer section representing:

    * **3 stereo inputs** (`L/R × 3`)
    * **1 stereo master output** (`L/R`)
  * Gain controls displayed below each stereo pair
  * Visual only for now

### Fixed

  **Layout integration**

  * New monitor, EQ, and mixer elements were added relative to the existing HTML layout system
  * Preserved the original wide/open page behavior instead of turning the UI into a fixed-size app

  **Library / Monitor workflow**

  * Library, oscilloscope, and monitor area now coexist in the same left-side module

  **Master audio routing**

  * Master volume, EQ, and master FX are connected within the audio path
  * Midi/Bank mode and sustain behavior are integrated into the master track workflow




### Main files

  * LICENSE.txt
  * TRADEMARK NOTICE.txt
  * Hardware Layout.txt
  * Schematic.txt 
  * hardware.txt

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

I/US (PRS: IUS) and IUS Music® are protected brand identifiers associated with the official IUS project.

The code in this repository is licensed separately under the MIT License. That software license does not grant permission to use the IUS name, the IUS Music name, the official logo, the visual identity, artwork, images, audio branding, or other protected brand assets unless explicit written permission is given by IUS Music.

## All rights in the IUS, I/US and IUS Music brand identity are reserved.
