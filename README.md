# 🎵 Musical Time-Stretching & Pitch-Shifting

**An interactive exploration of audio manipulation — from 1940s tape splicing to neural synthesis.**

🔗 **[View the live presentation →](https://brendanjameslynskey.github.io/MusicalTimeStretchingPitchShifting/)**

![HTML5](https://img.shields.io/badge/HTML5-single--file-E34F26?logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-Web%20Audio%20API-F7DF1E?logo=javascript&logoColor=black)
![License](https://img.shields.io/badge/license-MIT-blue)
![GitHub Pages](https://img.shields.io/badge/deploy-GitHub%20Pages-222?logo=github)

---

## Overview

This is a self-contained, single-file interactive presentation that covers the history, mathematics, implementation techniques, and future directions of musical time-stretching and pitch-shifting. It is designed for deployment on GitHub Pages with zero dependencies.

Time-stretching changes the duration of audio without affecting pitch. Pitch-shifting changes the pitch without affecting duration. These two operations — seemingly simple — require sophisticated signal processing to achieve, and have driven decades of research from Bell Labs to Google Brain.

---

## Contents

The presentation is organised into six chapters:

| Chapter | Topic | What's Covered |
|---------|-------|----------------|
| I | **History** | Timeline from varispeed tape (1940s) through The Beatles, the Eventide H910 Harmonizer (1975), the phase vocoder, PSOLA, Auto-Tune, DAW integration, and modern neural approaches |
| II | **Fundamentals** | The core problem of decoupling pitch and time; the time-stretch + resample pipeline |
| III | **Algorithms** | Tabbed exploration of four algorithm families: time-domain (OLA, SOLA, TD-PSOLA), frequency-domain (Phase Vocoder, Sinusoidal Modelling, CQT), hybrid (transient separation, wavelets, PVSOLA), and neural/AI (DDSP, RAVE, CLPCNet, diffusion models) |
| IV | **Mathematics** | Seven detailed equation boxes with expandable symbol-explanation panels covering the STFT, amplitude–phase decomposition, phase vocoder propagation, overlap-add reconstruction, the Gabor uncertainty principle, TD-PSOLA synthesis, and SOLA cross-correlation |
| V | **Interactive Demo** | Live browser-based audio tools (see below) |
| VI | **Future** | Neural vocoders, polyphonic editing, on-device processing, formant-aware shifting, adaptive multi-resolution analysis, differentiable DSP |

---

## Interactive Features

The presentation includes three live audio tools built with the **Web Audio API**, requiring no server or external libraries:

### 🎹 Synthesizer & Pitch Shifter
- Generate sine, sawtooth, square, and triangle waveforms at any frequency
- Apply pitch shifting in semitones and fine-tuning in cents
- A/B comparison: hear original then shifted tone back-to-back
- Real-time waveform visualisation on canvas

### 🎤 Voice Recorder & Processor
- Record up to 10 seconds from your microphone
- Apply independent time-stretch (0.5×–2.0×) and pitch-shift (±12 semitones)
- Uses a granular overlap-add engine implemented in JavaScript
- Visual waveform display of recorded audio

### 📊 Live Spectrogram
- Scrolling real-time spectrogram from microphone input
- Frequency mapped vertically, time scrolling horizontally
- Colour intensity represents amplitude

> **Note:** Microphone features require HTTPS or `localhost` and browser permission.


---

## Technical Details

| Aspect | Detail |
|--------|--------|
| **File** | Single `index.html` (~900 lines) |
| **Fonts** | DM Serif Display, IBM Plex Mono, Source Sans 3 (Google Fonts CDN) |
| **Audio** | Web Audio API — `OscillatorNode`, `AnalyserNode`, `MediaRecorder`, `AudioBuffer` |
| **Visualisation** | HTML5 Canvas for waveforms and spectrogram |
| **CSS** | Custom properties, grid/flexbox layout, responsive breakpoints |
| **JavaScript** | Vanilla JS, no frameworks or libraries |
| **Granular Engine** | 40ms Hann-windowed grains, 25% hop ratio, linear interpolation resampling |

---

## Equation Reference

Each equation box can be expanded to reveal a symbol glossary. The seven equations covered are:

1. **STFT** — The Short-Time Fourier Transform decomposition
2. **Amplitude–Phase** — Polar form of complex spectral coefficients
3. **Phase Propagation** — The core phase vocoder time-stretching equations (phase unwrapping, instantaneous frequency estimation, synthesis phase accumulation)
4. **Overlap-Add Reconstruction** — Inverse STFT via windowed OLA
5. **Gabor Uncertainty** — The time–frequency resolution trade-off (Δf · Δt ≥ 1/4π)
6. **TD-PSOLA Synthesis** — Pitch-synchronous overlap-add with repositioned pitch marks
7. **SOLA Cross-Correlation** — Optimal overlap alignment via waveform matching

---

## Key References

- Flanagan, J.L. & Golden, R.M. (1966). *Phase vocoder.* Bell System Technical Journal.
- Portnoff, M.R. (1976). *Implementation of the digital phase vocoder using the FFT.* IEEE Trans. ASSP.
- Dolson, M. (1986). *The phase vocoder: a tutorial.* Computer Music Journal.
- Moulines, E. & Charpentier, F. (1990). *Pitch-synchronous waveform processing techniques for TTS using diphones.* Speech Communication.
- Laroche, J. & Dolson, M. (1999). *Improved phase vocoder time-scale modification of audio.* IEEE Trans. Speech and Audio Processing.
- Engel, J. et al. (2020). *DDSP: Differentiable Digital Signal Processing.* ICLR 2020.
- Hayes, B. et al. (2024). *A review of differentiable digital signal processing for music and speech synthesis.* Frontiers in Signal Processing.

---

## License

MIT — free to use, modify, and distribute.

---

<p align="center">
  <em>From magnetic tape to neural networks — the art and science of bending sound.</em>
</p>
