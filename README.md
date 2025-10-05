Buimarkdown
  
# 🐱 kgwy-Kirara Proxy - 绮良良主题AI代理工具（基于[SucroseGameAssistant](https://github.com/Kin-L/SucroseGameAssistant)框架开发）
An open-source, hyper-cute AI proxy tool inspired by **Genshin Impact’s Kirara** — deeply built on the [SucroseGameAssistant](https://github.com/Kin-L/SucroseGameAssistant) framework (full attribution + direct link!) and packed with cat-ear charm that pops right off the screen! 📦✨


## 📢 核心归因 & 独家赞助商
### 🔗 基于框架：[SucroseGameAssistant](https://github.com/Kin-L/SucroseGameAssistant)
本项目**完全继承并扩展**了SucroseGameAssistant的核心能力——包括跨软件代理调度、轻量化进程监控、配置持久化等基础模块，所有原框架代码均保留清晰来源标注，严格遵循其开源协议。  
> 👉 强烈建议访问原框架仓库，给[SucroseGameAssistant](https://github.com/Kin-L/SucroseGameAssistant)点个Star！正是它的稳定基础，让绮良良主题的功能落地成为可能～

### 🐾 独家赞助商：[kgwy](https://github.com/kgwy)
从绮良良表情包设计、AI卡死检测模型优化，到适配SucroseGameAssistant框架的兼容性开发，均由kgwy全程支持。项目的每一处可爱细节与功能迭代，都离不开这份助力！


## 🌟 项目概述
本工具在SucroseGameAssistant的“实用代理核心”上，裹上了一层“绮良良专属糖衣”——既保留原框架对Windows 10/11的完美适配、低内存占用（≤200MB）、无侵入式操作（不读内存/不改文件）的优势，又新增：  
- 😺 **全场景绮良良交互**：从启动动画到错误提示，每一步都有动态表情包+猫咪音效  
- 🧠 **AI UI卡死检测**：基于TensorFlow Lite的轻量模型，10秒内识别软件卡住并自动重启  
- 📦 **“快递单”式配置**：将添加软件转化为“填写快递单”，操作逻辑更贴近绮良良“信使”设定  


## 📂 目录结构（与SucroseGameAssistant框架对齐）
 
 
kgwy-Kirara-Proxy/
├── assets/               # 绮良良专属可爱资源 🐱
│   ├── icons/
│   │   ├── kirara_app.ico       # 软件图标（绮良良头像）
│   │   ├── kirara_confused.gif  # 卡死提示表情包 🤔
│   │   ├── kirara_delivery.gif  # 切换成功表情包 📦
│   │   └── kirara_stamp.png     # 配置保存图标 ✅
│   └── sounds/
│       └── kirara_meow.wav      # 快捷键猫咪音效 😻
├── config/
│   ├── kirara_config.ini # 绮良良主题配置（表情包路径/音效开关）
│   └── sucrose_core.cfg  # 继承自SucroseGameAssistant的核心配置（未修改！）
├── src/
│   ├── sucrose_core/     # 直接继承自SucroseGameAssistant的核心模块 🔗
│   │   ├── proxy_scheduler.cpp  # 原框架的代理调度逻辑
│   │   └── process_monitor.cpp  # 原框架的进程监控工具
│   ├── kirara_ext/       # 绮良良主题扩展功能（新增代码）🐾
│   │   ├── KiraraUI.cpp          # 粉色猫咪风UI实现
│   │   ├── AIDetector.cpp        # AI卡死检测模块
│   │   └── EmojiManager.cpp      # 动态表情包渲染
│   └── main.cpp          # 入口：整合Sucrose核心与绮良良扩展
├── scripts/
│   ├── build_windows.bat # 一键编译脚本（兼容Sucrose框架依赖）
│   └── kirara_installer.iss      # 绮良良主题安装向导 📦
├── KiraraProxy.pro       # Qt项目配置（已包含SucroseCore路径）
├── LICENSE               # MIT协议（与SucroseGameAssistant一致）
├── ATTRIBUTION.md        # 详细归因文档（含Sucrose框架代码来源）
└── README.md             # 你正在阅读的可爱指南～ 😊
 
plaintext
  


## ✨ 核心功能（Sucrose基础 + 绮良良升级）
| 功能模块                | SucroseGameAssistant原框架能力       | 绮良良主题专属升级                          | 可爱指数 🐱 |
|-------------------------|---------------------------------------|---------------------------------------------|-------------|
| 多软件代理调度          | 支持4款软件切换，可选“定时/进程检测”模式 | 将“添加软件”改为“填写快递单”，切换成功弹出📦动画+“快递送达啦～”提示 | ⭐⭐⭐⭐⭐ |
| 进程监控                | 实时追踪软件运行状态，异常时重启       | 检测到卡死时显示🤔表情包+“快递卡住啦！重启ing”文字，播放委屈猫咪叫 | ⭐⭐⭐⭐⭐ |
| 配置持久化              | 保存软件路径/切换模式，下次启动自动加载 | 保存配置时弹出✅绮良良盖章动画，配置文件命名为`Kirara_Courier_Slip.ini` | ⭐⭐⭐⭐ |
| 快捷键控制              | 基础启动/暂停/退出快捷键              | 快捷键按下播放😻猫咪音效，悬浮提示带绮良良头像（默认：Ctrl+K启动/ Ctrl+P暂停） | ⭐⭐⭐⭐ |
| 日志管理                | 文本形式记录操作日志                  | 日志命名为`Kirara_Courier_Diary_YYYYMMDD.txt`，每行前缀带🐾符号 | ⭐⭐⭐⭐ |


## 🚀 快速开始（兼容Sucrose框架依赖）
### 1. 前置条件
- 系统：Windows 10/11（32/64位，与SucroseGameAssistant一致）  
- 工具：Qt 5.15+（带MinGW 8.1+编译器）、Python 3.9+（安装Sucrose框架依赖）  
- 额外：TensorFlow Lite 2.14（已打包在`assets/ai_model/`，无需额外下载）  


### 2. 安装方式（2种可选）
#### 方式1：下载预编译安装包（小白首选！）
1. 进入本项目[Releases页面](https://github.com/kgwy/kgwy-Kirara-Proxy/releases)  
2. 下载`KiraraProxy-Setup-v1.0.0.exe`（绮良良粉色安装向导！🎀）  
3. 双击安装 → 全程点击“下一步”（默认包含Sucrose核心依赖）  
4. 从桌面双击🐱图标启动工具  


#### 方式2：源码编译（需关联Sucrose框架）
```bash
# 1. 克隆本项目 + SucroseGameAssistant框架（必须！）
git clone https://github.com/kgwy/kgwy-Kirara-Proxy.git
git clone https://github.com/Kin-L/SucroseGameAssistant.git  # 克隆原框架

# 2. 将Sucrose核心模块复制到本项目（保持路径对齐）
cp -r SucroseGameAssistant/src/core kgwy-Kirara-Proxy/src/sucrose_core

# 3. 安装依赖（含Sucrose框架依赖 + 绮良良扩展依赖）
cd kgwy-Kirara-Proxy
pip install -r src/requirements.txt

# 4. 编译项目（Windows）
scripts/build_windows.bat

# 5. 启动工具（Sucrose核心会自动加载）
bin/kgwy-KiraraProxy.exe
 
 
3. 3步上手“绮良良快递”
 
1. 填写“快递单”（添加软件）
- 打开工具 → 切换到「快递单配置」tab
- 点击📦「添加快递单」→ 选择软件.exe文件（如微信/Chrome）
- 选择切换模式（🕒定时/🛠️进程检测）→ 点击✅「盖章保存」
2. 启动“快递派送”（开启代理）
- 按下 Ctrl+K 或点击🐱「绮良良出发！」按钮
- 看到📦动画+“第一份快递出发啦～”提示，代表工具已启动
3. 查看“快递日记”（日志）
- 切换到「快递日记」tab → 所有操作（启动/切换/重启）都带🐾前缀
- 点击「导出日记」可保存为TXT文件（纪念每一次“派送”～）
 
🧩 SucroseGameAssistant框架详细归因
 
本项目直接使用/修改的Sucrose框架模块如下，所有代码均保留原作者版权信息：
 
模块路径 用途 原框架来源链接 
 src/sucrose_core/proxy_scheduler.cpp  核心代理调度逻辑 https://github.com/Kin-L/SucroseGameAssistant/blob/main/src/core/proxy_scheduler.cpp 
 src/sucrose_core/process_monitor.cpp  进程监控与异常重启 https://github.com/Kin-L/SucroseGameAssistant/blob/main/src/core/process_monitor.cpp 
 config/sucrose_core.cfg  基础代理配置模板 https://github.com/Kin-L/SucroseGameAssistant/blob/main/config/core.cfg 
 
若需修改Sucrose核心逻辑，建议先参考原框架文档，避免破坏兼容性～
 
❤️ 支持与赞助
 
1. 支持本项目 & 原框架
 
- 给本项目点⭐：kgwy/kgwy-Kirara-Proxy
- 给原框架点⭐：Kin-L/SucroseGameAssistant（至关重要！）
- 分享：在原神社区/小红书发笔记，带话题#绮良良代理 #SucroseGameAssistant
 
2. 赞助独家支持者kgwy
 
所有赞助资金将用于：
 
- 绮良良新表情包/音效制作（比如新增“开心递快递”“累了摸鱼”动画）
- Sucrose框架新版本兼容性适配（确保工具长期可用）
- 新增功能开发（如绮良良语音提示、多语言支持）
 
赞助等级 金额 专属权益 
🐟 小鱼干赞助者 $5/月 独家绮良良表情包合集 + 加入“快递员社群”Discord 
📦 金牌快递员赞助者 $20/月 24小时优先bug修复 + 自定义绮良良UI主题（比如换“夏装绮良良”皮肤） 
🌟 老板级赞助者 $100/月 名字永久展示在“赞助者墙” + 参与新功能投票（如“是否加绮良良倒计时提醒”） 
 
👉 赞助链接：GitHub Sponsors/kgwy
 
📜 许可证说明
 
- 本项目：采用与SucroseGameAssistant一致的MIT License，可自由使用/修改/分发（需保留归因信息）。
- 绮良良相关资产：属于原神同人创作，仅用于非商业用途，尊重米哈游（miHoYo）知识产权。
- SucroseGameAssistant框架：遵循其原始许可证，详见原框架LICENSE。
 
📬 联系我们
 
- 绮良良代理开发组：@kgwy（DM可提功能建议/ bug反馈，带🐱前缀优先回复！）
- SucroseGameAssistant原作者：Kin-L（访问原框架仓库交流核心功能）
- 社群：Discord“绮良良的快递站”（链接在本项目Releases页面，可聊工具/晒绮良良截图～）
 
“只要是承诺过的快递，就一定会送到哦～” —— 绮良良 🐱📦
特别感谢SucroseGameAssistant框架提供的坚实基础，让可爱与实用能完美结合！lt with love for Kirara, and respect for DGA Sugar Proxy’s open-source work!
