# SFDL Loader für macOS

Native Mac-App zum Laden von `.sfdl`-Dateien. Im Browser auf eine SFDL klicken – der Download startet automatisch,
wird geprüft, entpackt und landet im gewünschten Ordner.

**[→ Neueste Version herunterladen](https://github.com/Krypt0x69/SFDLForMac/releases/latest)**

## Funktionen

- Öffnet `.sfdl` per Doppelklick, Drag & Drop oder automatisch aus dem Downloads-Ordner
- Verschlüsselte SFDLs mit Passwortliste im Schlüsselbund – gefragt wird nur, wenn keines passt
- Warteschlange mit Fortschritt, Geschwindigkeit, Restzeit, Pause und Fortsetzen
- Setzt abgebrochene Downloads fort, auch nach einem Neustart
- SFV-Prüfung und Entpacken (RAR, ZIP, 7z) eingebaut – nichts muss nachinstalliert werden
- Mehrere Zielordner, auch externe Laufwerke und NAS
- FTPS mit gemerkten Zertifikaten, optional SOCKS5-Proxy
- Mitteilungen bei Fertig und Fehler, optional per Pushover aufs Handy
- Menüleisten-Symbol mit Gesamtfortschritt, Light und Dark Mode

## Installation

1. Unter [Releases](https://github.com/Krypt0x69/SFDLForMac/releases/latest) die Datei `SFDLForMac-<Version>.dmg` laden.
2. DMG öffnen und **SFDL Loader** auf **Programme** ziehen.
3. Die App ist nicht von Apple notarisiert. Beim ersten Start daher einmal
   **Systemeinstellungen › Datenschutz & Sicherheit › „Dennoch öffnen“** wählen.

Voraussetzung: macOS 13 oder neuer, Apple Silicon oder Intel.

Optional die Prüfsumme vergleichen (die `.sha256`-Datei liegt beim Release):

```bash
shasum -a 256 -c SFDLForMac-<Version>.dmg.sha256
```

## Updates

SFDL Loader sucht selbst nach neuen Versionen (abschaltbar unter Einstellungen › Allgemein) und installiert sie auf
Wunsch. Jedes Update ist signiert; die App installiert nur Pakete, deren Signatur, Prüfsumme und Version stimmen.

## Lizenz

© 2026 Krypt0x · [GNU GPL v3.0](LICENSE). Mitgelieferte Fremdkomponenten: siehe
[THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md).
