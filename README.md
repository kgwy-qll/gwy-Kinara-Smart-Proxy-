Thanks for using Kirara Proxy! Let’s make daily tasks cuter, one "delivery" at a time.
markdown
  
# 🐱 kgwy-Kirara Proxy - 绮良良主题AI代理工具（基于DGA砂糖代理框架）
An open-source, hyper-cute AI proxy tool inspired by **Genshin Impact’s Kirara** — built on the [DGA Sugar Proxy Framework](https://github.com/your-dga-sugar-repo) (with clear attribution!) and packed with cat-ear charm that pops! 📦✨


## 📢 Core Attribution & Sponsor
- **Based On**: [DGA Sugar Proxy Framework](https://github.com/your-dga-sugar-repo) 🧩  
  *Full respect to the original DGA Sugar Proxy project — this tool extends its core proxy logic with Kirara-themed UI/AI features, following open-source collaboration norms.*  
- **Exclusive Sponsor**: [@kgwy](https://github.com/kgwy) 🐾  
  *This project is made possible by kgwy’s support — from AI model optimization to Kirara asset design, every cute detail has their touch!*


## 🌟 Project Overview
This tool wraps **DGA Sugar Proxy’s stable proxy core** with Kirara’s iconic pink-cat vibe, adding AI-powered UI hang detection and dynamic emoji feedback. It’s:  
- 🚀 **Efficient**: Auto-switch 4 apps + real-time stuck detection (10s interval)  
- 🎨 **Cute**: Every button, alert, and log is Kirara-themed (paw-shaped corners! Meow sounds! 😺)  
- 📜 **Compliant**: No memory reading/game modification — strictly follows DGA Sugar Proxy’s open-source protocol  
- 🔗 **Linked**: Fully inherits DGA Sugar Proxy’s cross-software compatibility (supports Windows 10/11)  


## 📂 Directory Structure (Aligned with DGA Sugar Proxy)
 
 
kgwy-Kirara-Proxy/
├── assets/               # Kirara’s cute assets (emojis/sounds) 🐱
│   ├── icons/
│   │   ├── kirara_app.ico       # App icon (Kirara’s face!)
│   │   ├── kirara_confused.gif  # UI hang alert 🤔
│   │   ├── kirara_delivery.gif  # App switch success 📦
│   │   └── kirara_stamp.png     # Config save ✅
│   └── sounds/
│       └── kirara_meow.wav      # Hotkey meow 😻
├── config/
│   ├── config.ini        # Kirara theme + DGA core settings 🛠️
│   └── sugar_proxy.cfg   # Inherited DGA Sugar Proxy config (unchanged!)
├── src/
│   ├── core/             # DGA Sugar Proxy core (forked & attributed) 🧩
│   │   └── sugar_proxy.cpp      # Original DGA proxy logic
│   ├── kirara/           # Custom Kirara features (new code!) 🐾
│   │   ├── KiraraUI.cpp          # Pink-themed UI
│   │   ├── AIDetector.cpp        # AI hang detection
│   │   └── EmojiManager.cpp      # Dynamic emoji rendering
│   └── main.cpp          # Entry (DGA core + Kirara UI integration)
├── scripts/
│   ├── build_windows.bat # One-click compile (supports DGA dependencies)
│   └── package_innosetup.iss     # Kirara-themed installer 📦
├── KiraraProxy.pro       # Qt project (includes DGA Sugar Proxy paths)
├── LICENSE               # MIT License (same as DGA Sugar Proxy)
├── ATTRIBUTION.md        # Full DGA Sugar Proxy attribution doc 📜
└── README.md             # You’re here! 😊
 
plaintext
  


## ✨ Key Features (DGA Core + Kirara Flair)
| Feature                  | DGA Sugar Proxy Base          | Kirara-Themed Upgrade                          | Cute Vibe 🐱 |
|--------------------------|--------------------------------|------------------------------------------------|--------------|
| Multi-App Proxy          | Supports 4-app switching       | "Delivery slip" UI (add apps = "create slips") | 📦 Add button = "New delivery" |
| Process Monitoring       | Tracks app runtime             | AI hang detection (TensorFlow Lite)            | 🤔 Stuck alert = "Package jammed!" |
| Config Persistence       | Saves proxy settings           | Kirara stamp icon + "Slip archived" prompt     | ✅ Save = "Stamp the slip!" |
| Hotkey Control           | Basic start/pause              | Custom meow sounds + emoji feedback            | 😻 `Ctrl+K` = "Kirara出发!" |
| Log Management           | Text-based logs                | "Delivery logs" (Kirara-named files: `Kirara_Courier_YYYYMMDD.txt`) | 📜 Logs = "Courier diary" |


## 🚀 Quick Start (Inherits DGA Sugar Proxy Workflow)
### 1. Prerequisites
- Same as DGA Sugar Proxy: Windows 10/11, Qt 5.15+ (MinGW 8.1+), Python 3.9+  
- Extra for Kirara features: TensorFlow Lite 2.14 (included in `assets/ai_model/`)


### 2. Install (2 Options)
#### Option 1: Prebuilt Installer (Easiest!)
1. Go to [Releases](https://github.com/kgwy/kgwy-Kirara-Proxy/releases)  
2. Download `KiraraProxy-Setup-v1.0.0.exe` (Kirara’s pink installer! 🎀)  
3. Follow prompts → Check "Include DGA Sugar Proxy core files" (auto-enabled)  
4. Launch from desktop (Kirara’s icon 🐱)


#### Option 2: Build from Source (With DGA Core)
```bash
# 1. Clone THIS repo + DGA Sugar Proxy repo (required for core!)
git clone https://github.com/kgwy/kgwy-Kirara-Proxy.git
git clone https://github.com/your-dga-sugar-repo.git dga-sugar-proxy

# 2. Link DGA core to our project
cp -r dga-sugar-repo/src/core kgwy-Kirara-Proxy/src/core

# 3. Install dependencies (DGA + Kirara)
pip install -r kgwy-Kirara-Proxy/src/requirements.txt

# 4. Compile (Windows)
cd kgwy-Kirara-Proxy
scripts/build_windows.bat

# 5. Launch (DGA core loads automatically!)
bin/kgwy-KiraraProxy.exe
 
 
3. Use the Tool (3 Steps)
 
1. Add "Delivery Slips" (Apps)
- Open app → Go to 快递单配置 (Delivery Slips) tab
- Click 📦 添加软件 (New Slip) → Select  .exe  (e.g., WeChat)
- Choose mode (Timer/Process Detection) → Click ✅ 保存 (Stamp Slip)
2. Start "Delivery" (Proxy)
- Press  Ctrl+K  or click 🚀 启动 (Kirara出发!)
- Kirara’s delivery GIF plays → DGA core launches first app
3. Check "Courier Logs"
- Go to 📜 快递日志 (Logs) tab → Export as TXT (named with Kirara!)
 
🧩 DGA Sugar Proxy Attribution
 
This project directly uses and extends the DGA Sugar Proxy Framework:
 
- Core proxy logic: Forked from  dga-sugar-repo/src/core/sugar_proxy.cpp 
- Process monitoring: Inherits  dga-sugar-repo/src/utils/process_monitor.h 
- License: Follows DGA Sugar Proxy’s MIT License (see ATTRIBUTION.md for full details)
- For original features/bugs: Visit the DGA Sugar Proxy GitHub
 
❤️ Support & Sponsor
 
Sponsor: @kgwy 🐾
 
- Why Sponsor? Funds go to Kirara asset updates (new GIFs/sounds) and DGA core compatibility fixes
- Sponsor Perks:
- 🐟 Rice Ball Tier ($5/month): Exclusive Kirara emojis + Discord access
- 📦 Courier Tier ($20/month): Priority support (24h response) + custom UI themes
- 🌟 Boss Tier ($100/month): Name in "Sponsor Wall" + co-design new Kirara features
 
Support the Project
 
1. Star THIS repo ⭐ + Star DGA Sugar Proxy (support the original!)
2. Share on Genshin communities: Tag #KiraraProxy #DGASugarProxy
3. Report bugs: Open Issues (add 🐛 in title!)
 
📜 License
 
- This project: MIT License (same as DGA Sugar Proxy)
- DGA Sugar Proxy: See their LICENSE
- Kirara assets: For non-commercial use (Genshin Impact fan work — respect miHoYo’s IP!)
 
📬 Contact
 
- Kirara Proxy Dev: @kgwy (DM for feature requests!)
- DGA Sugar Proxy Dev: Visit their GitHub
- Discord: Join "Kirara’s Courier Hub" (link in Releases!)
 
"只要是承诺过的快递，就一定会送到哦～" — Kirara 🐱📦
Built with love for Kirara, and respect for DGA Sugar Proxy’s open-source work!
