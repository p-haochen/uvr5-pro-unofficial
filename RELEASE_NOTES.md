# UVR5 Pro v1.0.0 — release notes

[繁體中文](#繁體中文)

## English

UVR5 Pro 1.0.0 is an **unofficial** build of Ultimate Vocal Remover GUI v5.6.1. It is not
affiliated with or endorsed by the Ultimate Vocal Remover developers. Free of charge, without
warranty.

### Platforms

| Platform | Assets | Signing |
| --- | --- | --- |
| Windows 11 x64, portable (Windows 10 not tested) | `UVR5Pro_1.0.0_Windows_x64_Portable.zip.001`, `.zip.002` | Not digitally signed |
| macOS, Apple Silicon | `UVR5Pro_1.0.0_macOS_arm64.zip` | Ad-hoc signature only; no Developer ID; not notarized |

SHA-256 checksums of all assets are in `SHA256SUMS.txt`. Setup guides:
[Windows](docs/INSTALL_WINDOWS.md), [macOS](docs/INSTALL_MACOS.md).
The LGPL source archives and `lgpl-build-scripts-1.0.0.zip` are also attached; they are not
needed to run UVR5 Pro.

### Highlights

- **Smart Separation:** recommends an installed model for your source and goal and explains
  why; remembers your model choice per situation; BS-RoFormer, MDX-Net and Demucs (including
  six-stem "All Stems") workflows.
- First-start Model Store setup that can reuse an existing model folder.
- Output named after the original song (Unicode names supported); existing files are never
  overwritten — a new run gets `(2)`, `(3)`, ….
- Windows: NVIDIA CUDA acceleration with CPU fallback; program files are checked with SHA-256
  when the program starts, and bundled third-party Python files when they are first loaded.
- Self-contained: no separate Python or runtime installation.

### Not included

- No AI models. Smart Separation downloads a model you select from its original public source
  only on request; each model has its own license and terms.
- No FFmpeg, Rubber Band or SoX.
- No automatic updates, telemetry or analytics.

### Known limitations

Windows:

- FLAC and MP3 output are unavailable (no encoder); UVR5 Pro offers WAV instead before
  starting.
- Unavailable: Phase Swapper and Matchering (the upstream tools call library functions that do
  not exist; UVR5 Pro says so before starting); Time Stretch; Change Pitch with Time Correction; in-app audio
  playback; Smart Separation single-model VR runs (except BVE lead/backing vocals); legacy
  Demucs v1/v2; the classic Download Center. *Open Model Folder* only shows instructions.
- Only one window can use the same `UserData` folder at a time.
- The first start after extracting a downloaded ZIP can take about half a minute while
  Windows scans the files.
- Rarely, a start can fail with `REAL_STARTUP_FAILURE`; starting again normally works.

macOS:

- Apple Silicon only. This exact build has not yet been run on a Mac. MP3 output and
  time-stretch/pitch tools are expected not to work;
  Phase Swapper and Matchering are unavailable. ONNX Runtime uses the CPU only; Apple-GPU (MPS) behaviour depends on the model.
- Gatekeeper blocks the first start until you choose *Open Anyway* (see the macOS guide).

### Licenses

See [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) and the `Licenses` folder inside each
download. Free of charge is not a statement that commercial use is allowed. The non-commercial
diffq library is not included, so the quantized Demucs models `v3 | mdx_q` and
`v3 | mdx_extra_q` are refused before they start; every other Demucs model works.

### Disclaimer

UVR5 Pro is unofficial derivative software. It has no official partnership with, or endorsement  
by, the original developers of Ultimate Vocal Remover or the providers of other third-party  
components.  
This software is provided free of charge and "AS IS", without any warranty, express or implied,  
including but not limited to the warranties of merchantability, fitness for a particular purpose  
and non-infringement.  
To the maximum extent permitted by applicable law, the developer is not liable for any loss of  
data, work interruption, loss of revenue or other damages arising from the use of, or the  
inability to use, this software.  
Users should back up important data themselves and make sure they have the right to use,  
process and distribute the audio and models they provide.  
This disclaimer does not modify, replace or limit any third-party license terms, and does not  
exclude any liability that cannot be excluded under applicable law.

---

## 繁體中文

UVR5 Pro 1.0.0 是 Ultimate Vocal Remover GUI v5.6.1 的**非官方**建置，與 Ultimate Vocal Remover
原作者無關，也未經其背書。免費提供，不附任何保證。

### 平台

| 平台 | 附件 | 簽章 |
| --- | --- | --- |
| Windows 11 x64（免安裝版；Windows 10 尚未測試） | `UVR5Pro_1.0.0_Windows_x64_Portable.zip.001`、`.zip.002` | 沒有數位簽章 |
| macOS（Apple Silicon） | `UVR5Pro_1.0.0_macOS_arm64.zip` | 只有 ad-hoc 簽章；沒有 Developer ID；未經 Apple 公證 |

所有附件的 SHA-256 檢查碼在 `SHA256SUMS.txt`。安裝說明：
[Windows](docs/INSTALL_WINDOWS.md)、[macOS](docs/INSTALL_MACOS.md)。
另附 LGPL 原始碼封存與 `lgpl-build-scripts-1.0.0.zip`；執行 UVR5 Pro 不需要它們。

### 主要功能

- **Smart Separation（智慧分離）：** 依來源與目標推薦已安裝的模型並說明理由；依情境記住你的模型選擇；
  支援 BS-RoFormer、MDX-Net、Demucs（含六軌 All Stems）等流程。
- 第一次啟動的 Model Store 設定，可沿用既有模型資料夾。
- 以原曲名命名輸出（支援 Unicode 檔名）；絕不覆寫既有檔案，重跑時改用 `(2)`、`(3)`…。
- Windows：NVIDIA CUDA 加速，沒有 GPU 時改用 CPU；啟動時以 SHA-256 檢查程式檔案，
  內附的第三方 Python 檔案則在第一次載入時檢查。
- 內含完整執行環境，不需另外安裝 Python 或執行環境。

### 不包含

- 不含任何 AI 模型。只有在你要求時，Smart Separation 才會從原始公開來源下載你選擇的模型；
  每個模型有各自的授權與使用條款。
- 不含 FFmpeg、Rubber Band、SoX。
- 沒有自動更新、遙測或使用統計。

### 已知限制

Windows：

- 無法輸出 FLAC、MP3（沒有編碼器）；開始前會詢問是否改用 WAV。
- 無法使用：Phase Swapper 與 Matchering（上游工具呼叫了不存在的函式庫功能，開始前會提示）；Time Stretch；開啟 Time Correction 的 Change Pitch；程式內播放音訊；
  Smart Separation 的 VR 單一模型執行（BVE 主唱／和聲分離除外）；舊版 Demucs v1/v2；
  Classic Download Center。「Open Model Folder」只顯示說明。
- 同一個 `UserData` 資料夾同時只能開啟一個視窗。
- 下載的 ZIP 解壓後第一次啟動，可能因 Windows 掃描檔案而需要約半分鐘。
- 偶爾可能出現 `REAL_STARTUP_FAILURE` 啟動失敗，再啟動一次通常即可。

macOS：

- 只支援 Apple Silicon；這個確切的版本尚未在 Mac 上執行過。MP3 輸出與變速、變調工具預期無法使用；Phase Swapper 與 Matchering 無法使用。
  ONNX Runtime 只用 CPU；Apple GPU（MPS）的表現依模型而定。
- 第一次開啟會被 Gatekeeper 攔下，需選「強制打開」（見 macOS 說明）。

### 授權

請見 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) 與每個下載檔內的 `Licenses` 資料夾。
免費提供並不表示可以商業使用。只授權非商業用途的 diffq 函式庫沒有內附，因此量化 Demucs 模型
`v3 | mdx_q` 與 `v3 | mdx_extra_q` 會在開始前提示無法使用；其他 Demucs 模型都可正常使用。

### 免責聲明

UVR5 Pro 為非官方衍生軟體，與 Ultimate Vocal Remover 原開發者及其他第三方元件提供者不存在官方合作或背書關係。  
本軟體免費提供，依現狀（AS IS）供使用者使用，不提供任何明示或默示擔保，包括但不限於適銷性、特定用途適用性及不侵權擔保。  
在適用法律允許的最大範圍內，開發者不對因使用或無法使用本軟體所造成的資料遺失、工作中斷、收益損失或其他相關損害承擔責任。  
使用者應自行備份重要資料，並確保有權使用、處理及散布所輸入的音訊與模型。  
本免責聲明不修改、取代或限制任何第三方授權條款，也不排除依法不得排除的責任。
