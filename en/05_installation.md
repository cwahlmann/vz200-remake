**[ZURÜCK](README.md)**
# <a name="installation">Installation des Raspberry Pi</a>

## Projekt bauen mit Gradle:
```
gradle createVZ200Zip
```
Es entsteht ein Zip mit allen benötigten Dateien unter `build\distributions\JemuVZ200.zip`

## Installieren der Desktop-Version des Betriebssystems Raspbian
siehe Raspbian-Dokumentation unter www.raspbian.org
(Raspbian Buster Desktop Lite)

## gebautes Zip installieren
Zip-Datei ins Home-Verzeichnis des Raspberry kopieren und entpacken.
Danach sollte folgende Verzeichnisstruktur entstanden sein:

```
pi@raspberrypi:~ $ unzip JemuVZ200.zip
Archive:  JemuVZ200.zip
   creating: vz200/
   creating: vz200/system/
   creating: vz200/system/vz/
   creating: vz200/system/vz/rom/
  inflating: vz200/system/vz/rom/VZ.CHR
  inflating: vz200/system/vz/rom/VZBAS12.ROM
  inflating: vz200/system/vz/rom/README.txt
   creating: vz200/tape/
  inflating: vz200/tape/README.txt
   creating: vz200/tape/default/
  inflating: vz200/tape/default/README.txt
   creating: vz200/vz/
  inflating: vz200/vz/README.txt
  inflating: vz200/vz200-all.jar
  inflating: desktop-wallpaper.png
  inflating: vz200.desktop
  inflating: vz200.sh
```

## Startskript ausführbar machen
`dos2unix` installieren:
```
sudo apt-get install dos2unix
```

Zeilenumbrüche nach Unix konvertieren:
```
dos2unix vz200.desktop
dos2unix vz200.sh
```

Execute-Flag setzen:
```
chmod +x vz200.sh
```

## Emulator automatisch starten
Die Datei `vz200.desktop` in den Autostart-Ordner kopieren:
```
mkdir ~/.config/autostart
cp vz200.desktop ~/.config/autostart
```
## joe Texteditor installieren
```
sudo apt-get install joe
```
(Alternativ kann auch der schon installierte Editor `nano` genutzt werden.)

## JAVA und ALSA-Sound-Treiber installieren
Installieren der OpenJDK-8 Runtime und des ALSA-Treibers mit `apt-get`:
```
sudo apt-get install openjdk-8-jre
sudo apt-get install alsa-base alsa-utils
```
Die Java-Sound-Konfiguration anpassen (PulseAudio auskommentieren, DirectAudioDevice einkommentieren):
```
sudo joe /etc/java-8-openjdk/sound.properties
#javax.sound.sampled.Clip=org.classpath.icedtea.pulseaudio.PulseAudioMixerProvider`
#javax.sound.sampled.Port=org.classpath.icedtea.pulseaudio.PulseAudioMixerProvider
#javax.sound.sampled.SourceDataLine=org.classpath.icedtea.pulseaudio.PulseAudioMixerProvider
#javax.sound.sampled.TargetDataLine=org.classpath.icedtea.pulseaudio.PulseAudioMixerProvider

javax.sound.sampled.Clip=com.sun.media.sound.DirectAudioDeviceProvider
javax.sound.sampled.Port=com.sun.media.sound.PortMixerProvider
javax.sound.sampled.SourceDataLine=com.sun.media.sound.DirectAudioDeviceProvider
javax.sound.sampled.TargetDataLine=com.sun.media.sound.DirectAudioDeviceProvider
```
Editor verlassen mit STRG-K und X.
   
Raspi-Configuration starten und folgende Einstellungen vornehmen:
- Umstellen audio auf headphone
```
sudo raspi-config
```

## Splash-Screen installieren:

Bearbeiten der Datei `/boot/config.txt`:
```
sudo joe /boot/config.txt
```
Folgende Zeile hinzufügen:
```
disable_splash=1
```

Bearbeiten der Datei `/usr/share/plymouth/themes/pix/pix.script`:
```
sudo joe /usr/share/plymouth/themes/pix/pix.script
```
Folgende Zeilen auskommentieren:
```
message_sprite = Sprite();
message_sprite.SetPosition(screen_width * 0.1, screen_height * 0.9, 10000);
my_image = Image.Text(text, 1, 1, 1);
message_sprite.SetImage(my_image);
```

Bearbeiten der Datei `/boot/cmdline.txt`:
```
sudo joe /boot/cmdline.txt
```
- `console=tty1` durch `console=tty3` ersetzen
- und folgende Parameter ans Ende der Zeile anfügen:
```
splash quiet plymouth.ignore-serial-consoles logo.nologo vt.global_cursor_default=0
```

Splash-Screen anpassen:
```
sudo cp ~/vz200/desktop-wallpaper-1.png /usr/share/plymouth/themes/pix/splash.png
```
Quelle: https://scribles.net/customizing-boot-up-screen-on-raspberry-pi/

In der Desktop-Umgebung das Hintergrundbild `~/vz200/desktop-wallpaper-1.png` einstellen.

## Lautstärke auf Maximum stellen:
```
amixer sset 'Master' 65536
```
Taskleiste ausblenden: Rechtsklick auf Taskleite - Leisteneinstellungen - Erweitert: Leiste bei Nichtbenutzung minimieren + Größe bei minimiertem Zustand: 0 Pixel

HDMI-Settings in /boot/config.txt anpassen: `disable-overscan=1`, `hdmi_group=1`, `hdmi_mode=3`

Nach einem Reboot sollte der Emulator im Vollbildmodus starten.

**[ZURÜCK](README.md)**
