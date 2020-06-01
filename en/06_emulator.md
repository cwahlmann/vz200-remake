**[BACK](README.md)**
# <a name="emulator">The VZ200 Emulator</a>

This Emulator is an adapted Variant of the Java-Emulator 'jemu': http://jemu.winape.net/

## Port Configuration

application.properties (Default 8080):

```
server.port = 10101
```

Reset Key: [ESC]

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

## Expansion Volume Control

PORT | IN / OUT | Description
-------|-------|-------------
251 | R/W | reads / sets the volume between 0 and 255

## REST Interface

```bash
curl -X POST http://localhost:8080/vz200/vz 
     -H "Content-Type:application/octet-stream" 
     --data-binary @/D/Downloads/8bit/vz200/jvz_021/vz_files/games_autostart/CRASH.vz
```
Basic Path: [HOST]:[PORT]/vz200

Endpoint | Method | Request | Response | Description
---------|--------|---------|----------|-------------
/        | GET    |         | String   | Info
/reset   | POST   |         | String   | Reset Computer
/vz      | POST   | application/octet-stream | String | load .vz-Programm
/vz[?autorun={True/False}][&range={start-end}]      | GET    |         | application/octet-stream | read .vz-Programm from Emulator; autorun: Save locally with Autostart Flag; range: RAM area (default: Basic-Pointer)
/bas     | POST   | application/octet-stream | String | Load Basic Program from Source
/bas     | GET   |          | application/octet-stream | Read Basic Program Source 
/asm[?autorun={True/False}]     | POST   | application/octet-stream | Range: {from-to} | Load Assembler Programm Source and optionally run it (default True)
/asmzip[?autorun={True/False}]     | POST   | application/octet-stream | Range: {from-to} | Load Zip file with Assembler Programm Source and run it optionally (default True)
/asm/{from[-to]} | GET    | | String | Read Memory Area as Assembler Code
/hex     | POST   | application/octet-stream | String | Load Hexadecimal Source and launch it
/hex/{from[-to]} | GET    | | String | Read Memory Area as in hexadecimal format
/printer/flush | GET | | String | Read most recent printed lines
/tape    | GET    |         | String | Read the name of the Tape inserted
/tape/{name} | POST    |        | String | Insert Tape with the given name
/tape/slot | GET    |         | Integer | Read the current slot of the Tape
/tape/slot/{id} | GET    | Integer | | Forward wind the Tape to the slot specified. 
/tape/play | POST | | Integer | Start Tape, returns slot
/tape/record | POST | | Integer | Start Recording, returns slot
/tape/stop | POST | | Integer | Stop Tape, returns slot
/typetext | POST | text/plain | String | Enters Text into the Basic PROMT of the VZ (work in progress) 
/sound/{volume} | POST | Integer | String | Set Audio Volume from 0 to 255
/sound     | GET  | | Integer | Read Audio Volume
/registers | GET  | | String | Returns the content of every Z80 register as JSON

**[BACK](README.md)**
