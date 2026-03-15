# IUS Official Drum Sequencer
## Prototype Hardware Revision B

## Product direction

Revision B replaces the earlier DSP centered prototype with a modular workstation architecture designed for high quality sampling, soundbank playback, stereo track printing, microphone sampling, touch based waveform editing, and future open source release.

## Core design goals

- Studio quality recording at 24 bit 48 kHz minimum
- No perceptible audio lag during heavy use
- Reliable track playback, recording, and waveform rendering at the same time
- Touch based waveform selection and future punch in editing
- Theme support on the main monitor
- External display support over HDMI
- Expandable storage using more than one micro SD slot and USB storage
- Open source friendly modular hardware partitioning

## Main hardware architecture

### 1. Main compute and UI board
This board runs the main application layer.

Responsibilities:
- Touch UI and theme engine
- Project management
- Soundbank and library browser
- DAW monitor rendering
- External display handling over HDMI
- File management across internal and removable media
- Touch editing gestures and timeline logic

Recommended processor class:
- Embedded Linux class system on module
- Compute Module class platform or equivalent

### 2. Real time audio engine board
This board owns deterministic audio work.

Responsibilities:
- Sample triggering
- Soundbank playback
- Per track playback and looping
- Per track stereo record print
- Microphone capture per track
- Master stereo mix record
- Waveform envelope extraction for monitor rendering
- Tight transport sync and low latency audio timing

Recommended processor class:
- High performance MCU or DSP audio processor
- STM32H7 class or equivalent

### 3. Audio I O and analog board
This board handles the analog front end and conversion.

Responsibilities:
- Mic preamp path
- Stereo line input conditioning
- ADC and DAC conversion
- Output filtering and line driving
- Headphone amplifier
- Audio clocking and low noise analog power handling

### 4. Control surface board
This board handles the physical interface.

Responsibilities:
- Track buttons and LEDs
- Master transport controls
- Jog or scroll control on the right side for precise waveform navigation
- Per track record controls
- Optional encoders, knobs, and status lighting

### 5. Display and touch board
This board handles the integrated monitor.

Responsibilities:
- Touch panel
- Display timing and backlight domain
- Main DAW waveform monitor
- Grid overlay support
- Edit cursor and waveform interaction

## Control layout summary

### Master section
- Mic Rec button
- Mix Rec button
- Play
- Stop
- Pause
- Sustain
- Master effects controls
- Master volume

### Per track controls
Each track requires separate controls for separate functions.

- Arm button for sample and soundbank readiness
- Track Rec button for printing the track behavior in stereo
- Mic Rec button for hold to sample recording
- Play button
- Loop button
- Track select or settings access as needed

### Track lane behavior
- A track lane belongs to the track number, not to temporary monitor position
- Track colors are fixed:
  - Track 1 red
  - Track 2 blue
  - Track 3 white
  - Track 4 red
  - Track 5 blue
- Engaged but silent tracks display a flat line
- Active signal displays waveform energy
- Recording writes waveform from left to right
- Finished waveforms remain on the timeline for later editing

## Monitor and editing system

The monitor is a DAW waveform display.
It is not an EQ bar display.
It is not an oscilloscope.

Required behavior:
- Fixed monitor frame size
- Adaptive lane height when more tracks are engaged
- Mirrored waveform display around the center line
- Dark background
- Vertical guides and timeline grid support
- Red playhead or edit marker
- Touch based cursor placement and future punch in workflow
- External monitor output for soundbank, piano, and waveform views

## Storage architecture

### Internal storage
- Boot and system storage on the compute platform
- Local project cache

### Removable storage
- More than one micro SD card slot
- One slot may be optimized for projects and recordings
- One slot may be optimized for sample and soundbank libraries

### External storage
- USB storage support for hard drives and SSDs
- Required folder structure so the app can understand projects, samples, soundbanks, exports, and backups

## Ports and expansion

Revision B should preserve current core audio and power ports where practical, while expanding the digital I O.

Required additions:
- HDMI output
- Two USB C ports minimum
- USB A host port or ports
- More than one micro SD slot

Existing analog and audio ports should remain part of the design set unless replaced by a formal later revision.

## Audio system rules

- Single fixed audio clock domain for stable operation
- Minimum internal target of 24 bit 48 kHz
- Higher rates only if validated under full system load
- Real time playback and recording audio must be buffered in RAM
- Direct removable media access must not sit in the hardest real time audio path

## Firmware and event model

Each control should map cleanly to firmware events.

Examples:
- ARM on or off
- TRACK REC start or stop
- MIC REC start or stop
- MIX REC start or stop
- PLAY toggle
- LOOP toggle
- Track select
- Scroll jog delta
- Touch timeline select
- Cursor set
- Grid toggle
- Snap mode toggle

This event driven approach makes the platform easier to maintain and easier to open source.

## Open source release goal

Revision B should be documented from the beginning as a modular open hardware platform.

Publishable modules:
- Main compute and UI board
- Real time audio engine board
- Audio I O and analog board
- Control surface board
- Display and touch board

