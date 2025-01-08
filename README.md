# Windows-Tweaks
## MPC-BE iPhone MOV Hochformat
Optionen > Video > Videorender > Enhanced Video Render (custom presets) > Präsentationsmodus << **Flip/FlipEx**
![hvec-hochformat-iphone](https://github.com/OnaldUck/Windows-Tweaks/assets/35377000/147ad73b-a54f-4711-a5e6-da209792db13)

## Scrolrichtung invertieren / änder auf natürlich wie bei Mac
Einfach in Powershell folgenden Script ausführen
'Get-ItemProperty HKLM:\SYSTEM\CurrentControlSet\Enum\HID\*\*\Device` Parameters FlipFlopWheel -EA 0 | ForEach-Object { Set-ItemProperty $_.PSPath FlipFlopWheel 1 }'
