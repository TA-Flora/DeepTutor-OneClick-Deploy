# DeepTutor One-Click Deploy (Windows)

[English](README.md) | [简体中文](README.zh-CN.md)

One-click DeepTutor deployment for Windows. Double-click the `.bat` and it automatically detects/installs Python & a portable Node.js LTS, downloads the latest DeepTutor source, builds the web frontend, and creates a desktop shortcut. Supports custom install drives, ghproxy mirror fallback, PyPI retry, and auto-opened failure logs.

> DeepTutor © HKU Data Intelligence Lab — [HKUDS/DeepTutor](https://github.com/HKUDS/DeepTutor) (MIT License). This repository only provides deployment scripts and does not include DeepTutor source code.

## Requirements

- Windows 10/11 64-bit
- Internet access (GitHub; ghproxy mirror is built in)
- At least 5 GB free disk space
- Python 3.11–3.13 — auto-installed via winget if missing
- Node.js 20+ — auto-installed as portable Node 22 LTS if missing

## Install

1. Extract the zip anywhere (e.g. Desktop).
2. Double-click **`DeepTutor-安装.bat`** — a terminal opens and the install starts (about 3–8 minutes).
3. If prompted for Python or Node.js, type `y` + Enter to auto-install.
   - On first install you'll be asked where to put DeepTutor / Python / Node.js. Enter a custom path (e.g. `D:\DeepTutor`) to use another drive, or press Enter for the default location. Already-installed dependencies are not asked again; updates skip the location prompts entirely.
   - If the install fails, the full log (`DeepTutor-安装日志.txt`) opens in Notepad automatically — copy the error text for bug reports, no screenshot needed. Press `R` to retry right away.

Then double-click the **DeepTutor** desktop shortcut. First launch builds the Web UI once (a progress window will show, may take a few minutes).

## Advanced usage (optional, from a terminal)

```powershell
# Custom install / data / runtime locations
powershell -ExecutionPolicy Bypass -File .\DeepTutor-Install.ps1 -InstallRoot "D:\DeepTutor" -DataRoot "E:\Data" -RuntimeRoot "F:\Runtime"
# Custom Node.js / Python locations
powershell -ExecutionPolicy Bypass -File .\DeepTutor-Install.ps1 -NodeRoot "D:\NodeHome" -PythonRoot "D:\Python313"
# Fully unattended (no prompts)
powershell -ExecutionPolicy Bypass -File .\DeepTutor-Install.ps1 -NoPrompt
```

## Uninstall

**Keep your data:**

1. Close DeepTutor.
2. Delete the version folders under `C:\Users\<you>\AppData\Local\DeepTutor\versions`.
3. Delete the desktop shortcut.

**Full removal:**

1. Close DeepTutor.
2. Delete the whole `C:\Users\<you>\AppData\Local\DeepTutor` folder.
3. Delete the desktop shortcut.

## License

BSD 3-Clause Clear — see [LICENSE](LICENSE). DeepTutor itself is MIT-licensed by HKU Data Intelligence Lab.
