# What?
A simple Magisk module for Android which remaps physical hardware keys to any of Android's [virtual software keycodes]([https://source.android.com/devices/input/key-character-map-files). For example, remapping your physical *CAPS_LOCK* key to *KEYCODE_POWER* (power button).

By default in release `v1.0`, the following keys are remapped:
* CAPS_LOCK --> KEYCODE_POWER
* NUMPAD_MULTIPLY --> KEYCODE_POWER

# Why?
Why not?  :)

# How?
This is accomplished by modifying `Vendor_ffff_Product_ffff.kl` and `Vendor_ffff_Product_ffff.kcm` in `/system/usr/keychars/`. Thanks to Magisk, we can inject these files systemlessly without modifying the root filesystem; the net effect is the same.

This module has been tested to work with [scrcpy](https://github.com/Genymobile/scrcpy) in OTG mode (`scrcpy --otg --hid-keyboard --hid-mouse`). Android detects `scrcpy`'s OTG mode as a Generic [HID](https://en.wikipedia.org/wiki/Human_interface_device) (specifically Device `ffff` with Vendor `ffff`), which is the same as any physical keyboard connected via USB.

This module has been tested to work on stock Android 11, 12 & 13, but _should_ still be compatible back to Android 7.

# Help?!
This module does not include any options for customization. However, doing so is trivial. If you wish to add or modify any key bindings, you can download the [latest release](https://github.com/Jefferderp/Magisk-KeyboardRemaps/releases/latest), unpack the zip file, and modify `Vendor_ffff_Product_ffff.kl` as desired. The existing file contains my customizations, which are clearly notated. Refer to [this page](https://developer.android.com/reference/android/view/KeyEvent) for a list of valid keycodes. Once finished, re-zip the module and install via Magisk.

See [Issue #3](https://github.com/Jefferderp/Magisk-KeyboardRemaps/issues/3) if you get stuck.

# I said help!?
While I appreciate your interest in this module, I'm not offering support unless you have a specific question. Every Android device is different, and you will need to find, modify and inject the specific file which determines your keycode mappings.

Thanks to the following resources which helped me put this together:
* http://gustavepate.github.io/blog/20130714/android-keyboard-layout-logitech-tablet-keyboard/
* https://developer.android.com/reference/android/view/KeyEvent
* https://source.android.com/devices/input/key-character-map-files
* https://forum.xda-developers.com/t/how-to-remap-mouse-buttons-and-is-possible-to-make-kl-and-kcm-files-for-it.3190940/
* https://topjohnwu.github.io/Magisk/guides.html
