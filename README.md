# Guitar Improvisation Trainer

An interactive guitar scale and chord explorer that runs entirely in your browser. Pick a root and any of 80+ scales and modes, see every note on the fretboard, hear it played, and get chord progressions and fingerings that fit.

No installation, no dependencies, no build step. It's one HTML file.

## Try it

Open `index.html` or 'guitar-scales.html' in any modern browser, or visit the live version if GitHub Pages is enabled for this repo.

## Features

**Fretboard**
- 80+ scales and modes, grouped by family: diatonic modes, harmonic and melodic minor modes, harmonic major modes, pentatonic and blues, symmetrical scales, bebop, double harmonic, world scales, and more
- Any of the 12 roots, with sensible sharp/flat spelling per key
- Tunings: standard, half step down, Drop D, DADGAD, Open G, Open E, and 7-string
- 12 to 24 frets, with inlays where you expect them
- Toggle labels between note names and scale degrees (R, ♭3, ♯4...)

**Chords**
- Builds a chord on every degree of the scale using only scale tones, with the 7th version where the scale allows one
- Suggests a progression matched to the scale's character, with accurate Roman numerals; cycle through alternatives or list every chord in the scale
- Tap a chord to highlight its tones on the neck, hear it strummed, and see up to four suggested fingerings ranked by playability (root in the bass, low position, four-fret stretch, no muted strings in the middle)
- Fingerings are calculated for the tuning you've selected

**Playback**
- Plucked-string synthesis via the Web Audio API — no audio files
- Play the scale, the progression, or the scale over the progression
- Notes light up on the fretboard as they play
- Tempo slider (40–240 bpm)
- Repeat once, 2×, 4×, 8×, or loop until stopped
- Scale speed of 1×–4× per pass through the chords
- Metronome with accented downbeat and a visual beat indicator
- Audio mode selector (auto / desktop / iPhone) and a "Test sound" button

## How it works

Everything is computed from a table of interval sets (semitones above the root). Chord qualities come from stacking thirds within the scale, fingerings from a small search over the fretboard scored for comfort, and audio from a Karplus-Strong string model rendered into audio buffers on demand.

## Browser notes

- Audio starts on your first tap, as browsers require.
- On iPhone, the app requests a "playback" audio session so it plays even with the ring/silent switch on.
- Open the file in a real browser (e.g. Safari) rather than a file preview, which won't run the scripts.
- On desktop, if "Test sound" reports audio running but you hear nothing, check that the browser tab isn't muted and that the browser is using the right output device.

## Contributing

The scale table is at the top of the script — adding a scale is one line: `["Name", [0, 2, 4, ...]]`. Pull requests welcome.

## License

MIT
