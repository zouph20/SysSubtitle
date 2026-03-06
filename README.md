# SysSubtitle

> 实时语音字幕翻译 · Real-time Speech-to-Text Translation for iOS

[![TestFlight](https://img.shields.io/badge/TestFlight-Join%20Beta-blue?logo=apple)](https://testflight.apple.com/join/YOUR_CODE)
[![Platform](https://img.shields.io/badge/platform-iOS%2017%2B-lightgrey?logo=apple)](https://www.apple.com/ios/)
[![Swift](https://img.shields.io/badge/Swift-6-orange?logo=swift)](https://swift.org)

---

## 简介 / What is SysSubtitle?

SysSubtitle 可以实时捕获 iOS 系统音频或麦克风声音，自动识别语音并翻译为目标语言，支持多说话人识别和 PiP 画中画悬浮字幕。

SysSubtitle captures system audio (via Broadcast Extension) or microphone input on iOS, performs real-time speech recognition and translation with multi-speaker diarization and Picture-in-Picture subtitle overlay.

**适用场景 / Use Cases:**
- 📺 看外语视频/直播，实时中文字幕
- 🎧 听外语播客，边听边看翻译
- 🗣 面对面外语对话，实时翻译辅助
- 📞 外语视频通话，字幕跟踪

---

## 功能特性 / Features

| 功能 | 说明 |
|------|------|
| 🎙 双音频模式 | 屏幕录制 (系统音频) / 麦克风拾音 |
| 🗣 多说话人识别 | Deepgram diarization，6 色自动区分 A-F |
| 🌐 实时翻译 | 四级管线 T0→T1→T2→T3，零延迟感 |
| 📺 PiP 画中画 | 切到其他 App 也能看字幕 |
| 🔄 说话人校准 | Track B REST 自动修正 + 手动全录音修正 |
| 🤖 LLM 校准 | Gemini / GPT 音频校准，Claude 文本校准 |
| 💾 录音保存 | WAV 本地存储，支持导出分享 |
| 📊 诊断系统 | 完整 timeline、延迟统计、修正追踪 |

---

## 支持语言 / Supported Languages

| 语言 | 识别 | 翻译 |
|------|:----:|:----:|
| 日本語 | ✅ | ✅ |
| 한국어 | ✅ | ✅ |
| English | ✅ | ✅ |
| 中文 | ✅ | ✅ |

---

## 快速开始 / Quick Start

### 1. 配置 API Key

首次使用需要配置至少两个 API Key：

| 服务 | 用途 | 获取地址 | 免费额度 |
|------|------|---------|---------|
| **Deepgram** | 语音识别 (必需) | [console.deepgram.com](https://console.deepgram.com) | $200 ≈ 550 小时 |
| **DeepL** | 翻译 (推荐) | [deepl.com/pro-api](https://www.deepl.com/pro-api) | 每月 50 万字符 |

打开 App → ⚙️ 设置 → API 标签页 → 填入 Key → 点测试验证

### 2. 屏幕录制模式

```
设置 → 选择「📡 屏幕录制」
     → 点击「开始录屏」(或控制中心 → 长按录屏 → 选 SysSubtitle)
     → 回到主界面点「开始」
     → 切到视频/播客 App → 字幕自动显示
```

### 3. 麦克风模式

```
设置 → 选择「🎙 麦克风」
     → 回到主界面点「开始」
     → 外放音频或直接对话 → 字幕自动显示
```

### 4. PiP 画中画

开启 PiP 后，切到其他 App 字幕悬浮窗持续显示：

设置 → 显示 → PiP 画中画 → 开启

---



---

## 技术栈 / Tech Stack

- **Language**: Swift 6 + SwiftUI
- **Target**: iOS 17.0+
- **Speech Recognition**: Deepgram Nova-3 (WebSocket + REST), Apple SFSpeech
- **Translation**: DeepL, Claude, Google Translate, Apple Translation
- **LLM Calibration**: Gemini, GPT (audio), Claude (text)
- **Audio**: AVAudioEngine, Broadcast Extension, App Groups
- **PiP**: AVPictureInPictureController + CoreGraphics rendering

---

## 费用估算 / Cost Estimate

| 服务 | 费用 | 说明 |
|------|------|------|
| Deepgram | ~$0.006/min | $200 免费额度 ≈ 550 小时 |
| DeepL Free | 免费 | 每月 50 万字符 ≈ 8-10 小时对话 |
| Apple Translation | 免费 | 需下载离线语言包 |

**推荐组合**: Deepgram + DeepL Free → 日常使用基本免费

---

## 文档 / Documentation

- 📖 [使用教程 / User Guide](USER_GUIDE.md)
- 🔒 [隐私政策 / Privacy Policy](PRIVACY.md)

---

## 开发 / Development

```

### 构建要求

- Xcode 16+
- iOS 17.0+ 真机 (Broadcast Extension 不支持模拟器)
- Apple Developer 账号 (App Groups + Broadcast Extension 需要)
- `import Combine` 在所有含 `@Published` 的文件中

### App Groups

主 App 和 Broadcast Extension 共享数据通过 App Groups：
- 音频 chunks + manifest.json
- full_recording.wav
- 心跳 + 停止信号

---

## License

MIT License — See [LICENSE](LICENSE) for details.

---

## Contact

📧 zouph20@gmail.com
