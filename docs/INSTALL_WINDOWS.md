# UVR5 Pro 1.0.0 for Windows — download and setup

[繁體中文](#繁體中文)

## English

### 1. Download

GitHub limits each release file to 2 GiB, so the Windows ZIP is published in two parts.
From the v1.0.0 release, download **all three** files into the same folder:

- `UVR5Pro_1.0.0_Windows_x64_Portable.zip.001`
- `UVR5Pro_1.0.0_Windows_x64_Portable.zip.002`
- `SHA256SUMS.txt`

### 2. Check the downloads

Open PowerShell in that folder and run:

```powershell
Get-FileHash .\UVR5Pro_1.0.0_Windows_x64_Portable.zip.00* -Algorithm SHA256
```

Each hash must match its line in `SHA256SUMS.txt`. Do not continue if any hash differs;
download that part again.

### 3. Join and extract

The two parts are simply the first and second half of one ZIP file. Use either method.

**Method A — 7-Zip (free, <https://www.7-zip.org/>):** right-click
`UVR5Pro_1.0.0_Windows_x64_Portable.zip.001` → 7-Zip → *Extract files…*, and extract to
a short path such as `C:\UVR5Pro\`. 7-Zip reads `.zip.002` automatically.

**Method B — no extra software:** open **Command Prompt** (press Win+R, type `cmd`, press
Enter), go to the download folder with `cd /d "<download folder>"`, and run:

```bat
copy /b UVR5Pro_1.0.0_Windows_x64_Portable.zip.001 + UVR5Pro_1.0.0_Windows_x64_Portable.zip.002 UVR5Pro_1.0.0_Windows_x64_Portable.zip
```

This command does not work as typed in PowerShell or Windows Terminal's PowerShell tab;
there, put `cmd /c ` in front of it.

Check the joined file:

```powershell
Get-FileHash .\UVR5Pro_1.0.0_Windows_x64_Portable.zip -Algorithm SHA256
```

It must match the `UVR5Pro_1.0.0_Windows_x64_Portable.zip` line in `SHA256SUMS.txt`. Then
right-click the ZIP → *Extract All…* and choose a short path such as `C:\UVR5Pro\`.

Use a short destination path: some files are nested deeply, and very long paths can make
Windows' built-in extraction fail.

If the joined ZIP's *Properties* window shows an **Unblock** checkbox, you may tick it before
extracting (only after the hash check passed). Otherwise the first start can take noticeably
longer while Windows scans the files; later starts are not affected.

### 4. Start

Double-click **`UVR5 Pro.cmd`** in the extracted folder (or run `UVR_Pro\UVR_Pro.exe`).

The program is not digitally signed, so Windows SmartScreen may show "Windows protected your
PC". Only if your hashes matched, choose *More info* → *Run anyway*.

On the first start UVR5 Pro asks once where to keep models (the *Model Store*). You can reuse
an existing UVR5 Pro model folder. Models are not included; Smart Separation downloads a model
you select only when you ask it to.

### 5. Where data is kept, updating and removal

- Settings, logs and default output: the `UserData` folder next to the program folder.
- Models: the Model Store folder you chose.
- To remove UVR5 Pro, close it and delete the extracted folder. Delete the Model Store folder
  separately if you no longer need the models.

### Requirements and limitations

- 64-bit x86 Windows 11 (tested); Windows 10 has not been tested. About 5.3 GB after
  extraction, plus model space.
- No separate runtime is normally needed. If Windows reports a missing VCRUNTIME140 or
  MSVCP140 DLL, install the Microsoft Visual C++ Redistributable (x64).
- NVIDIA GPU optional (CUDA). Without one, separation runs on the CPU.
- See the [release notes](../RELEASE_NOTES.md) for features that are not available.

---

## 繁體中文

### 1. 下載

GitHub 限制每個 Release 檔案不得超過 2 GiB，所以 Windows 版 ZIP 分成兩個檔案發布。
請從 v1.0.0 Release 把下面**三個檔案**下載到同一個資料夾：

- `UVR5Pro_1.0.0_Windows_x64_Portable.zip.001`
- `UVR5Pro_1.0.0_Windows_x64_Portable.zip.002`
- `SHA256SUMS.txt`

### 2. 核對下載檔

在該資料夾開啟 PowerShell，執行：

```powershell
Get-FileHash .\UVR5Pro_1.0.0_Windows_x64_Portable.zip.00* -Algorithm SHA256
```

每個雜湊值都必須與 `SHA256SUMS.txt` 中對應的一行相同。任何一個不同就不要繼續，請重新下載該檔案。

### 3. 合併與解壓

兩個檔案就是同一個 ZIP 的前半與後半，以下兩種方式擇一即可。

**方式 A — 7-Zip（免費，<https://www.7-zip.org/>）：** 在
`UVR5Pro_1.0.0_Windows_x64_Portable.zip.001` 上按右鍵 → 7-Zip →「解壓縮檔案…」，
解壓到短路徑，例如 `C:\UVR5Pro\`。7-Zip 會自動讀取 `.zip.002`。

**方式 B — 不安裝其他軟體：** 開啟「**命令提示字元**」（按 Win+R，輸入 `cmd` 後按 Enter），
以 `cd /d "<下載資料夾>"` 切換到下載資料夾，然後執行：

```bat
copy /b UVR5Pro_1.0.0_Windows_x64_Portable.zip.001 + UVR5Pro_1.0.0_Windows_x64_Portable.zip.002 UVR5Pro_1.0.0_Windows_x64_Portable.zip
```

這行指令不能直接在 PowerShell（或 Windows 終端機的 PowerShell 分頁）中執行；
在 PowerShell 中請在前面加上 `cmd /c `。

核對合併後的檔案：

```powershell
Get-FileHash .\UVR5Pro_1.0.0_Windows_x64_Portable.zip -Algorithm SHA256
```

結果必須與 `SHA256SUMS.txt` 中 `UVR5Pro_1.0.0_Windows_x64_Portable.zip` 那一行相同。
接著在 ZIP 上按右鍵 →「解壓縮全部…」，選擇短路徑，例如 `C:\UVR5Pro\`。

請使用短的目的地路徑：部分檔案的路徑很深，路徑過長時 Windows 內建的解壓可能失敗。

若合併後 ZIP 的「內容」視窗有「解除封鎖」核取方塊，可在雜湊核對通過後勾選再解壓；
否則第一次啟動時 Windows 會花較久時間掃描檔案，之後的啟動不受影響。

### 4. 啟動

在解壓出的資料夾中按兩下 **`UVR5 Pro.cmd`**（或執行 `UVR_Pro\UVR_Pro.exe`）。

程式沒有數位簽章，Windows SmartScreen 可能顯示「Windows 已保護您的電腦」。
只有在雜湊值核對相符時，才選「其他資訊」→「仍要執行」。

第一次啟動時只會詢問一次模型要放在哪裡（Model Store），可以沿用既有的 UVR5 Pro 模型資料夾。
程式不含模型；只有在你要求時，Smart Separation 才會下載你選擇的模型。

### 5. 資料位置、更新與移除

- 設定、紀錄與預設輸出：程式資料夾旁的 `UserData` 資料夾。
- 模型：你選擇的 Model Store 資料夾。
- 移除：關閉程式後刪除整個解壓資料夾即可；不再需要模型時，另行刪除 Model Store 資料夾。

### 需求與限制

- 64 位元 x86 的 Windows 11（已測試）；Windows 10 尚未測試。解壓後約 5.3 GB，另需模型空間。
- 一般不需要另外安裝執行環境。若 Windows 回報缺少 VCRUNTIME140 或 MSVCP140 DLL，
  請安裝 Microsoft Visual C++ 可轉散發套件（x64）。
- NVIDIA 顯示卡為選用（CUDA）；沒有時以 CPU 分離。
- 無法使用的功能請見 [Release Notes](../RELEASE_NOTES.md)。
