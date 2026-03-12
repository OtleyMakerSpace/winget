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

## To investigate

Programs need to be installed already.
Start with a base Windows 10, and install using winget.

Try the GitHub hosted apps first as they are complicated. Confirm that they are working:

```
FreeCAD.FreeCAD
KiCad.KiCad
SoftFever.OrcaSlicer
Prusa3D.PrusaSlicer
```

Then try:

```
Google.Chrome
3Dflow.3DFZephyr.Free
```

Need to find the corrrect ID for Firefox.
Should be [Mozilla.Firefox](https://winget.run/pkg/Mozilla/Firefox) but it's possibly out-of-date.

en-GB version is [Mozilla.Firefox.en-GB](https://winstall.app/apps/Mozilla.Firefox.en-GB)

Try uninstalling, reboot then install using winget. Check the locale.

Can we host `lists` and `mods` directories on GitHub, for autoupdating?

## Known working app IDs

These are confirmed as working:

```
Git.Git
Python.Python.3.13
Ultimaker.Cura
dotPDN.PaintDotNet
Microsoft.VisualStudioCode
Microsoft.WindowsTerminal
3Dflow.3DFZephyr.Free
```

## Non-working app IDs

These do not work:

```
ARP\Machine\X64\Mozilla Firefox
```

## Unknown (test these)

Check these, then move to working/non-working:

```
FreeCAD.FreeCAD
KiCad.KiCad
SoftFever.OrcaSlicer
Prusa3D.PrusaSlicer
7zip.7zip
Google.Chrome
Microsoft.Edge
Notepad++.Notepad++
Open-Shell.Open-Shell-Menu
VideoLAN.VLC
GIMP.GIMP.3
Inkscape.Inkscape
Adobe.Acrobat.Reader.64-bit
```

## The old way of doing things

### Currently handled by ninite

These are updated using ninite, but require an admin. Can we automate them with winget?

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
