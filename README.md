# winget

Using `winget` (Windows Package Manager) to automate application updates.

## Links

[winget.run](https://winget.run/)

Microsoft website which lets you search for available packages.

[Winget-AutoUpdate](https://github.com/Romanitho/Winget-AutoUpdate?tab=readme-ov-file#readme)

Uses winget to auto-update apps (with system context) and notify users when updates are available and installed.
Can be configured to run whenever any user logs in.

[WAU Settings GUI (for Winget-AutoUpdate)](https://github.com/KnifMelti/WAU-Settings-GUI?tab=readme-ov-file#readme)

Provides a user-friendly portable standalone interface to modify every aspect of Winget-AutoUpdate (WAU).

## How to use winget manually

### Install an application

```
winget install --id <app ID>
```

### Upgrade an application

```
winget upgrade --id <app ID>
```

### Check an installed application

```
winget list --id <app ID>
```

## To setup auto updates

- Download the latest [WAU Settings GUI](https://github.com/KnifMelti/WAU-Settings-GUI/releases) zip file
- Unzip and run (can be run as a portable app)
- Allow it to install Winget-AutoUpdate
- Check "Run at user logon"
- Copy [excluded_apps.txt](lists/excluded_apps.txt) to `C:\Program Files\Winget-AutoUpdate`
- Click "Run WAU"
- Check logs

## To investigate

**Programs need to be installed already.**
We can use `winget` to install them.
Firefox needs special treatment.

Can we host `lists` and `mods` directories on GitHub, for autoupdating?
Doesn't look like it, but we can store in a network share, and clone our repo into that.

## Known working app IDs

These are confirmed as working.

### Development tools

```
Notepad++.Notepad++
Microsoft.VisualStudioCode
Git.Git
```

### CAD / design

```
KiCad.KiCad
GIMP.GIMP.3
Inkscape.Inkscape
dotPDN.PaintDotNet
```

### 3D

```
SoftFever.OrcaSlicer
Prusa3D.PrusaSlicer
Ultimaker.Cura
3Dflow.3DFZephyr.Free
```

### Web browsers

```
Google.Chrome
Microsoft.Edge
Mozilla.Firefox.en-GB
```

### Media

```
VideoLAN.VLC
```

## Non-working applications

### Firefox

```
ARP\Machine\X64\Mozilla Firefox
```

This appears in the list because Firefox was installed using the regular Windows installer.

To fix: uninstall Firefox, and re-install (with the correct locale) using winget:

```
winget install --id Mozilla.Firefox.en-GB
```

### FreeCAD

```
FreeCAD.FreeCAD
```
FreeCAD [has issues](https://github.com/microsoft/winget-pkgs/issues/288310), and should not be upgraded with winget.

## Unknown (test these)

Check these, then move to working/non-working:

```
Python.Python.3.13
Microsoft.WindowsTerminal
7zip.7zip
Open-Shell.Open-Shell-Menu
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
