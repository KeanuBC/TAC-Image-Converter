# TAC Image Converter

**Lost 1996 Archive System Aesthetic**

TAC Image Converter is a Python image-processing tool designed to transform ordinary images into a retro visual style inspired by 1990s computer graphics, low-resolution game imagery, CRT monitors, and corrupted archival displays.

It includes adjustable image scaling, color reduction, visual effects, aspect-ratio modes, and experimental display filters.

## Features

### Standard Image Modes

| Mode | Description |
|---|---|
| `keep` | Preserves the original aspect ratio. |
| `background` | Forces a 16:9 aspect ratio. |
| `card` | Uses 5:7 portrait, 7:5 landscape, or 1:1 square proportions. |

### Test Modes

| Mode | Description |
|---|---|
| `max_test` | Generates versions with progressively smaller maximum dimensions. |
| `base_test` | Generates versions using progressively smaller internal render heights. |
| `pixel_test` | Generates versions with progressively smaller pixel scales. |
| `palette_test` | Generates versions with progressively smaller color palettes. |
| `full_test` | Runs all standard and testing modes automatically. |

### Display Filters

The converter includes several display styles:

- `none` — no additional display tint.
- `pipboy` — green monochrome terminal aesthetic.
- `amber` — amber monitor tint.
- `terminal_blue` — blue terminal display.
- `ice` — cold archival display.
- `blood` — red warning display.
- `violet` — purple retro display.
- `rainbow` — rainbow phosphor effect.
- `random_rainbow` — randomized rainbow colors.
- `random` — experimental glossy color effect.
- `reversed` — inverted colors.
- `cursed` — experimental color corruption.
- `corrupted` — randomized visual glitches and distortion.
- `ascii` — simulated monochrome ASCII display.
- `ascii_color` — simulated color ASCII display.
- `full_collection` — generates the standard display collection.

### Adjustable Settings

The script allows you to configure:

- Maximum output width and height.
- Internal render resolution.
- Pixel enlargement scale.
- Color palette size.
- Contrast and brightness.
- Noise intensity.
- Scanline strength.
- Bloom strength.
- VHS blur.
- Chromatic aberration.
- Individual visual effect toggles.

## Supported Formats

**Input**
- PNG
- JPG
- JPEG
- WEBP

**Output**
- PNG

## Installation

Install the required Python packages:

```bash
python -m pip install Pillow numpy opencv-python
```

See [SETUP.md](SETUP.md) for detailed installation and configuration instructions.

## Configuration

Before running the converter, edit the input and output paths near the top of the script:

```python
INPUT_FOLDER = r"C:\Path\To\Input"
OUTPUT_FOLDER = r"C:\Path\To\Output"
```

Choose the processing mode:

```python
MODE = "keep"
```

Choose the display filter:

```python
DISPLAY_MODE = "none"
```

Adjust the remaining settings to customize the appearance.

## Running the Converter

Run the script:

```bash
python tac_image_converter.py
```

The converter processes supported images directly inside the configured input folder and saves the resulting PNG files in the output directory.

## Output Structure

The output structure depends on the selected modes.

Example:

```text
TAC_Output/
├── keep/
│   └── none/
├── background/
│   └── none/
├── card/
│   └── none/
├── max_test/
│   └── 1920x1080/
├── base_test/
│   └── 180/
├── pixel_test/
│   └── 8/
└── palette_test/
    └── 48/
```

Display modes create their own folders inside the corresponding output directories.

## Important Notes

- The script uses configured folder paths rather than asking for folders at runtime.
- Only files directly inside the input folder are scanned.
- Existing output files with the same destination name may be overwritten.
- Different input files with the same filename stem can produce the same output filename.
- `full_test` can generate a substantial number of images.
- Some visual filters are experimental.

## License

This project is licensed under the MIT License.
