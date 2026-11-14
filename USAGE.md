# Using AdeptBLE

This guide describes the keymap in `config/AdeptBLE.keymap` in the [firmware repository](https://github.com/taichan1113/mouse-test/tree/main). The prebuilt `.uf2` in this repository is an older build, so some behavior may differ.

For build instructions, see the [README](./README.md).

## Power

The slide switch on the back of the board connects the battery.

- Turn the switch on to use the trackball wirelessly.
- While USB is connected, the trackball stays powered even if the switch is off.
- The switch must be on for the battery to charge over USB.

## Connect over Bluetooth

### First connection

1. Turn the trackball on. It starts on profile 0 and is ready to pair.
2. Open the Bluetooth settings on your computer.
3. Select **AdeptBLE**. The prebuilt `.uf2` may appear as **mouse_test** instead.
4. Move the ball to check that the pointer moves.

### Connect another device

The trackball stores up to five devices, one on each profile.

1. Hold SW1 and press a button from the [Bluetooth profiles](#bluetooth-profiles) table to select an empty profile.
2. Pair the new device from its Bluetooth settings.

To switch devices later, select that device's profile the same way.

### Fix a connection

If a device won't connect, clear the pairing on both sides:

1. Select the device's profile.
2. Hold SW2 and press SW6 to clear that profile.
3. Remove the trackball from the device's Bluetooth settings.
4. Pair again.

## Buttons

This is the layout seen from the front of the board, the side with the switches, with the USB connector at the top:

```text
SW1   SW2   SW3   SW4

SW5               SW6
```

| Button | Tap | Hold |
| --- | --- | --- |
| SW1 | Back | Bluetooth profiles |
| SW2 | Forward | Device functions |
| SW3 | Middle click | Middle click |
| SW4 | Right click | Scroll |
| SW5 | Left click | Left click |
| SW6 | Turn on precision mode | Scroll |

Pressing SW3 and SW4 together is also a right click.

### Bluetooth profiles

Hold SW1 and press:

| Button | Profile |
| --- | --- |
| SW2 | 0 |
| SW3 | 1 |
| SW4 | 2 |
| SW5 | 3 |
| SW6 | 4 |

### Device functions

Hold SW2 and press:

| Button | Action |
| --- | --- |
| SW1 | Enter firmware update mode |
| SW6 | Clear the current Bluetooth profile |

## Scroll and precision modes

- **Scroll:** Hold SW4 or SW6 and roll the ball to scroll. Scrolling stops when you release the button.
- **Scroll lock:** While holding SW4 or SW6, press SW3 or SW5 to keep scrolling after you release. Press SW4 or SW6 to return to normal.
- **Precision:** Tap SW6 to slow the pointer to one fifth of its speed. Tap SW6 again to return to normal.

## Change the buttons

You can remap the buttons without rebuilding the firmware, using [ZMK Studio](https://zmk.studio/). The firmware source has ZMK Studio enabled. The prebuilt `.uf2` in this repository may not.

1. Connect the trackball to your computer over USB. ZMK Studio doesn't work over Bluetooth.
2. Open [zmk.studio](https://zmk.studio/) in Chrome or Edge, and select **AdeptBLE**.
3. Select a button, then choose its behavior and key.
4. Click **Save**. Unsaved changes are lost when the trackball restarts.

To add a shortcut, such as copy, use **Key Press** with the key and its modifier, for example `C` with **L GUI** for Cmd + C on macOS. The `Copy` and `Paste` keys in the key list don't work on macOS.

To undo all your changes, use **Restore Stock Settings** in ZMK Studio.

## Update the firmware

1. Connect the trackball to your computer over USB.
2. Hold SW2 and press SW1, or double-press the reset button on the XIAO. A USB drive appears.
3. Copy the new `.uf2` file to the drive. The XIAO restarts when the copy finishes.
