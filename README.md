# deja vu Meeting Pro

AI-powered meeting assistant — real-time transcription, smart summaries, task extraction, and glossary management, all in one page.

[中文说明](#中文说明)

---

## Features

- **Real-time Recording & Transcription** — Tencent Cloud ASR for live speech-to-text with per-sentence timestamps
- **AI Summary Generation** — Structured meeting summaries via LLM (OpenAI-compatible, DeepSeek, Claude)
- **Task Auto-Extraction** — LLM-powered action item detection with assignee and deadline
- **Glossary Management** — Auto-detect technical terms, one-click add to vocabulary, grouped by meeting/domain/date
- **Task Management** — Create, edit, mark complete, set deadlines and priority
- **Calendar View** — Monthly calendar with task deadlines, drag-to-resize columns
- **History** — Browse past meetings with transcripts, summaries, tasks, and recordings
- **Dark Mode** — Full light/dark theme support

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | Vanilla HTML/CSS/JS, no framework |
| Speech-to-Text | Tencent Cloud ASR WebSocket SDK |
| Audio Recording | Browser `MediaRecorder` API |
| AI | Configurable LLM API (OpenAI-compatible, DeepSeek, Claude) |
| Data Storage | Browser IndexedDB |

## Quick Start

### Prerequisites

- A modern browser with `MediaDevices` API support (Chrome / Edge / Firefox)
- Tencent Cloud account with ASR service enabled (for transcription)
- An LLM API key (for AI features)

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/ai-meeting-assistant.git
cd ai-meeting-assistant
```

### 2. Open the app

Open `dejavu_meeting_pro_allfrontend.html` in your browser, or serve it with any static file server:

```bash
# Using Python
python3 -m http.server 8080

# Using Node.js
npx serve .
```

### 3. Configure settings

Go to **Settings** in the sidebar to configure:
- **LLM API Key** — for AI summary, task extraction, and glossary features
- **Tencent Cloud credentials** — for real-time speech recognition

## Usage

1. Click **Start Recording** to begin real-time transcription
2. After the meeting, click **Stop** — the AI will auto-generate a summary, extract tasks, and detect technical terms
3. Add terms to your glossary with one click
4. Review tasks in the **Tasks** page or **Calendar** view
5. Browse past meetings in the **History** page

## Project Structure

```
.
├── dejavu_meeting_pro_allfrontend.html   # Main application (single-page)
├── fonts/                                # Local font files
│   ├── NotoSansSC-VariableFont_wght.ttf
│   ├── NotoSerifSC-VariableFont_wght.ttf
│   ├── DMMono-Regular.ttf
│   └── DMMono-Medium.ttf
├── tencentcloud-speech-sdk-js-main/      # Tencent Cloud Speech SDK
├── LICENSE
└── README.md
```

## Known Limitations

- Only records microphone input; use [BlackHole](https://github.com/ExistentialAudio/BlackHole) or similar to capture system audio
- Data is stored in browser IndexedDB; clearing browser data will erase history

## Roadmap

- [ ] Audio file upload & async transcription
- [ ] Speaker diarization (multi-speaker identification)
- [ ] Electron packaging for desktop app with system audio capture

## License

[MIT](LICENSE)

---

## 中文说明

deja vu 会议妙记 —— AI 辅助的会议助手，将实时语音转录、智能摘要、任务提取和术语管理整合在同一个界面中。

### 功能模块

- **实时录音与转录** — 腾讯云 ASR 实时语音识别，逐句标注时间戳
- **AI 摘要生成** — 将转录文本送入大语言模型，输出结构化会议摘要
- **任务自动提取** — 从转录文本中识别行动项，自动设置负责人和截止日期
- **术语检测与词汇表** — 自动扫描专业词汇，一键收录至词汇表
- **任务管理** — 新建、编辑、标记完成、设置截止日期和紧急标记
- **日历视图** — 以月历形式展示任务截止日期
- **历史会议** — 浏览历史会议的转录、摘要、任务和录音
- **深色模式** — 完整的明暗主题切换

### 快速开始

1. 用浏览器打开 `dejavu_meeting_pro_allfrontend.html`
2. 在设置页配置 LLM API Key（用于摘要、任务提取、术语检测）
3. 在设置页配置腾讯云凭证（用于语音识别）
4. 点击「开始录音」即可使用

### 技术实现

| 层面 | 技术 |
|------|------|
| 前端 | 纯 HTML/CSS/JS，无框架依赖 |
| 语音识别 | 腾讯云 ASR WebSocket SDK |
| 音频录制 | 浏览器原生 `MediaRecorder` API |
| AI 功能 | 可配置的 LLM API（支持 OpenAI 兼容接口、DeepSeek、Claude） |
| 数据存储 | 浏览器 IndexedDB，无需数据库 |

### 已知限制

- 只能录制麦克风输入，无法直接捕获系统内部声音；可配合 BlackHole 等虚拟音频设备使用
- 数据存储在浏览器 IndexedDB，清除浏览器数据会导致历史记录丢失
