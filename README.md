# Claude & Codex in third-party

中文：Claude & Codex 三方接入

Public downloads and user guide for CC3P.

CC3P helps users manage local configuration for Claude Code, Claude Desktop, and Codex across official account mode and third-party model provider mode.

- Latest release: https://github.com/sssstwee/cc3p-download/releases/latest
- User guide page: https://sssstwee.github.io/cc3p-download/

## English Quick Start

1. Open the latest release page.
2. Download the installer for your operating system.
3. Install and open CC3P.
4. Run `Environment Check`.
5. Add or sync a profile for Claude Code, Claude Desktop, or Codex.
6. Review the generated local config.
7. Click `Apply`.
8. Restart the target app or open a new terminal session if needed.

### Which Installer Should I Use?

| System | Recommended Package |
| --- | --- |
| macOS Apple Silicon | macOS arm64 `.dmg` |
| macOS Intel | macOS x64 `.dmg` |
| Windows | `.msi` or `.exe` |
| Linux | `.deb`, `.rpm`, or `.AppImage` |

### macOS First Launch Authorization

If macOS blocks CC3P because it is not from the App Store or an identified developer, try the safer system flow first: open `System Settings` > `Privacy & Security`, then click `Open Anyway` for CC3P.

If you trust this release and need to authorize it from Terminal, run:

```bash
sudo xattr -rd com.apple.quarantine "/Applications/cc3p.app"
open "/Applications/cc3p.app"
```

Advanced option: show/enable the `Anywhere` Gatekeeper option, then restore the default setting after CC3P opens normally.

```bash
sudo spctl --master-disable
sudo spctl --master-enable
```

### What CC3P Changes

CC3P writes local user config files only:

- Claude Code: `~/.claude/settings.json`
- Claude Desktop: macOS `~/Library/Application Support/Claude-3p/configLibrary`; Windows `%APPDATA%\Claude-3p\configLibrary`
- Codex: `~/.codex/auth.json` and `~/.codex/config.toml`

## 中文快速开始

1. 打开最新 release 页面。
2. 下载当前系统对应的安装包。
3. 安装并打开 CC3P。
4. 先运行「环境检查」。
5. 为 Claude Code、Claude Desktop 或 Codex 添加/同步配置。
6. 检查生成的本地配置内容。
7. 点击「应用」。
8. 如目标应用需要重启读取配置，请重启应用或打开新的终端会话。

### 应该下载哪个安装包？

| 系统 | 推荐安装包 |
| --- | --- |
| macOS Apple Silicon | macOS arm64 `.dmg` |
| macOS Intel | macOS x64 `.dmg` |
| Windows | `.msi` 或 `.exe` |
| Linux | `.deb`、`.rpm` 或 `.AppImage` |

### macOS 首次启动授权

如果 macOS 提示 CC3P 不是来自 App Store 或无法验证开发者，优先使用系统方式：打开「系统设置」>「隐私与安全性」，在 CC3P 提示项旁点击「仍要打开」。

如果你确认安装包来自本仓库 release，并希望用命令行处理，可以执行：

```bash
sudo xattr -rd com.apple.quarantine "/Applications/cc3p.app"
open "/Applications/cc3p.app"
```

高级选项：临时显示/开启 Gatekeeper 的「任何来源」选项。应用可正常打开后，建议恢复默认安全设置：

```bash
sudo spctl --master-disable
sudo spctl --master-enable
```

### CC3P 会修改什么？

CC3P 只写入当前用户的本地配置：

- Claude Code：`~/.claude/settings.json`
- Claude Desktop：macOS `~/Library/Application Support/Claude-3p/configLibrary`；Windows `%APPDATA%\Claude-3p\configLibrary`
- Codex：`~/.codex/auth.json` 和 `~/.codex/config.toml`

## Safety

- Keep API keys private.
- Review generated config before applying.
- Running terminal sessions may keep old config; open a new session after applying.
- Source code is not published in this repository. This repository only hosts public downloads and user documentation.
