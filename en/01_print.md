**[BACK](README.md)**
# <a name="print">Designing and printing the Parts</a>
## 3d Model
The model has been designed with Autodesk Fusion 360.

**Word of advice**: The model of the computer case and the electronics within are sized at 70% of the original size. The STL files do reflect this already, though in the Fusion files (.3mf) the case still has it's original size. If you want to build the replica in 100% you need to adjust the ports for the keyboard controller and circuit board before having it being acit-treat. Also most likely the positon of the reset button holder needs to be adapted.

![3d-Layout bottom](../3d-model/screenshots/VZ-Fusion-v3-Boden.png "3d Layout bottom")
![3d-Layout Monitor](../3d-model/screenshots/monitor-v2_2.png "3d Layout Monitor")

## Resources and downloads

Hardware
* [STL files on Thingiverse](https://www.thingiverse.com/thing:4415555)
* [Gerber-files for keyboards circuit board](../resources/gerber/vz200-keyboard-layout.zip)
* [Graphics for the keyboard](resources/aufkleber/Aufkleber-2x70perc.png)
* [Graphics for the logo](resources/aufkleber/logo_7x70perc_A4.png)

Software
* [JemuVZ200 Emulator V2.0](resources/releases/JemuVZ200-2.0.zip)
* VZ200 Companion App (TODO)

Documentation and Examples
* [Z80 instruction set](resources/doc/z80.pdf)
* [VZ200 Basic instruction set](resources/doc/VZ200-Basic.pdf)
* ["Hello World" (assembler) tutorial](resources/doc/tutorial/hello-world-asm-tutorial.pdf)
* ["Side Scrolling" (assembler) tutorial](resources/doc/tutorial/side-scroll-asm-tutorial.pdf)
* [Tutorial presentation (LibreOffice)](resources/doc/tutorial/VZ200-tutorial.odp)

Sources are available at:
* https://github.com/cwahlmann/vz200-remake

## Printing

The STL files exported from Fusion 360 have to be prepared and sliced for printing, we used Cura 4.x. This project already contains GCODE files for Creality Ender 3. 

We recommend printing with PLA for the VZ200 Case, the keyboard mask and the reset button. For the keyboard mat a flexible material is required, like NinjaFlex or TPU.

With the VZ200 we use white for the case, chocolade brown for the keyboard mask and any color for the keyboard mat, it will be painted later anyways.

**[BACK](README.md)**
