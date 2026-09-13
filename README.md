# Outline Edits

A reusable Codex skill and Python toolkit for making short 3D outline / blueprint edits from **a topic and a music track**. A reference video is optional.

The workflow grew out of an iterated Starship edit: opaque dark geometry, white contours, quickly typed code-style text, continuous camera moves, and impact shakes that overlap object entrances. It retains those lessons while developing a new sequence for each topic and track.

## What's included

- **A production workflow:** music analysis, subject research, scene planning, Blender modeling, compositing, export checks, and optional publishing.
- **Portable effects:** a tunable shake preset, directional motion blur, white typewriter text, and opaque-subject compositing.
- **Blender helpers:** stable camera aiming, rotation about a world axis, and centered assembly pivots.
- **Video inspection:** sequential decoding, actual frame timestamps, contact sheets, and full-resolution frames for selected time ranges.

This is an agent workflow plus reusable building blocks. It is not a one-command music-to-video generator. An agent still needs to plan the edit, build or obtain the subject, and render the scenes. The original Starship project, music, reference footage, fonts, and account credentials are not included.

## Install as a Codex skill

Clone this repository into your Codex skills directory:

```sh
git clone https://github.com/flaceja/outline-edits.git ~/.codex/skills/outline-edits
```

On Windows PowerShell:

```powershell
git clone https://github.com/flaceja/outline-edits.git "$env:USERPROFILE/.codex/skills/outline-edits"
```

If you use a custom Codex home, use its `skills` directory instead. Keep an existing installation or local changes before replacing it. The root [SKILL.md](SKILL.md) and [agent metadata](agents/openai.yaml) define the skill. Its detailed workflow notes are written in German; prompts and video text can use your requested language.

Example request:

> Use $outline-edits. Topic: Porsche 911. Music: the attached track. Develop the sequence, text, and camera movement yourself.

You can also specify an excerpt, length, aspect ratio, reference clip, or different visual style. Music and topic alone are enough to start. Publishing or deleting a post requires a corresponding user request.

## Run the helpers directly

Use Python 3.10 or newer; the helpers were tested with Python 3.12. Install the Python dependencies from the repository folder:

```sh
python -m pip install -r requirements.txt
```

Install [FFmpeg and FFprobe](https://ffmpeg.org/download.html) and put both executables on `PATH` for video encoding and inspection. Blender helpers must run inside [Blender](https://www.blender.org/download/); they were tested with Blender 5.2. OpenCV is optional and accelerates image remapping; the NumPy fallback works without it.

### Effects preview

Supply a local monospace font:

```sh
python scripts/edit_effects.py --demo work/demo --font /path/to/monospace.ttf
```

Windows example using an installed font:

```powershell
python scripts/edit_effects.py --demo work/demo --font C:/Windows/Fonts/consolab.ttf
```

This produces a **silent 1.2-second synthetic diagnostic**, `effects-demo.mp4`, and a contact sheet. It demonstrates the helpers; it is not a finished edit or a bundled Starship model.

### Inspect an exported video

```sh
python scripts/reference_frames.py my-edit.mp4 work/inspection --range 2.0:2.6 --range 5.1:5.8 --overview-every 0.5
```

The script decodes sequentially and uses actual timestamps, including variable-frame-rate sources. It saves overview sheets, every frame inside the requested windows, and a `frame-index.json` containing the local source path. Keep generated inspection folders private when they contain private media or paths.

### Use the modules

| File | Purpose |
| --- | --- |
| [scripts/edit_effects.py](scripts/edit_effects.py) | `apply_shake`, `typed_title`, `code_text_layer`, `composite_layers`, `directional_blur_rgba` |
| [scripts/blender_motion.py](scripts/blender_motion.py) | `aim_camera`, `rotate_world`, `make_center_pivot`, `quaternion_step_degrees` |
| [assets/outline-impact.json](assets/outline-impact.json) | Timing, zoom, lens bend, normalized translation, and roll keyframes |

See [compositing](references/compositing.md) for an import example and effect parameters, and [Blender motion](references/blender-motion.md) for coordinate and pivot conventions. The preset supports landscape and portrait frames. Choose new hit times for the supplied music; do not reuse the Starship timestamps as a universal template.

## Workflow notes

- [Music and topic, without a reference video](references/music-driven.md)
- [Optional video-reference analysis](references/reference-analysis.md)
- [Blender geometry and motion](references/blender-motion.md)
- [Text, compositing, audio, and export](references/compositing.md)
- [Publishing when requested](references/publishing.md)
- [Lessons from the Starship example](references/starship-case.md)

## Checks

Run the portable regression checks:

```sh
python -m unittest discover -s tests -v
```

The suite checks neutral shake frames, portrait and landscape pulses, alpha-correct motion blur, and variable-frame-rate inspection. FFmpeg-dependent checks are skipped when FFmpeg or FFprobe is unavailable. These checks do not replace visual review of a finished edit.

## License

The code, workflow documentation, and included numeric preset are available under the [MIT License](LICENSE). Music, fonts, footage, downloaded models, Blender, FFmpeg, and Python dependencies retain their own licenses. Supplying or downloading media does not change its license.
