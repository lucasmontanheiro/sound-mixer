# Project Context: Sound Mixer

This file provides context and technical details for AI agents (like Gemini) working on this project.

## Project Overview
The **Sound Mixer** is a minimalist web application that allows users to record their voice (or any microphone input) over a backing track. It mixes the two sources in real-time, provides level controls, and allows downloading the final mixed recording.

## Technical Architecture
The application is built using standard web technologies and leverages the **Web Audio API** for signal routing and processing.

### Audio Graph
The audio signal flow is as follows:
1.  **Microphone Input**: Captured via `navigator.mediaDevices.getUserMedia`.
2.  **Backing Track**: Loaded via an `<audio>` element.
3.  **Gain Nodes**: Independent `micGainNode` and `backingGainNode` allow real-time volume adjustment via UI sliders.
4.  **Mix Bus**: A central `GainNode` where both signals are merged.
5.  **Master Gain**: Final volume control before output (hardcoded to 0.9 for headroom).
6.  **Outputs**:
    *   **Speakers**: Connected to `audioCtx.destination` for monitoring.
    *   **Analyser**: Used for the VU meter visualization.
    *   **MediaStreamDestination**: Captures the mixed stream for the `MediaRecorder`.

## Key Components (index.html)
- **UI**: Simple controls for Start/Stop, Mic Level, Backing Level, and a VU Meter.
- **`start()` Function**: Initializes the `AudioContext`, sets up the nodes, starts the backing track, and begins recording.
- **`stop()` Function**: Stops recording, closes the `AudioContext`, and cleans up stream tracks.
- **VU Meter**: A `requestAnimationFrame` loop that calculates RMS (Root Mean Square) from the analyser data to update the `<meter>` element.

## Development & Usage
- **Requirement**: Must be served over `localhost` or HTTPS for microphone access.
- **Headphones Recommended**: To prevent feedback/loopback from the backing track into the microphone.

## Future Enhancements (TODO)
- Support for uploading custom backing tracks.
- Waveform visualization for the recorded result.
- Effects processing (e.g., reverb or compression) for the microphone input.
