# UVR5 Pro 1.0.0 — 非官方版本（Unofficial Build）

[English](README.md)

UVR5 Pro 是 [Ultimate Vocal Remover GUI](https://github.com/Anjok07/ultimatevocalremovergui)
v5.6.1 的**非官方**建置，另外加入「Smart Separation（智慧分離）」視窗。
本程式**不是**由 Ultimate Vocal Remover 原作者製作，也未經其背書或支援；
UVR5 Pro 的問題請不要回報給官方 UVR 專案。

UVR5 Pro 免費提供，依「現狀」提供，不附任何形式的保證。

本儲存庫只有說明文件。程式與其 SHA-256 檢查碼（`SHA256SUMS.txt`）放在
[v1.0.0 Release](../../releases/tag/v1.0.0) 的附件中；本儲存庫不包含程式原始碼。

## 原始專案與致謝

> 沒有 Ultimate Vocal Remover 專案的心血，就沒有 UVR5 Pro。

UVR5 Pro 以 [Ultimate Vocal Remover GUI](https://github.com/Anjok07/ultimatevocalremovergui)
v5.6.1 為基礎，介面、分離引擎與模型支援都來自原始專案。
特別感謝原版的核心開發者 [Anjok07](https://github.com/Anjok07) 與 [aufr33](https://github.com/aufr33)，
以及所有參與原版開發、模型訓練與音訊分離研究的貢獻者。
UVR 可使用的模型來自許多不同的作者與專案，並非全部出自同一個團隊。

- **UVR5 Pro 新增的部分：**「Smart Separation（智慧分離）」視窗，依你選擇的音源、目標與偏好
  引導推薦模型。其餘部分都是原始專案的成果。
- **獨立維護的非官方版本：** UVR5 Pro 由個人獨立維護，未經原作者的官方背書。
- **原始專案：** <https://github.com/Anjok07/ultimatevocalremovergui>
- **[支持原始專案（Support the Original Project）](https://www.buymeacoffee.com/uvr5)**（UVR 官方提供的贊助連結）

## 下載

| 平台 | Release 附件 | 說明 |
| --- | --- | --- |
| Windows x64 | `UVR5Pro_1.0.0_Windows_x64_Portable.zip.001` ＋ `.zip.002` | 同一個 ZIP 分成兩個檔案，**兩個都要下載**。見 [Windows 說明](docs/INSTALL_WINDOWS.md)。 |
| macOS（Apple Silicon） | `UVR5Pro_1.0.0_macOS_arm64.zip` | 未經 Apple 公證。見 [macOS 說明](docs/INSTALL_MACOS.md)。 |
| 檢查碼 | `SHA256SUMS.txt` | 每個 Release 附件，以及合併後 Windows ZIP 的 SHA-256。 |
| LGPL 原始碼 | `libsndfile-1.2.0.tar.xz`、`lame-3.100.tar.gz`、`mpg123-1.29.3.tar.bz2`、`mpg123-1.30.2.tar.bz2` | 兩個平台內附的 LGPL 音訊函式庫原始碼（執行 UVR5 Pro 不需要）。 |
| LGPL 建置腳本 | `lgpl-build-scripts-1.0.0.zip` | 上游當時建置這些函式庫所用的腳本與 vcpkg port 檔，附版本對應說明（執行 UVR5 Pro 不需要）。 |

開啟前請先用 `SHA256SUMS.txt` 核對每個下載的檔案。

## 包含內容

- UVR v5.6.1 的介面與分離引擎，以及 Smart Separation。
- 完整的內附執行環境（Python、PyTorch 與其他函式庫）。不需要另外安裝 Python 或任何執行環境。

## 不包含的內容

- **不含任何 AI 模型。** 只有在你要求時，Smart Separation 才會從你所選模型的原始公開來源下載該模型；
  也可以沿用既有的 UVR 模型資料夾。每個模型有各自的授權與使用條款，使用前請自行確認。
- 不含 FFmpeg、Rubber Band、SoX；需要它們的功能無法使用（見 [Release Notes](RELEASE_NOTES.md)）。
- 沒有自動更新、遙測或使用統計。

## 系統需求（摘要）

- **Windows：** 64 位元 x86 的 Windows 11（已測試）；Windows 10 尚未測試。解壓後程式約 5.3 GB，
  另需模型空間（建議 20 GB 以上）。NVIDIA 顯示卡為選用；沒有時以 CPU 分離。
- **macOS：** Apple Silicon（M 系列）Mac；不支援 Intel Mac。程式宣告的最低系統為 macOS 12.3。
  程式約 1.3 GB，另需模型空間。這個確切的 macOS 版本尚未在 Mac 上執行過
  （1.0.0 先前的測試版曾在一台 Apple Silicon Mac 上試用）。

## 簽章狀態

- **Windows：** 程式**沒有數位簽章**。第一次啟動前 Windows SmartScreen 可能顯示警告。
- **macOS：** 只有 **ad-hoc（臨時）簽章**，**沒有 Apple Developer ID 簽章，也沒有經過 Apple 公證**。
  第一次開啟會被 Gatekeeper 攔下，需在「系統設定」中手動允許。
  [macOS 說明](docs/INSTALL_MACOS.md) 使用 Apple 官方的「強制打開」步驟；
  完全不需要關閉 Gatekeeper 或系統完整性保護（SIP）。

## 授權

UVR5 Pro 以 Ultimate Vocal Remover GUI 為基礎；其作者以 MIT 授權發布
（「Copyright (c) 2022 Ultimate Vocal Remover」）。每個下載檔都內含第三方元件，各自適用其授權；
請見 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) 與下載檔內的 `Licenses` 資料夾。
Windows 版內附的 Intel 執行庫（oneMKL、OpenMP 執行庫、oneTBB）依 Intel 自己的授權條款轉散發，
該條款完整適用，下方的免責聲明不會改變它們。

免費提供並不表示可以商業使用：內附元件與每個模型都有各自的條款。只授權非商業用途的 diffq
函式庫沒有內附，因此量化 Demucs 模型 `v3 | mdx_q` 與 `v3 | mdx_extra_q` 無法使用。要用於商業用途前，請先閱讀
[Commercial use](THIRD_PARTY_NOTICES.md#commercial-use) 一節並自行確認。

## 免責聲明

UVR5 Pro 為非官方衍生軟體，與 Ultimate Vocal Remover 原開發者及其他第三方元件提供者不存在官方合作或背書關係。  
本軟體免費提供，依現狀（AS IS）供使用者使用，不提供任何明示或默示擔保，包括但不限於適銷性、特定用途適用性及不侵權擔保。  
在適用法律允許的最大範圍內，開發者不對因使用或無法使用本軟體所造成的資料遺失、工作中斷、收益損失或其他相關損害承擔責任。  
使用者應自行備份重要資料，並確保有權使用、處理及散布所輸入的音訊與模型。  
本免責聲明不修改、取代或限制任何第三方授權條款，也不排除依法不得排除的責任。

## 致謝

Ultimate Vocal Remover 的介面、模型與研究成果全部歸功於 UVR 開發者，以及官方
[UVR README](https://github.com/Anjok07/ultimatevocalremovergui#readme) 中列出的作者。
