[![change to english version](images/en.png)](en)

# vz200-remake
Ein Nachbau des VZ200 Color Computers (Vtech / Dick Smith 1983)

![Prototyp](images/vz200-teaser.jpg "VZ200 - 70%")

# *VZ200-remake* auf der Makerfaire-Ruhr

    Wir haben uns sehr gefreut, im Programm der Makerfaire-Ruhr in Dortmund dabei zu sein.
    
    Allerdings wurde die Messe aufgrund der aktuellen Corona-Krise abgesagt, was wir einerseits sehr bedauern, 
    andererseits aber auch nachvollziehen können, denn die Gesundheit geht vor.

    Stattdessen werden wir jetzt nach und nach alles, was wir dort präsentieren wollten, 
    online stellen. Möge der eine oder die andere glückliche Stunden damit verbringen,
    den VZ200 nachzudrucken, zusammenzulöten und aufzubauen!
    
    Sollte die Makerfaire später im Jahr nachgeholt werden, was wir hoffen, so stehen die
    Chancen gut, dass wir uns dort sehen ;-) 

Hier findet ihr schon mal das Video, das bei der Makerfaire im Hintergrund mitlaufen sollte:

[![VZ200 Presentation Makerfaire](images/vz200-remake-presentation-youtube.png)](https://www.youtube.com/watch?v=7TxQ1y71ufA)

[![makerfaire-ruhr.com/maker2020](images/makerfaire-ruhr-banner.png)](https://www.makerfaire-ruhr.com/meet-the-makers)

![Screenshot_02](images/screenshot_02.png "Basic Programming")
![Screenshot_03](images/screenshot_03.png "Charset")
![Screenshot_05](images/screenshot_05.png "the hunter - bit by a bat")

# Das erwartet dich:

* Design- und Druckdaten für ...

... einen VZ200 Color Computer in 70% Originalgröße

... einen Monitor mit TFT-Display, Raspberry PI und Lautsprecher

* Platinendesign und .gbr-Dateien für eine funktionierende Tastatur
* VZ200-Emulator (basierend auf 'jemu': http://jemu.winape.net) mit Datasette-Emulation und REST-Schnittstelle
* VZ200 Companion App zur Fernsteuerung des VZ200 über die REST-Schnittstelle
* Liste aller benötigten Bauteile
* detaillierte Bau- und Installationsanleitung

# Impressionen von der Baustelle
 
Der VZ200 sollte eine voll funktionsfähige Gummitastatur bekommen. Gelöst haben wir das mit einer selbst designten Platine mit Drucktastern, auf der die gedruckte Matte mit Gummitasten liegt, verbunden mit einem USB-Tastaturcontroller. In Einzelteilen: 

![img_chassis_19_platine_teile](images/img_chassis_19_platine_teile.jpg "Tastatur in Einzelteilen")

Der Emulator läuft auf einem Raspberri PI 3b und einem aufgesetzten 5 Zoll HDMI-Display. Für den Sound sorgt ein kleiner Verstärkerchip. Alles zusammen wird in ein Monitorgehäuse eingebaut.

![img_monitor_12_raspberry_tft_audio_funktion](images/img_monitor_12_raspberry_tft_audio_funktion.jpg "VZ200 auf dem Raspi mit Sound")

Hier ein Bild des ersten fertigen Modells. Den Source zum Spiel gibt es unter [the-hunter.asm](examples/the-hunter.asm), oder als .VZ-File [thehunter.vz](examples/thehunter.vz)

![VZ200-komplett-5Zoll-Monitor-TheHunter](images/VZ200-komplett-5Zoll-Monitor-TheHunter.jpg "das erste fertige Modell")


