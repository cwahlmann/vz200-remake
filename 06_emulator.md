**[ZURÜCK](README.md)**
# <a name="emulator">Der VZ200 Emulator</a>

Der genutzte Emulator ist eine angepasste Version des Java-Emulators 'jemu': http://jemu.winape.net/

## Port Konfiguration

application.properties (Default 8080):

```
server.port = 10101
```

Reset-Taste: [ESC]

## Erweiterung Netzwerk-Info

```basic
OUT 250,0:FOR I=1 to 4:PRINT INP(250);:NEXT
192 168 1 100
READY
```

PORT | IN / OUT | Beschreibung
-----|----------|-------------
250  | IN       | READ part of IP-Adress at [index] and increment [index]
250  | OUT      | SET [index] to [n] (0-3)

## Erweiterung Audio Device

```basic
OUT 251,0:REM SOUND OFF
READY
OUT 251,INP(251)+50:REM DO IT LOUDER
READY
```

PORT | IN / OUT | Beschreibung
-----|----------|-------------
251  | IN       | READ sound volume
251  | OUT      | SET sound volume to [n]

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

## REST-Interface

Informationen zu den einzelnen Methoden können online abgerufen werden:

* Swagger-UI: [host:port]/api/swagger
* Open-API-Doc: [host:port]/v3/api-docs

## Australian Graphics Mod

PORT | IN / OUT | Beschreibung                        | Format
-----|----------|-------------------------------------|--------------------------------------------------
32   | OUT      | Grafikmodus und Gfx-RAM-Page setzen | ---MMMPP (MMM = Modus 0-7, PP = Gfx-RAM-Page 0-3)

| MODUS | Beschreibung
|-------|--------------------------------
| 0     | 64x64, 4 colors
| 1     | 128x64, monochrome
| 2     | 128x64, 4 colors (default)
| 3     | 128x96, monochrome
| 4     | 128x96, 4 colors
| 5     | 128x192, monochrome
| 6     | 128x192, 4 colors
| 7     | 256x192, monochrome

Der Mod kann über die Konfigurationsdatei ~/.jemu deaktiviert / aktiviert (default) werden.

**[ZURÜCK](README.md)**
