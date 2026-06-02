# osu converter

A lightweight drag-and-drop desktop app for converting **osu!mania** maps into **Etterna-ready song folders**.

Built with a simple CustomTkinter interface, featuring a Popcat drop zone

## Features

- Drag-and-drop `.osz`, `.olz`, `.zip`, `.osu`, or map folders
- Imports osu!mania charts into an Etterna `Songs` folder
- Automatically copies common map assets
- Generates Etterna-style image assets:
  - `background.png`
  - `banner.png`
  - `jacket.png`
  - `cdtitle.png`
- Can patch `.osu` background events to use the generated background
- Saves your Etterna folder and pack folder settings
- Includes a small import log so you can see what happened 

## Download

Go to the **Releases** page and download the latest `osu_converter.zip`.

After downloading:

1. Extract the zip
2. Open the extracted `osu_converter` folder
3. Double-click `osu converter.exe`

Do not move the `.exe` out of its folder unless you enjoy breaking things for sport. The app needs the bundled `_internal` files beside it.

## How to use

1. Open `osu converter.exe`
2. Click the gear icon in the top-right
3. Set your Etterna folder or Etterna `Songs` folder
4. Set your pack folder name, for example:

   ```text
   OSU Ports
   ```

5. Drag an osu!mania map, archive, or folder onto the Popcat area
6. Restart Etterna or reload songs if the imported maps do not appear

## Supported input

The app supports:

```text
.osz
.olz
.zip
.osu
folders containing .osu files
```

Only osu!mania charts are imported. Regular osu!standard, taiko, and catch charts are skipped because Etterna is not here to solve every rhythm game problem mankind has invented.

## Output location

Imported songs are placed into your selected Etterna `Songs` folder under the pack name you choose.

Example:

```text
Etterna/Songs/OSU Ports/Artist - Title (Mapper)/
```

## Settings

Click the gear icon to change:

- Etterna folder / Songs folder
- Pack folder name
- Overwrite existing copied assets
- Patch `.osu` background event to `background.png`

Settings are saved automatically.

## Building from source

This project is written in Python.

Install requirements:

```bash
pip install -r requirements.txt
```

Run from source:

```bash
python src/popcat_importer/main.py
```

Build with PyInstaller:

```bash
pyinstaller --noconfirm --clean --onedir --windowed ^
  --name "osu converter" ^
  --paths "src" ^
  --add-data "src\popcat_importer\assets;assets" ^
  --collect-all customtkinter ^
  --collect-all tkinterdnd2 ^
  src\popcat_importer\main.py
```

On Windows, the included `START_HERE.bat` can build the app automatically if you are working from the source version.

## Requirements

For running the built release:

- Windows
- No Python install required if using the release build

For building from source:

- Python 3.10+
- CustomTkinter
- tkinterdnd2
- Pillow
- PyInstaller

## Notes

If imported songs or artwork do not show up in Etterna:

- restart Etterna
- reload songs
<img width="1359" height="881" alt="Screenshot_23" src="https://github.com/user-attachments/assets/a252bc64-f7db-46b0-afef-1dae4eef9773" />
<img width="1410" height="899" alt="Screenshot_24" src="https://github.com/user-attachments/assets/7c275f40-c393-4d16-b65c-111829fa0140" />

