# Third-party notices

Local3D is built with software made by other people, and it works with AI models and programs that are not part of it. This page is a readable summary.

**The complete notices, with every license text, are installed with the app:**

- Windows: `resources\licenses\THIRD_PARTY_NOTICES.txt` inside the folder Local3D is installed in, plus `LICENSES.chromium.html` and `LICENSE.electron.txt` next to `Local3D.exe`.
- Linux: the same files inside the unpacked folder (or inside the AppImage).
- In the app: **Settings → About → Credits and licenses**.

Where this summary and the installed file differ, the installed file is the one that matches your copy of the app.

## About Local3D

Local3D is published by YourJunny. It is an independent project. **Tencent is not affiliated with, associated with, sponsoring or endorsing Local3D.** The same is true of every other company and project named on this page: their names are used only to say what Local3D contains or works with.

Local3D itself is closed source. Its terms are in [LICENSE.md](LICENSE.md).

## Programs Local3D runs but does not contain

These are separate programs under the GNU General Public License (GPL). Local3D does not include their code. It starts them as separate programs and talks to them through files, the command line and a local network connection on your own computer.

| Program | License | How it gets on your computer | Source code |
| --- | --- | --- | --- |
| **ComfyUI** (the generation engine) | GPL-3.0 | When you click to install the engine, the app downloads the source code of ComfyUI version 0.38.2 from its official repository and sets it up in the app's own data folder. ComfyUI is written in Python, so what you receive is its source code, together with its `LICENSE` file. You may use, change and share it under the GPL. | <https://github.com/comfyanonymous/ComfyUI> (tag `v0.38.2`) |
| **Blender** (optional) | GPL-2.0-or-later (its releases are GPL-3.0-or-later) | Local3D never downloads or installs Blender. It only uses a Blender you installed yourself, for FBX export, "Open in Blender" and the cleanup script. | <https://www.blender.org/> and <https://projects.blender.org/blender/blender> |

The packages ComfyUI needs (PyTorch and others) are downloaded by Python's package installer from their official sources into ComfyUI's own environment, each under its own license.

Three small helper scripts that run inside Blender ship with the app (`glb_to_fbx.py`, `open_in_blender.py`, `cleanup_template.py`). They are under the MIT license, which is compatible with the GPL.

If you use your own ComfyUI instead of the one the app installs, the app does not change it.

## AI models

Local3D contains no AI models. You download them inside the app from their official sources. Each one is licensed to you by its maker, not by Local3D. The app shows each license before the download and stores a copy in the `licenses` folder inside your models folder.

| Model | Made by | License | What to know |
| --- | --- | --- | --- |
| TRELLIS.2 | Microsoft | MIT | Free for any use, including commercial. |
| Pixal3D and Pixal3D (multi-view) | Tsinghua University and Tencent ARC (copyright Tencent) | MIT | Free for any use, including commercial. Comes with a notice asking for responsible use. |
| DINOv3 image encoder (a file used by TRELLIS.2 and Pixal3D) | Meta | DINOv3 License | Commercial use is allowed. Not for military, weapons, nuclear or espionage uses. The file may only be passed on under the same license. The same file contains the NAF upsampler, under Apache-2.0. |
| MoGe (a file used by Pixal3D) | Microsoft | MIT | |
| Hunyuan3D 2.0, Hunyuan3D 2mv, Hunyuan3D 2mv Turbo | Tencent | Tencent Hunyuan 3D 2.0 Community License Agreement | **Not licensed for use in the European Union, the United Kingdom or South Korea**, and that covers the results too. Elsewhere free to use, including commercially, unless your products have more than 1 million monthly active users. You may not use the model or its results to improve another AI model. Tencent's acceptable use policy applies. |
| Hunyuan3D 2.1 | Tencent | Tencent Hunyuan 3D 2.1 Community License Agreement | The same limits as above. |
| Z-Image-Turbo | Alibaba (Tongyi-MAI) | Apache-2.0 | Free for any use, including commercial. |
| Stable Diffusion XL base 1.0 | Stability AI | CreativeML Open RAIL++-M | Free for any use, including commercial, within the use restrictions listed in the license. |
| BiRefNet | ZhengPeng | MIT | Free for any use, including commercial. |
| Real-ESRGAN x4plus | Xintao Wang | BSD-3-Clause | Free for any use, including commercial. |

Notices the licenses prescribe:

- Tencent Hunyuan 3D 2.0 is licensed under the Tencent Hunyuan 3D 2.0 Community License Agreement, Copyright © 2025 Tencent. All Rights Reserved. The trademark rights of "Tencent Hunyuan" are owned by Tencent or its affiliate.
- Tencent Hunyuan 3D 2.1 is licensed under the Tencent Hunyuan 3D 2.1 Community License Agreement, Copyright © 2025 Tencent. All Rights Reserved. The trademark rights of "Tencent Hunyuan" are owned by Tencent or its affiliate.

The Hunyuan3D licenses limit how the models and their results may be used (sections 5(a) and 5(b) of each agreement). Those limits apply to you when you use these models. Read the full text in the app before you download them.

Stable Fast 3D (Stability AI Community License) is listed in the app but cannot be downloaded in this version.

## Software inside the app

Everything below is under a permissive license (MIT, BSD, Apache-2.0, ISC, PSF, Zlib or the SIL Open Font License) unless a line says otherwise.

**The application shell**

- Electron (MIT), which contains Chromium (BSD-3-Clause and others) and Node.js (MIT and others). Their notices are in `LICENSES.chromium.html`.
- FFmpeg, inside Chromium, is under the **GNU Lesser General Public License (LGPL-2.1-or-later)**. It ships as its own file (`ffmpeg.dll` on Windows, `libffmpeg.so` on Linux), exactly as the Electron project builds it. You may replace that file with your own build. Its source is available from the Electron and Chromium projects.

**The user interface**

- React, React DOM and Scheduler (MIT)
- TanStack Query (MIT)
- Zustand (MIT)
- three.js and three-mesh-bvh (MIT)
- Lucide icons (ISC)
- The Archivo typeface, Copyright 2020 The Archivo Project Authors (SIL Open Font License 1.1)

**The app's own engine (Python)**

- CPython 3.12 (PSF-2.0), from the python-build-standalone project, with the libraries built into it: OpenSSL (Apache-2.0), SQLite (public domain), zlib, bzip2, XZ, libffi, Expat, mpdecimal, libuuid, and on Linux ncurses and libedit. On Windows it includes Microsoft's Visual C++ runtime files, redistributed unchanged under Microsoft's terms.
- pip (MIT)
- FastAPI, Starlette, Uvicorn, websockets, Pydantic, AnyIO, h11, Click, idna and their small helper packages (MIT or BSD)
- aiohttp and its helper packages (Apache-2.0, MIT, PSF-2.0)
- NumPy and SciPy (BSD-3-Clause)
- trimesh (MIT), pyfqmr (MIT), xatlas (MIT), mapbox-earcut (ISC), manifold3d (Apache-2.0)
- embreex (BSD-2-Clause), which contains Intel Embree and TBB (Apache-2.0)
- Pillow (MIT-CMU), which contains FreeType, used under the FreeType License
- psutil (BSD-3-Clause)
- fontTools (MIT)
- OpenTelemetry API (Apache-2.0). Only the interface definitions are present. Nothing is collected or sent.
- The Archivo Bold font file used for text on 3D prints (SIL Open Font License 1.1)

Two things in this group are not permissive, and both are separate, replaceable library files:

- **On Linux only**, the NumPy and SciPy packages carry `libquadmath`, under the **LGPL-2.1-or-later**. It is a separate shared library file inside those packages' folders. You may replace it with your own build.
- NumPy and SciPy also carry the GCC runtime library `libgfortran`, under the GPL **with the GCC Runtime Library Exception**, which allows its use in a program under any license.

**The Windows installer and the Linux AppImage launcher** (separate programs, not part of the app)

- The Windows setup and uninstall programs are made with NSIS (zlib/libpng license). They contain plug-ins built from 7-Zip and StdUtils, both under the LGPL-2.1-or-later.
- The start of the `.AppImage` file is the AppImage project's launcher (MIT). It contains libfuse (LGPL-2.1), squashfuse, Zstandard, zlib, mimalloc and musl.

## Your rights under the LGPL

For the parts under the GNU Lesser General Public License named above, you may replace the library with your own version, and you may modify and reverse engineer Local3D as far as is needed to debug such a change. Local3D's own terms say so in section 3.

## Questions

If you believe a notice is missing or wrong, please open an issue: <https://github.com/YourJunny/Local3D/issues>
