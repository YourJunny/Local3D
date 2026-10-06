# Changelog

## v0.1.0 (pre-release), 2026-10-06

The first public build. It is a pre-release for testing.

**Please read first:** this build was tested with a simulated generation engine on Linux. It has not yet been run on a real Windows PC with a graphics card, and no AI model has been run through it on real hardware yet. The Windows installer was built and inspected, not run. Expect rough edges, and please report what you find.

### What is in it

- Image to 3D, with background removal you can check and fix by hand, and several input views for the models that accept them.
- Text to 3D through a reference picture that you approve first.
- Eight styles: Realistic, Low Poly, Pixel Art, Stylized / Hand-Painted, Clay / Sculpt, Game Ready, Voxel, Wireframe / Technical.
- A batch queue with pause, resume, reorder, cancel and retry. It survives a restart of the app.
- A 3D viewer with five display modes, lighting presets, size readout, turntable and screenshots.
- Selecting part of a model (piece, brush or lasso) and smoothing, subdividing, reducing, deleting or filling holes. Every edit is a new version.
- Repainting textures with the image model: repaint a selected region from a prompt, paint a whole new texture (seams between sides are possible), give a model one plain material, and sharpen a blurry texture.
- Sketch to 3D, and changing the reference picture with a prompt before the 3D step.
- A library with versions, favorites, tags, search, compare, go back to an older version, trash and import.
- Export to `.glb`, `.gltf`, `.obj`, `.stl` and `.3mf`, and to `.fbx` when Blender is installed. Presets for Unity, Unreal Engine, Godot and Roblox. "Send to" for those four and "Open in Blender".
- Print preparation: real size, check and repair, flat base, hollowing, splitting into parts, and opening the file in a slicer.
- Examples to load and try, scenes that put several models into one file, and projects with a shared style and size.
- Automation, in Settings: a watch folder, overnight mode (planned start, temperature limit, shutdown when done), automatic library backups, and a command line for scripts.
- Import of your own ComfyUI workflow, run outside the app's usual steps.
- A first-run setup that checks the computer, suggests models, installs the generation engine and downloads what you pick.
- Installers for Windows and Linux, and a portable Windows build.

### Models you can download in the app

TRELLIS.2, Pixal3D, Pixal3D (multi-view), Hunyuan3D 2.0, Hunyuan3D 2.1, Hunyuan3D 2mv, Hunyuan3D 2mv Turbo, Z-Image-Turbo, Stable Diffusion XL base 1.0, BiRefNet and Real-ESRGAN x4plus.

### Known limits

- The memory figures shown for each model are the makers' figures or estimates. None has been measured in this app. Time estimates are rough until the app has run a few jobs on your PC.
- The Hunyuan3D models produce a shape without colors or textures.
- The Hunyuan3D models are not licensed for use in the EU, the UK or South Korea.
- Stable Fast 3D is listed but cannot be downloaded, because its download needs a sign-in.
- The installers are not code-signed. Windows shows a warning on first run.
- No macOS version. AMD graphics cards are untested.
- Not included: regenerating the shape of one part of a model, automatic skeletons for characters, TripoSR, Shap-E and the original TRELLIS.
- No screen yet for saving your own styles.
- Sharpening the texture cannot be switched on for every generation; run it afterwards from the Edit tab.

### Known issues

- **"Paint with a prompt" can fail with the wrong explanation.** On a model whose parts share the same area of the texture (for example a model made of several parts that each use the whole texture picture), it stops and suggests picking another side to paint from. Another side will not help. The cause is the model's texture layout, and this version cannot repaint such a model.
- **The details panel can show the previous model.** While a new job runs on the Generate screen, the panel on the right still shows the result before it. It changes when the new model is done.
- **A texture tool loses sight of its job if you restart the app.** The tool in the Edit tab no longer shows progress after a restart. The job is still in the Queue, and its result is saved as a new version as usual.
- **"Check for updates" says that no release has been published.** It looks for full releases only, and this is a pre-release. Look at the Releases page for newer versions.
- **Parts of the app have had less testing than the rest:** downloading models (pause, resume, checking files, moving the models folder) and the update check were tried by hand, not by automated tests. If a download misbehaves, please report it with a diagnostics file.
