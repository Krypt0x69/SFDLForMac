# SFDLForMac

Native Mac-App zum Laden von `.sfdl`-Dateien. Im Browser auf eine SFDL klicken – SFDLForMac übernimmt den Rest:
laden, prüfen, entpacken, sauber benennen und in die richtige Bibliothek legen.

**[→ Neueste Version herunterladen](https://github.com/Krypt0x69/SFDLForMac/releases/latest)** · macOS 13 oder neuer ·
Apple Silicon und Intel · Deutsch · kostenlos (GPL-3.0)

## So funktioniert's

1. Auf eine `.sfdl` klicken – im Browser, per Doppelklick im Finder oder per Drag & Drop aufs Fenster oder Dock-Symbol.
   Neue SFDLs im Downloads-Ordner erkennt die App auch von selbst.
2. SFDLForMac entschlüsselt die Datei mit deiner Passwortliste, listet alle Teile und lädt los.
3. Danach wird geprüft, entpackt, aufgeräumt und einsortiert – und du bekommst eine Mitteilung.

## Funktionen

### Laden

- **Kein Terminal, kein Tippen** – `.sfdl`-Dateien öffnen sich direkt in der App, der Download startet sofort
  (oder auf Wunsch erst, wenn du das Häkchen beim Paket setzt).
- **Oder manuell steuern** – Pakete anhaken und mit **Start, Pause und Stopp** oben im Fenster alle ausgewählten
  auf einmal steuern.
- **Ordner überwachen** – neue SFDLs im Downloads-Ordner (oder einem eigenen Ordner) landen automatisch in der Liste.
- **Passwortliste** im Schlüsselbund. Die Passwörter werden der Reihe nach probiert, gefragt wird nur, wenn keines passt –
  das richtige merkt sich die App.
- **Pakete und Dateien einzeln an- und abwählen**, z. B. nur eine von mehreren SFDLs oder einzelne Teile laden.
- **Parallele Verbindungen** gesamt und pro Paket, **Speedlimit**, optional **Chunk-Download** großer Dateien über
  mehrere Verbindungen.
- **Fortsetzen statt neu laden** – nach Abbruch, Pause oder Neustart des Macs geht es an der Stelle weiter.
- **Automatische Wiederholung** bei Verbindungsfehlern (5 Versuche mit wachsender Wartezeit).
- **Mehrere Ziele** – Mac, externe Platte oder NAS, pro Paket umstellbar. Ist ein Laufwerk nicht verbunden oder voll,
  wartet das Paket und startet von selbst, sobald es wieder da ist.
- **Blacklist** für Dateien, die du nie laden willst (z. B. `*.exe`, `*sample*`).

### Nach dem Download

- **SFV-Prüfung** – fehlerhafte Teile werden automatisch neu geladen.
- **Entpacken** von RAR, ZIP und 7z (auch mehrteilig und passwortgeschützt) mit eingebautem `unar` –
  nichts muss nachinstalliert werden. Danach verschwinden Archive und Prüfdateien.
- **Filme und Serien getrennt einsortieren**
  - `Film.Name.2020.German.DL.1080p…` → `Filme/Film Name (2020)/`
  - `Serie.Name.S01E02.German…` → `Serien/Serie Name/Season 01/`
- **Jellyfin, Emby oder Plex** bekommen Bescheid und lesen die Bibliothek sofort neu ein. Auflösung, Codecs und
  Tonspuren erkennt der Medienserver dabei selbst aus der Datei.
- **Speedreport** mit eigener Vorlage – zum Kopieren oder als Datei im Paketordner.
- **Wenn alles fertig ist:** App beenden, Ruhezustand oder Mac ausschalten (mit Countdown zum Abbrechen).
  Während Downloads laufen, geht der Mac nicht in den Ruhezustand.

### Benachrichtigungen

- Mitteilungen von macOS bei „fertig“ und bei Fehlern.
- Zusätzlich aufs Handy über **Telegram** (eigener Bot) oder **Pushover** – mit Test-Button.

### Oberfläche

- Ein Eintrag pro SFDL mit Fortschritt, Geschwindigkeit, Restzeit und Status, aufklappbar bis zur einzelnen Datei.
  Nach dem Entpacken zeigt der Eintrag die fertige Datei.
- Oben Gesamtgeschwindigkeit, Gesamtfortschritt und freier Speicher am Ziel.
- **Menüleisten-Symbol** mit Gesamtfortschritt – die App arbeitet auch ohne offenes Fenster weiter.
- **Protokoll** (⌥⌘L) zum Nachlesen, was passiert ist – ohne Passwörter.
- Light und Dark Mode, ganz im Stil von macOS.

### Sicherheit

- **Verschlüsselte Verbindungen (FTPS).** Das Server-Zertifikat wird beim ersten Kontakt gemerkt und danach geprüft.
  Server, die TLS können, werden auch dann verschlüsselt angesprochen, wenn die SFDL es nicht verlangt –
  ein späterer Rückfall auf Klartext wird blockiert.
- **Optional SOCKS5-Proxy** für alle Verbindungen.
- **Nichts landet außerhalb des Zielordners** – Datei- und Ordnernamen aus SFDL und Server werden gesäubert,
  Archive vor dem Entpacken auf gefährliche Pfade und Links geprüft.
- Geladene Dateien bekommen das **Quarantäne-Merkmal** von macOS, damit Gatekeeper sie prüft.
- **Passwörter, Tokens und Schlüssel im Schlüsselbund**, nie im Klartext oder im Protokoll. Die App öffnet keine Ports.
- **Signierte Updates** – installiert wird nur, was mit dem Projektschlüssel signiert ist und zur App passt.

## Installation

1. Unter [Releases](https://github.com/Krypt0x69/SFDLForMac/releases/latest) die Datei `SFDLForMac-<Version>.dmg` laden.
2. DMG öffnen und **SFDLForMac** auf **Programme** ziehen.
3. Die App ist nicht von Apple notarisiert. Beim ersten Start daher einmal
   **Systemeinstellungen › Datenschutz & Sicherheit › „Dennoch öffnen“** wählen.
4. Zugriff auf den Ordner „Downloads“ und Mitteilungen erlauben.

Optional die Prüfsumme vergleichen (die `.sha256`-Datei liegt beim Release):

```bash
shasum -a 256 -c SFDLForMac-<Version>.dmg.sha256
```

## Updates

SFDLForMac sucht selbst nach neuen Versionen – beim Start und einmal am Tag, abschaltbar unter
Einstellungen › Allgemein – und installiert sie auf Wunsch mit einem Klick. Laufende Downloads werden dafür angehalten
und setzen nach dem Neustart fort.

## Häufige Fragen

**macOS fragt nach einem Update erneut nach Zugriff auf „Downloads“.**
Die App ist ohne kostenpflichtiges Apple-Entwicklerkonto signiert. macOS behandelt deshalb jede neue Version wie eine
neue App. Einfach erneut erlauben.

**Wo liegen meine Daten?**
Download-Liste, SFDL-Archiv und gemerkte Server-Zertifikate unter `~/Library/Application Support/SFDLForMac`,
Passwörter und Zugangsdaten im Schlüsselbund. Archivierte SFDLs sind nur für deinen Benutzer lesbar.

## Lizenz

© 2026 Krypt0x · [GNU GPL v3.0](LICENSE). Mitgelieferte Fremdkomponenten: siehe
[THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md).
