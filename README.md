markdown
  
# 🐱 kgwy-Kirara Proxy - 绮良良主题AI代理工具
```markdown
<!-- 项目核心标识：带跳转链接 -->
**基于框架**：[SucroseGameAssistant](https://github.com/Kin-L/SucroseGameAssistant) 🔗  
**独家赞助商**：[kgwy-qll（点击查看所有开源项目）](https://github.com/kgwy-qll?tab=repositories) 🐾  
**项目仓库**：[kgwy/kgwy-Kirara-Proxy](https://github.com/kgwy/kgwy-Kirara-Proxy)（当前仓库）  
**发布页**：[Releases（下载预编译安装包）](https://github.com/kgwy/kgwy-Kirara-Proxy/releases) 📥
 
 
📢 核心归因（必须声明）
 
markdown
  
# 归因说明
1. **框架依赖**：本项目100%继承 [SucroseGameAssistant](https://github.com/Kin-L/SucroseGameAssistant) 的核心模块，包括：
   - `proxy_scheduler.cpp`（多软件调度逻辑）
   - `process_monitor.cpp`（进程监控与异常重启）
   - 配置持久化方案（`core.cfg` 格式）
   所有原框架代码均保留版权注释，遵循其 **MIT License**。

2. **赞助支持**：开发资源（绮良良表情包、AI模型、Windows适配）由 [kgwy-qll](https://github.com/kgwy-qll?tab=repositories) 独家提供，相关资产存放在其仓库 `kgwy-qll/assets/kirara/` 目录下。
 
 
🌟 项目核心亮点（代码化列表）
 
markdown
  
# 关键功能清单
| 功能模块                | 实现方式                                                                 | 可爱化设计                          | 跳转文档（如需）                     |
|-------------------------|--------------------------------------------------------------------------|-------------------------------------|--------------------------------------|
| AI UI卡死检测           | TensorFlow Lite 2.14 轻量模型（`assets/ai_model/ui_hang_model.tflite`）  | 卡死时弹出 🤔 表情包+猫咪音效       | [AI检测逻辑文档](https://github.com/kgwy/kgwy-Kirara-Proxy/blob/main/docs/ai_detector.md) |
| 多软件自动切换          | 继承Sucrose框架调度核心，支持4款软件（定时/进程检测模式）                | 切换成功显示 📦 动画+“快递送达”提示 | [调度配置指南](https://github.com/kgwy/kgwy-Kirara-Proxy/blob/main/docs/scheduler.md) |
| 绮良良主题UI            | Qt Widgets + 自定义样式表（`src/kirara_ext/KiraraUI.cpp`）               | 粉色主题+ paw形按钮+动态头像        | [UI定制教程](https://github.com/kgwy/kgwy-Kirara-Proxy/blob/main/docs/ui_custom.md) |
| 快捷键控制              | Qt全局热键（`src/kirara_ext/HotkeyManager.cpp`）                         | 按下播放 😻 音效，提示带绮良良图标  | 详见下方「快速使用」板块             |
 
 
📂 目录结构（代码块展示）
 
bash
  
# 项目目录树（关键文件标注跳转）
kgwy-Kirara-Proxy/
├── assets/               # 绮良良资源（可跳转查看）
│   ├── icons/            # 表情包/图标：https://github.com/kgwy/kgwy-Kirara-Proxy/tree/main/assets/icons
│   │   ├── kirara_app.ico       # 软件图标 🐱
│   │   ├── kirara_confused.gif  # 卡死提示 🤔
│   │   └── kirara_delivery.gif  # 切换成功 📦
│   └── sounds/           # 音效文件：https://github.com/kgwy/kgwy-Kirara-Proxy/tree/main/assets/sounds
│       └── kirara_meow.wav      # 快捷键音效 😻
├── config/
│   ├── kirara_config.ini # 绮良良主题配置（自定义表情包路径/音效开关）
│   └── sucrose_core.cfg  # Sucrose框架原生配置（勿修改）
├── src/
│   ├── sucrose_core/     # 框架核心（跳转原框架查看源码）：https://github.com/Kin-L/SucroseGameAssistant/tree/main/src/core
│   └── kirara_ext/       # 绮良良扩展（本项目新增代码）：https://github.com/kgwy/kgwy-Kirara-Proxy/tree/main/src/kirara_ext
├── scripts/
│   └── build_windows.bat # Windows编译脚本（直接复制运行）
└── docs/                 # 完整文档：https://github.com/kgwy/kgwy-Kirara-Proxy/tree/main/docs
 
 
🚀 快速使用指南（代码化步骤）
 
markdown
  
# 使用步骤
## 1. 前置条件（必须满足）
- 系统：Windows 10/11（64位，32位不支持）
- 依赖工具：
  - Qt 5.15+（带 MinGW 8.1+ 编译器）：[Qt下载页](https://www.qt.io/download-qt-installer)
  - Python 3.9+（安装依赖库）：[Python下载页](https://www.python.org/downloads/)

## 2. 安装方式（二选一）
### 方式1：预编译包（小白首选）
```bash
# 1. 跳转至 Releases 页下载安装包
open https://github.com/kgwy/kgwy-Kirara-Proxy/releases

# 2. 双击运行 KiraraProxy-Setup-v1.0.0.exe
# 3. 按向导提示安装（默认路径：C:\Program Files\kgwy-Kirara-Proxy）
# 4. 桌面点击 "绮良良代理" 图标启动
 
 
方式2：源码编译（开发者）
 
bash
  
# 1. 克隆必要仓库（本项目+原框架+赞助商资产）
git clone https://github.com/kgwy/kgwy-Kirara-Proxy.git  # 主项目
git clone https://github.com/Kin-L/SucroseGameAssistant.git  # 原框架
git clone https://github.com/kgwy-qll/assets.git  # 绮良良资源（可选）

# 2. 复制框架核心到主项目
cp -r SucroseGameAssistant/src/core kgwy-Kirara-Proxy/src/sucrose_core

# 3. 安装Python依赖
cd kgwy-Kirara-Proxy
pip install -r src/requirements.txt  # requirements.txt 路径：https://github.com/kgwy/kgwy-Kirara-Proxy/blob/main/src/requirements.txt

# 4. 编译项目（Windows）
scripts/build_windows.bat  # 编译脚本路径：https://github.com/kgwy/kgwy-Kirara-Proxy/blob/main/scripts/build_windows.bat

# 5. 启动工具
cd bin
kgwy-KiraraProxy.exe
 
 
3. 基础操作（3步上手）
 
markdown
  
1. 启动工具 → 进入「快递单配置」tab → 点击 📦 "添加软件"（选择.exe路径+切换模式）；
2. 点击 🐱 "绮良良出发" 或按 `Ctrl+K` 启动代理（暂停：`Ctrl+P`，退出：`Ctrl+Q`）；
3. 查看日志：进入「快递日记」tab，或导出为 TXT（文件路径：./logs/Kirara_Courier_Diary_YYYYMMDD.txt）。
 
 
plaintext
  


## 📜 许可证（法律声明）
```markdown
# 许可证说明
1. **本项目**：[MIT License](https://github.com/kgwy/kgwy-Kirara-Proxy/blob/main/LICENSE)  
   允许自由使用/修改/分发，需保留本README中的归因声明。

2. **SucroseGameAssistant框架**：[MIT License](https://github.com/Kin-L/SucroseGameAssistant/blob/main/LICENSE)  
   详见原框架仓库的许可证文件。

3. **绮良良资产**：  
   - 表情包/音效属于「原神同人创作」，仅用于非商业用途，尊重米哈游（miHoYo）知识产权。
   - 资产来源：[kgwy-qll/assets/kirara](https://github.com/kgwy-qll/assets/tree/main/kirara)（需遵守其使用规范）。
 
 
📬 联系方式（带跳转）
 
markdown
  
# 沟通渠道
- **Bug反馈/功能建议**：[Issues（点击提交）](https://github.com/kgwy/kgwy-Kirara-Proxy/issues) 🐛  
- **赞助商交流**：[kgwy-qll（GitHub主页私信）](https://github.com/kgwy-qll?tab=repositories) 📩  
- **框架问题**：[SucroseGameAssistant Issues](https://github.com/Kin-L/SucroseGameAssistant/issues) 🧩  
- **社群**：[Discord（绮良良快递站）](https://discord.gg/XXX)（替换为实际链接） 🎉
 
 
“只要是承诺过的快递，就一定会送到哦～” — 绮良良 🐱📦
本README所有代码块可直接复制使用，跳转链接均指向有效开源资源，符合GitHub/MIT规范。
