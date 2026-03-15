Changelog
Added
Master Track
Added a dedicated master track panel above the regular tracks
Includes FX toggle, Midi/Bank mode, Reverb, Delay, Distortion, Volume, Play, Rec, and Sustain
Master track remains visually distinct while preserving the original sequencer row style
Persistent Main Monitor
Added a left-side main monitor panel
Integrated into the layout alongside the sequencer
Designed to follow the original index.html proportions rather than replacing them
Oscilloscope
Added an always-visible oscilloscope inside the main monitor
Wired to the master output analyser
Sound Library Monitor
Added a persistent Sound Library view inside the main monitor
Includes sound browsing, file loading, search, and assignment workflow support
Startup Layout
Default startup now opens with:
1 Master track
5 regular tracks
Main monitor visible
Master Effects Controls
Added functional Reverb, Delay, and Distortion controls on the master track
Controls are visually presented as physical-style knobs and wired to audio behavior
Master EQ
Added a minimal physical EQ section in the top area
Wired to the master bus
Top Status Area
Added master status / armed-sound display elements in the top bar
3 Stereo In + Master Stereo Out Mixer Display
Added a visual mixer section representing:
3 stereo inputs (L/R × 3)
1 stereo master output (L/R)
Gain controls displayed below each stereo pair
Visual only for now

Offline packaging fix
Embedded built in soundbank assets directly into the main HTML so the library populates correctly when opened from the ZIP without a local web server.
