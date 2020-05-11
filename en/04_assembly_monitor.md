**[ZURÜCK](README.md)**
# <a name="monitor">Zusammenbau des Monitors mit TFT-Display, Raspberry-Pi und Lautsprecher</a>

## benötigte Bauteile

| Bauteil | Beschreibung |
| ------- | ------------ |
| Gedruckte Teile | Vorderseite, Front, Rückseite, Befestigungsring für Lautsprecher, 4 Gummifüße |
| Audio-Verstärker | Mini Audio Verstärkerplatine PAM8403 DC 5V (z.B. über https://www.roboter-bausatz.de) |
| 3,5er Stereo Klinkenstecker | gerne gebraucht, da dieser sowieso "entkernt" werden muss |
| Lautsprecher | 2 Zoll / 5 cm Miniaturlautsprecher 3 W 4 Ohm |
| Widerstände für Spannungsteiler: 1x 1000 kOhm, 1x 47 Ohm| der Spannungsteiler reduziert Spannung direkt am Lautsprecher und damit auch die Verstärker-eigenen Störgeräusche |
| Raspberry Pi | Modell >= 3b |
| TFT-Display | JOY-iT 5“ HDMI Touchscreen Display |
| 4 Schrauben M2 6mm | Befestigung des Lautsprechers im Gehäuse |
| 4 Schrauben M2 8mm | Verschrauben des Gehäuses |
| 4 Schrauben M2 6mm| Befestigung des Displays |

![Audio Schaltplan](audio/audio_schaltplan_skaliert.png "Audio Verstärker Schaltplan")
![Bauteile Druck](images/img_monitor_02_bauteile_druck.jpg "Bauteile Druck")
![Bauteile elektrisch](images/img_monitor_01_bauteile_elektrisch.jpg "Bauteile elektrisch")

## Zusammenbau des Monitors

Das TFT wird auf die GPIO-Pins des Raspberry aufgesteckt und anschließend mit der HDMI-Brücke verbunden.

![TFT-Display](images/img_monitor_03_raspberry_tft.jpg "TFT-Display")
![TFT-Display](images/img_monitor_04_raspberry_tft_2.jpg "TFT-Display")

Der Audioverstärker "PAM8403" verstärkt die Signale des Raspberry sehr laut, produziert dabei aber auch eine Menge Nebengeräusche. Durch einen Spannungsteiler wird die Lautstärke etwas abgedämpft, was sich positiv auf die Störgeräusche auswirkt. 

![Lautsprecher Spannungsteiler](images/img_monitor_05_speaker_spannungsteiler.jpg "Lautsprecher Spannungsteiler")
![Lautsprecher Spannungsteiler Detail](images/img_monitor_06_speaker_spannungsteiler_2.jpg "Lautsprecher Spannungsteiler Detail")

Das Audiokabel wird wie abgebildet an den Klinkenstecker gelötet.

![Audiokabel](images/img_monitor_07_klinke.jpg "Audiokabel")
![Audiokabel Detail](images/img_monitor_08_klinke_2.jpg "Audiokabel Detail")

Die Stromversorgung des Audioverstärkers wird über die GPIO-Pins am TFT-Display abgegriffen (das TFT nutzt nur wenige der Pins selbst).

![Power-Kabel Löten](images/img_monitor_09_audioverstärker_power.jpg "Power-Kabel Löten")
![Power-Kabel](images/img_monitor_10_audioverstärker_power_2.jpg "Power-Kabel")

Die Gesamtverkabelung sieht dann so aus. Bitte auf die Bezeichnungen an der Verstärkerplatine achten, die Stecker dürfen nicht verkehrt eingesteckt werden.

![Audio-Verkabelung](images/img_monitor_11_audio_gesamt.jpg "Audio-Verkabelung")

Wenn alles richtig ist, kann der rohe VZ200 schon in Betrieb genommen werden.

![Funktionstest](images/img_monitor_12_raspberry_tft_audio_funktion.jpg "Funktionstest")

Um Kurzschlüssel vorzubeugen, wird um den langen Widerstand des Spannungsteilers ein Stück Isolierband geklebt.

![Lautsprecher Isolierung](images/img_monitor_13_speaker_isolierung.jpg "Lautsprecher Isolierung")

Der Lautsprecher wird mit Hilfe des gedruckten Rings mit vier Schrauben ins Gehäuse geschraubt. Die Verstärkerplatine wird mit doppelseitigem Klebeband, einem Stück Kautschuk o.ä. angeklebt.

![Einbau in Monitor Lautsprecher und Verstärker](images/img_monitor_14_speaker_verstärker_einbau.jpg "Einbau in Monitor Lautsprecher und Verstärker")

Das TFT_Display wird mit dem angesteckten Raspberry mit vier Schrauben in der Vorderseite des Gehäuses befestigt.

![Einbau in Monitor TFT](images/img_monitor_16_raspberry_tft_einbau_2.jpg "Einbau in Monitor TFT")

Dann werden alle Kabel an die Verstärkerplatine gesteckt und die beiden Monitorhälften werden mit 4 Schrauben aneinander geschraubt.

![Verkabelung](images/img_monitor_17_verkabelung_gesamt.jpg "Verkabelung")

Unten an den Monitor werden die vier Gummifüße geklebt.

![Gummifuesse ankleben](images/img_monitor_18_gummifuesse.jpg "Gummifuesse ankleben")

Die separat gedruckte Front wird nun von vorne an das Gehäuse geklebt.

![Monitor Front aufkleben](images/img_monitor_21_monitor_front.jpg "Monitor Front aufkleben")

Wer mag, kann das Gehäuse noch nach Belieben mit Farbe versehen. Hier ein Beispiel im RETRO-Look.

![Monitor bemalt](images/img_monitor_22_monitor_bemalt.jpg "Monitor bemalt")

**[ZURÜCK](README.md)**
