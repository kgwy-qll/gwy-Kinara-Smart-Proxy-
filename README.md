🐱 kgwy-Kirara Proxy - 绮良良主题AI代理工具（基于SucroseGameAssistant框架）
 
An open-source, cat-ear charm-packed AI proxy tool inspired by Genshin Impact’s Kirara — with direct links to sponsors, full framework attribution, and cuteness that grabs attention at first glance! 📦✨
 
📢 核心归因 & 独家赞助商
 
🔗 基于框架：SucroseGameAssistant
 
本项目完全继承SucroseGameAssistant的核心代理能力（跨软件调度、进程监控、配置持久化），所有原框架代码均标注清晰来源，严格遵循其开源协议。
 
👉 点击跳转原框架仓库，给SucroseGameAssistant点Star！是它的稳定基础，让绮良良主题功能得以落地～
 
🐾 独家赞助商主页：kgwy-qll
 
本项目的所有开发资源（绮良良表情包设计、AI模型优化、框架适配）均由kgwy独家支持，其所有开源项目（含原神、鸣潮等系列助手）均可在赞助商主页查看！
 
👉 点击直达：kgwy-qll的开源仓库主页，探索更多可爱风技术工具～
 
🌟 项目概述
 
本工具在SucroseGameAssistant“轻量实用核心”上，叠加了绮良良专属设计：
 
- ✅ 保留原框架优势：Windows 10/11适配、≤200MB内存占用、无侵入式操作（不读内存/不改文件）
- 😺 新增可爱交互：动态表情包（启动📦/卡死🤔/成功✅）+ 猫咪音效，每步操作都有绮良良陪伴
- 🧠 强化AI能力：基于TensorFlow Lite的10秒卡死检测，自动重启软件避免卡顿
- 📦 趣味化操作：将“添加软件”转化为“填写快递单”，贴合绮良良“信使”设定
 
📂 目录结构（与Sucrose框架对齐）
 
plaintext
  
kgwy-Kirara-Proxy/
├── assets/               # 绮良良可爱资源 🐱
│   ├── icons/（头像/表情包）
│   └── sounds/（猫咪音效）
├── config/               # 配置文件（含Sucrose核心配置）
├── src/
│   ├── sucrose_core/     # Sucrose框架核心模块 🔗
│   └── kirara_ext/       # 绮良良主题扩展（新增代码）
├── scripts/              # 一键编译/安装脚本
└── README.md             # 你正在阅读的指南～
 
 
✨ 核心功能（Sucrose基础 + 绮良良升级）
 
功能模块 Sucrose原框架能力 绮良良主题升级 可爱指数 🐱 
多软件代理 4款软件切换（定时/进程检测） 切换成功弹📦动画+“快递送达啦～”提示 ⭐⭐⭐⭐⭐ 
进程监控 异常重启 卡死时显🤔表情包+委屈猫咪叫 ⭐⭐⭐⭐⭐ 
配置保存 自动加载配置 保存弹✅盖章动画，配置文件名带“快递单” ⭐⭐⭐⭐ 
快捷键控制 启动/暂停/退出 按快捷键播😻音效，提示带绮良良头像 ⭐⭐⭐⭐ 
 
🚀 快速开始
 
1. 前置条件
 
- 系统：Windows 10/11
- 工具：Qt 5.15+、Python 3.9+
- 框架依赖：SucroseGameAssistant核心（源码编译需克隆）
 
2. 安装方式
 
方式1：下载预编译包（小白首选）
 
1. 进入本项目Releases
2. 下载 KiraraProxy-Setup-v1.0.0.exe （粉色安装向导🎀）
3. 双击安装 → 桌面点击🐱图标启动
 
方式2：源码编译
 
bash
  
# 1. 克隆本项目 + Sucrose框架 + 赞助商主页（可选）
git clone https://github.com/kgwy/kgwy-Kirara-Proxy.git
git clone https://github.com/Kin-L/SucroseGameAssistant.git
git clone https://github.com/kgwy-qll?tab=repositories  # 🌟 克隆赞助商仓库

# 2. 安装依赖 + 编译
cd kgwy-Kirara-Proxy
pip install -r src/requirements.txt
scripts/build_windows.bat

# 3. 启动
bin/kgwy-KiraraProxy.exe
 
 
❤️ 支持与赞助
 
1. 支持本项目 & 关联仓库
 
- 给本项目点⭐：kgwy-Kirara Proxy
- 给原框架点⭐：SucroseGameAssistant
- 关注赞助商：kgwy-qll的开源主页（点击跳转，查看更多可爱工具～）
 
2. 赞助方式
 
所有赞助资金用于绮良良资源更新与框架适配，可通过赞助商主页的「Sponsor」按钮支持，赞助者名单将在本项目README置顶致谢！
 
📜 许可证
 
- 本项目：MIT License（与Sucrose框架一致，需保留归因）
- 绮良良资产：原神同人非商用，尊重米哈游IP
- 赞助商仓库：遵循各项目独立许可证（详见kgwy-qll主页）
 
📬 联系我们
 
- 开发组：kgwy（DM提建议，带🐱前缀优先回复）
- 赞助商：kgwy-qll（点击跳转主页，了解更多项目）
- 原框架作者：Kin-L（交流Sucrose核心功能）
 
“只要是承诺过的快递，就一定会送到哦～” — 绮良良 🐱📦
🌟 感谢kgwy-qll的独家支持，让技术也能充满可爱温度！
