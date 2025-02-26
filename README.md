# Windows-Tweaks
## MPC-BE iPhone MOV Hochformat
Optionen > Video > Videorender > Enhanced Video Render (custom presets) > Präsentationsmodus << **Flip/FlipEx**
![hvec-hochformat-iphone](https://github.com/OnaldUck/Windows-Tweaks/assets/35377000/147ad73b-a54f-4711-a5e6-da209792db13)

## Scrollrichtung invertieren / änder auf natürlich wie bei Mac
Einfach in Powershell folgenden Script ausführen

```
Get-ItemProperty HKLM:\SYSTEM\CurrentControlSet\Enum\HID\*\*\Device` Parameters FlipFlopWheel -EA 0 | ForEach-Object { Set-ItemProperty $_.PSPath FlipFlopWheel 1 }'

```

## Festplatte läuft voll
## Python
Der Ordner `AppData\Local\pip` ist sehr groß obwohl man Python installiert hat. Kann davon kommen, wenn man portabels Python nutzt, z.b. in StabilityMatrix.

Lösung, die Systemvariable PIP_CACHE_DIR setzten.

`PIP_CACHE_DIR=d:\Render\pip` setzten.

### Steam
Es gibt auch zwei Verzeichnise, die recht groß sind und sich nicht verschieben lassen. Symbolische Verknüpfung geht immer :-).
```
mklink /d "c:\Program Files (x86)\Steam\steamapps\workshop\" "d:\Render\Steam\workshop\"
mklink /d "c:\Program Files (x86)\Steam\steamapps\common\SteamVR\" "d:\Render\Steam\SteamVR\"
```
