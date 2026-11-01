# UVR5 Pro 1.0.0 — Unofficial Build

[繁體中文說明](README.zh-TW.md)

UVR5 Pro is an **unofficial** build of
[Ultimate Vocal Remover GUI](https://github.com/Anjok07/ultimatevocalremovergui) v5.6.1
with an added *Smart Separation* window. It is **not** made, endorsed or supported by the
Ultimate Vocal Remover developers. Please do not report UVR5 Pro problems to the official
UVR project.

UVR5 Pro is free of charge. It is provided "as is", without warranty of any kind.

This repository contains only documentation. The programs and their SHA-256 checksums
(`SHA256SUMS.txt`) are attached to the [v1.0.0 release](../../releases/tag/v1.0.0); this
repository does not contain the program source code.

## Original Project & Acknowledgements

> UVR5 Pro exists because of the work of the Ultimate Vocal Remover project.

UVR5 Pro is based on [Ultimate Vocal Remover GUI](https://github.com/Anjok07/ultimatevocalremovergui)
v5.6.1. Its interface, separation engines and model support all come from the original project.
Special thanks to its core developers, [Anjok07](https://github.com/Anjok07) and
[aufr33](https://github.com/aufr33), and to everyone who has contributed to the original
application, to model training and to audio source separation research. The models UVR can use
come from many different authors and projects, not from a single team.

- **What UVR5 Pro adds:** the *Smart Separation* window, a guided workflow that recommends models
  for a chosen source, goal and priority. Everything else is the work of the original project.
- **Independent and unofficial:** UVR5 Pro is maintained independently and is not endorsed by the
  original authors.
- **Original project:** <https://github.com/Anjok07/ultimatevocalremovergui>
- **[Support the Original Project](https://www.buymeacoffee.com/uvr5)** (the official UVR donation
  link)

## Downloads

| Platform | Release assets | Notes |
| --- | --- | --- |
| Windows x64 | `UVR5Pro_1.0.0_Windows_x64_Portable.zip.001` + `.zip.002` | Two parts of one ZIP; download **both**. See [Windows guide](docs/INSTALL_WINDOWS.md). |
| macOS on Apple Silicon | `UVR5Pro_1.0.0_macOS_arm64.zip` | Not notarized. See [macOS guide](docs/INSTALL_MACOS.md). |
| Checksums | `SHA256SUMS.txt` | SHA-256 of every release asset and of the joined Windows ZIP. |
| LGPL source code | `libsndfile-1.2.0.tar.xz`, `lame-3.100.tar.gz`, `mpg123-1.29.3.tar.bz2`, `mpg123-1.30.2.tar.bz2` | Source of the LGPL audio libraries bundled in both packages (not needed to run UVR5 Pro). |
| LGPL build scripts | `lgpl-build-scripts-1.0.0.zip` | The upstream scripts and recipes that built those libraries, with a version map (not needed to run UVR5 Pro). |

Verify every download against `SHA256SUMS.txt` before opening it.

## What is included

- The UVR v5.6.1 interface and separation engines, plus Smart Separation.
- A complete private runtime (Python, PyTorch and the other libraries). You do not need to
  install Python or any other runtime.

## What is not included

- **No AI models.** Models are not bundled. Smart Separation downloads a model you select
  from that model's original public source only when you ask it to, and an existing folder
  of UVR models can be reused. Each model keeps its own license and terms; check them before
  use.
- No FFmpeg, Rubber Band or SoX. Features that need them are unavailable (see the
  [release notes](RELEASE_NOTES.md)).
- No automatic updates, telemetry or analytics.

## System requirements (summary)

- **Windows:** 64-bit x86 Windows 11 (tested); Windows 10 has not been tested. About 5.3 GB
  for the extracted program, plus space for models (20 GB or more recommended). An NVIDIA
  GPU is optional; without one, separation runs on the CPU.
- **macOS:** a Mac with Apple Silicon (M-series). Intel Macs are not supported. The app
  declares macOS 12.3 as its minimum. About 1.3 GB for the app, plus space for models.
  This exact macOS build has not yet been run on a Mac (earlier 1.0.0 test builds were tried
  on one Apple Silicon Mac).

## Signing status

- **Windows:** the program is **not digitally signed**. Windows SmartScreen may warn before
  the first start.
- **macOS:** the app carries only an **ad-hoc signature**. It has **no Apple Developer ID
  signature and is not notarized by Apple**. Gatekeeper blocks the first start until you
  allow it in System Settings. The [macOS guide](docs/INSTALL_MACOS.md) uses Apple's own
  "Open Anyway" step; you never need to disable Gatekeeper or System Integrity Protection.

## Licenses

UVR5 Pro is built on Ultimate Vocal Remover GUI, which its authors publish under the MIT
license ("Copyright (c) 2022 Ultimate Vocal Remover"). Every package bundles third-party
components under their own licenses; see [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)
and the `Licenses` folder inside each download. On Windows, the Intel runtime libraries
(oneMKL, the OpenMP runtime, oneTBB) are redistributed under Intel's own license terms, which
apply in full; the disclaimer below does not change them.

Free of charge is not a statement that commercial use is allowed: bundled components and each
model have their own terms. The non-commercial diffq library is not included, so the quantized
Demucs models `v3 | mdx_q` and `v3 | mdx_extra_q` are unavailable. See
[Commercial use](THIRD_PARTY_NOTICES.md#commercial-use) before using UVR5 Pro commercially.

## Disclaimer

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

## Credits

All credit for Ultimate Vocal Remover, its interface, models and research goes to the UVR
developers and to the authors credited in the official
[UVR README](https://github.com/Anjok07/ultimatevocalremovergui#readme).
