# Windows-Tweaks
## MPC-BE iPhone MOV Hochformat
Optionen > Video > Videorender > Enhanced Video Render (custom presets) > Präsentationsmodus << **Flip/FlipEx**
![hvec-hochformat-iphone](https://github.com/OnaldUck/Windows-Tweaks/assets/35377000/147ad73b-a54f-4711-a5e6-da209792db13)

## Scrollrichtung invertieren / änder auf natürlich wie bei Mac
Einfach in Powershell folgenden Script ausführen

Bei Win11 ist es mittlerweile über Einstellungen möglich

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
### Hi DPI Remotedesktop
Remote Desktop für Bildschirme mit 4K Auflösung.

```
https://poweruser.blog/remote-desktop-client-on-hidpi-retina-displays-work-around-pixel-scaling-issues-1529f142ca93
cd %systemroot%\system32
copy mstsc.exe mstsc2.exe
cd %systemroot%\system32\de-de\
copy mstsc.exe.mui mstsc2.exe.mui
```
```
reg add "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers" /t REG_SZ /v "C:\Windows\System32\mstsc2.exe" /d "~ DPIUNAWARE" /f
```

Jetzt muss man nur noch eine Desktopverknüpfung mit **mstsc2.exe** erstellen.

### Ansicht für Ordner übernehmen
Die Ansicht für alle Bilderordner einmal definieren.

1. In den gewünschten Ordner reingehen. **Ansicht > Optionen > Ansicht > Für Ordner übernehem**

![Image](https://github.com/user-attachments/assets/f35f105b-fed8-47ea-86cf-4e37861876b1)

2. **Rechte Maus auf den Ordner > Anpassen > Ordertyp** wählen

![Image](https://github.com/user-attachments/assets/b0a4d651-5bb2-4847-b361-e18a25c8dfd7)
