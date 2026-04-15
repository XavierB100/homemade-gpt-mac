# 🤖 HomeMade GPT — macOS Edition

A custom GPT you can train on your own text data (books, WhatsApp chats, notes — anything!) and chat with locally. This is the macOS-native port of the original [homemade-gpt](https://github.com/XavierB100/homemade-gpt), rebuilt for Apple Silicon.

> **Runs entirely on your Mac — no internet, no API keys, no cost.**

---

## ✨ What's different in this Mac version?

| Feature | Windows original | macOS edition |
|---------|-----------------|---------------|
| GPU acceleration | NVIDIA CUDA | **Apple MPS (Metal)** |
| Launcher | `.bat` file | `.command` (double-click) |
| Desktop shortcut | PowerShell `.ps1` | `create_mac_app.sh` |
| Recommended hardware | Any Windows PC | M1/M2/M3/M4 Mac |

---

## 🚀 Quick Start

### 1. Install Python dependencies

Open Terminal in this folder and run:

```bash
pip3 install -r requirements.txt
```

> **Tip:** Use a virtual environment for a cleaner setup:
> ```bash
> python3 -m venv .venv
> source .venv/bin/activate
> pip install -r requirements.txt
> ```

### 2. Launch the app

**Option A — Double-click (easiest):**
- Double-click `HomeMade_GPT.command` in Finder
- If macOS blocks it: right-click → Open → Open

**Option B — Terminal:**
```bash
python3 desktop_launcher.py
```

The app opens at **http://127.0.0.1:5000** in your browser automatically.

---

## 🖥️ Create a Dock / Desktop App Icon

Run this once to get a clickable `.app` on your Desktop (drag it to your Dock!):

```bash
bash create_mac_app.sh
```

> First launch: right-click → Open → Open to bypass Gatekeeper once.

---

## 📖 How to train your own model

1. Open the app and go to the **Train** tab
2. Upload a `.txt` file (book, chat log, anything)
3. Pick a model size (start with `tiny` or `small`)
4. Hit **Start Training** and watch it go!

On Apple Silicon your M1/M2/M3 Mac will automatically use the **Metal GPU** — training that took hours on older hardware takes minutes here.

---

## 💬 Chatting with your model

1. Go to the **Chat** tab
2. Select your trained model from the dropdown
3. Start chatting!

---

## 📦 Requirements

- macOS 12 Monterey or later
- Python 3.9+
- PyTorch ≥ 2.0 (with MPS support built-in)

---

## 🗂️ Project Structure

```
homemade-gpt-mac/
├── web_app.py              # Flask web application
├── desktop_launcher.py     # App launcher with signal handling
├── HomeMade_GPT.command    # 🍎 macOS double-click launcher
├── create_mac_app.sh       # 🍎 Creates a .app bundle for Dock
├── requirements.txt        # Python dependencies
├── src/
│   ├── models/
│   │   └── enhanced_gpt.py     # GPT model architecture
│   ├── training/
│   │   ├── train.py            # Training loop
│   │   └── data_loader.py      # Data processing
│   └── chat/
│       └── chat.py             # Chat interface
├── templates/              # HTML templates
├── data/                   # Training data
└── models/                 # Saved model checkpoints
```

---

## 🔗 Original Project

Based on [homemade-gpt](https://github.com/XavierB100/homemade-gpt) — originally built on Windows.

---

*Made with ❤️ by Xavier Blake*
