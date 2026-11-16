# Third-party notices

Biverse itself is MIT-licensed (see `LICENSE`). It bundles or uses the following components.

| Component | Use | Licence |
|---|---|---|
| [sherpa-onnx](https://github.com/k2-fsa/sherpa-onnx) 2.0.1 | Speech recognition engine (Kroko, Nemotron, Parakeet) | Apache License 2.0 |
| [ONNX Runtime](https://github.com/microsoft/onnxruntime) (bundled by sherpa-onnx) | Neural network runtime | MIT |
| [Kroko ASR](https://huggingface.co/Banafo/Kroko-ASR) English community streaming model (2025-08-06), by Banafo, ONNX export by sherpa-onnx | Built-in live speech model | CC-BY-SA, as stated on the model card (the repository's LICENSE file is empty and gives no version). Attribution: "Kroko ASR community model by Banafo". The model files keep this licence; Biverse's own code is MIT |
| [NVIDIA Parakeet TDT 0.6B v2](https://huggingface.co/nvidia/parakeet-tdt-0.6b-v2), int8 ONNX export by sherpa-onnx | Optional high-accuracy model pack | CC-BY-4.0. Attribution: "parakeet-tdt-0.6b-v2 by NVIDIA". NVIDIA does not endorse Biverse |
| [NVIDIA Nemotron Speech Streaming EN 0.6B](https://huggingface.co/nvidia/nemotron-speech-streaming-en-0.6b) (160 ms chunks), int8 ONNX export by sherpa-onnx | Optional live high-accuracy model pack | [NVIDIA Open Model License](https://www.nvidia.com/en-us/agreements/enterprise-software/nvidia-open-model-license/). Notice: "Licensed by NVIDIA Corporation under the NVIDIA Open Model License" (also written to `NOTICE.txt` in the model folder). NVIDIA does not endorse Biverse |
| [Qwen2.5-1.5B-Instruct](https://huggingface.co/Qwen/Qwen2.5-1.5B-Instruct-GGUF) (GGUF q4_k_m) | Optional AI summary pack | Apache License 2.0 (Alibaba Cloud / Qwen team) |
| [llama.cpp](https://github.com/ggml-org/llama.cpp) b12366 `llama-completion` | Runs the AI summary model in the optional pack | MIT |
| [Silero VAD](https://github.com/snakers4/silero-vad) | Speech/pause detection in the Parakeet pack | MIT |
| [Vosk API](https://github.com/alphacep/vosk-api) 0.3.44 (`libvosk`, Python bindings) | Offline speech recognition | Apache License 2.0 |
| [vosk-model-small-en-us-0.15](https://alphacephei.com/vosk/models) | English speech model, © 2020 Alpha Cephei Inc | Apache License 2.0 |
| Kaldi (statically linked into libvosk) | Speech recognition toolkit | Apache License 2.0 |
| [python-sounddevice](https://github.com/spatialaudio/python-sounddevice) 0.5.6 | Audio input | MIT |
| [PortAudio](http://www.portaudio.com/), bundled by sounddevice on Windows and macOS | Audio I/O library | MIT-style PortAudio licence |
| cffi | Used by vosk and sounddevice | MIT |
| requests, srt, tqdm | Imported by vosk; not used by Biverse | Apache-2.0 / MIT / MPL-2.0 AND MIT |
| [Pillow](https://python-pillow.org/) 11.3.0 (10.4.0 in the Windows 7 builds), with its bundled libjpeg-turbo, libpng, libwebp, zlib and FreeType | Idle screen and background pictures (JPEG, PNG, WebP, GIF) | MIT-CMU (HPND); the bundled libraries are under BSD-style, libpng, zlib and FreeType licences |
| [PyAV](https://github.com/PyAV-Org/PyAV) 19.0.2 (Windows x64 and macOS builds only) | Idle screen video | BSD-3-Clause |
| [FFmpeg](https://ffmpeg.org/) libraries (libavcodec, libavformat, libavutil, libswscale, …), bundled by PyAV | Decoding idle screen videos | **GPL-2.0-or-later** as built for PyAV (with x264 and x265); see "GPL components" below |
| [x264](https://www.videolan.org/developers/x264.html), [x265](https://www.videolan.org/developers/x265.html), bundled by PyAV | Linked into FFmpeg (video *encoders*; Biverse only decodes) | GPL-2.0-or-later |
| libvpx, dav1d, SVT-AV1, libvmaf, Opus, libwebp, zlib, libiconv, MinGW runtime (libgcc, libstdc++, winpthreads), bundled by PyAV | Codecs and support libraries for FFmpeg | BSD-3-Clause / BSD-2-Clause / BSD-2-Clause-Patent / BSD-3-Clause-Clear / Zlib / LGPL-2.1 / GPL-3.0 with GCC runtime exception / MIT |
| certifi | CA certificates for HTTPS model downloads (Settings → Models) | MPL-2.0 |
| Python and Tcl/Tk (bundled by PyInstaller) | Runtime and GUI | PSF licence / Tcl/Tk BSD-style licence |
| PyInstaller bootloader | Packaging | GPL-2.0 with a bootloader exception that allows distributing bundled apps under any licence |

## GPL components (idle screen video)

The Windows x64 and macOS downloads include PyAV, whose FFmpeg is built with the GPL-licensed
x264 and x265 libraries. Those downloads therefore contain code under the GNU General Public
License, version 2 or later, and as distributed the program as a whole is covered by it.
Biverse's own source code stays under the MIT licence, which is compatible. The Windows 7
(`windows-legacy-*`) downloads do not include PyAV and have no GPL components (apart from the
PyInstaller bootloader, which has its own exception).

Source code for the GPL components, as used in these downloads:

- PyAV 19.0.2: https://github.com/PyAV-Org/PyAV/tree/v19.0.2 (also on PyPI as `av-19.0.2.tar.gz`)
- The FFmpeg, x264, x265 and codec builds bundled in the PyAV 19.0.2 wheels, with their build
  scripts and source archives: https://github.com/PyAV-Org/pyav-ffmpeg
- FFmpeg: https://ffmpeg.org/download.html · x264: https://code.videolan.org/videolan/x264 ·
  x265: https://bitbucket.org/multicoreware/x265_git

If any of these links stop working, ask for the source through the Biverse issue tracker
(https://github.com/CeoFred/biverse/issues) and it will be provided for at least three years
after the release that contained it.

## Bible texts

All bundled translations are in the **public domain**.

| Code | Translation | Source | Status |
|---|---|---|---|
| KJV | King James Version (1769 Oxford text) | [scrollmapper/bible_databases](https://github.com/scrollmapper/bible_databases) (MIT-licensed repository), commit `59b18c5a` | Public domain, except in the UK, where Crown rights (letters patent) apply. UK churches should check their own licensing |
| WEB | World English Bible | [eBible.org](https://ebible.org/engwebp/) | Public domain. "World English Bible" is a trademark of eBible.org, so the name is used only for the unmodified text |
| ASV | American Standard Version (1901) | scrollmapper | Public domain |
| YLT | Young's Literal Translation (1898) | scrollmapper | Public domain |
| BBE | Bible in Basic English (1965) | scrollmapper | Treated as public domain by its distributors. Churches should confirm its status in their country |

The scrollmapper repository is under the MIT License, "Copyright (c) 2024 Scrollmapper". Its
full text is the standard MIT licence (the same text as Biverse's `LICENSE`, with that
copyright line).

Biverse never bundles copyrighted translations such as NIV, NKJV, ESV or NLT. A church that
holds a licence can import one locally (see USER_GUIDE.md, "Adding a licensed translation").

## Full licence texts

- Apache License 2.0: https://www.apache.org/licenses/LICENSE-2.0
- BSD licences: https://opensource.org/licenses/BSD-3-Clause and https://opensource.org/licenses/BSD-2-Clause
- GNU GPL version 2: https://www.gnu.org/licenses/old-licenses/gpl-2.0.html
- GNU LGPL version 2.1: https://www.gnu.org/licenses/old-licenses/lgpl-2.1.html
- MIT: https://opensource.org/licenses/MIT
- PortAudio: http://www.portaudio.com/license.html
- Python: https://docs.python.org/3/license.html
- Tcl/Tk: https://www.tcl.tk/software/tcltk/license.html
