Note: this is a fork from
https://github.com/GeorgeSpinner/Adafruit_Trinket_Mini_Auto_PICKnMIX

It can be used to automatically start
[PICKnMIX](http://unibios.free.fr/picknmix.html) on a Neo Geo with Unibios 4.0
installed. It does so by simulating pressing the start button at boot.

The main differences from the original project are:
- A Makefile
- The red LED is used to show when a start button press is simulated
- There are a few precompiled .hex files for convenience, including a
  bootloader (micronucleus) which can later be updated over USB.


# Adafruit_Trinket_Mini_Auto_PICKnMIX
Auto-start PICKnMIX with Adafruit Trinket Mini 3v/5v PCB
(5V recommended)
## Adafruit Trinket Mini 3v/5v Auto PICKnMIX for MVS 161 in 1 (Banana Cart)

Start button will be held for 5 seconds with POWER ON (the red LED will also be on)

If any button wired to pin 2 is held during POWER ON sequence, the regular 161 in 1 menu will be displayed

How to setup:
  - PWR - JAMMA PIN 3
  - GND - JAMMA PIN 1
  - 0   - JAMMA PIN 17
  - 2   - JAMMA PIN 25 <--- Careful, this is not PIN 1 but PIN 2

In the above setup - The Holding the D button during POWER ON will skip PICKnMIX

### Does NOT work with standard Adafruit Trinket Mini 3v/5v bootloader (takes more than 2 seconds before code executes)
Must use Bootloader found here: https://forums.adafruit.com/download/file.php?id=34218 (trinketloader_skippow25.zip) 

Or you can use the micronucleus bootloader in prebuilt/micronucleus-bootloader.hex (the micronucleus command line
utility can later be used to update code etc - use a USB 2.0 port for that). This bootloader was slightly modified
to reduce boot time (FAST_EXIT_NO_USB_MS set to 300).
