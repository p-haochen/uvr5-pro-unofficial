# Third-party notices — UVR5 Pro 1.0.0

UVR5 Pro is an unofficial build of Ultimate Vocal Remover GUI v5.6.1 and is not affiliated
with or endorsed by its developers. It is distributed free of charge and without warranty.

The complete notices and license texts ship inside each download:

- Windows: `UVR_Pro/Licenses/` (start with `THIRD_PARTY_NOTICES.txt`)
- macOS: `UVR5 Pro.app/Contents/Resources/Licenses/` (a copy of `THIRD_PARTY_NOTICES.txt` is
  also next to the app in the ZIP)

Bundled Python distributions keep their license files in their `*.dist-info` folders. For
distributions published without a license file, the texts are in
`ADDITIONAL-PACKAGE-LICENSES.txt` in the same Licenses folder.
This page summarises the components whose licenses carry conditions beyond keeping a copyright
notice. It is not legal advice.

## Ultimate Vocal Remover GUI

MIT License — "Copyright (c) 2022 Ultimate Vocal Remover" (`UVR-MIT-LICENSE.txt`).

## Commercial use

UVR5 Pro is free of charge. That is not a statement that UVR5 Pro, a bundled component or any
model may be used for commercial purposes:

- **diffq is not included.** diffq is licensed for non-commercial use only
  ([CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/)). It is needed only by the
  quantized Demucs v3 models `v3 | mdx_q` and `v3 | mdx_extra_q`, so UVR5 Pro does not ship it and
  refuses those two models before anything starts. Every other Demucs model works without it.
- **Bundled components** keep their own licenses (see below). Some of them, such as the NVIDIA and
  Intel runtime libraries on Windows, may be used only as part of this application.
- **Models** are not part of UVR5 Pro, and each one has its own license and terms.

If you plan any commercial use, check these licenses yourself first.

## Components with additional conditions

| Component | License | Notes |
| --- | --- | --- |
| libsndfile 1.2.0 with mpg123 and LAME 3.100 (inside python-soundfile 0.12.1) | GNU LGPL 2.1 or later (mpg123: LGPL 2.1; LAME: LGPL 2 or later) | Separate, replaceable library. The corresponding source code and the scripts used to build the library are attached to the v1.0.0 release (see below). Each package's notices explain how to use a modified library. The same library also contains libogg, libvorbis, FLAC and Opus under BSD licenses (full texts in `libsndfile-codecs-BSD.txt` in each package's Licenses folder, and in the last section). |
| autocommand 2.2.2 (inside setuptools) | GNU LGPL 3.0 | Source files shipped; LGPL 3.0 and GPL 3.0 texts included. |
| certifi, tqdm | MPL 2.0 (tqdm partly MIT) | Source files shipped unmodified. |
| NVIDIA CUDA runtime libraries and cuDNN (Windows, inside PyTorch) | NVIDIA CUDA Toolkit EULA, cuDNN SLA | Redistributed unmodified and only as part of this application. |
| Intel oneAPI Math Kernel Library 2021.4.0, Intel OpenMP runtime 2021.4.0 and oneTBB 2021.13.1 (Windows) | oneMKL and the OpenMP runtime: Intel Simplified Software License (Version February 2020); oneTBB: Intel Simplified Software License (Version October 2022) | Redistributed unmodified, in binary form. The OpenMP runtime DLLs are taken from Intel's redistributable NuGet package `intelopenmp.redist.win` 2021.4.0.3556. Full texts: `Licenses/Intel-Simplified-Software-License-2020-02.txt`, `mkl-2021.4.0.dist-info/LICENSE.txt`, `tbb-2021.13.1.dist-info/LICENSE.txt`. Intel's terms apply in full and are not changed by UVR5 Pro's disclaimer. The Intel OpenMP GPU-offload plugins are not included. |
| Microsoft DirectML and Visual C++ runtime (Windows) | Microsoft terms (torch-directml: MIT) | Redistributed unmodified. |
| Montserrat font | SIL Open Font License 1.1 | Copyright 2011 The Montserrat Project Authors. |
| Python 3.11 runtime | PSF License, plus OpenSSL 3 (Apache 2.0), libffi, expat, bzip2, zlib, mpdecimal and other software incorporated in CPython | Texts included in each package. |

All other bundled Python distributions use permissive licenses (MIT, BSD, Apache 2.0, ISC, PSF,
HPND and similar).

## Source code of the LGPL components

The release attaches these source archives of the LGPL components in the bundled libsndfile
library, exactly as published by their projects:

- `libsndfile-1.2.0.tar.xz`
- `lame-3.100.tar.gz`
- `mpg123-1.29.3.tar.bz2` (Windows build) and `mpg123-1.30.2.tar.bz2` (macOS build)

`lgpl-build-scripts-1.0.0.zip` contains, unchanged, the build scripts and vcpkg port recipes that
the upstream libsndfile-binaries project used to build the two shipped libraries. It also maps
each shipped library to the upstream build that produced it and records how the source
archives were verified.

These files will also be provided on request through this repository's issue tracker for at
least three years after the release.

## BSD licenses of the codecs inside libsndfile

The libsndfile library in both packages statically contains these libraries:

- libogg 1.3.5
- libvorbis 1.3.7
- FLAC: 1.3.4 in the Windows build, 1.4.2 in the macOS build
- Opus 1.3.1

Their licenses follow. The same texts ship in each package as
`Licenses/libsndfile-codecs-BSD.txt` and are also in `lgpl-build-scripts-1.0.0.zip`
(`codec-licenses/`).

### libogg 1.3.5

```text
Copyright (c) 2002, Xiph.org Foundation

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions
are met:

- Redistributions of source code must retain the above copyright
notice, this list of conditions and the following disclaimer.

- Redistributions in binary form must reproduce the above copyright
notice, this list of conditions and the following disclaimer in the
documentation and/or other materials provided with the distribution.

- Neither the name of the Xiph.org Foundation nor the names of its
contributors may be used to endorse or promote products derived from
this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
``AS IS'' AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
A PARTICULAR PURPOSE ARE DISCLAIMED.  IN NO EVENT SHALL THE FOUNDATION
OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY
THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
```

### libvorbis 1.3.7

```text
Copyright (c) 2002-2020 Xiph.org Foundation

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions
are met:

- Redistributions of source code must retain the above copyright
notice, this list of conditions and the following disclaimer.

- Redistributions in binary form must reproduce the above copyright
notice, this list of conditions and the following disclaimer in the
documentation and/or other materials provided with the distribution.

- Neither the name of the Xiph.org Foundation nor the names of its
contributors may be used to endorse or promote products derived from
this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
``AS IS'' AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
A PARTICULAR PURPOSE ARE DISCLAIMED.  IN NO EVENT SHALL THE FOUNDATION
OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY
THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
```

### FLAC (libFLAC) 1.3.4 and 1.4.2

The 1.3.4 text reads "Copyright (C) 2011-2016  Xiph.Org Foundation"; the 1.4.2 text is shown.

```text
Copyright (C) 2000-2009  Josh Coalson
Copyright (C) 2011-2022  Xiph.Org Foundation

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions
are met:

- Redistributions of source code must retain the above copyright
notice, this list of conditions and the following disclaimer.

- Redistributions in binary form must reproduce the above copyright
notice, this list of conditions and the following disclaimer in the
documentation and/or other materials provided with the distribution.

- Neither the name of the Xiph.Org Foundation nor the names of its
contributors may be used to endorse or promote products derived from
this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
``AS IS'' AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
A PARTICULAR PURPOSE ARE DISCLAIMED.  IN NO EVENT SHALL THE FOUNDATION OR
CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL,
EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO,
PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR
PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF
LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING
NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS
SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
```

### Opus 1.3.1

```text
Copyright 2001-2011 Xiph.Org, Skype Limited, Octasic,
                    Jean-Marc Valin, Timothy B. Terriberry,
                    CSIRO, Gregory Maxwell, Mark Borgerding,
                    Erik de Castro Lopo

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions
are met:

- Redistributions of source code must retain the above copyright
notice, this list of conditions and the following disclaimer.

- Redistributions in binary form must reproduce the above copyright
notice, this list of conditions and the following disclaimer in the
documentation and/or other materials provided with the distribution.

- Neither the name of Internet Society, IETF or IETF Trust, nor the
names of specific contributors, may be used to endorse or promote
products derived from this software without specific prior written
permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
``AS IS'' AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT OWNER
OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL,
EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO,
PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR
PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF
LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING
NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS
SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

Opus is subject to the royalty-free patent licenses which are
specified at:

Xiph.Org Foundation:
https://datatracker.ietf.org/ipr/1524/

Microsoft Corporation:
https://datatracker.ietf.org/ipr/1914/

Broadcom Corporation:
https://datatracker.ietf.org/ipr/1526/
```

## Not included

- No model weights. Models downloaded through Smart Separation come from their original public
  sources and keep their own licenses and terms.
- No FFmpeg, Rubber Band or SoX.
- matchering (GPL v3) is not included: the upstream Matchering tool cannot run with the published
  matchering library, so UVR5 Pro marks it unavailable.
