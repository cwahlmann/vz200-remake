[![zur deutschen Seite](../images/de.png)](../README.md)

# vz200-remake
A remake of the VZ200 Color Computer (Vtech / Dick Smith 1983)

![Prototyp](../images/vz200-teaser.jpg "VZ200 - 70%")

# *VZ200-remake* at the Makerfaire-Ruhr

    We are pleased being part of the program of the Makerfair-Ruhr in Dortmund.
    
    To our regret the fair has been cancelled like many other events due to the Corona crisis going on,
    though we do understand the reasoning behind this. Health comes first.  

    To make up for it we now will put online all the material we meant to present to you
    at the makerfaire. May some of you spend happy hours reprinting,
    souldering and assembling the VZ200! 
        
    If there is any chance for the faire to be held later this year, you most
    likely will find us there ;-)

Here you already find the video, that should have been running in the background of the faire:

[![VZ200 Presentation Makerfaire](../images/vz200-remake-presentation-youtube.png)](https://www.youtube.com/watch?v=7TxQ1y71ufA)

[![makerfaire-ruhr.com/maker2020](../images/makerfaire-ruhr-banner.png)](https://www.makerfaire-ruhr.com/meet-the-makers)

![Screenshot_02](../images/screenshot_02.png "Basic Programming")
![Screenshot_03](../images/screenshot_03.png "Charset")
![Screenshot_05](../images/screenshot_05.png "the hunter - bit by a bat")

# that's waiting for you:

* design- and printdata for ...

... a VZ200 Color Computer 70% of the original size

... a monitor with built-in TFT-display, Raspberry PI and speaker

* circuit board design and .gbr files for a full functional keyboard
* VZ200 emulator (based on 'jemu': http://jemu.winape.net) with datasette-emulation and REST-interface
* VZ200 Companion App to control your VZ200 from remote by the REST-interface
* list of all needed parts
* detailled building and installation instruction

# Impressions from the construction site
 
The VZ200 should have a fully functional rubber keyboard. We solved this with a self-designed circuit board with push buttons, on which the printed mat with rubber buttons lies, connected to an USB keyboard controller. In pieces:

![img_chassis_19_platine_teile](../images/img_chassis_19_platine_teile.jpg "keyboard in pieces")

The emulator runs on a Raspberry PI 3b combined with a 5 inch HDMI display. A small amplifier chip provides the sound. Everything is built into a monitor housing.

![img_monitor_12_raspberry_tft_audio_funktion](../images/img_monitor_12_raspberry_tft_audio_funktion.jpg "VZ200 auf dem Raspi mit Sound")

Here is a picture of the first finished model. The source for the game is available at [the-hunter.asm](../examples/the-hunter.asm), or get the .VZ-file [thehunter.vz](../examples/thehunter.vz)

![VZ200-komplett-5Zoll-Monitor-TheHunter](../images/VZ200-komplett-5Zoll-Monitor-TheHunter.jpg "das erste fertige Modell")
