# talk-type

**Hold a key, speak, release — your words appear at the cursor.**
An offline push-to-talk dictation tool for Windows, tuned for Traditional Chinese mixed with English.

[English](#english) · [繁體中文](#繁體中文)

> This repository hosts **release builds only**. The source code is maintained in a private repository.

---

## English

### Features

- **Push-to-talk anywhere** — hold Right Ctrl (configurable), speak, release; the text is pasted into whatever app has focus. A toggle mode handles longer passages.
- **On-device recognition** — speech never leaves your computer. Choose from several open models (Qwen3-ASR, Whisper, Breeze-ASR-25, SenseVoice, X-ASR, Parakeet) directly from the tray menu.
- **Traditional Chinese, Taiwan usage** — simplified-to-traditional conversion, Taiwan-specific wording, punctuation clean-up and proper spacing between Chinese and English.
- **Personal dictionary** — correct names and jargon the recognizer keeps getting wrong.
- **Safe pasting** — never types into password fields; restores your clipboard afterwards and keeps dictated text out of the Win+V history.
- **Optional rewriting** — polish or summarise each sentence through an OpenAI-compatible service you configure (local Ollama / LM Studio, or a cloud provider). Off by default.

### Requirements

- Windows 10 or 11, x64
- About 1–2 GB of free memory while recognising, and disk space for the models you choose (150 MB – 1.1 GB each)
- An internet connection for the first model download

### Install

1. Download the latest `talk-type-vX.Y.Z.zip` from [Releases](../../releases/latest).
2. **Before extracting**, unblock the zip: right-click → *Properties* → tick *Unblock* → *OK*
   (or in PowerShell: `Unblock-File .\talk-type-vX.Y.Z.zip`).
   The builds are not code-signed; without this step Windows SmartScreen will warn on every launch.
3. Extract to a permanent folder, e.g. `D:\Apps\talk_type\`, and run `talk_type.exe`.
4. On first launch talk-type creates its settings, adds desktop and Start-menu shortcuts, enables start-on-login (can be turned off in the tray menu) and downloads the default model with a progress indicator.

### Updating

Versions after v0.11.0 check this repository for new releases at start-up and once a day. When one is available, the tray menu offers **Update** and a link to the release notes; the download is verified (SHA-256) before the program replaces itself and restarts. Settings, dictionary and models are kept. The previous executable is left as `talk_type.old.exe` in case you need to roll back.

For v0.11.0 and earlier, quit talk-type from the tray, then repeat the install steps with the new zip.

### Privacy and network use

Recognition runs entirely on your computer, and talk-type keeps no logs of what you say. It connects to the internet only to:

- download recognition models from their official sources (Hugging Face, the sherpa-onnx GitHub releases), verified by SHA-256;
- check this repository for updates and download them;
- send text to your rewriting service, only if you turned that feature on.

### Models and licences

Models are not bundled; each is downloaded from its publisher and remains under its own licence (MIT, Apache-2.0, CC-BY-4.0 or the FunASR Model License, depending on the model).

### Disclaimer

A personal project, provided as is, without warranty of any kind.

---

## 繁體中文

### 功能

- **按住就說**：在任何程式裡按住右 Ctrl（可改）說話，放開後文字貼到游標處；長段落可用切換模式。
- **本機辨識**：語音不會離開你的電腦。可從系統匣切換多個開放模型（Qwen3-ASR、Whisper、Breeze-ASR-25、SenseVoice、X-ASR、Parakeet）。
- **繁體中文、台灣用語**：簡轉繁、兩岸用語修正、標點整理、中英文之間自動加空白。
- **個人字典**：常被聽錯的人名與專有名詞，加進字典就會自動修正。
- **安全貼上**：不會輸入到密碼欄位；貼上後還原剪貼簿，說的話也不會進 Win+V 歷史。
- **整理方式（選用）**：把每句交給你設定的 OpenAI 相容服務潤飾或整理成重點（本機 Ollama／LM Studio 或雲端服務），預設關閉。

### 系統需求

- Windows 10 或 11（x64）
- 辨識時約需 1–2 GB 可用記憶體；每個模型 150 MB–1.1 GB 的磁碟空間
- 第一次下載模型時需要網路

### 安裝

1. 到 [Releases](../../releases/latest) 下載最新的 `talk-type-vX.Y.Z.zip`。
2. **解壓縮前先解除封鎖**：在 zip 上按右鍵 →「內容」→ 勾「解除封鎖」→「確定」（或在 PowerShell 執行 `Unblock-File .\talk-type-vX.Y.Z.zip`）。程式沒有程式碼簽章，不解除的話每次啟動 SmartScreen 都會警告。
3. 解壓縮到固定的資料夾（例如 `D:\Apps\talk_type\`），執行 `talk_type.exe`。
4. 第一次啟動時會建立設定檔、在桌面與開始功能表放捷徑、開啟開機自動啟動（可從系統匣取消），並下載預設模型（浮動窗顯示進度）。

### 更新

v0.11.0 之後的版本會在啟動時與每天一次檢查這個 repo 有沒有新版。有新版時，系統匣出現「更新」和版本說明的連結；按下後下載、驗證 SHA-256，通過才換掉程式並重新啟動。設定檔、字典與模型都會保留；舊版的執行檔留成 `talk_type.old.exe`，需要時可以手動換回。

v0.11.0（含）以前的版本：先從系統匣「結束」，再用新的 zip 照安裝步驟做一次。

### 隱私與連網

辨識全程在本機執行，也不會記錄你說的內容。只有以下情況會連網：

- 從官方來源（Hugging Face、sherpa-onnx 的 GitHub Release）下載辨識模型，並以 SHA-256 驗證；
- 到這個 repo 檢查與下載新版；
- 你自己開了「整理方式」時，把文字送到你設定的服務。

### 模型與授權

程式不附帶模型，模型由各自的發布者提供，適用各自的授權（依模型為 MIT、Apache-2.0、CC-BY-4.0 或 FunASR Model License）。

### 免責聲明

個人專案，依現狀提供，不附任何保證。
