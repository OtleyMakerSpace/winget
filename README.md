# winget

Can we use `winget` (Windows Package Manager) to automate application updates?

## Links

[Winget-AutoUpdate](https://github.com/Romanitho/Winget-AutoUpdate?tab=readme-ov-file#readme)

Uses the Winget tool to daily update apps (with system context) and notify users when updates are available and installed.

[WAU Settings GUI (for Winget-AutoUpdate)](https://github.com/KnifMelti/WAU-Settings-GUI?tab=readme-ov-file#readme)

Provides a user-friendly portable standalone interface to modify every aspect of Winget-AutoUpdate (WAU).

## To upgrade an app manually

```
winget upgrade --id <app ID>
```

## Known working app IDs

```
Git.Git
Python.Python.3.13
Ultimaker.Cura
```

## Non-working app IDs

## Unknown (test these)

### Currently handled by ninite

These are updated using ninite, but require an admin. Can we automate them?

```
7Zip
Chrome
Edge
Firefox
Notepad++
Open Shell
VLC
Visual Studio Code
GIMP
Inkscape
Paint.NET
```

### Currently require manual checking

```
3DF Zephyr free
```

### Hosted on GitHub

These GitHub projects are being followed, so we get an email when a new release is available. The software needs to be individually updated by an admin.

[FreeCAD](https://github.com/FreeCAD/FreeCAD/releases)

```
FreeCAD.FreeCAD
```

[KiCad](https://github.com/KiCad/kicad-source-mirror/releases)

```
KiCad.KiCad
```

Checks for updates on startup and redirects to the download page

[OrcaSlicer](https://github.com/SoftFever/OrcaSlicer/releases)

```
SoftFever.OrcaSlicer
```

Download the “OrcaSlicer_Windows_Installer” file

[PrusaSlicer](https://github.com/prusa3d/PrusaSlicer/releases)

```
Prusa3D.PrusaSlicer
```

Checks for updates on startup and redirects to the download page

[UltiMaker Cura](https://github.com/Ultimaker/Cura/releases)

```
Ultimaker.Cura
```

Download the “-win64-X64.msi” file and install “Complete”

[Git for Windows](https://github.com/git-for-windows/git/releases)

```
Git.Git
```

Download the “-64-bit.exe” file
