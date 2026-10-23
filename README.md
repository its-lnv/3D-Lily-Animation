# 3D Botanical Lily Animation with Python

A procedural 3D botanical animation of a bouquet of Oriental lilies, created with Python. The animation is designed in a vertical 9:16 format for Instagram Reels.

## Features

- Procedurally constructed 3D lily flowers
- Detailed petals, stems, leaves, stamens, and pistils
- Animated flower construction and reveal
- Vertical 1080 x 1920 video format
- Python-based animation generation

## Technologies

- Python 3.14
- NumPy (installed from `requirements.txt`)
- OpenCV (installed from `requirements.txt`)
- FFmpeg

## Project structure

```text
lily-animation-python/
├── generate_lily_animation.py
├── index.html
├── LICENSE
├── README.md
├── requirements.txt
├── media/
│   ├── lily_3d_botanical_animation.mp4
│   ├── preview_1.8s.png
│   ├── preview_3.8s.png
│   ├── preview_6.4s.png
│   └── preview_11.5s.png
└── .gitignore
```

Generated videos and preview images are placed in `media/`. They are ignored by Git because they are build outputs and can be regenerated from the Python script.

## Installation and setup

Follow these steps from a new terminal after cloning or downloading the project.

### 1. Install Python

Install Python 3.14 for Windows from [python.org](https://www.python.org/downloads/). During installation, enable **Add Python to PATH**.

Confirm that Python and pip are available:

```powershell
py -3.14 --version
py -3.14 -m pip --version
```

### 2. Open the project folder

```powershell
cd "E:\path\to\lily-animation-python"
```

Replace the path with the location where you downloaded this repository.

### 3. Create and activate a virtual environment

```powershell
py -3.14 -m venv .venv
.\.venv\Scripts\Activate.ps1
```

If PowerShell blocks activation, run this once in PowerShell and then repeat the activation command:

```powershell
Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
```

### 4. Install the Python libraries

Upgrade pip and install every Python dependency listed in `requirements.txt`:

```powershell
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

The requirements file installs:

- `numpy`, used for numerical calculations
- `opencv-python`, imported by the script as `cv2`

### 5. Install FFmpeg

FFmpeg is required only for generating the MP4 video. It is an external program, so it cannot be installed through `requirements.txt`.

On Windows, install it with WinGet:

```powershell
winget install --id Gyan.FFmpeg.Shared --exact
```

Close and reopen the terminal after installation, then confirm that FFmpeg is available:

```powershell
ffmpeg -version
```

If `ffmpeg` is not recognized, add the FFmpeg `bin` directory to the Windows `PATH`, reopen the terminal, and run the check again.

## Running the project

### Generate the full animation

With the virtual environment activated and FFmpeg available, run:

```powershell
python generate_lily_animation.py
```

The MP4 is written to `media/lily_3d_botanical_animation.mp4`.

### Generate preview images

```powershell
python generate_lily_animation.py --preview
```

Preview PNG files are written to `media/`.

The script creates the `media/` directory automatically if it does not exist.

### Run without activating the virtual environment

You can run the script using the virtual environment's Python executable directly:

```powershell
.\.venv\Scripts\python.exe generate_lily_animation.py --preview
.\.venv\Scripts\python.exe generate_lily_animation.py
```

### Troubleshooting

- **`ModuleNotFoundError: No module named 'cv2'`**: activate `.venv` and run `python -m pip install -r requirements.txt`.
- **`ModuleNotFoundError: No module named 'numpy'`**: activate `.venv` and run `python -m pip install -r requirements.txt`.
- **`FileNotFoundError` mentioning `ffmpeg`**: install FFmpeg, ensure its `bin` folder is on `PATH`, and reopen the terminal.
- **`/usr/bin/env: python3` on Windows**: use `python generate_lily_animation.py` from PowerShell instead of a Linux/macOS run command.

## Output

The script generates a vertical animated lily video suitable for short-form content, along with several preview keyframes.

## About

Created as a Python animation project exploring procedural botanical modeling and cinematic visual storytelling.

If you found this project through my coding reels, feel free to explore the source code!

## License

This project is licensed under the MIT License. See [LICENSE](./LICENSE) for the full license text.

---

If you like this project, consider starring the repository.
