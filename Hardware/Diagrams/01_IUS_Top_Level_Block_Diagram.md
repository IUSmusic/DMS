# IUS Top-Level Hardware Block Diagram
Revision B


## Top-level diagram content to draw
- Main Compute / UI Board
- Real-Time Audio and Control Board
- Audio I/O / Analog Board
- Control Surface Board
- Display and Touch Subsystem
- Storage and External I/O Subsystem
- Power System
- HDMI External Display Path
- Master Bus and Track Engine relationships

## Top-level Mermaid reference
```mermaid
flowchart LR
    PSU[Power System\nBattery / DC In / Charging / Regulation]
    UI[Main Compute / UI Board\nEmbedded Linux-class SOM\nWaveform UI / Themes / Touch / HDMI]
    RT[Real-Time Audio and Control Board\nDeterministic audio scheduling\nTrack engine coordination]
    AIO[Audio I/O and Analog Board\nMic preamps / line input / codec / line out / headphone amp]
    CTRL[Control Surface Board\nTrack buttons / transport / LEDs / jog wheel / scanning]
    DISP[Display and Touch Subsystem\nMain touch monitor\nDAW waveform view / grid / playhead]
    STORE[Storage and External I/O\n2x microSD / USB-C / USB-A / project media]
    HDMI[HDMI Output\nExternal monitor for recorder / soundbank / piano UI]
    MIDI[MIDI / USB MIDI / expansion I/O]
    MASTER[Master Stereo Bus]
    TRACKS[5 Track Engines\nArm / Track Rec / Mic Rec / Playback]

    PSU --> UI
    PSU --> RT
    PSU --> AIO
    PSU --> CTRL
    PSU --> DISP
    PSU --> STORE

    CTRL <--> RT
    CTRL <--> UI
    DISP <--> UI
    STORE <--> UI
    UI --> HDMI
    MIDI <--> UI
    MIDI <--> RT

    AIO <--> RT
    RT <--> TRACKS
    TRACKS --> MASTER
    MASTER --> RT
    RT --> AIO
    UI <--> RT
```

