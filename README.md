🐱 kgwy-Kirara Proxy - 绮良良主题AI代理工具（开源完整版）
 
An open-source, cute-themed AI proxy tool inspired by Kirara (Genshin Impact’s cat-ear courier) — built for efficiency, packed with charm, and ready to "deliver" a seamless experience! 📦
 
🌟 Project Overview
 
This tool combines AI-powered UI hang detection and auto software switching with Kirara’s iconic pink-cat aesthetic. It’s lightweight (≤200MB runtime), compliant (no memory reading/game modification), and perfect for streamlining daily tasks — all while keeping the vibe fun and cozy.
 
🎨 Core Vibe: Kirara’s "courier spirit" → Every feature is framed as a "delivery task" (e.g., adding software = "creating a delivery slip", switching apps = "dropping off a package").
 
📂 Directory Structure
 
plaintext
  
kgwy-Kirara-Proxy/
├── assets/               # Kirara-themed resources (the cute stuff!)
│   ├── icons/            # Emojis, app icon, and UI graphics
│   │   ├── kirara_app.ico       # App icon (Kirara’s face) 🐱
│   │   ├── kirara_confused.gif  # For UI hang alerts 🤔
│   │   ├── kirara_delivery.gif  # For successful app switches 📦
│   │   └── kirara_stamp.png     # For saved configs ✅
│   ├── sounds/
│   │   └── kirara_meow.wav      # Meow sound for hotkeys 😺
│   └── ai_model/
│       └── ui_hang_model.tflite # Lightweight AI model (1.2MB)
├── config/
│   └── config.ini        # Customizable settings (theme, AI, hotkeys)
├── docs/                 # User guides + screenshots
│   ├── install_guide.md  # Step-by-step setup (with pics!)
│   └── screenshots/
│       ├── main_ui.png   # Main window (pink + Kirara emoji)
│       └── config_ui.png # Software setup page ("delivery slips")
├── scripts/              # One-click tools for devs
│   ├── build_windows.bat # Compile for Windows (MinGW)
│   └── package_inno.iss  # Create installer (Kirara-themed wizard)
├── src/                  # Core code (clean + commented)
│   ├── main.cpp          # App entry (loads theme + init)
│   ├── KiraraProxy.h/cpp # AI logic + app switching
│   ├── KiraraUI.h/cpp    # Pink UI + emoji rendering
│   └── AIDetector.h/cpp  # UI hang detection (TensorFlow Lite)
├── KiraraProxy.pro       # Qt project config (ready to build)
├── LICENSE               # MIT License (free to use/modify)
└── README.md             # You’re reading this! 😊
 
 
✨ Key Features (Kirara-Style!)
 
Feature What It Does Cute Twist 🐱 
AI UI Hang Detection Monitors apps for stuck interfaces (10s checks) using TensorFlow Lite. Shows Kirara’s confused GIF + "Package stuck! Restarting~" alert. 
Auto App Switching Cycles up to 4 apps (2 modes: Timer or Process Detection). Plays delivery GIF + "Next package delivered!" when switching. 
Kirara-Themed UI Soft pink palette, round buttons (like cat paws!), and dynamic emojis. UI scales with screen size (1080P/2K friendly). 
"Delivery Logs" Logs all events (starts, switches, hangs) with timestamps. Exportable as TXT. Logs named  Kirara_Courier_YYYYMMDD.txt  (cute archive!). 
Custom Hotkeys Quick controls for daily use (no mouse needed!). Plays meow sound when pressed (toggleable in config). 
 
Default Hotkeys
 
Action Hotkey 
Start Proxy  Ctrl + K  
Pause Proxy  Ctrl + P  
Exit Proxy  Ctrl + Q  
Open Logs  Ctrl + L  
 
🚀 Quick Start
 
1. Prerequisites
 
- OS: Windows 10/11 (32/64-bit; macOS/Linux coming soon!)
- Tools: Qt 5.15+ (with MinGW 8.1+), Python 3.9+ (for dependencies)
- Hardware: CPU supporting SSE4.2 (for TensorFlow Lite), ≥2GB RAM
 
2. Install
 
Option 1: Download Prebuilt Installer (Easiest!)
 
1. Go to the Releases Page
2. Download  KiraraProxy-Setup-v1.0.0.exe 
3. Run the installer → Follow Kirara’s pink-themed wizard (click "Next" 3x!)
4. Launch from desktop shortcut (Kirara’s icon 🐱)
 
Option 2: Build from Source (For Devs)
 
bash
  
# 1. Clone the repo
git clone https://github.com/kgwy/kgwy-Kirara-Proxy.git
cd kgwy-Kirara-Proxy

# 2. Install dependencies (Qt + Python libs)
# - Qt: Download from https://www.qt.io/download (select 5.15 + MinGW)
# - Python: Run `pip install -r src/requirements.txt`

# 3. Compile (Windows)
scripts/build_windows.bat

# 4. Launch the app
bin/kgwy-KiraraProxy.exe
 
 
3. Use the Tool (3 Simple Steps!)
 
1. Add "Delivery Slips" (Software)
- Open the app → Go to the 快递单配置 (Delivery Slips) tab
- Click 添加软件 (Add App) → Select an  .exe  file (e.g., WeChat, Chrome)
- Choose a mode:
- 🕒 Timer: Switch every X seconds (e.g., 300 = 5 mins)
- 🛠️ Process Detection: Switch when the app closes
- Click 保存配置 (Save Slip) (Kirara’s stamp icon pops up! ✅)
2. Start "Delivery" (Proxy)
- Click the 启动代理 (Start Delivery) button (or  Ctrl + K )
- Kirara’s delivery GIF plays → First app launches automatically
3. Check Logs (Optional)
- Go to the 快递日志 (Delivery Logs) tab to see timestamps for all actions
- Click 导出日志 (Export Logs) to save as a TXT file
 
🛠️ Tech Stack
 
Category Tools/Libraries 
Core Language C++ (Qt 5.15) 
AI & Computer Vision TensorFlow Lite 2.14 (UI hang detection), OpenCV 4.8.0 (screenshot checks) 
UI/UX Qt Widgets (pink theme), Pillow (emoji rendering) 
Automation PyAutoGUI (simulate inputs), psutil (process monitoring) 
Packaging Inno Setup 6 (installer), Git (version control) 
 
🤝 Contribute (Join the Courier Team!)
 
We’d love to have you help improve Kirara Proxy! Here’s how:
 
1. Report Bugs/Request Features
 
- Open an Issue
- For bugs: Add "🐛 Bug" in the title + steps to reproduce (e.g., "Kirara’s GIF doesn’t play on switch")
- For features: Add "✨ Feature" + your idea (e.g., "Add Kirara’s voice lines for alerts")
 
2. Submit Code
 
1. Fork this repo → Create a branch:  git checkout -b feature/kirara-voice 
2. Write code (keep it consistent with the pink-cat theme!)
3. Commit:  git commit -m "Add Kirara voice line for success alerts" 
4. Push:  git push origin feature/kirara-voice  → Open a Pull Request
 
3. Design Contributions
 
- Help update emojis/GIFs (Kirara’s expressions!)
- Improve the installer’s pink theme
- Add translation (e.g., English/Japanese for global users)
 
❤️ Support the Project
 
Building cute, useful tools takes time — your support keeps Kirara delivering!
 
Way to Support Link/Action 
Star the Repo Click the ⭐ button at the top of the GitHub page 
Sponsor Me GitHub Sponsors (exclusive perks!) 
Buy a Coffee Ko-fi (Kirara gets a fish snack! 🐟) 
Share with Friends Post about it on Genshin communities/Reddit (tag #KiraraProxy) 
 
Sponsor Perks
 
- 🐱 Rice Ball Supporter ($5/month): Exclusive Discord access + weekly "Kirara’s Courier Diary"
- 📦 Pro Courier ($20/month): Priority bug fixes (24h response) + custom Kirara emoji
- 🌟 Enterprise Partner ($100/month): Dedicated support + your logo on the README
 
📜 License
 
This project is licensed under the MIT License — you can:
 
- Use it for personal/commercial purposes
- Modify the code (keep Kirara’s theme intact!)
- Distribute it (include the original LICENSE file)
 
See LICENSE for full details.
 
📬 Contact
 
- GitHub: @kgwy (DM me anytime!)
- Discord: kgwy#1234 (Join the "Kirara’s Courier Hub" server!)
- Email: kgwy.dev@example.com (For business collaborations)
 
"只要是承诺过的快递，就一定会送到哦～" — Kirara 🐱📦
Thanks for using Kirara Proxy! Let’s make daily tasks cuter, one "delivery" at a time.
