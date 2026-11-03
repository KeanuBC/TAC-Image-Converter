# TAC Image Converter - Setup & Installation

## 1. Requirements

- Python 3.9 or newer recommended
- Pillow
- NumPy
- OpenCV

## 2. Install Dependencies

Open Command Prompt or a terminal and run:

```bash
python -m pip install Pillow numpy opencv-python
```

## 3. Project Files

A simple project structure:

```text
TAC-Image-Converter/
├── tac_image_converter.py
├── README.md
├── SETUP.md
└── LICENSE
```

## 4. Configure Input and Output Folders

Open `tac_image_converter.py` and locate the PATHS section.

```python
INPUT_FOLDER = r"C:\EXAMPLE\PATH\TO\FILE.txt"
OUTPUT_FOLDER = r"C:\EXAMPLE\PATH\TO\FILE.txt"
```

Replace these placeholders with actual folder locations.

Example:

```python
INPUT_FOLDER = r"C:\Users\YourName\Pictures\Originals"
OUTPUT_FOLDER = r"C:\Users\YourName\Pictures\TAC_Output"
```

**Important:** These must be folder paths, not individual image file paths.

The output folder will be created automatically if it does not exist.

## 5. Choose a Processing Mode

Find the MODE setting:

```python
MODE = "keep"
```

Available options:

| Setting | Purpose |
|---|---|
| `keep` | Preserve original aspect ratio. |
| `background` | Force 16:9 output. |
| `card` | Create portrait, landscape, or square output. |
| `max_test` | Test different maximum resolutions. |
| `base_test` | Test different internal render heights. |
| `pixel_test` | Test different pixel scales. |
| `palette_test` | Test different palette sizes. |
| `full_test` | Run all processing modes. |

## 6. Choose a Display Filter

Find the DISPLAY_MODE setting:

```python
DISPLAY_MODE = "none"
```

Available options include:

```python
"none"
"pipboy"
"amber"
"terminal_blue"
"ice"
"blood"
"violet"
"rainbow"
"random_rainbow"
"random"
"reversed"
"cursed"
"corrupted"
"ascii"
"ascii_color"
"full_collection"
```

`full_collection` generates the standard display filters automatically when used with a standard processing mode or `full_test`.

## 7. Customize Image Effects

The converter includes individual effect toggles:

```python
ENABLE_DITHER = True
ENABLE_SCANLINES = True
ENABLE_NOISE = True
ENABLE_BLOOM = True
ENABLE_CHROMA = True
ENABLE_VHS_BLUR = True
ENABLE_SHARPEN = True
```

Set an effect to `True` to enable it or `False` to disable it.

You can also adjust the effect strengths and image-processing settings.

## 8. Run the Converter

Once the paths and settings are configured, run:

```bash
python tac_image_converter.py
```

The program will scan the configured input folder and process supported images.

Processed images are saved as PNG files in the configured output folder.

## 9. Important Notes

- The input folder is not scanned recursively.
- Only PNG, JPG, JPEG, and WEBP files are processed.
- Original images are not modified.
- Output files may be overwritten if their destination filenames already exist.
- Files with identical names but different extensions may overwrite each other's output.
- Testing modes can produce many images and consume significant storage space.

For best results, use a separate output folder and keep backups of your original images.

## 10. Troubleshooting

### OpenCV Is Missing

Run:

```bash
python -m pip install --upgrade opencv-python
```

### Pillow or NumPy Is Missing

Run:

```bash
python -m pip install --upgrade Pillow numpy
```

### No Images Found

Check that:
- The input folder path is correct.
- The folder contains supported image formats.
- The images are directly inside the selected input folder rather than only inside subfolders.

### Output Images Are Being Replaced

Check for files with identical names but different extensions. The converter uses the filename without its original extension when creating the `_TAC.png` output name.
