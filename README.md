# Mard Markdown Editor

A lightweight, installation-free Markdown editor supporting 10 languages, 1300+ emoji, Mermaid charts, and KaTeX formulas.

## Download

| Platform | File | Size |
|----------|------|------|
| **macOS (Apple Silicon)** | [Mard_1.0.0_aarch64.dmg](https://github.com/Paulsxb/Mard/releases/download/v1.0.0/Mard_1.0.0_aarch64.dmg) | ~4 MB |
| **Windows (Portable)** | [Mard_Portable.exe](https://github.com/Paulsxb/Mard/releases/download/v1.0.0/Mard_Portable.exe) | ~11 MB |
| **Windows (Installer)** | [Mard_1.0.0_x64-setup.exe](https://github.com/Paulsxb/Mard/releases/download/v1.0.0/Mard_1.0.0_x64-setup.exe) | ~3 MB |
| **Windows (MSI)** | [Mard_1.0.0_x64_en-US.msi](https://github.com/Paulsxb/Mard/releases/download/v1.0.0/Mard_1.0.0_x64_en-US.msi) | ~4 MB |

[Full release notes →](https://github.com/Paulsxb/Mard/releases/tag/v1.0.0)

## macOS Installation / macOS 安装说明

The macOS app is ad-hoc signed (not notarized), so Gatekeeper blocks it. Follow the steps below.

**中文：**
1. 下载 DMG → 挂载 → 将 Mard.app 拖入「应用程序」文件夹
2. 打开终端（Terminal），依次执行以下 3 条命令：

```bash
xattr -cr /Applications/Mard.app
codesign --force --deep --sign - /Applications/Mard.app
open /Applications/Mard.app
```

3. 首次通过 `open` 命令启动后，以后双击即可正常运行。

> 若提示 `codesign: command not found`，需先安装 Xcode Command Line Tools：`xcode-select --install`

**English:**
1. Download the DMG → mount → drag Mard.app to Applications
2. Open Terminal and run these 3 commands:

```bash
xattr -cr /Applications/Mard.app
codesign --force --deep --sign - /Applications/Mard.app
open /Applications/Mard.app
```

3. After the first launch via `open`, double-click will work from then on.

> If you see `codesign: command not found`, install Xcode Command Line Tools first: `xcode-select --install`

> **Why?** The app uses ad-hoc code signing (free). A paid Apple Developer account ($99/year) is needed for notarization. On macOS Sequoia, `xattr -cr` alone is insufficient — the app must be re-signed locally to pass Gatekeeper.

---

## Build Guide / 构建指南 (Developers)

> **给 Mac 上的 Claude Code 读取并执行。** 本目录已包含编译 macOS 版本所需的全部源码。

---

## 1. 背景

Mard 是一个 Markdown 编辑器网页应用：
- 基于 Tauri v2 (Rust) 打包为原生桌面应用
- 前端是单个 `www/index.html`，所有 JS/CSS 已内联本地化，零 CDN 依赖
- 支持 1300+ Emoji 表情选择、Mermaid 图表、KaTeX 公式、多语言等
- Windows 版本的 exe (9.6MB) 已在 Windows 机器上构建成功

**本次目标：在本 Mac 上编译出 macOS 版本的 `.app` 和 `.dmg`。**

---

## 2. 操作步骤

### 2.1 检查环境

```bash
# 必须：Node.js >= 18
node --version

# 必须：Rust >= 1.70
rustc --version
cargo --version

# 必须：Xcode Command Line Tools（提供 macOS SDK）
xcode-select --install 2>&1 || echo "already installed"
```

如果 Rust 未安装：
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source ~/.cargo/env
```

### 2.2 安装 npm 依赖

```bash
cd Mard_Mac
npm install
```

这会安装 `@tauri-apps/cli`（已在 package.json 的 devDependencies 中）。

### 2.3 编译 macOS 应用

```bash
npm run tauri build
```

首次编译需要下载 Rust crates（约 5-10 分钟），后续增量编译只需几十秒。

### 2.4 构建产出

构建成功后，产物在 `src-tauri/target/release/bundle/` 下：

| 文件 | 路径 | 说明 |
|------|------|------|
| `.app` 应用包 | `bundle/macos/Mard.app` | 双击即可运行的 macOS 应用 |
| `.dmg` 安装镜像 | `bundle/dmg/Mard_1.0.0_x64.dmg` | 分发给其他 Mac 用户的标准格式 |

> 如果是 Apple Silicon (M1/M2/M3/M4) Mac，二进制将原生适配 arm64；Intel Mac 则为 x64。

---

## 3. 注意事项

1. **代码签名**：默认使用 ad-hoc 签名（本地可运行）。如果要分发给他人，首次打开需要右键 →「打开」来绕过 Gatekeeper。如需正式签名，需要 Apple Developer Program ($99/年)。

2. **WebView2**：macOS 使用系统内置的 WKWebView，无需额外安装任何运行时。

3. **不要修改 `src-tauri/tauri.conf.json` 和 `src-tauri/Cargo.toml`**，除非你知道自己在做什么。`bundle.targets` 已设为 `"all"`，macOS 上会自动选择正确的打包格式。

4. **如果构建失败并报 `error: linking with cc failed`**，说明缺少 macOS SDK。运行 `xcode-select --install` 后再试。

5. **构建完成后**，将 `.app` 或 `.dmg` 复制回 Windows 机器（通过 U 盘、AirDrop 或网盘），放在 `D:\My_App\Mard\` 目录下即可。

---

## 4. 快速排查

| 错误 | 解决 |
|------|------|
| `rustc: command not found` | 安装 Rust：`curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs \| sh` |
| `xcrun: error: unable to find utility "xcodebuild"` | 安装 Xcode CLI：`xcode-select --install` |
| `error: linking with cc failed` | 同上 |
| `npm: command not found` | 安装 Node.js：`brew install node`（或从 nodejs.org 下载） |
| `The configured frontendDist includes...` | 确认 `www/` 目录存在且包含 `index.html` |
