## Handsolderable version of Ploopy Adept BLE modification

Original work forked from : https://github.com/taichan1113/AdeptBLE

# Excuse

AdeptBLE is a great idea, but it uses 0603 components, I wanted to use 0806 as they are more managable, and easy to handsoler

## electronics

Designed by KiCAD and produted by [JLCPCB](https://jlcpcb.com/)

Basically you need XIAO nRF52840 board, PMW3610 optical sensor, omron D2LS-21 mouse switch, 6-pin slide switch and battery.

Other parts are set as below.

TODO - Provide updated BOM

## firmware (Stock firmware from taichan1113 will work)

Here includes uf2 file built by zmk.

You can find the code [here](https://github.com/taichan1113/mouse-test/tree/main).

## housing

I updated the houseing to support the pcb better, and have cutout for battery wire below the pcb to avoid any mis-alignment.

## NOTE: 

Desin are not tested in very depth, i created one single prototype which is working without issues, YMMV. reach out in case you find issues or open PR.