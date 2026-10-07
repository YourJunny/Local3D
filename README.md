# Local3D

Local3D is a free desktop app that makes 3D models on your own PC. You type a prompt or drop in a picture, and the app builds a 3D model you can view, edit, keep in a library and export to game engines, Blender or a 3D printer.

Everything runs on your computer. There is no account, no sign-in, no subscription and no telemetry.

> **Status: early pre-release. Please read this before you download.**
>
> - This version has been tested with a **simulated generation engine on Linux**. The app, its queue, library, editing, print and export tools were exercised that way, without a graphics card.
> - It has **not yet been run on a real Windows PC with a graphics card**. No AI model has been downloaded and run through the app on real hardware yet. The Windows installer was built and inspected, not run.
> - The memory figures in the model table below come from the model makers or from estimates. None of them has been measured in this app.
> - Expect rough edges. If something fails, please [report it](#reporting-a-problem).

## Who it is for

- Hobbyists who want a 3D model from a picture or an idea.
- Indie game developers who need props and placeholder assets.
- People who 3D print and want a printable model from a picture.

You do not need Python, a terminal or any 3D experience.

## What it does

- **Image to 3D.** Drop in a picture of one object. The app removes the background, shows you the cut-out, lets you fix it by hand, and builds the model. Some models accept several views (front, left, back, right).
- **Text to 3D.** Type a prompt. The app first draws a reference picture on your PC and shows it to you. You accept it or ask for another, and then the 3D model is built from it.
- **Eight styles.** Realistic, Low Poly, Pixel Art, Stylized / Hand-Painted, Clay / Sculpt, Game Ready, Voxel and Wireframe / Technical. A style changes the picture step, the model's settings and the mesh that comes out, and can be applied to a model you already have.
- **Batch queue.** Queue many generations and let them run one at a time. Pause, resume, reorder, cancel and retry. The queue survives a restart of the app. One failed job does not stop the rest.
- **3D viewer.** Turn, slide and zoom. Display modes: textured, clay, wireframe, normals and UV checker. Lighting presets, size readout, turntable and screenshots.
- **Editing.** Select part of a model by clicking a piece, by brush or by lasso, then smooth it, subdivide it, reduce its triangles, delete it or fill holes. Every edit is saved as a new version with a before/after view. Nothing is overwritten.
- **Repainting textures (uses the image model).** Select a region and describe how it should look; the app repaints what one side of the model shows of it. Paint a whole new texture from a prompt: the model is repainted one side after another, so seams between sides and painted-in light and shadow are possible, and only the color is replaced. Give a model one plain material such as gold or wood without any AI. Enlarge and sharpen a blurry texture. These change how the surface looks, never its shape.
- **Library.** Every model is kept with its versions, the prompt and picture that made it, and all its settings. Favorites, tags, search, compare two versions, go back to an older version, trash with restore, import of `.glb` and `.obj` files.
- **Export.** `.glb`, `.gltf`, `.obj`, `.stl` and `.3mf`; `.fbx` when Blender is installed. Separate texture maps. Presets for Unity, Unreal Engine, Godot and Roblox.
- **Send to.** Copy a model straight into a Unity, Unreal or Godot project folder, or write a file that fits Roblox Studio's limits. Open a model in Blender.
- **Prepare for printing.** Set the real size in millimeters or inches, check and repair the mesh so it is closed, add a flat base, hollow it with drain holes, split a large model into parts with pegs, export `.stl` or `.3mf`, and open the file in Cura, PrusaSlicer, OrcaSlicer or Bambu Studio.
- **One click deeper.** Draw a rough sketch and let the image model turn it into the starting picture. Change the reference picture with a prompt before the 3D step. Load an example recipe to try. Put several models together in a scene and export them as one file. A watch folder that queues every picture you drop into it. Overnight mode: start the queue at a set time, pause it when the graphics card gets too hot, and shut the computer down when the queue is done, after a countdown you can cancel. Automatic backups of your library. A command line for queueing jobs and exporting from scripts, off until you turn it on. Import of your own ComfyUI workflow, for people who know ComfyUI.

## What it cannot do

- It is not a full modeling tool: no sculpting, no animation, no UV editor.
- It does not train or fine-tune AI models.
- It does not regenerate the shape of one part of a model. This was planned as an experimental feature and left out because it could not be made reliable with the available models.
- It does not add a skeleton to characters (auto-rig).
- The Hunyuan3D models produce a shape without colors or textures in this app.
- There is no macOS version. AMD graphics cards are untested.

## Requirements

| | |
| --- | --- |
| **System** | Windows 10 or 11 (64-bit), or 64-bit Linux with glibc 2.28 or newer (Ubuntu 20.04, Debian 10 and later). |
| **Graphics card** | An NVIDIA card is needed to generate models. See the memory (VRAM) figures in the [model table](#models). The app checks your card and driver and tells you which models suit it. RTX 20-series and newer cards need NVIDIA driver 580 or newer. |
| **Memory** | 16 GB of system memory is the estimate for the 3D models. |
| **Disk space** | About 610 MB for the app on Windows, 650 MB on Linux. About 12 GB free to install the generation engine. Then the models you choose: about 9 GB for TRELLIS.2, and about 12 GB more for the text-to-image model if you want text to 3D. Models can live on a different drive. |
| **Internet** | Only to download the engine and the models you pick, and for the update check when you click it. After that the app works offline. |

**Without a supported graphics card** the app still opens. Generation is switched off, with the reason shown. The library, the viewer, import, editing tools that do not use AI, print preparation and export all work.

The app warns you when a model may be too large for your card, and names one that should fit. It does not block you: you can still try.

## Download

Get it from the **[Releases page](https://github.com/YourJunny/Local3D/releases)**. The current version is **0.1.0**, a pre-release.

> **Not published yet.** The 0.1.0 files are built but have not been put on the Releases page yet. If that page is empty, check back soon.

| File | Size | For |
| --- | --- | --- |
| `Local3D-0.1.0-win-x64-setup.exe` | 150 MB | Windows 10/11. The installer. This is the one most people want. |
| `Local3D-0.1.0-win-x64-portable.zip` | 259 MB | Windows. The same app as a folder. Unzip it anywhere, for example on a USB drive, and start `Local3D.exe`. Everything it stores stays in a `data` folder next to it. |
| `Local3D-0.1.0-linux-x86_64.AppImage` | 237 MB | Linux. One file. |
| `Local3D-0.1.0-linux-x64.tar.gz` | 251 MB | Linux. The same app as a folder. |
| `SHA256SUMS.txt` | | The checksums below, as a file. |

The downloads contain no AI models and no generation engine. The app downloads those later, only when you click.

> [!WARNING]
> **Windows will warn you that this file isn't trusted. This is expected, and you can safely continue.**
>
> You will see "Windows protected your PC" and "Unknown publisher". Your browser may also say the file is "not commonly downloaded". Windows shows this for every program that isn't code-signed, and code signing is a paid certificate that this free app doesn't have yet. The warning does not mean anything was found in the file: the download is safe. Get it only from the [Releases page](https://github.com/YourJunny/Local3D/releases), and if you want to be sure it's the published file, [check its checksum](#check-your-download). How to get past the warning is under [Install](#windows).

### Check your download

The installers are not code-signed, so it is worth checking that the file you got is the file that was published. Each file has a SHA-256 checksum:

| File | SHA-256 |
| --- | --- |
| `Local3D-0.1.0-win-x64-setup.exe` | `24ef4604529bfc47de71b83ada874e6e3893ea50e7219061e936ba37be4a2e20` |
| `Local3D-0.1.0-win-x64-portable.zip` | `b6132688f20a894574ac02476bbd59a578aae6a0b1d31cfee116eb6a2f792872` |
| `Local3D-0.1.0-linux-x86_64.AppImage` | `b9267b80c7e0a4f576705db6ff45b10e585843ba2a243ed8f86c22f4ee2f0074` |
| `Local3D-0.1.0-linux-x64.tar.gz` | `07a3c1d07160d712c9550e1008b8ff2f6457eff134dc115f6abc03ad80f1f759` |

On Windows, open PowerShell in the folder with the download and run:

```powershell
Get-FileHash .\Local3D-0.1.0-win-x64-setup.exe -Algorithm SHA256
```

The long value it prints under `Hash` must be the same as in the table. PowerShell prints capital letters; that makes no difference. If it is not the same, delete the file and download it again from the Releases page.

On Linux, with `SHA256SUMS.txt` in the same folder: `sha256sum -c SHA256SUMS.txt --ignore-missing`

## Install

### Windows

1. Run `Local3D-0.1.0-win-x64-setup.exe`.
2. **Windows will show a blue "Windows protected your PC" box.** Click **More info**, then **Run anyway**. The publisher is shown as "Unknown publisher".
   This happens because the installer is not code-signed. A code-signing certificate costs money, and this is a free app. The warning does not mean Windows found anything wrong, but it also means Windows cannot vouch for the file, so download it only from the Releases page above and [check it](#check-your-download). Your browser may also say the file is "not commonly downloaded", and some antivirus programs are suspicious of unsigned installers.
3. Accept the license terms.
4. Keep **Only for me** selected. This needs no administrator rights.
5. Choose the folder, or keep the suggested one, and finish.

Uninstalling removes the program. It does not remove your library, your downloaded models or your settings.

### Linux

1. Make the AppImage executable: right-click it, open Properties and allow it to run as a program, or run `chmod +x Local3D-0.1.0-linux-x86_64.AppImage`.
2. Double-click it.

## First run

A short setup opens the first time you start the app. You can skip it and run it again later from Settings.

1. **This computer.** The app checks your graphics card, driver, memory and disk space.
2. **Choose models.** It suggests models that suit your computer. You decide which to get. Each model has a "Terms and conditions" link that opens its license.
3. **Install and download.** Click the button. The app installs the generation engine (ComfyUI) into its own folder and downloads the models you picked. This is several gigabytes and can take a while. Nothing is downloaded before you click.
4. **First generation.** Run one sample to see that everything works on your computer.

Then open **Generate**, drop in a picture of a single object or type a prompt, keep the default style and model, and press **Generate**.

## Models

The app ships with no AI models. You download the ones you want inside the app, with one click and no sign-in, from their official sources. Each model comes with its own license. The app shows the license before you download and keeps a copy next to the model's files.

| Model | Best for | License | Download | Graphics memory (not measured in this app) | Notes |
| --- | --- | --- | --- | --- | --- |
| **TRELLIS.2** | Highest quality, full color and material textures | MIT. One file, the DINOv3 image encoder, is under Meta's DINOv3 License. | 9.0 GB (19.3 GB with every quality tier) | Draft 12 GB, Standard 16 GB, High 24 GB (estimates) | Makes the shape and its textures. |
| **Pixal3D** | Results that match the input picture closely | MIT. Same DINOv3 encoder file. | 10.0 GB (20.9 GB with every tier) | Draft 12 GB, Standard 16 GB, High 24 GB (estimates) | Built on TRELLIS.2. |
| **Pixal3D (multi-view)** | Front, side and back pictures of the same object | MIT. Same DINOv3 encoder file. | 9.3 GB (20.3 GB with every tier) | Draft 12 GB, Standard 16 GB, High 24 GB (estimates) | Up to four views. The front view is required. |
| **Hunyuan3D 2.0** | Shapes without color on mid-range cards | Tencent Hunyuan 3D 2.0 Community License | 5.4 GB | 6 GB (maker's figure) | **Not licensed for use in the EU, the UK or South Korea.** Shape only. |
| **Hunyuan3D 2.1** | Finer shapes without color | Tencent Hunyuan 3D 2.1 Community License | 7.8 GB | 10 GB (maker's figure) | **Not licensed for use in the EU, the UK or South Korea.** Shape only. |
| **Hunyuan3D 2mv** and **2mv Turbo** (multi-view) | Shapes without color from several views | Tencent Hunyuan 3D 2.0 Community License | 5.4 GB each | 6 GB (estimate) | **Not licensed for use in the EU, the UK or South Korea.** Shape only. |
| **Z-Image-Turbo** | Drawing the reference picture for text to 3D | Apache-2.0 | 12.2 GB (32.5 GB with every tier) | Standard 8 GB, High 12 GB (estimates) | The default text-to-image model. |
| **Stable Diffusion XL base 1.0** | Text to 3D on smaller cards | CreativeML Open RAIL++-M | 6.9 GB | 6 GB (estimate) | Has use restrictions listed in its license. |
| **BiRefNet** | Removing the background of your picture | MIT | 0.4 GB | 2 GB (estimate) | Downloaded together with every 3D model. |
| **Real-ESRGAN x4plus** | Sharpening a blurry texture | BSD-3-Clause | 0.1 GB | 2 GB (estimate) | Optional. |

Files that several models share are downloaded and stored once.

About the Hunyuan3D territory restriction: the license of these models does not apply in the European Union, the United Kingdom or South Korea, and that covers what you make with them too. The app cannot check where you are. It shows the restriction at the top of the model's terms and leaves the choice to you. Using these models where the license does not apply is your responsibility.

Stable Fast 3D is listed in the app but switched off, because its download needs a sign-in and this app never asks for one.

## Privacy

- Nothing you type, drop in or make is uploaded.
- No telemetry and no analytics.
- The app uses the internet only for downloads you click (the engine and models) and for the update check you click.
- The app and its engine listen only on your own computer. They cannot be reached from the network.
- **One exception, off by default:** "Upload to Roblox" sends one model to Roblox with your own Roblox API key, and only when you click Upload for that model.

## License

Local3D is free to use, including for commercial work. It is closed source: the code is not published. The full terms are in [LICENSE.md](LICENSE.md). They are a draft that has not yet been reviewed by a lawyer.

What you make is yours, within the license of the model that produced it. Each AI model has its own license and some have limits. Read a model's terms before you rely on its output.

## Credits and third-party software

Local3D is built with open-source software, and it runs ComfyUI and, if you have it, Blender as separate programs under their own licenses. See [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md). The complete license texts are installed with the app.

Local3D is published by YourJunny. It is an independent project. It is not affiliated with, associated with, sponsored by or endorsed by Tencent, Microsoft, Meta, Stability AI, Alibaba, NVIDIA, Unity, Epic Games, Roblox, the Blender Foundation, the Godot project or the ComfyUI project. Their names are used only to say what the app works with.

## Reporting a problem

Open an issue here: **[github.com/YourJunny/Local3D/issues](https://github.com/YourJunny/Local3D/issues)**

It helps a lot if you attach a diagnostics file:

1. In the app, open **Settings → About → Export diagnostics**.
2. The app builds one zip file with logs, settings and hardware details. Your pictures and prompts are left out unless you tick the box to include them.
3. Attach the zip to your issue and describe what you did and what happened.

The app does not send anything by itself.

## Changes and known issues

See [CHANGELOG.md](CHANGELOG.md).
