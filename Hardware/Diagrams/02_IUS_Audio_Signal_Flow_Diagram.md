# IUS Audio Signal-Flow Diagram
Revision B


## Audio signal-flow Mermaid reference
```mermaid
flowchart LR
    MIC[Mic Inputs]
    LINE[Line Inputs]
    SAMPLE[Sample Playback Engine]
    SB[Soundbank / Piano Role Engine]
    UP[Uploaded Audio / Backing Tracks]

    PRE[Analog Front End\nProtection / preamp / filter]
    CODEC[Audio Codec ADC/DAC]
    RT[Real-Time Audio Engine]

    T1[Track 1]
    T2[Track 2]
    T3[Track 3]
    T4[Track 4]
    T5[Track 5]

    TR1[Track 1 Record Tap]
    TR2[Track 2 Record Tap]
    TR3[Track 3 Record Tap]
    TR4[Track 4 Record Tap]
    TR5[Track 5 Record Tap]

    MASTER[Master Stereo Bus]
    MFX[Master FX / processing]
    MREC[Master Mix Record Tap]
    DAC[Output stage]
    HP[Headphones]
    LOUT[Main Stereo Out]

    MIC --> PRE --> CODEC --> RT
    LINE --> PRE
    SAMPLE --> RT
    SB --> RT
    UP --> RT

    RT --> T1 --> TR1 --> MASTER
    RT --> T2 --> TR2 --> MASTER
    RT --> T3 --> TR3 --> MASTER
    RT --> T4 --> TR4 --> MASTER
    RT --> T5 --> TR5 --> MASTER

    MASTER --> MFX --> MREC --> DAC --> HP
    DAC --> LOUT
```

## Behavior notes
- Each track has separate Arm / Sample, Track Rec, and Mic Rec behavior.
- Track Rec prints the track behavior/output in stereo.
- Mic Rec is hold-to-record sampling on that track.
- The master has separate Mic Rec and Mix Rec behavior.
- The monitor is fed from track/master waveform buffers, not from an oscilloscope-only path.

