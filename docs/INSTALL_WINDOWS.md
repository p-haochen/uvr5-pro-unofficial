# UVR5 Pro 1.0.0 for Windows — download and setup

[繁體中文](#繁體中文)

## English

### 1. Download

The Windows program is published in two forms with **exactly the same files inside**
(16,177 files, checked file by file with SHA-256). Choose one.

- **Recommended — one file:** `UVR5Pro_1.0.0_Windows_x64_Portable.7z` (1,481,107,038 bytes, about 1.4 GiB), plus
  `SHA256SUMS.txt`.
- **Alternative — two-part ZIP:** `UVR5Pro_1.0.0_Windows_x64_Portable.zip.001` and
  `.zip.002` (about 2.9 GB together), plus `SHA256SUMS.txt`. GitHub limits each release file
  to 2 GiB, so this ZIP is split in two. These are the original v1.0.0 files and their
  checksums are unchanged; see [Two-part ZIP](#two-part-zip-alternative) below.

Download the files into the same folder.

### 2. Check the download

Open PowerShell in that folder and run:

```powershell
Get-FileHash .\UVR5Pro_1.0.0_Windows_x64_Portable.7z -Algorithm SHA256
```

The hash must match the `UVR5Pro_1.0.0_Windows_x64_Portable.7z` line in `SHA256SUMS.txt`.
Do not continue if it differs; download the file again.

### 3. Extract

If the `.7z` file's *Properties* window shows an **Unblock** checkbox, you may tick it before
extracting (only after the hash check passed). Otherwise the first start can take noticeably
longer while Windows scans the files; later starts are not affected.

Extract to a short path such as `C:\UVR5Pro\`: some files are nested deeply, and very long
paths can make extraction fail. Use either tool:

- **Windows 11 without extra software:** right-click the `.7z` file → *Extract All…*, and
  choose `C:\UVR5Pro\` as the destination. Recent Windows 11 versions open `.7z` files natively
  (tested on Windows 11 build 26200). Built-in extraction is slower than 7-Zip
  (in our test about 3.5 minutes, against under half a minute with 7-Zip).
- **7-Zip (free, <https://www.7-zip.org/>):** right-click the `.7z` file → 7-Zip →
  *Extract files…*, and extract to `C:\UVR5Pro\`.

Windows 10 and older Windows 11 versions cannot open `.7z` files without 7-Zip; there, use
7-Zip or the two-part ZIP.

You get the folder `UVR5Pro_1.0.0_Windows_x64_Portable` (about 5.3 GB).

### Two-part ZIP (alternative)

The two parts are simply the first and second half of one ZIP file. First check both parts:

```powershell
Get-FileHash .\UVR5Pro_1.0.0_Windows_x64_Portable.zip.00* -Algorithm SHA256
```

Each hash must match its line in `SHA256SUMS.txt`. Do not continue if any hash differs;
download that part again. Then use either method.

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

Windows 版提供兩種下載方式，**內含的檔案完全相同**（16,177 個檔案，已用 SHA-256 逐檔比對）。擇一即可。

- **推薦：單一檔案** `UVR5Pro_1.0.0_Windows_x64_Portable.7z`（1,481,107,038 位元組，約 1.4 GiB），以及 `SHA256SUMS.txt`。
- **替代：分成兩卷的 ZIP** `UVR5Pro_1.0.0_Windows_x64_Portable.zip.001` 與 `.zip.002`
  （合計約 2.9 GB），以及 `SHA256SUMS.txt`。GitHub 限制每個 Release 檔案不得超過 2 GiB，
  所以這個 ZIP 分成兩個檔案。它們就是原本 v1.0.0 的檔案，檢查碼沒有改變；見下方
  [分卷 ZIP](#分卷-zip替代方式)。

請把檔案下載到同一個資料夾。

### 2. 核對下載檔

在該資料夾開啟 PowerShell，執行：

```powershell
Get-FileHash .\UVR5Pro_1.0.0_Windows_x64_Portable.7z -Algorithm SHA256
```

結果必須與 `SHA256SUMS.txt` 中 `UVR5Pro_1.0.0_Windows_x64_Portable.7z` 那一行相同。
不同就不要繼續，請重新下載。

### 3. 解壓

若 `.7z` 檔的「內容」視窗有「解除封鎖」核取方塊，可在雜湊核對通過後勾選再解壓；
否則第一次啟動時 Windows 會花較久時間掃描檔案，之後的啟動不受影響。

請解壓到短路徑，例如 `C:\UVR5Pro\`：部分檔案的路徑很深，路徑過長時解壓可能失敗。以下工具擇一：

- **Windows 11，不安裝其他軟體：** 在 `.7z` 檔上按右鍵 →「解壓縮全部…」，目的地選 `C:\UVR5Pro\`。
  較新的 Windows 11 版本內建可開啟 `.7z`（已在 Windows 11 組建 26200 測試）。
  內建解壓比 7-Zip 慢（我們的測試約 3.5 分鐘，7-Zip 不到半分鐘）。
- **7-Zip（免費，<https://www.7-zip.org/>）：** 在 `.7z` 檔上按右鍵 → 7-Zip →「解壓縮檔案…」，
  解壓到 `C:\UVR5Pro\`。

Windows 10 與較舊的 Windows 11 版本不安裝 7-Zip 就無法開啟 `.7z`，請改用 7-Zip 或分卷 ZIP。

解壓後會得到 `UVR5Pro_1.0.0_Windows_x64_Portable` 資料夾（約 5.3 GB）。

### 分卷 ZIP（替代方式）

兩個檔案就是同一個 ZIP 的前半與後半。請先核對兩個檔案：

```powershell
Get-FileHash .\UVR5Pro_1.0.0_Windows_x64_Portable.zip.00* -Algorithm SHA256
```

每個雜湊值都必須與 `SHA256SUMS.txt` 中對應的一行相同。任何一個不同就不要繼續，請重新下載該檔案。
接著以下兩種方式擇一即可。

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
