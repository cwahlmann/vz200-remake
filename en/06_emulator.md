**[BACK](README.md)**
# <a name="emulator">The VZ200 Emulator</a>

This Emulator is an adapted Variant of the Java-Emulator 'jemu': http://jemu.winape.net/

## Port Configuration

application.properties (Default 8080):

```
server.port = 10101
```

Reset Key: [ESC]

## Expansion to get network info

```basic
OUT 250,0:FOR I=1 to 4:PRINT INP(250);:NEXT
192 168 1 100
READY
```

PORT | IN / OUT | Description
-----|----------|-------------
250  | IN       | READ part of IP-Adress at [index] and increment [index]
250  | OUT      | SET [index] to [n] (0-3)

## Expansion for audio

```basic
OUT 251,0:REM SOUND OFF
READY
OUT 251,INP(251)+50:REM DO IT LOUDER
READY
```

PORT | IN / OUT | Description
-----|----------|-------------
251  | IN       | READ sound volume
251  | OUT      | SET sound volume to [n]

## Expansion to load and save .vz files:

```basic
OUT 252,1
READY
```

PORT | IN / OUT | Description
-----|----------|-------------
252  | OUT      | LOAD .vz program no. [n]
253  | OUT      | SAVE .vz program no. [n]

All programs with n <= 100 are readonly and have be stored in [home]/vz200/vz.

## Expansion Tape Control

```basic
PRINT INP(254)
10
READY
```

PORT | IN / OUT | Description
-----|----------|-------------
254  | OUT      | 0: STOP, 1: PLAY, 16: RECORD
255  | OUT      | REWIND to position [n]
254, 255  | IN  | get LSB / MSB of tape position

(Stored in [home]/vz200/tape)

## REST Interface

Information about the provided methods is available online at:

* Swagger-UI: [host:port]/api/swagger
* Open-API-Doc: [host:port]/v3/api-docs

## Australian Graphics Mod

PORT | IN / OUT | Description
-----|----------|----------------------------------------------------
32   | OUT      | set graphic-mode und Gfx-RAM-Page
     |          | ---MMMPP (MMM = mode 0-7, PP = gfx-RAM-page 0-3)
     |          | mode 0: 64x64, 4 colors
     |          | mode 1: 128x64, monochrome
     |          | mode 2: 128x64, 4 colors (default)
     |          | mode 3: 128x96, monochrome
     |          | mode 4: 128x96, 4 colors
     |          | mode 5: 128x192, monochrome
     |          | mode 6: 128x192, 4 colors
     |          | mode 7: 256x192, monochrome

Der Mod kann über die Konfigurationsdatei ~/.jemu deaktiviert / aktiviert (default) werden.

**[BACK](README.md)**
