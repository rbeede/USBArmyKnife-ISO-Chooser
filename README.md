# USBArmyKnife-ISO-Chooser
Script that uses an ESP32-S3 with USBArmyKnife to allow selecting an ISO to present as a CDROM device

Similar to tools like Ventoy, Grub2, or Rufus but allows for additional compatiblilty for booting. It also simplifies SecureBoot and allowing the user to select an ISO without having to extract or modify the ISO contents.

See my blog entry <a href="https://www.rodneybeede.com/security/ESP32-USB-Army-Knife.html">ESP32 USB Army Knife Tutorial</a> for an example of setup.

To use with an already flashed ESP32-S3 device just copy the .iso files to the storage card, plug into the ESP32 device, then plug-in the ESP32 to a USB port. If your device has a display it will give instructions and allow you to see which ISO you can mount.

See also <a href="https://github.com/i-am-shodan/USBArmyKnife/tree/master/examples/simple_ui">https://github.com/i-am-shodan/USBArmyKnife/tree/master/examples/simple_ui</a> for code syntax examples.

### The Catch

The LilyGo T-Dongle S3 USB device (ESP32-S3) did successfully mount the ISO and show it as a CDROM on a computer. However, the I/O read performance from the device was super, super slow and not really usable for an ISO. Around 355KB/s which was not usable.

Additionally, the firmware only supported FAT32 for filesystems so ISOs larger than 4GB could not be loaded onto the microSD card.
