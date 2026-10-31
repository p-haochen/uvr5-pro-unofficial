# UVR5 Pro 1.0.0 for macOS (Apple Silicon) — download and setup

[繁體中文](#繁體中文)

## English

### Before you start

- Requires a Mac with Apple Silicon (M-series chip). Intel Macs and Rosetta are not supported.
- The app declares macOS 12.3 as its minimum. This exact build has not yet been run on a Mac;
  earlier 1.0.0 test builds were tried on one Apple Silicon Mac. Other macOS versions and Mac
  models have not been tested.
- **Signing:** the app has only an *ad-hoc* signature. It is **not** signed with an Apple
  Developer ID and **not** notarized by Apple, so Apple has not checked it. macOS blocks the
  first start until you allow it as shown below. You never need to disable Gatekeeper or
  System Integrity Protection, and you never need `sudo`.

### 1. Download and check

Download `UVR5Pro_1.0.0_macOS_arm64.zip` and `SHA256SUMS.txt` from the v1.0.0 release. In
Terminal, run (adjust the folder if needed):

```sh
cd ~/Downloads
shasum -a 256 UVR5Pro_1.0.0_macOS_arm64.zip
```

The result must match the line for this file in `SHA256SUMS.txt`. Do not continue otherwise.

### 2. Install

1. Double-click the ZIP in Finder to unpack it.
2. Drag **UVR5 Pro.app** into the **Applications** folder. Move it there *before* the first
   start; opening it directly from Downloads can make macOS run it from a temporary read-only
   location.

### 3. First start (Apple's "Open Anyway")

1. Double-click **UVR5 Pro** in Applications. macOS reports that it cannot verify the app.
   Click **Done** (not *Move to Trash*).
2. Open **System Settings → Privacy & Security**, scroll to *Security*, and click
   **Open Anyway** next to the message about UVR5 Pro.
3. Confirm with your password or Touch ID, then click **Open**.

- On macOS 13 and 14 you can instead Control-click the app in Finder → *Open* → *Open*.
  From macOS 15 only the System Settings way works.
- The *Open Anyway* button appears for about an hour after the block; if it is gone, repeat
  step 1.
- The first check of the roughly 1.3 GB app can take a minute or more ("Verifying…").
- Allowing the app means you chose to trust this unnotarized build; it is not an Apple check.
- If, after allowing the app, macOS shows further warnings about individual `.so` or `.dylib`
  files, do not allow them one by one. Quit the app; this build cannot be used on that Mac.

When UVR5 Pro first reads Downloads, Desktop, Documents or an external drive, macOS asks for
permission; allow it if you want to use files there.

### 4. Models and data

- No models are included. On the first start UVR5 Pro asks where to keep models. Smart
  Separation downloads a model you select only when you ask it to; you can also reuse an
  existing folder of UVR models.
- Settings: `~/Library/Application Support/UVR5 Pro`. Temporary files:
  `~/Library/Caches/UVR5 Pro`. Logs (kept on your Mac only): `~/Library/Logs/UVR5 Pro`.
  Default output: `~/Music/UVR5 Pro/Output`.
- To remove UVR5 Pro, delete the app; delete the folders above and your model folder if you
  no longer need them.

### Limitations on macOS

- No FFmpeg: MP3 output is expected to fail; decoding of non-WAV input relies on macOS and is
  not fully tested.
- No Rubber Band or SoX: time-stretch and pitch-change tools are expected not to work.
- ONNX Runtime runs on the CPU only. Apple-GPU (MPS) results and speed depend on the model;
  if GPU output sounds wrong, turn off *GPU Conversion* and use the CPU.
- macOS cannot stop other programs from changing an input file during separation; please do
  not edit input files while they are being processed.
- No automatic updates and no DMG installer.

---

## 繁體中文

### 開始之前

- 需要 Apple Silicon（M 系列晶片）的 Mac；不支援 Intel Mac，也不能用 Rosetta 執行。
- 程式宣告的最低系統為 macOS 12.3。這個確切的版本尚未在 Mac 上執行過；1.0.0 先前的測試版曾在一台
  Apple Silicon Mac 上試用。其他 macOS 版本與 Mac 機型尚未測試。
- **簽章：** 只有 ad-hoc（臨時）簽章，**沒有** Apple Developer ID 簽章，也**沒有**經過 Apple 公證，
  也就是 Apple 沒有檢查過這個程式。第一次開啟會被 macOS 攔下，需依下方步驟手動允許。
  完全不需要關閉 Gatekeeper 或系統完整性保護（SIP），也不需要使用 `sudo`。

### 1. 下載與核對

從 v1.0.0 Release 下載 `UVR5Pro_1.0.0_macOS_arm64.zip` 與 `SHA256SUMS.txt`。
在「終端機」執行（資料夾不同時請自行修改）：

```sh
cd ~/Downloads
shasum -a 256 UVR5Pro_1.0.0_macOS_arm64.zip
```

結果必須與 `SHA256SUMS.txt` 中該檔案那一行相同，否則請不要繼續。

### 2. 安裝

1. 在 Finder 中按兩下 ZIP 解壓。
2. 把 **UVR5 Pro.app** 拖到「**應用程式**」資料夾。請在第一次開啟**之前**移過去；
   直接在「下載項目」中開啟，macOS 可能會把它放到暫時的唯讀位置執行。

### 3. 第一次開啟（Apple 官方的「強制打開」）

1. 在「應用程式」中按兩下 **UVR5 Pro**，macOS 會表示無法驗證此 App，按「**完成**」（不要按「丟到垃圾桶」）。
2. 打開「**系統設定 › 隱私權與安全性**」，捲到「安全性」區塊，在 UVR5 Pro 的訊息旁按「**強制打開**」。
3. 用登入密碼或 Touch ID 確認，再按「**打開**」。

- macOS 13、14 也可以在 Finder 中按住 Control 點 App →「打開」→「打開」；macOS 15 起只能用系統設定的方式。
- 「強制打開」按鈕只在被攔下後約一小時內出現；不見時請重做步驟 1。
- 第一次檢查約 1.3 GB 的程式可能需要一分鐘以上（顯示「正在驗證…」）。
- 允許開啟代表你自行選擇信任這個未公證的版本，並不代表 Apple 已檢查過它。
- 若允許後 macOS 又針對個別 `.so` 或 `.dylib` 檔案跳出警告，請不要逐一允許；
  請結束程式，表示此版本無法在該台 Mac 上使用。

UVR5 Pro 第一次讀取「下載項目」「桌面」「文件」或外接硬碟時，macOS 會詢問權限；需要使用那些位置的檔案時請允許。

### 4. 模型與資料

- 不含任何模型。第一次開啟時會詢問模型要放在哪裡。只有在你要求時，Smart Separation 才會下載你選擇的模型；
  也可以沿用既有的 UVR 模型資料夾。
- 設定：`~/Library/Application Support/UVR5 Pro`；暫存：`~/Library/Caches/UVR5 Pro`；
  紀錄（只存在你的 Mac）：`~/Library/Logs/UVR5 Pro`；預設輸出：`~/Music/UVR5 Pro/Output`。
- 移除：刪除 App；不再需要時，另行刪除上述資料夾與模型資料夾。

### macOS 版限制

- 不含 FFmpeg：MP3 輸出預期會失敗；非 WAV 輸入由 macOS 解碼，尚未完整測試。
- 不含 Rubber Band、SoX：變速、變調工具預期無法使用。
- ONNX Runtime 只用 CPU。Apple GPU（MPS）的結果與速度依模型而定；若 GPU 輸出聽起來不正常，
  請關閉「GPU Conversion」改用 CPU。
- macOS 無法禁止其他程式在分離期間改寫輸入檔；處理期間請不要編輯輸入檔。
- 沒有自動更新，也沒有 DMG 安裝檔。
