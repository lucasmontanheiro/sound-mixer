# Project Context: Sound Mixer (PRO)

This file provides context and technical details for AI agents working on the Sound Mixer Pro project.

## Project Overview
The **Sound Mixer Pro** is a high-fidelity, mobile-first web application designed for musicians (specifically guitarists) to record live performances over backing tracks. It features a "DAW-inspired" dark interface, real-time VU metering, and a seamless "Jam Zone" workflow.

## Technical Architecture
Built with standard web technologies (HTML/JS/Tailwind CSS), leveraging the **Web Audio API** for low-latency signal processing.

### Audio Graph & Routing
1.  **Microphone Input**: Captured via `getUserMedia` with `echoCancellation` disabled for raw instrument fidelity.
2.  **Backing Track**: High-quality MP3/WAV playback via `<audio>` element.
3.  **Gain Nodes**: 
    *   `micGainNode`: Default 2.00 (adjustable 0-5).
    *   `backingGainNode`: Default 0.60 (adjustable 0-2).
4.  **Monitoring System**: A dedicated `monitorGain` node allows "Mute Monitoring" (enabled by default) to prevent feedback when not using headphones.
5.  **Recording Path**: A central `mixBus` merges both signals into a `MediaStreamDestination` for the `MediaRecorder`.
6.  **Visual Feedback**: An `AnalyserNode` calculates RMS levels in real-time, driving a "No-Squint" high-visibility VU meter.

## Key UI Components (index.html)
- **The Jam Zone**: A prominent, pulsing record button designed for visibility from a distance (e.g., on a music stand).
- **Track Carousel**: A horizontal selector for built-in backing tracks and custom file uploads.
- **Results Modal**: A high-impact overlay that "pops" upon recording completion, providing instant playback and sharing/download options.
- **Mixer Console**: Thumb-friendly sliders for balancing levels.

## Styling & Design
- **Framework**: Tailwind CSS.
- **Icons**: Lucide-react (Lucide-JS).
- **Palette**: Charcoal/Slate with "Electric Orange" action accents.
- **Design Pillar**: "No-Squint" Rule — high-visibility states and large touch targets for musicians.

## Current Catalog
The app includes a curated list of backing tracks spanning Blues, Jazz, Indie Folk, Neo-Soul, Funk, and Rock.
