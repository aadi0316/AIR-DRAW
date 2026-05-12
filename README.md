# ✋ Air Draw — Gesture-Powered Paint App

> Draw in the air with your finger. No mouse. No stylus. Just your hand and a webcam.

---

## 🎨 What is This?

**Air Draw** is a real-time, hand-gesture-controlled painting application. Using your webcam, it tracks your index finger via [MediaPipe](https://mediapipe.dev/) and lets you paint on a virtual canvas — no physical input device needed.

Point your finger → draw. Pinch your fingers together → lift the pen. Hover over a color button → switch colors. It's that simple.

---

## 🖼️ Demo

```
┌────────────────────────────────────────────┐
│ [CLEAR] [BLUE] [GREEN] [RED] [YELLOW]      │  ← UI Toolbar (top of webcam feed)
│                                            │
│         (your webcam feed here)            │
│     ✦ hand landmarks drawn in real-time    │
│                                            │
└────────────────────────────────────────────┘

Separate "Paint" window shows your clean canvas drawing.
```

---

## 🚀 Features

- 🖐️ **Real-time hand tracking** using MediaPipe (single hand, 21 landmarks)
- 🎨 **4 paint colors** — Blue, Green, Red, Yellow
- ✏️ **Lift-pen gesture** — pinch thumb and index finger to stop drawing
- 🗑️ **Clear button** — hover your finger to wipe the canvas instantly
- 🪟 **Dual window output** — live webcam view + clean paint canvas side by side
- 💾 **Stroke memory** — uses deques to efficiently store and replay strokes

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| `OpenCV` | Webcam capture, drawing, window rendering |
| `MediaPipe` | Hand landmark detection |
| `NumPy` | Canvas array manipulation |
| `collections.deque` | Efficient stroke point storage |

---

## 📦 Installation

### 1. Clone the repo

```bash
git clone https://github.com/aadi0316/AIR-DRAW.git
cd air-draw
```

### 2. Install dependencies

```bash
pip install opencv-python mediapipe numpy
```

> **Python 3.7–3.10** is recommended for best MediaPipe compatibility.

---

## ▶️ Usage

```bash
python air_draw.py
```

Two windows will open:
- **Output** — your webcam feed with hand landmarks overlaid
- **Paint** — the clean drawing canvas

Press **`Q`** to quit.

---

## 🤚 Gesture Guide

| Gesture | Action |
|---------|--------|
| ☝️ Index finger extended | Draw on canvas |
| 🤏 Thumb + index finger close together (`< 30px`) | Lift pen (stop drawing) |
| ☝️ Hover over **CLEAR** button (top bar) | Erase entire canvas |
| ☝️ Hover over **BLUE / GREEN / RED / YELLOW** | Switch active color |

---

## 📁 Project Structure

```
air-draw/
│
├── Air_Draw_ml.py       # Main application script
└── README.md
```

---

## ⚙️ Configuration

You can tweak these constants near the top of `air_draw.py`:

| Variable | Default | Description |
|----------|---------|-------------|
| `max_num_hands` | `1` | Max hands to track |
| `min_detection_confidence` | `0.7` | Hand detection threshold |
| `kernel` | `5×5` | Dilation kernel (unused, reserved) |
| Deque `maxlen` | `1024 / 512` | Max points stored per stroke |

---

## 🐛 Known Issues & Limitations

- Works best in **good lighting** conditions
- Detection may be unreliable if the **hand is partially out of frame**
- Only tracks **one hand** at a time
- Canvas size is hardcoded to `471×636` — resize in the source if needed

---

## 🔮 Potential Improvements

- [ ] Save canvas as image (`S` key to screenshot)
- [ ] Adjustable brush size via gesture
- [ ] Eraser tool
- [ ] Multi-hand support
- [ ] Background removal for cleaner UI

---

## 🙌 Acknowledgements

- [MediaPipe by Google](https://mediapipe.dev/) for the hand tracking solution
- [OpenCV](https://opencv.org/) for computer vision utilities

---

## 📄 Contact

For questions or suggestions, feel free to contact:

- **Name**: Aditya Rana
- **Email**: .
- **LinkedIn**: [Aditya Rana](https://www.linkedin.com/in/aditya-rana-7490a7366/)

Happy Drawing! 🎨 
