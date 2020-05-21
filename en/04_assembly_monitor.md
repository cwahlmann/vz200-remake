**[BACK](README.md)**
# <a name="monitor">Monitor Assembly with TFT Display, Raspberry-Pi and Speaker</a>

## Required Parts

| Part | Description |
| ------- | ------------ |
| 3D Printed parts | Case Front and Back, Front Plate (optional), holding ring for speaker, 4 rubber feet (TPU) |
| Audio Amplifier | Mini Audio Amplifier PAM8403 DC 5V |
| 3.5" Stereo plug | best use a used one since it has to be ripped apart anyway |
| Speaker | 2" / 5 cm mini speaker 3 W 4 Ohm |
| Resistors for the voltage divider : 1x 1000 kOhm, 1x 47 Ohm| This divider reduces the voltage directly at the speaker to minimize volume and amplifier noise |
| Raspberry Pi | Modell >= 3b |
| TFT-Display | JOY-iT 5“ HDMI Touchscreen Display |
| 4 screws M2 6mm | To attach the speaker within the case |
| 4 screws M2 8mm | To assemble and fasten the case |
| 4 screws M2 6mm| To attach the display |
| Double side adhesive tape | To attach the Audio Amplifier |

Attention: Other than the VZ 200 model the Monitor parts do not need to be scaled down to 70%.

![Audio schematics](../audio/audio_schaltplan_skaliert.png "Audio Amplifier Schematics")
![Parts Printed](../images/img_monitor_02_bauteile_druck.jpg "Parts Printed")
![Electric parts](../images/img_monitor_01_bauteile_elektrisch.jpg "Electric parts")

## Assemble the Monitor

Attach the TFT display to the GPIO Pins of the Raspberry and then connect both parts with the HDMI bridge.

![TFT Display](../images/img_monitor_03_raspberry_tft.jpg "TFT Display")
![TFT Display](../images/img_monitor_04_raspberry_tft_2.jpg "TFT Display")

The Audio Amplifier "PAM8403" amplifies the Raspberry signal quite a bit, yet also produces a lot of noise. By inserting a voltage divider and resistors both audio volume and noise will be dampened to an acceptable level.

![Speaker voltage divider](../images/img_monitor_05_speaker_spannungsteiler.jpg "Speaker voltage divider")
![Speaker voltage divider Detail](../images/img_monitor_06_speaker_spannungsteiler_2.jpg "Speaker voltage divider Detail")

Solder the audio cable to the audio plug as shown here.

![Audio cable](../images/img_monitor_07_klinke.jpg "Audio cable")
![Audio cable Detail](../images/img_monitor_08_klinke_2.jpg "Audio cable Detail")

Power for the audio amplifier is taken from the GPIO pins of the TFT display (the display only utilizes a few Pins itself).

![Solder Power Cable](../images/img_monitor_09_audioverstärker_power.jpg "Solder Power Cable")
![Power Cable](../images/img_monitor_10_audioverstärker_power_2.jpg "Power Cable")

Here's how the completed cabeling looks like. Please pay attention to the labels on the amplifier board, those plugs must be plugged in with the correct orientation.

![Audio Cabeling](../images/img_monitor_11_audio_gesamt.jpg "Audio Cabeling")

The VZ200 can be now run through a first test.

![functional test](../images/img_monitor_12_raspberry_tft_audio_funktion.jpg "functional test")

To avoid shortages, apply an isolating tape to the long resistor of the voltage divider. 

![Speaker isolation](../images/img_monitor_13_speaker_isolierung.jpg "Speaker isolation")

Attach the speaker with the 3D printed ring to the back case and fasten it with four screws. Use double side adhesive tape to attach the audio amplifier.

![Monitor Speaker and Amplifier assembly](../images/img_monitor_14_speaker_verstärker_einbau.jpg "Monitor Speaker and Amplifier assembly")

Then use another 4 screws to attach the TFT display with the plugged in Raspberry to the case front.

![Monitor TFT & Rasbpi assembly](../images/img_monitor_16_raspberry_tft_einbau_2.jpg "Monitor TFT & Rasbpi assembly")

To complete the monitor interior plug in all cables to the amplifier board and assemble the two monitor parts by fastening them with 4 screws.

![Cabeling](../images/img_monitor_17_verkabelung_gesamt.jpg "Cabeling")

Glue the four monitor feet onto the bottom side of the monitor.

![Glue rubber feet](../images/img_monitor_18_gummifuesse.jpg "Glue rubber feet")

Then either glue the seperately printed front panel to the front or design your own one. 

![Glue monitor front panel](../images/img_monitor_21_monitor_front.jpg "Glue monitor front pane")

Now paint the monitor to your liking. Here is an example in a 1950er retro look;

![Painted Monitor](../images/img_monitor_22_monitor_bemalt.jpg "Painted Monitor")

**[BACK](README.md)**
