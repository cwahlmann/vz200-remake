**[BACK](README.md)**
# <a name="installation">Prepare and install the Emulator on the Raspberry Pi</a>

## Build the project with Gradle

From the Emulator sub directory run
```
gradle createVZ200Zip
```

You'll get a zip file with all the files required located at `build\distributions\JemuVZ200.zip`.

## Install the desktop variant of Raspbian OS

Follow the instructions on https://www.raspbian.org/ by using the image for "Raspbian Buster Desktop Lite".

## Install the emulator

Copy and extract the Zip file to the home directory of the Raspberry.
The resulting directory structure should look like this:

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

## Make the start script executable 

If you built the Emulator on a Windows machine perform two additional steps:

1. Install `dos2unix`:
```
sudo apt-get install dos2unix
```

2. Convert Linefeeds to Unix Style:
```
dos2unix vz200.desktop
dos2unix vz200.sh
```

Set Execute Flag:
```
chmod +x vz200.sh
```

## Launch Emulator automatically

Copy the file `vz200.desktop` to the autostart directory:
```
mkdir ~/.config/autostart
cp vz200.desktop ~/.config/autostart
```

## Install joe Text Editor

```
sudo apt-get install joe
```
(You may also use the already installed `nano` editor)

## Install JAVA and the ALSA Sound Driver

Install OpenJDK-8 Runtime and ALSA Driver by `apt-get`:
```
sudo apt-get install openjdk-8-jre
sudo apt-get install alsa-base alsa-utils
```

Adapt the Java Sound Configuration (comment PulseAudio, uncomment DirectAudioDevice):
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
Exit the Joe Editor by STRG-K and X.

Launch Raspi Configuration and change the following Settings:
- Switch audio to headphone 
```
sudo raspi-config
```

## Install the Splash-Screen:

Edit `/boot/config.txt`:
```
sudo joe /boot/config.txt
```
Add this line:
```
disable_splash=1
```

Edit `/usr/share/plymouth/themes/pix/pix.script`:
```
sudo joe /usr/share/plymouth/themes/pix/pix.script
```
Comment these lines:
```
message_sprite = Sprite();
message_sprite.SetPosition(screen_width * 0.1, screen_height * 0.9, 10000);
my_image = Image.Text(text, 1, 1, 1);
message_sprite.SetImage(my_image);
```

Edit `/boot/cmdline.txt`:
```
sudo joe /boot/cmdline.txt
```
- Replace `console=tty1` with `console=tty3`
- and add this parameter to the end of the line:
```
splash quiet plymouth.ignore-serial-consoles logo.nologo vt.global_cursor_default=0
```

Adapt Splash Screen:
```
sudo cp ~/vz200/desktop-wallpaper-1.png /usr/share/plymouth/themes/pix/splash.png
```
Source: https://scribles.net/customizing-boot-up-screen-on-raspberry-pi/

From within the Desktop Environment change the background image to `~/vz200/desktop-wallpaper-1.png`.

## Set Volume to Max:

```
amixer sset 'Master' 65536
```
Hide Taskbar: : Right Click on Taskbar -> Bar Settings -> Advanced: Minimize Task Bar when not used + Size when minimized: 0 Pixel

Adapt HDMI Settings in /boot/config.txt: `disable-overscan=1`, `hdmi_group=1`, `hdmi_mode=3`

After a reboot the Emulator should launch in Fullscreen Mode. 

**[BACK](README.md)**
