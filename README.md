# kgwy-Kinara-Smart
绮良良
kgwy-Kinara Smart Proxy - 开源完整方案
 
以下是适配开源平台（GitHub/GitLab）的 kgwy-Kinara Smart Proxy 完整版，包含可直接上传的仓库结构、核心代码、文档说明、赞助入口与用户下载指南，确保用户能快速理解、使用并支持项目。
 
一、开源仓库结构（标准GitHub/GitLab目录）
 
plaintext
  
kgwy-Kinara-Smart-Proxy/
├── .github/                # GitHub配置（ISSUE模板、赞助按钮）
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug_report.md   # Bug反馈模板
│   │   └── feature_request.md # 功能需求模板
│   └── FUNDING.yml         # GitHub赞助配置（关联kgwy收款方式）
├── 3rdparty/               # 第三方依赖库（预编译Windows版本）
│   ├── sugar-proxy-1.2/    # 砂糖代理框架
│   ├── opencv-4.8.0/       # OpenCV（截图识别）
│   └── tensorflow-lite-2.14/ # TFLite（AI检测）
├── assets/                 # 视觉资源（Kinara形象、表情包）
│   ├── icons/
│   │   ├── app_icon.ico    # 软件图标（Kinara头像）
│   │   ├── running.gif     # 运行中表情包
│   │   ├── success.gif     # 成功表情包
│   │   ├── error.gif       # 错误表情包
│   │   └── hang.gif        # 卡死表情包
│   └── sponsor/
│       ├── kgwy_alipay.png # kgwy支付宝收款码
│       └── kgwy_wechat.png # kgwy微信收款码
├── config/                 # 配置文件
│   ├── ai_model/
│   │   └── ui_hang_model.tflite # AI界面卡死检测模型
│   └── smtp_template.ini   # 邮箱通知模板
├── docs/                   # 文档
│   ├── install_guide.md    # 安装指南
│   ├── user_manual.md      # 使用手册
│   └── dev_guide.md        # 开发指南
├── scripts/                # 辅助脚本
│   ├── build_windows.bat   # Windows编译脚本（MinGW）
│   └── package_inno.iss    # Inno Setup打包脚本（生成安装包）
├── src/                    # 核心代码
│   ├── main.cpp            # 程序入口
│   ├── MainWindow.cpp      # 主窗口（含Kinara表情包交互）
│   ├── SugarProxyIntegration.cpp # 砂糖代理集成
│   ├── AIDetector.cpp      # AI界面卡死检测
│   ├── SoftAutoRunner.cpp  # 软件自动化（启动/切换）
│   ├── EmailNotifier.cpp   # 邮箱通知
│   └── SponsorManager.cpp  # 赞助入口管理
├── ui/                     # UI布局文件
│   ├── MainWindow.ui       # 主窗口UI
│   ├── SoftConfigDialog.ui # 软件配置对话框
│   └── SponsorDialog.ui    # 赞助弹窗UI
├── include/                # 头文件
│   ├── MainWindow.h
│   ├── SugarProxyIntegration.h
│   ├── AIDetector.h
│   ├── SoftAutoRunner.h
│   ├── EmailNotifier.h
│   └── SponsorManager.h
├── res/                    # 资源文件索引
│   └── KinaraAssets.qrc    # 关联assets目录下的图片/表情包
├── LICENSE                 # MIT开源协议
├── README.md               # 项目首页（用户第一眼看到的内容）
└── KinaraProxy.pro         # Qt项目配置文件（编译入口）
 
 
二、核心文档（用户/开发者友好）
 
1. README.md（开源平台首页）
 
markdown
  
# kgwy-Kinara Smart Proxy 🐱💻
A cute-style open-source proxy tool driven by **Kinara** (pink twin-tailed girl), integrated with AI UI hang detection, software automation, and email notifications. Sponsored by [kgwy](https://github.com/kgwy).

## 🌟 Key Features
- **AI-Powered UI Hang Detection**: Automatically detect if the software interface is stuck, with Kinara's emoji feedback.
- **Software Automation**: Support 4 custom softwares, auto-start via screenshot recognition, cycle switching (timer/process detection mode).
- **Cute Emoji Feedback**: Kinara's dynamic emojis show running status (running/success/error/hang).
- **Email Notifications**: Auto-send status emails (start/switch/stuck) to your inbox.
- **Lightweight & Open-Source**: Based on Sugar Proxy framework, small size, MIT license.

## 📸 Kinara's Emoji Status
| Status       | Emoji                  | Description                     |
|--------------|------------------------|---------------------------------|
| Running      | ![Running](assets/icons/running.gif) | Kinara is starting the software! |
| Success      | ![Success](assets/icons/success.gif) | Software switched successfully! |
| Error        | ![Error](assets/icons/error.gif)     | Oops, something went wrong!     |
| UI Hang      | ![Hang](assets/icons/hang.gif)       | Interface stuck, need help?     |

## 🚀 Quick Start
### 1. Download
- **Latest Release**: [Click here](https://github.com/kgwy/kgwy-Kinara-Smart-Proxy/releases) to download the Windows installer (KinaraProxy-Setup.exe).
- **Source Code**: Clone this repo: `git clone https://github.com/kgwy/kgwy-Kinara-Smart-Proxy.git`

### 2. Install
- Double-click `KinaraProxy-Setup.exe`, follow the wizard (with Kinara's cute installation interface).
- No extra dependencies needed (all included in the installer).

### 3. Use
1. Open the software, click **"Add Software"** to configure up to 4 softwares:
   - Upload the screenshot of the software's start button (for recognition).
   - Choose mode: Timer (auto-switch after N seconds) / Process Detection (switch when software exits).
2. Click **"Start Cycle"** to run automatically.
3. Check email for status notifications (configure SMTP in "Settings" first).

## 🛠️ Development Guide
### Dependencies
- Qt 5.15+ (with Widgets/Network modules)
- OpenCV 4.8.0 (screenshot recognition)
- TensorFlow Lite 2.14 (AI hang detection)
- Sugar Proxy 1.2 (proxy framework)

### Build
1. Install Qt 5.15+ and add to system PATH.
2. Run `scripts/build_windows.bat` (Windows) to compile the source code.
3. The output is in `bin/` directory.

### Package
1. Install Inno Setup 6+.
2. Open `scripts/package_inno.iss` with Inno Setup.
3. Click "Run" (F9) to generate the installer.

## ❤️ Sponsor kgwy
This project is sponsored by **kgwy** and maintained by the open-source community. If you like Kinara Proxy, please support us to keep updating!

### Sponsorship Ways
- **GitHub Sponsors**: [Sponsor kgwy on GitHub](https://github.com/sponsors/kgwy)
- **Alipay**: ![Alipay](assets/sponsor/kgwy_alipay.png)
- **WeChat Pay**: ![WeChat](assets/sponsor/kgwy_wechat.png)

### Sponsor Benefits
| Tier         | Monthly Amount | Benefits                                                                 |
|--------------|----------------|--------------------------------------------------------------------------|
| Rice Ball Supporter | ¥5        | Exclusive Discord access, weekly "Kinara's Rice Ball Diary" tech newsletter. |
| Pro Developer | ¥50         | All above + Priority bug fix (24h response), 1 custom Kinara emoji/year. |
| Enterprise Partner | ¥500    | All above + Dedicated tech support (8h/month), private deployment, brand logo on README. |

## 📄 License
[MIT License](LICENSE) - Free for commercial and non-commercial use, please keep the original copyright notice.

## 🤝 Contribute
1. Fork this repo.
2. Create a feature branch: `git checkout -b feature/your-feature`.
3. Commit your changes: `git commit -m "Add your feature"`.
4. Push to the branch: `git push origin feature/your-feature`.
5. Open a Pull Request.

## 📧 Contact
- GitHub: [kgwy](https://github.com/kgwy)
- Email: kgwy@example.com (replace with your actual email)
 
 
2. install_guide.md（安装指南）
 
markdown
  
# kgwy-Kinara Smart Proxy - Installation Guide
This guide helps you install Kinara Proxy on Windows 10/11 (32/64-bit).

## 📋 Prerequisites
- Windows 10/11 (32/64-bit)
- At least 100MB free disk space
- Internet connection (for email notifications, optional)

## 🚀 Step-by-Step Installation
### 1. Download the Installer
Go to the [Releases page](https://github.com/kgwy/kgwy-Kinara-Smart-Proxy/releases) and download the latest `KinaraProxy-Setup.exe`.

### 2. Run the Installer
- Double-click `KinaraProxy-Setup.exe`. If a "User Account Control" prompt pops up, click "Yes".
- You'll see Kinara's welcome interface (pink theme with Kinara's avatar). Click "Next".

### 3. Accept the License
- Read the MIT License (short and friendly), check "I accept the terms in the License Agreement", then click "Next".

### 4. Choose Installation Path
- Default path: `C:\Program Files\kgwy-Kinara Smart Proxy` (recommended for most users).
- If you want to change the path, click "Browse" and select a folder, then click "Next".

### 5. Select Additional Tasks
- Check "Create a desktop shortcut" (easy to launch later).
- Check "Add to Start Menu" (optional), then click "Next".

### 6. Install
- Click "Install" to start the installation. The progress bar will show Kinara's loading animation.
- Wait for 1-2 minutes (depending on your computer speed).

### 7. Complete the Installation
- Click "Finish". If you check "Launch kgwy-Kinara Smart Proxy now", the software will open immediately.

## ❌ Troubleshooting Installation Issues
### 1. "Installer failed to start"
- Cause: Missing Windows updates or antivirus blocking.
- Fix: Update Windows to the latest version, temporarily disable antivirus, then re-run the installer.

### 2. "Insufficient disk space"
- Cause: Not enough free space in the selected path.
- Fix: Choose another drive with at least 100MB free space.

### 3. "Permission denied"
- Cause: No admin rights.
- Fix: Right-click the installer, select "Run as administrator".

## 📞 Get Help
If you encounter other issues, please open an [Issue](https://github.com/kgwy/kgwy-Kinara-Smart-Proxy/issues) on GitHub, or contact kgwy via email: kgwy@example.com.
 
 
三、核心代码（确保可编译运行）
 
1. src/main.cpp（程序入口）
 
cpp
  
#include <QApplication>
#include "MainWindow.h"
#include "AIDetector.h"
#include <QMessageBox>
#include <QDir>

int main(int argc, char *argv[])
{
    QApplication a(argc, argv);
    
    // Set app info
    a.setApplicationName("kgwy-Kinara Smart Proxy");
    a.setApplicationVersion("1.0.0");
    a.setOrganizationName("kgwy");
    a.setWindowIcon(QIcon(":/icons/app_icon.ico"));

    // Initialize AI detector (load model from config)
    AIDetector aiDetector;
    QString modelPath = QDir::currentPath() + "/config/ai_model/ui_hang_model.tflite";
    if (!QFile::exists(modelPath)) {
        modelPath = QApplication::applicationDirPath() + "/config/ai_model/ui_hang_model.tflite";
    }
    if (!aiDetector.initModel(modelPath)) {
        QMessageBox::warning(nullptr, "AI Model Warning", 
            "AI UI hang detection model failed to load. This feature will be disabled.");
    }

    // Show main window
    MainWindow w(&aiDetector);
    w.show();

    return a.exec();
}
 
 
2. src/MainWindow.cpp（主窗口+Kinara表情包交互）
 
cpp
  
#include "MainWindow.h"
#include "ui_MainWindow.h"
#include "SoftConfigDialog.h"
#include "SponsorDialog.h"
#include "EmailNotifier.h"
#include <QDateTime>
#include <QDebug>

MainWindow::MainWindow(AIDetector *aiDetector, QWidget *parent)
    : QMainWindow(parent)
    , ui(new Ui::MainWindow)
    , m_aiDetector(aiDetector)
    , m_softAutoRunner(new SoftAutoRunner)
    , m_emailNotifier(new EmailNotifier)
{
    ui->setupUi(this);
    setWindowTitle("kgwy-Kinara Smart Proxy");

    // Initialize Kinara emoji (show idle emoji first)
    ui->lblKinaraEmoji->setPixmap(QPixmap(":/icons/running.gif").scaled(150, 150, Qt::KeepAspectRatio));

    // Connect soft auto runner signals
    connect(m_softAutoRunner, &SoftAutoRunner::statusChanged, this, [=](RunnerStatus status, const QString &emojiPath) {
        // Update emoji
        ui->lblKinaraEmoji->setPixmap(QPixmap(emojiPath).scaled(150, 150, Qt::KeepAspectRatio));
        // Update status text
        QString statusText;
        switch (status) {
            case RunnerStatus::IDLE: statusText = "Idle - Ready to start"; break;
            case RunnerStatus::RUNNING: statusText = "Running - Kinara is working!"; break;
            case RunnerStatus::SUCCESS: statusText = "Success - Software switched"; break;
            case RunnerStatus::ERROR: statusText = "Error - Check configuration"; break;
            case RunnerStatus::HANG: statusText = "Hang - Interface stuck, try restarting"; break;
        }
        ui->lblStatus->setText(statusText);
        // Update log
        ui->txtLog->append(QString("[%1] %2").arg(QDateTime::currentDateTime().toString("HH:mm:ss")).arg(statusText));
    });

    // Connect email notification signal
    connect(m_softAutoRunner, &SoftAutoRunner::needSendEmail, this, [=](const QString &title, const QString &content) {
        if (m_emailNotifier->isConfigured()) {
            m_emailNotifier->sendEmail(title, content);
            ui->txtLog->append(QString("[%1] Email sent: %2").arg(QDateTime::currentDateTime().toString("HH:mm:ss")).arg(title));
        } else {
            ui->txtLog->append("[Warning] Email not configured, skip sending");
        }
    });

    // Connect AI hang detection (check every 30 seconds)
    m_hangCheckTimer.setInterval(30000);
    connect(&m_hangCheckTimer, &QTimer::timeout, this, &MainWindow::checkUIHang);

    // Connect buttons
    connect(ui->btnAddSoft, &QPushButton::clicked, this, &MainWindow::addSoftConfig);
    connect(ui->btnStart, &QPushButton::clicked, this, [=]() {
        m_softAutoRunner->startCycle();
        m_hangCheckTimer.start();
        ui->btnStart->setEnabled(false);
        ui->btnStop->setEnabled(true);
    });
    connect(ui->btnStop, &QPushButton::clicked, this, [=]() {
        m_softAutoRunner->stopCycle();
        m_hangCheckTimer.stop();
        ui->btnStart->setEnabled(true);
        ui->btnStop->setEnabled(false);
    });
    connect(ui->btnSponsor, &QPushButton::clicked, this, [=]() {
        SponsorDialog dialog(this);
        dialog.exec();
    });
    connect(ui->btnEmailConfig, &QPushButton::clicked, this, &MainWindow::configureEmail);
}

MainWindow::~MainWindow()
{
    delete ui;
    delete m_softAutoRunner;
    delete m_emailNotifier;
}

// Add software configuration
void MainWindow::addSoftConfig()
{
    SoftConfigDialog dialog(this);
    if (dialog.exec() == QDialog::Accepted) {
        SoftConfig config = dialog.getConfig();
        if (m_softAutoRunner->addSoftConfig(config)) {
            // Update software list
            ui->lstSoft->addItem(QString("%1 (Mode: %2, Timeout: %3s)")
                .arg(config.softName)
                .arg(config.isTimerMode ? "Timer" : "Process Detection")
                .arg(config.timeoutSec));
            ui->txtLog->append(QString("[%1] Added software: %2").arg(QDateTime::currentDateTime().toString("HH:mm:ss")).arg(config.softName));
        } else {
            ui->txtLog->append("[Error] Failed to add software (max 4 or invalid template)");
        }
    }
}

// Configure email settings
void MainWindow::configureEmail
