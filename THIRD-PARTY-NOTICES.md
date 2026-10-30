# Fremdkomponenten

SFDLForMac liefert zwei Hilfsprogramme mit, die aus fremdem Quellcode gebaut werden. Sie liegen als eigenständige
Programme in `SFDLForMac.app/Contents/Helpers/` und werden nur aufgerufen, nicht in die App gelinkt.

| Komponente | Verwendet für | Lizenz | Quellcode (genau dieser Stand) |
|---|---|---|---|
| XADMaster (`unar`, `lsar`) | Entpacken und Prüfen von RAR/ZIP/7z | LGPL-2.1 | https://github.com/MacPaw/XADMaster/tree/7cb9ee0abbb163f261e4cb74501e15067032319c |
| UniversalDetector | Zeichensatz-Erkennung in XADMaster | LGPL-2.1 | https://github.com/MacPaw/universal-detector/tree/4eb832d999628edcd3d134e46bd35357c8c99a85 |

Der vollständige Lizenztext liegt in der App unter `Contents/Resources/LICENSE-unar.txt`. Gebaut wird unverändert
aus dem oben verlinkten Stand (Universal-Binary für macOS 13+); die Programme lassen sich daraus selbst bauen und in
der App austauschen.

Außerdem nutzt die App die in macOS enthaltenen Bibliotheken libcurl und zlib.
