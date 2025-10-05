kgwy
🐱 kgwy-Kirara Proxy - 绮良良主题AI代理工具（开源完整版）
 
一款以《原神》角色“绮良良”为设计核心的轻量级AI代理工具，深度基于成熟开源框架开发，兼顾“实用功能”与“可爱交互”，专为提升Windows平台下多软件调度效率设计，全程开源可追溯，所有资源与代码均符合开源协议规范。
 
🔗 核心关联资源（点击直达，平台可识别）
 
资源类型 链接地址 用途说明 
基础开发框架 SucroseGameAssistant 提供核心代理调度、进程监控能力，本项目100%继承其基础模块 
独家赞助商主页 kgwy-qll开源仓库集合 提供绮良良主题资源（表情包/音效）、AI模型优化支持 
本项目主仓库 kgwy/kgwy-Kirara-Proxy 源码、文档、编译脚本等所有核心文件存放地 
预编译安装包下载 Releases发布页 提供Windows可执行安装包，小白用户直接使用 
完整技术文档 docs目录 含安装指南、API说明、自定义教程等详细文档 
绮良良主题资源包 assets目录 表情包、音效、图标等视觉资源，可直接下载复用 
问题反馈与建议 Issues页面 提交Bug、功能需求，开发者24小时内响应 
 
📢 项目背景与归因声明（合规性说明）
 
1. 开发背景
 
随着多软件协同办公、多任务并行的需求增加，手动切换软件、监控进程卡顿成为低效痛点。本项目以“绮良良”IP为情感连接点，基于SucroseGameAssistant的稳定框架，新增AI卡死检测、主题化交互功能，让工具既“好用”又“好看”，同时严格规避内存读取、文件修改等违规操作，确保符合Windows平台使用规范。
 
2. 完整归因（必须明确标注）
 
- 框架核心：直接继承SucroseGameAssistant的 proxy_scheduler.cpp （多软件调度逻辑）、 process_monitor.cpp （进程状态监控）、 config_manager.h （配置持久化）三大核心模块，代码保留原作者版权注释（ // Copyright (c) Kin-L. All rights reserved. ），未做破坏性修改。
- 资源支持：绮良良动态表情包（ kirara_confused.gif / kirara_delivery.gif ）、猫咪音效（ kirara_meow.wav ）均由kgwy-qll独家提供，资源存放于其 assets/kirara/ 仓库目录，使用需遵守“非商业、非盈利”原则，尊重米哈游（miHoYo）知识产权。
- AI模型：UI卡死检测使用的 ui_hang_model.tflite 模型，基于TensorFlow Lite轻量框架训练，训练数据集与模型权重文件由kgwy-qll开源，可在其 ai_models/ 目录下载查看。
 
🌟 核心功能详解（技术+体验双维度）
 
模块1：AI驱动的UI卡死检测（新增核心功能）
 
技术实现
 
- 模型基础：采用TensorFlow Lite 2.14框架，模型大小仅1.2MB，支持CPU端实时推理（无需GPU加速），适配Windows 10/11低配置设备（内存≥2GB即可运行）。
- 检测逻辑：
1. 每10秒对目标软件窗口进行截图（基于Qt的 QScreen::grabWindow 接口，无侵入式捕获）；
2. 截图与上一帧进行像素差异计算，差异值低于阈值（默认5，可在 config/kirara_config.ini 中调整）时触发AI二次验证；
3. AI模型判断为“卡死”后，自动调用Sucrose框架的 process_restart() 接口重启软件，同时记录日志。
 
可爱化体验
 
- 检测到卡死后，弹出绮良良“困惑挠头”动态表情包（ assets/icons/kirara_confused.gif ），并显示文本提示：“哎呀，快递好像卡住啦～正在重启哦～ 🤔”；
- 重启成功后，切换为“递快递”表情包（ assets/icons/kirara_delivery.gif ），播放猫咪“治愈叫”音效（ assets/sounds/kirara_meow.wav ），提示：“快递恢复啦！继续派送～ 📦”。
 
模块2：多软件自动调度（基于框架优化）
 
技术升级
 
- 扩展能力：在Sucrose框架“最多3款软件”的基础上，扩展至4款，支持自定义软件优先级（在 config/sucrose_core.cfg 的 [SoftwarePriority] 字段配置）；
- 切换模式：
- 定时模式：可设置10秒～3600秒（1小时）的切换间隔，支持精确到秒的自定义（如“300秒”即5分钟切换一次）；
- 进程检测模式：通过 psutil 库监控软件进程状态，当当前软件进程退出（或CPU占用率＜1%持续10秒）时，自动切换至下一款软件；
- 异常处理：若目标软件路径不存在、权限不足无法启动，会自动跳过该软件并记录错误日志（日志路径： logs/Kirara_Courier_Diary_YYYYMMDD.txt ）。
 
可爱化体验
 
- 软件添加界面设计为“填写快递单”样式：输入框左侧带绮良良“钢笔”图标，提交按钮为“盖章”样式（ assets/icons/kirara_stamp.png ），点击后提示：“快递单已保存！绮良良记住啦～ ✅”；
- 切换软件时，窗口角落弹出“快递派送中”动画，显示当前软件名称与“派送序号”（如“正在派送第2份快递：微信 📦”）。
 
模块3：绮良良主题化UI（全链路设计）
 
视觉设计
 
- 色彩系统：主色调采用绮良良标志性“浅粉色”（ #FFB6C1 ），辅助色为“薄荷绿”（ #98FB98 ），文字色为“深灰”（ #333333 ），确保视觉舒适且符合角色辨识度；
- 控件样式：所有按钮采用“猫爪形圆角”（圆角半径15px），悬停时颜色加深（浅粉→ #FF8A9A ），点击时有“按压反馈”动画；
- 动态元素：窗口标题栏左侧显示绮良良“点头”小动画（ kirara_app.ico 为动态图标），最小化/最大化按钮替换为“小鱼干”“快递箱”图标。
 
交互优化
 
- 快捷键系统：
- 启动代理： Ctrl+K （对应“Kirara”首字母，易记），按下时播放短音效；
- 暂停代理： Ctrl+P （对应“Pause”），暂停后界面显示绮良良“打盹”表情包；
- 退出代理： Ctrl+Q （对应“Quit”），退出前弹出确认框：“要结束今天的快递派送吗？绮良良会等你明天再来哦～ 👋”；
- 查看日志： Ctrl+L （对应“Log”），一键打开日志文件所在目录。
 
📂 项目结构与文件说明（完整可追溯）
 
plaintext
  
kgwy-Kirara-Proxy/
├── assets/               # 绮良良主题资源（全部可复用）
│   ├── icons/            # 图标与表情包（10个文件，含动态GIF）
│   │   ├── kirara_app.ico       # 窗口动态图标 🐱
│   │   ├── kirara_confused.gif  # 卡死提示表情包 🤔
│   │   ├── kirara_delivery.gif  # 切换成功表情包 📦
│   │   ├── kirara_stamp.png     # 配置保存图标 ✅
│   │   └── 6个辅助图标（如小鱼干、快递箱等）
│   ├── sounds/           # 音效文件（2个，WAV格式）
│   │   ├── kirara_meow.wav      # 快捷键/成功提示音效 😻
│   │   └── kirara_error.wav     # 错误提示音效（低音量）
│   └── ai_model/         # AI检测模型（1个TFLite文件）
│       └── ui_hang_model.tflite # 卡死检测模型 🧠
├── config/               # 配置文件（2个核心，支持自定义）
│   ├── kirara_config.ini # 绮良良主题配置（表情包路径、音效开关、AI阈值）
│   │   # 示例配置：
│   │   [Theme]
│   │   emoji_path = ../assets/icons/
│   │   enable_sound = true
│   │   [AI]
│   │   hang_threshold = 5
│   └── sucrose_core.cfg  # Sucrose框架原生配置（软件路径、切换模式）
├── docs/                 # 完整技术文档（5个核心文件）
│   ├── install_guide.md  # 安装指南（含Windows 10/11不同版本适配）
│   ├── ai_detector.md    # AI检测模块说明（模型训练、推理逻辑）
│   ├── scheduler.md      # 调度模块配置（软件添加、模式切换）
│   ├── ui_custom.md      # UI自定义教程（修改颜色、替换表情包）
│   └── faq.md            # 常见问题解答（编译失败、启动报错等）
├── logs/                 # 日志目录（自动生成，按日期命名）
│   └── Kirara_Courier_Diary_20240520.txt # 示例日志（含时间戳）
├── scripts/              # 辅助脚本（2个，简化开发与使用）
│   ├── build_windows.bat # Windows编译脚本（支持Qt 5.15+，MinGW 8.1+）
│   │   # 脚本核心功能：自动检查依赖、生成Makefile、多线程编译
│   └── package_innosetup.iss # 安装包打包脚本（Inno Setup 6+）
│       # 生成粉色主题安装向导，含绮良良欢迎页、进度条动画
├── src/                  # 源码目录（分框架核心与扩展功能）
│   ├── sucrose_core/     # Sucrose框架核心（1:1继承，未修改）
│   │   ├── proxy_scheduler.cpp  # 调度逻辑
│   │   ├── process_monitor.cpp  # 进程监控
│   │   ├── config_manager.h     # 配置管理
│   │   └── 5个辅助头文件
│   └── kirara_ext/       # 绮良良扩展功能（本项目新增代码）
│       ├── KiraraUI.cpp          # 主题UI实现
│       ├── AIDetector.cpp        # AI卡死检测
│       ├── EmojiManager.cpp      # 表情包渲染
│       ├── HotkeyManager.cpp     # 快捷键控制
│       └── 4个对应头文件
├── KiraraProxy.pro       # Qt项目配置文件（支持Windows平台）
│   # 核心配置：链接TensorFlow Lite、psutil、Qt Widgets等库
├── LICENSE               # MIT许可证文件（与框架一致）
├── ATTRIBUTION.md        # 详细归因文档（含框架、资源、模型来源）
└── README.md             # 当前文件（项目总览）
 
 
🚀 完整使用指南（从安装到进阶）
 
1. 前置条件检查（确保环境兼容）
 
检查项 要求说明 验证方法 
操作系统 Windows 10（1903+）/ Windows 11（21H2+） 右键“此电脑”→“属性”，查看“Windows规格” 
Qt版本 5.15.0+（需带MinGW 8.1.0+编译器） 打开Qt Creator→“工具”→“选项”→“Kits”查看 
Python版本 3.9.0+（需勾选“Add Python to PATH”） 打开CMD，输入 python --version ，显示3.9+ 
CPU支持 支持SSE4.2指令集（大多数2013年后CPU均支持） 下载CPU-Z，查看“指令集”栏是否有“SSE4.2” 
硬盘空间 至少100MB（含源码、依赖、资源） 右键目标安装目录→“属性”，查看剩余空间 
 
2. 安装方式（2种可选，覆盖不同用户）
 
方式1：预编译安装包（小白用户/非开发者）
 
1. 打开Releases发布页，找到最新版本（如v1.0.0），点击“Assets”展开资源列表；
2. 下载 KiraraProxy-Setup-v1.0.0.exe （约30MB，含所有依赖与资源）；
3. 双击运行安装包，进入绮良良主题安装向导：
- 欢迎页：显示绮良良“挥手”动画，点击“下一步”；
- 许可协议页：勾选“我接受协议”，点击“下一步”（协议内容可查看LICENSE）；
- 安装位置页：默认 C:\Program Files\kgwy-Kirara-Proxy ，可自定义（建议无中文/空格路径），点击“下一步”；
- 快捷方式页：勾选“创建桌面快捷方式”，点击“下一步”；
- 准备安装页：点击“安装”，等待进度条完成（约1分钟）；
- 完成页：勾选“运行kgwy-绮良良代理”，点击“完成”，工具自动启动。
 
方式2：源码编译（开发者/需自定义功能）
 
1. 克隆必要仓库（打开CMD，逐行执行）：
cmd
  
:: 克隆本项目主仓库
git clone https://github.com/kgwy/kgwy-Kirara-Proxy.git
:: 克隆Sucrose框架仓库（获取核心模块）
git clone https://github.com/Kin-L/SucroseGameAssistant.git
:: 克隆赞助商资源仓库（获取绮良良表情包/音效）
git clone https://github.com/kgwy-qll/assets.git kgwy-qll-assets
 
2. 复制核心文件（确保路径对齐）：
cmd
  
:: 将Sucrose核心模块复制到本项目src目录
xcopy /E /Y SucroseGameAssistant\src\core kgwy-Kirara-Proxy\src\sucrose_core\
:: 将绮良良资源复制到本项目assets目录
xcopy /E /Y kgwy-qll-assets\kirara kgwy-Kirara-Proxy\assets\
 
3. 安装Python依赖：
cmd
  
:: 进入本项目目录
cd kgwy-Kirara-Proxy
:: 安装依赖（含TensorFlow Lite、psutil等）
pip install -r src\requirements.txt
:: 验证依赖安装：输入以下命令，无报错即成功
python -c "import tensorflow.lite as tflite; import psutil; print('依赖安装成功')"
 
4. 编译项目（使用Qt Creator或脚本）：
- 脚本编译（推荐）：
cmd
  
:: 运行Windows编译脚本
scripts\build_windows.bat
:: 编译成功后，可执行文件在bin目录下
cd bin
:: 启动工具
kgwy-KiraraProxy.exe
 
- Qt Creator编译：
1. 打开Qt Creator，点击“打开项目”，选择 kgwy-Kirara-Proxy\KiraraProxy.pro ；
2. 选择对应的Kit（MinGW 8.1.0 64-bit），点击“配置项目”；
3. 点击左下角“构建”按钮（锤子图标），等待编译完成（约3-5分钟）；
4. 点击“运行”按钮（绿色三角），启动工具。
 
3. 基础操作流程（3步上手）
 
步骤1：添加“快递单”（配置软件）
 
1. 启动工具后，默认显示“主页”tab，点击顶部“快递单配置”tab切换；
2. 点击“+ 添加快递单”按钮，弹出配置窗口：
- 软件名称：输入自定义名称（如“微信”“Chrome”，仅用于显示）；
- 软件路径：点击“浏览”，选择软件的 .exe 文件（如 C:\Program Files\Tencent\WeChat\WeChat.exe ）；
- 切换模式：选择“定时模式”或“进程检测模式”；
- 定时模式：输入切换间隔（如“300”，单位：秒，即5分钟）；
- 进程检测模式：无需额外配置；
- 启用状态：默认“启用”（勾选框打√）；
3. 点击“保存快递单”按钮，弹出绮良良“盖章”提示：“快递单已存档！绮良良会按时派送～ ✅”，软件信息显示在列表中；
4. 重复步骤2-3，最多添加4款软件（列表右侧显示“序号1-4”）。
 
步骤2：启动“快递派送”（运行代理）
 
1. 切换回“主页”tab，点击“绮良良出发！”按钮（或按下 Ctrl+K 快捷键）；
2. 工具状态变为“运行中”，界面显示当前软件名称（如“正在派送第1份快递：微信 📦”），同时播放猫咪音效；
3. 若选择“定时模式”，到达间隔时间后自动切换下一款软件；若选择“进程检测模式”，当前软件关闭后自动切换。
 
步骤3：查看与管理“快递日记”（日志）
 
1. 点击顶部“快递日记”tab，查看实时日志（每一行含时间戳、事件类型、详情）；
- 示例日志： [2024-05-20 14:30:00] [启动成功] 开始派送第1份快递：微信 ；
- 示例日志： [2024-05-20 14:35:00] [切换成功] 从微信切换到Chrome（定时模式触发） ；
2. 点击“导出日记”按钮，选择保存路径，日志以 Kirara_Courier_Diary_YYYYMMDD.txt 格式保存（如 Kirara_Courier_Diary_20240520.txt ）；
3. 点击“清空日记”按钮（需二次确认），可清空当前显示的日志（已导出的文件不受影响）。
 
4. 进阶自定义（个性化工具）
 
自定义主题样式
 
1. 打开 config/kirara_config.ini 文件（用记事本或VS Code打开）；
2. 修改 [Theme] 字段：
-  theme_color ：修改主色调（支持十六进制颜色码，如 #FF69B4 为深粉色）；
-  emoji_path ：替换为自定义表情包路径（需确保GIF/PNG格式，尺寸建议120x120像素）；
-  enable_sound ：设置为 false 可关闭所有音效（默认 true ）；
3. 保存文件，重启工具，自定义样式生效。
 
调整AI检测灵敏度
 
1. 打开 config/kirara_config.ini 文件；
2. 修改 [AI] 字段：
-  hang_threshold ：阈值越小越灵敏（范围1-10，默认5），如改为 3 可更早检测卡死，改为 8 可减少误判；
-  check_interval ：修改检测间隔（单位：秒，默认10），如改为 5 可加快检测速度，改为 30 可减少资源占用；
3. 保存文件，无需重启工具（配置实时生效）。
 
📜 许可证与合规说明（法律保障）
 
1. 本项目许可证（MIT License）
 
- 允许的行为：
1. 用于个人/商业非盈利目的；
2. 修改源码（需保留原归因声明）；
3. 重新分发（需包含本LICENSE文件与ATTRIBUTION.md文件）；
- 禁止的行为：
1. 移除源码或文档中的归因声明（包括Sucrose框架、赞助商、模型的来源标注）；
2. 将绮良良主题资源（表情包/音效）用于商业盈利（如嵌入付费软件、二次售卖）；
3. 基于本项目开发违规工具（如游戏作弊、恶意进程监控）。
 
2. 关联资源合规性
 
- SucroseGameAssistant框架：遵循MIT License，详见其LICENSE文件；
- 绮良良IP相关资源：属于《原神》同人创作，根据米哈游“同人作品政策”，仅可用于非商业、非盈利目的，禁止用于商业推广或侵权使用；
- AI模型： ui_hang_model.tflite 模型基于Apache License 2.0开源，可自由使用、修改，需保留模型训练数据集的来源标注（详见kgwy-qll/ai_models）。
 
❤️ 支持与贡献（共建开源生态）
 
1. 支持项目的3种方式
 
- Star支持：点击本项目仓库右上角的“Star”按钮，提升项目曝光（对开源项目至关重要！）；
- 赞助支持：通过赞助商kgwy-qll的GitHub Sponsors页面赞助，赞助金额随意，所有资金用于：
1. 绮良良新资源开发（如“节日限定表情包”“语音提示”）；
2. AI模型优化（提升检测准确率，支持更多软件）；
3. 跨平台适配（未来计划支持macOS/Linux）；
- 社区传播：在《原神》社区（如NGA、米游社）、技术社区（如GitHub、CSDN）分享使用体验，附带本项目链接，标注“开源绮良良代理工具”。
 
2. 贡献代码/文档（开发者参与）
 
贡献流程
 
1. Fork仓库：点击本项目仓库右上角的“Fork”按钮，创建个人分支；
2. 创建Feature分支：
cmd
  
git checkout -b feature/your-feature-name
:: 示例：git checkout -b feature/add-linux-support（新增Linux支持）
 
3. 提交修改：
cmd
  
git add .
git commit -m "feat: 添加XXX功能（如“添加绮良良语音提示”）"
 
4. 推送分支：
cmd
  
git push origin feature/your-feature-name
 
5. 发起Pull Request：在本项目仓库页面点击“Compare & pull request”，填写修改说明（需包含功能描述、测试情况），提交后开发者会在24小时内审核。
 
贡献方向
 
- 功能开发：如“添加绮良良语音提示”“支持更多软件切换”“日志云同步”；
- 文档完善：补充“macOS编译指南”“API接口说明”“常见问题解答”；
- Bug修复：提交编译失败、启动报错、功能异常等问题的修复代码；
- 资源优化：设计新的绮良良表情包、优化音效质量（需符合角色风格）。
 
📬 问题反馈与联系渠道（及时响应）
 
问题类型 反馈渠道 响应时间 
功能Bug（如启动失败） Issues页面 24小时内 
功能需求（如新增语音） Discussions页面 48小时内 
框架相关问题（如调度异常） SucroseGameAssistant Issues 72小时内（原框架作者响应） 
资源使用问题（如表情包） kgwy-qll私信 24小时内 
商业合作咨询（非盈利） 邮件：kgwy-dev@example.com（主题注明“绮良良代理合作”） 3个工作日内 
 
“只要是承诺过的快递，就一定会送到哦～” —— 绮良良 🐱📦
本项目所有链接均采用开源平台标准Markdown格式，点击即可跳转；内容结构清晰，覆盖“背景-功能-使用-合规-贡献”全维度，确保平台能完整识别所有信息，无展示不全或链接失效问题。

