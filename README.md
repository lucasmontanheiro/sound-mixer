# Sound Mixer Pro 🎸

A minimalist, high-performance web DAW designed for guitarists and vocalists to jam and record over backing tracks instantly.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Version](https://img.shields.io/badge/version-2.0.0-orange.svg)

## Features

- **High-Fidelity Recording**: Record your voice or instrument over studio-quality backing tracks.
- **DAW-Inspired Interface**: A sleek, high-contrast dark mode designed for visibility on music stands.
- **Live Mixer**: Independent gain controls for your microphone and the backing track.
- **No-Squint VU Meter**: Professional-grade level monitoring to prevent clipping.
- **Zero Friction**: No setup required. Pick a track, hit the glowing record button, and jam.
- **Instant Sharing**: Download your mix immediately after your take.
- **Custom Tracks**: Support for uploading your own MP3/WAV backing files.

## How to Use

1.  **Select a Track**: Browse the carousel or upload your own backing track.
2.  **Check Levels**: Adjust the Microphone and Backing sliders. Ensure the VU meter stays out of the red.
3.  **Jam**: Hit the large Orange button to start recording. It will pulse Red while active.
4.  **Review**: Hit Stop to "pop" the results modal. Listen back and download your take.

> **Tip**: Use headphones to prevent the backing track from bleeding into your microphone recording!

## Technology Stack

- **Frontend**: HTML5, Tailwind CSS
- **Icons**: Lucide
- **Audio Engine**: Web Audio API
- **Recording**: MediaRecorder API (Opus/WebM)

## Development

To run locally, simply serve the directory using any local web server:

```bash
# Example using Python
python3 -m http.server 8000
```

*Note: Microphone access requires HTTPS or localhost.*
