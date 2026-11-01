# 汇通全球 FXLive — GitHub 云端自动打包工程 (Android `.apk` + iOS `.ipa`)

本工程已配置好 **Capacitor 6 跨平台移动框架** 与 **GitHub Actions 云端自动构建流水线**。您无需在自己电脑上安装沉重的 Android Studio 或苹果 Xcode，只需把本文件夹上传到您的 GitHub 仓库，GitHub 的免费云服务器就会自动为您编译出**安卓 `.apk` 安装包**和**苹果 `.ipa` 安装包**！

---

## 🚀 三步在 GitHub 上自动打包下载到手机

### 第一步：在 GitHub 创建仓库并上传文件
1. 登录您的 [GitHub](https://github.com/) 账号，点击右上角 **`+`** -> **`New repository`**。
2. 仓库名称填写例如：`fxlive-app`，选择 **Public（公开仓库，可免费不限次使用 GitHub Actions 云打包和 GitHub Pages）**，点击 **`Create repository`**。
3. 在新建好的仓库页面中，点击 **`uploading an existing file`**（或者使用 Git 命令行推送），将本压缩包解压后的**所有文件和文件夹**（包含 `.github` 文件夹、`www` 文件夹、`package.json`、`capacitor.config.json`）拖入上传，并点击底部的 **`Commit changes`**。
   > ⚠️ **注意**：上传时请确保隐藏文件夹 `.github/workflows/build-mobile.yml` 也被一同上传（如果您使用网页拖拽上传，也可以在仓库顶栏点击 **Actions** -> **New workflow** -> **set up a workflow yourself**，将 `.github/workflows/build-mobile.yml` 的内容粘贴进去保存）。

### 第二步：等待 GitHub Actions 自动编译完成（约 2~3 分钟）
1. 上传完成后，点击仓库顶部的 **`Actions`** 标签页。
2. 您会看到名为 **「自动打包 Android (.apk) & iOS (.ipa) & 发布手机版」** 的工作流正在自动运行（黄色转圈 🟡）。
3. 等待约 2~3 分钟变成绿色勾号 ✅ 后，点进该次运行记录，滑到页面最底部的 **`Artifacts`（构建产物）** 区域，即可直接点击下载：
   - 📦 **`FXLive-Android-APK-安装包`**：解压后即为 `FXLive_汇通全球_Android安装版.apk`，发到任何安卓手机上点击即可直接安装！
   - 📦 **`FXLive-iOS-IPA安装包与Xcode工程`**：内含 `FXLive_汇通全球_iOS未签名版.ipa` 与完整 Xcode 工程。

---

## 📱 安卓与苹果手机具体安装方法

### 🤖 安卓手机 (Android)
- 从 GitHub Actions 的 `Artifacts` 下载 `FXLive-Android-APK-安装包` 并解压得到 **`FXLive_汇通全球_Android安装版.apk`**。
- 通过微信、QQ 或数据线发送到安卓手机，点击即可直接安装到桌面。

### 🍎 苹果手机 (iPhone / iOS) —— 两种方式任选
由于苹果系统的安全机制限制，未经过 App Store 的应用有以下两种安装方式：
1. **方式 A：免签直接安装到桌面（最推荐、永久不过期）**
   - 在您的 GitHub 仓库点击顶部 **`Settings`** -> 左侧 **`Pages`** -> 在 `Build and deployment` 的 `Source` 下拉框选择 **`GitHub Actions`**。
   - GitHub 会为您生成一个专属网址（如 `https://您的用户名.github.io/fxlive-app/`）。
   - 用 iPhone 自带的 **Safari 浏览器**打开该网址，点击底部正中间的 **「分享」按钮 ->「添加到主屏幕」**，即可在 iPhone 桌面生成全屏独立运行的原生级 App！
2. **方式 B：安装 `.ipa` 原生包（适合习惯自签名的用户）**
   - 从 GitHub Actions 下载 `FXLive_汇通全球_iOS未签名版.ipa`。
   - 在电脑上使用 **爱思助手 (i4Tools)**、**Sideloadly** 或手机端 **AltStore / 巨魔 (TrollStore)** 导入该 `.ipa` 文件即可签名安装到 iPhone。

---

## 💻 如果您使用 Git 命令行上传（快捷指令）
在解压后的本文件夹内打开终端（Terminal / Git Bash），依次运行：
```bash
git init
git add .
git commit -m "初始化汇通全球 FXLive 双端自动打包工程"
git branch -M main
git remote add origin https://github.com/您的GitHub用户名/您的仓库名.git
git push -u origin main
```
推送完成后，直接去 GitHub 仓库的 **Actions** 页面下载打包好的安装文件即可！
