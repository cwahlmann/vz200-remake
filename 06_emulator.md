**[ZURÜCK](README.md)**
# <a name="emulator">Der VZ200 Emulator</a>

Der genutzte Emulator ist eine angepasste Version des Java-Emulators 'jemu': http://jemu.winape.net/

## Port Konfiguration

application.properties (Default 8080):

```
server.port = 10101
```

Reset-Taste: [ESC]

## Erweiterung laden / speichern von .vz:

```basic
OUT 252,1
READY
```

PORT | IN / OUT | Beschreibung
-----|----------|-------------
252  | OUT      | LOAD .vz program no. [n]
253  | OUT      | SAVE .vz program no. [n]

Alle Programme n <= 100 sind readonly.

(werden in [home]/vz200/vz abgelegt)

## Erweiterung Tape-Controle

```basic
PRINT INP(254)
10
READY
```

PORT | IN / OUT | Beschreibung
-----|----------|-------------
254  | OUT      | 0: STOP, 1: PLAY, 16: RECORD
255  | OUT      | REWIND to position [n]
254, 255  | IN  | get LSB / MSB of tape position

(werden in [home]/vz200/tape abgelegt)

## Erweiterung Volume-Controle

PORT | IN / OUT | Beschreibung
-------|-------|-------------
251 | R/W | liest / setzt die Lautstärke (0-255)

## REST-Interface

```bash
curl -X POST http://localhost:8080/vz200/vz 
     -H "Content-Type:application/octet-stream" 
     --data-binary @/D/Downloads/8bit/vz200/jvz_021/vz_files/games_autostart/CRASH.vz
```
Basis-Pfad: [HOST]:[PORT]/vz200

Endpunkt | Method | Request | Response | Beschreibung
---------|--------|---------|----------|-------------
/        | GET    |         | String   | Info
/reset   | POST   |         | String   | Reset Computer
/vz      | POST   | application/octet-stream | String | .vz-Programm einspielen
/vz[?autorun={True/False}][&range={start-end}]      | GET    |         | application/octet-stream | .vz-Programm auslesen; autorun: mit Autostart-Flag speichern; range: Speicherbereich (default: Basic-Pointer)
/bas     | POST   | application/octet-stream | String | Basic-Programm-Source einspielen
/bas     | GET   |          | application/octet-stream | Basic-Programm-Source auslesen. 
/asm[?autorun={True/False}]     | POST   | application/octet-stream | Range: {von-bis} | Assembler-Programm-Source einspielen und ggf. starten (default True)
/asmzip[?autorun={True/False}]     | POST   | application/octet-stream | Range: {von-bis} | Zip-Datei mit Assembler-Programm-Source einspielen und ggf. starten (default True)
/asm/{von[-bis]} | GET    | | String | Speicherbereich als Maschinenprogramm auslesen
/hex     | POST   | application/octet-stream | String | Hexadezimalen Source einspielen und starten
/hex/{von[-bis]} | GET    | | String | Speicherbereich in hexadezimalem Format auslesen
/printer/flush | GET | | String | zuletzt gedruckte Zeilen auslesen
/tape    | GET    |         | String | Namen des eingelegten Tapes lesen
/tape/{name} | POST    |        | String | Type mit angegebenem Namen einlegen
/tape/slot | GET    |         | Integer | aktuellen Slot des Tapes lesen
/tape/slot/{id} | GET    | Integer | | Tape zu angegebenem Slot spulen
/tape/play | POST | | Integer | Tape starten; gibt Slot zurück
/tape/record | POST | | Integer | Aufnahme starten; gibt Slot zurück
/tape/stop | POST | | Integer | Tape stoppen; gibt Slot zurück
/typetext | POST | text/plain | String | Tippt Text in den Bildschirm des VZ (in Arbeit)
/sound/{volume} | POST | Integer | String | Audio-Lautstärke schreiben von 0 bis 255
/sound     | GET  | | Integer | Audio-Lautstärke lesen
/registers | GET  | | String | gibt den den Wert aller Z80-Register als JSON zurück

**[ZURÜCK](README.md)**
