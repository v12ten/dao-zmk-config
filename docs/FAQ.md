# FAQ

- [FAQ](#faq)
  - [How to change the keymap?](#how-to-change-the-keymap)
  - [How to flash the keyboard?](#how-to-flash-the-keyboard)
  - [How to pair halves?](#how-to-pair-halves)
  - [Problems](#problems)
    - [I'm getting File Transfer Error after copying firmware to the keyboard](#im-getting-file-transfer-error-after-copying-firmware-to-the-keyboard)
    - [The keyboard keeps disconnecting (unable to connect) continuously](#the-keyboard-keeps-disconnecting-(unable-to-connect)-continuously)

## How to change the keymap?

1. Fork the [repository](https://github.com/yumagulovrn/dao-zmk-config)
1. Make changes to the [dao.keymap](../config/boards/arm/dao/dao.keymap) file in your repository
1. Commit changes to your repository
1. Go to `Actions` tab in your repository
1. Wait for the GitHub Action to complete
1. Grab `firmware.zip` file - it contains firmware for both of your halves

## How to flash the keyboard?

1. Obtain `firmware.zip`
1. Unzip `firmware.zip` - you should have `dao_left.uf2`, `dao_right.uf2` and `settings_reset.uf2` files
1. Turn off the power for selected half (move slider to position `OFF`)
1. Connect selected half to the PC via USB-C cable
1. Press `RESET` button **twice** to enter DFU mode - you should see new USB device in your file manager
1. Copy the corresponding firmware to the root directory of the new USB device
1. Disconnect selected half from the PC
1. Repeat steps 3-7 for the other half

## How to pair halves?

1. Turn off the power for both halves (move slider to position `OFF`)
1. Turn on the power for both halves (move slider to position `ON`)
1. Press `RESET` button **once** on both halves **simultaneously**

## Problems

### I'm getting File Transfer Error after copying firmware to the keyboard

It's OK. Proof: https://zmk.dev/docs/troubleshooting#file-transfer-error

### The keyboard keeps disconnecting (unable to connect) continuously

Flash each half of the keyboard using the `settings_reset.uf2` file, and then reflash them with your own firmware