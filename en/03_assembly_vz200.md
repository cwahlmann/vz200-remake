**[BACK](README.md)**
# <a name="assemblyvz200">Assembly of the VZ200</a>

The case contains a fully functional keyboard with power LED and a reset button.

At a size of 70 % of the original VZ200 the Raspberry Pi will not fit into the case, thus it will be integrated into the monitor. The VZ200 will be connected to the Raspberry by a USB 2.0 cable.

## Required Parts

| Part | Description |
| ------- | ------------ |
| 3D printed parts | Bottom case, Back cover, Keyboard (Frame, mask, keyboard mat), Reset Switch + Clamp |
| Printed Logo | clear, self adhesive and transparent A4 Polyester foil for ink jets |
| Printed Keys on vinyl sheet | white matt self adhesive A4 vinyl foil for ink jets |
| Printed Keyboard mask on vinyl sheet  | white matt self adhesive A4 vinyl foil for ink jets |
| Scale modeling color | e.g. EMAIL COLOR by Revell, matt 35 (skin tone) and matt 85 (brown) |
| Keyboard circuit board | available through various workshops by providing the accompanied GBR files |
| Keyboard controller | an USB keyboard controller with predefined mapping: KEYWARRIOR24_8_MODUL_KW24_8_MOD |
| USB cabel | USB cable with a 2.0 plug on one and bare wires on the other end |
| 45 micro switches | To be soldered to the keyboard cirquit board, 6x6 mm |
| 1 red LED | Power-LED, 3mm |
| 1 resistor | 150 Ohm (brown / green / brown) |
| Small piece of perforated circuit board | Used for the reset button, hole distance 2.54 mm |
| 1 micro switch | for the reset button, 6x6 mm |
| 2 x red / white wire ca. 10 cm | to connect the POWER LED and the reset button |
| 2 x 8 core flat cable ca. 10 cm | to connect keyboard controller to keyboard cirquit board |
| Isolation tape | to isolate reset button from keyboard cirquit board | 
| 7 small screws M2 5mm | to attach keyboard controller and cirquit board |
| 2 short screws M2 8mm | to attach reset button board |
| 2 short M2 5mm and 2 long M2 20mm screws | to assemble the VZ200 case |

## Attach the Logo to the back VZ200 casing
![Sticker Logo](../images/resized/img_chassis_01_aufkleber_logo.jpg "Sticker Logo")

Apply the printed logo to the back case cover as shown in the picture.

![Back case cover](../images/resized/img_chassis_02_abdeckung_hinten.jpg "Back case cover")

## Assemble the keyboard
For this step you require the printed keyboard mat, the scale modeling color and the printed keyboard stickers. Do not use Airbrush or any other spraying color as this will soak the TPU and increase it's size substantially.

The keys of the mat need to be painted first with Revell Matt 35, Skin Color as a base color, then overpainted with Matt 35, brown. There is no need to paint the whole mat as it is also covered by the keyboard mask, plus this helps fitting the keys into the mask and allow them move freely.

![Keyboard mat and stickers](../images/resized/img_chassis_03_aufkleber.jpg "Stickers")
![Keyboard mat and stickers](../images/resized/img_chassis_04_tastaturmatte.jpg "Keyboard Mat")

The stickers have to be cut now.

![Cutting the keyboard stickers](../images/resized/img_chassis_05_aufkleber.jpg "Cutting the keyboard stickers")
![Cutting the keyboard stickers 2](../images/resized/img_chassis_06_aufkleber.jpg "Cutting the keyboard stickers 2")

Important notice: To achieve a rounded look cut the corners diagonally.

![Cutting the keyboard stickers 3](../images/resized/img_chassis_07_aufkleber.jpg "Cutting the keyboard stickers 3")
![Cutting the keyboard stickers 4](../images/resized/img_chassis_08_aufkleber.jpg "Cutting the keyboard stickers 4")
![Cutting the keyboard stickers 5](../images/resized/img_chassis_09_aufkleber.jpg "Cutting the keyboard stickers 5")

The cut stickers are now applied on to the keyboard mat.

![Applying the keyboard stickers](../images/resized/img_chassis_10_tastaturmatte_aufkleber.jpg "Applying the keyboard stickers")
![Applying the keyboard stickers](../images/resized/img_chassis_11_tastaturmatte_aufkleber.jpg "Applying the keyboard stickers")

Now to prepare the keyboard mask. Have the 3d printed mask and the ink jet printed sticker ready.

![Keyboard mask sticker](../images/resized/img_chassis_12_tastaturabdeckung_aufkleber.jpg "Keyboard mask sticker")

Now cut the holes for the keys and the Power LED.

![Keyboard mask sticker cutting](../images/resized/img_chassis_13_aufkleber.jpg "Keyboard mask sticker cutting")
![Keyboard mask sticker cutting 2](../images/resized/img_chassis_14_aufkleber.jpg "Keyboard mask sticker cutting 2")

Now the sticker will be applied to the mask. Carefully adjust the sticker to make sure the holes are centered around their counterparts on the mask.

There will be a small margin left so that the keys won't be hampered by the sticker.

![Apply Keyboard mask sticker](../images/resized/img_chassis_15_tastaturabdeckung_aufkleber.jpg "Apply Keyboard mask sticker")

Now the keyboard mat will be inserted into the mask's back and the mask inserted into the keyboard frame.

![Insert Keyboard mask into the frame](../images/resized/img_chassis_17_abdeckung_vorne_komplett.jpg "Insert Keyboard mask into the frame")
![Keyboard mask in frame from below](../images/resized/img_chassis_18_abdeckung_vorne_unten.jpg "Keyboard mask in frame from below")

## Soldering and assemblying of the electronics

The Image shows an overview of the parts required:

![Parts overview circuit board](../images/resized/img_chassis_19_platine_teile.jpg "Parts overview circuit board")

The reset button goes onto the perforated mini board:

![Reset button](../images/resized/img_chassis_20_platine_reset.jpg "Reset button")
![Reset button 2](../images/resized/img_chassis_21_platine_reset.jpg "Reset button 2")

Connect the Reset button with the red / white wire to the keyboard circuit board.

![Reset button 3](../images/resized/img_chassis_22_platine_reset.jpg "Reset button 3")

Then screw in the two short screws into the board to later attach it to the bottom case.

![Reset button 4](../images/resized/img_chassis_23_platine_reset.jpg "Reset button 4")

Now connect the USB cable to the keyboard controller like shown here. 

**Attention:** The cabel needs to be put through the hole in back of the bottom cover and knotted once inside to prevent drag on the cables.

| USB cable bare wire color | Controller port | 
| --------------------- | -------------------- |
| Red | +5V |
| White | D- |
| Green | D+ |
| Black | GND |

In addition solder the second red/white wire to +5V and GND for the Power LED.

| Power LED bare wire color | Controller port | 
| --------------------- | -------------------- |
| Redd | +5V |
| White | GND |

![Keyboard Controller 2](../images/resized/img_chassis_25_platine_controller.jpg "Keyboard Controller 2")

Now solder the grey 8-core flat cable to the Controller, at the ports X0-X7 and Y0-Y7:

![Keyboard Controller 3](../images/resized/img_chassis_26_platine_controller.jpg "Keyboard Controller 3")
![Keyboard Controller 4](../images/resized/img_chassis_27_platine_controller.jpg "Keyboard Controller 4")

Now add the micro switches, the Power LED and the resistor to the keyboard cirquit board:

![Circuit board micro switches](../images/resized/img_chassis_28_platine_taster.jpg "Circuit board micro switches")

The positive pole of the LED (long leg) needs to go into the square hole of the circuit board.

![Circuit Board Power LED](../images/resized/img_chassis_29_platine_powerled.jpg "Circuit Board Power LED")

The orientation of the microswitches goes with the distances between the holes on the circuit board.

![Circuit board micro switches 2](../images/resized/img_chassis_30_platine_taster.jpg "Circuit board micro switches 2")

Now solder the red / white wire, already connected to +5V / GND of the keyboard controller, to the keyboard circuit board. 

The white bordered soldering contact represents Negative (white bare wire), the quadratic contact is Positive (red bare wire).

After this solder the two 8-core flat cables to the keyboard circuit board. Please double check for the correct orientation and connections; the soldering contacts on the keyboard circuit board are labeled x0-x7 and y0-y7. 

![Circuit board Controller](../images/resized/img_chassis_31_platine_controller.jpg "Circuit board Controller")
![Circuit board Controller 2](../images/resized/img_chassis_32_platine_controller.jpg "Circuit board Controller 2")

Now insert the reset button into the case. First push the 3D printed reset button into the hole on the side and secure it with the clamp.

![Circuit board reset button](../images/resized/img_chassis_33_platine_reset.jpg "Circuit board reset button")
![Circuit board reset button 2](../images/resized/img_chassis_34_platine_reset.jpg "Circuit board reset button 2")

Then add the mini board with the micro switch.

![Circuit board reset button 3](../images/resized/img_chassis_35_platine_reset.jpg "Circuit board reset button 3")

Fasten the keyboard controller with three short screws to the bottom case.

![Circuit board assembly](../images/resized/img_chassis_36_platine_einbau.jpg "Circuit board assembly")

Cover the reset switch with a small piece of isolation tape to avoid contact between the screw and the keyboard cirquit board.

![Circuit board assembly 2](../images/resized/img_chassis_37_platine_einbau.jpg "Circuit board assembly 2")

Attach the cirquit board to the bottom case with four short screws.

![Circuit board assembly 3](../images/resized/img_chassis_38_platine_einbau.jpg "Circuit board assembly 3")

Last but not least add the keyboard frame and the back cover and fasten them to the bottom case with two long and to short screws.

![Chassis Assembly](../images/resized/img_chassis_39.jpg "Chassis Assembly")
![Chassis Assembly 2](../images/resized/img_chassis_41.jpg "Chassis Assembly 2")
![Chassis Assembly 3](../images/resized/img_chassis_40.jpg "Chassis Assembly 3")

Congratulations, You have just completed your first VZ200 replica!

The JEmu emulator can be run on a Raspberry Pi 3b+ or higher or on a PC. Plug in the VZ200 as an USB keyboard in either case.

Important notice: In case the keyboard produces more than one keypress unintentionally or shows multiple different chars at once on one keypress, there most likely is a shortcut between one or more of the micro switches. This may happen occasionally if not all of the very fine threads of the wires have been soldered correctly and produce a bridge to another micro switch. 

To get rid of that we recommend inspecting the circuit board under a strong lamp from every angle, probably utilizing a magnifying glas. Even the most tiny threads will light up eventually and you'll be able to cut and remove them. Focus on the keys producing erroneous results.

Another source for errors: Cold soldering contacts (this applies to the whole project). These are easily spotted by their slightly matt and milky surface. Please resolder these.

**[BACK](README.md)**
