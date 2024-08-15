# What?
A simple Magisk module for Android which remaps physical hardware keys to virtual software keys. For example, remapping your physical *CAPS_LOCK* key to *KEYCODE_POWER* (power button).

# Why?
Why not?  :)

# How?
This is accomplished by injecting modified versions of `Vendor_ffff_Product_ffff.kl` and `Vendor_ffff_Product_ffff.kcm` to /system/usr/keychars/ via Magisk.

This module has been tested to work with [scrcpy](https://github.com/Genymobile/scrcpy) in OTG mode (`scrcpy --otg --hid-keyboard --hid-mouse`), which Android detects as a Generic [HID](https://en.wikipedia.org/wiki/Human_interface_device) (Device `ffff` with Vendor `ffff`). This has been tested to work with Android 11 through 13, but should work with Android 7 (or possibly earlier).

By default in `v1.0`, the following keys are remapped:
* CAPS_LOCK --> KEYCODE_POWER
* NUMPAD_MULTIPLY --> KEYCODE_POWER

This module does not currently offer user customization. If you wish to add or modify any key bindings, you can download the [latest release](https://github.com/Jefferderp/Magisk-KeyboardRemaps/releases/latest), unpack the zip file, and modify `Vendor_ffff_Product_ffff.kl` as desired. The existing file contains my customizations, which are clearly notated. Refer to [this page](https://developer.android.com/reference/android/view/KeyEvent) for a list of valid keycodes. Once finished, re-zip the module and install via Magisk.

# Help?!
While I appreciate your interest in this module, I am typically unavailable for technical support. That said, please *feel free to open an issue* if you see something wrong with this code.

Thanks to the following resources which helped me put this together:
* http://gustavepate.github.io/blog/20130714/android-keyboard-layout-logitech-tablet-keyboard/
* https://developer.android.com/reference/android/view/KeyEvent
* https://source.android.com/devices/input/key-character-map-files
* https://forum.xda-developers.com/t/how-to-remap-mouse-buttons-and-is-possible-to-make-kl-and-kcm-files-for-it.3190940/
* https://topjohnwu.github.io/Magisk/guides.html
