# Sound Mixer

A minimalist, high-fidelity web application for recording voice or instruments over backing tracks. Built with the Web Audio API for real-time mixing and low-latency monitoring.

## 🎧 Features

- **Real-time Mixing**: Blend microphone input with high-quality backing tracks.
- **Record Cover UI**: Intuitive, swipeable interface for selecting backing tracks styled as classic vinyl records.
- **Live Monitoring**: VU Meter for visual level monitoring to prevent clipping.
- **Independent Gain Controls**: Fine-tune Mic and Backing levels via a collapsible settings panel.
- **Instant Download**: Exports your mix as a high-quality audio file (WebM/OGG) immediately after recording.
- **Local Audio Support**: Automatically pulls backing tracks from the local `/audio` directory.

## 🛠 Technical Stack

- **Web Audio API**: Handles the complex signal routing, gain nodes, and real-time analysis.
- **MediaRecorder API**: Captures the mixed audio stream for export.
- **CSS Grid/Flexbox**: Responsive, mobile-first design with modern aesthetics.

## 🚀 Getting Started

### Requirements
- **Secure Context**: Due to microphone security policies, this app must be served over `localhost` or `HTTPS`.
- **Headphones Recommended**: To prevent feedback/loopback from the backing track into your microphone.

### Setup
1. Clone the repository.
2. Ensure your backing tracks are in the `audio/` folder.
3. Serve the directory using a local server:
   ```bash
   # Using Python
   python3 -m http.server 8000
   
   # Using Node.js
   npx serve .
   ```
4. Open `http://localhost:8000` in your browser.

## 🎛 How to Use
1. **Select a Track**: Swipe through the record covers and tap to select your backing track.
2. **Adjust Levels**: Expand "Levels & Settings" to calibrate your microphone gain.
3. **Record**: Hit **Start Recording**. The backing track will play automatically.
4. **Stop & Save**: Hit **Stop**. Your mixed recording will appear below for playback and download.

---
*Created for musicians and creators who need a simple, no-fuss recording setup.*
