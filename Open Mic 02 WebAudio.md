# WebAudio
[@mollerse](https://twitter.com/@mollerse)

- Oscillator => Gain => Audiodestination
- MIDI
	- `navigator.requestMIDIAccess().then(midi => /* use midi */)`
	- monophonic: map midi input to frequency
	- polyphonic: map of notes to gain, turn off only the one triggered
- supersaw effect
	- mulitple oscillators, slightly detuned
- demo: https://github.com/mollerse/audible-code-presentation