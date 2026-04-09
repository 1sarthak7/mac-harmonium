# Mac Harmonium

A premium web-based virtual harmonium that uses your MacBook's lid angle (or your Spacebar) to control the bellows (air pressure). Press keys and pump the bellows to play!

Created by [@1sarthak7](https://github.com/1sarthak7/mac-harmonium)

-Touch Support**: Play using your mouse, keyboard, or touch screen.

## Requirements

- Python 3.7+
- macOS (for hardware lid sensor)
- `websockets` library
- `pybooklid` library (for MacBook lid sensor)
- A modern web browser (Chrome, Firefox, Safari)

## Installation

1. **Set up a virtual environment** (recommended):
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```

2. **Install required Python packages**:
   ```bash
   pip install websockets pybooklid
   ```

## Getting Started

### Step 1: Start the Backend (Lid Sensor)

First, run the Python WebSocket server that reads your laptop's lid angle:

```bash
python harmonium.py
```

*Note: If you do not have a MacBook or don't want to use the lid sensor, you can skip this step and just use the Spacebar to pump the bellows.*

### Step 2: Open the Web UI

Because modern browsers block web audio from local files by default, it is highly recommended to serve the HTML file over a local HTTP server:

```bash
python3 -m http.server 8080
```

Then, open your browser and navigate to: [http://localhost:8080/harmonium.html](http://localhost:8080/harmonium.html)

### Step 3: Play!

1. **Activate Audio**: Click anywhere on the dashboard. You will see the text "Audio Active".
2. **Pump Air**: 
   - *Option A*: Press the **Spacebar** repeatedly to fill the gold air pressure gauge.
   - *Option B*: Push your MacBook lid down to manually pump the bellows.
3. **Play Notes**: Press and hold any of the mapped keys while there is air in the gauge to play sound!

## Key Mapping

```
White Keys (Natural Notes):
A = C
S = D
D = E
F = F
G = G
H = A
J = B
K = C (octave)

Black Keys (Sharps):
W = C#
E = D#
T = F#
Y = G#
U = A#
```

## Troubleshooting

**No sound?**
- Make sure you clicked on the page first so the browser allows audio to play.
- You **must** pump the bellows (Spacebar or lid) before pressing a key; if the gold gauge is empty, the volume is zero!

**"Address already in use" Error on Step 1?**
- This means `harmonium.py` is already running in the background. You don't need to start it again.

## Stopping

- **Backend**: Press `Ctrl+C` in the terminal to stop `harmonium.py` or the `http.server`.
- **Frontend**: Simply close the browser tab.

## License

Feel free to use and modify this project as you wish!

<br/>

<br/>


<div align="center">

Built with precision by [Sarthak Bhopale](https://github.com/1sarthak7).


</div
