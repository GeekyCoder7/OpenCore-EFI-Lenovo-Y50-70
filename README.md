## OpenCore EFI for Lenovo Y50-70 (SHD-1080p) updated for Big Sur

### For installing BigSur use PRE-EFI.
### After installation, use POST-EFI.

### Updated to OpenCore 0.6.4

**Specs:**
  - Intel Core i7-4710HQ
  - Intel HD4600 integrated GPU
  - Nvidia GTX 860M 4GB (unsupported)
  - 16GB DDR4 Ram
  - Broadcom BCM94352Z (Network card)
  
  ### For Dual Boot Users ONLY:
 - Make sure you have your Microsoft folder in your EFI, you need to add manually into your config.plist like this: <br>
  Misc -> BlessOverride -> \EFI\Microsoft\Boot\bootmgfw.efi <br>
  Or you can simply use the file named "Config-DualBoot.plist", but you just have to delete the "Config.plist" and rename "Config-DualBoot.plist" into "Config.plist".
  
 
 Before updating any kext create pendrive copy of actual EFI so if something wont
 work you can restore it.
 
 **What works:**
 
 - built-in keyboard
 - built-in trackpad (multi gestures)
 - HDMI video/audio with hotplug
 - AirPlay mirroring to AppleTV
 - native WiFi & Bluetooth via BCM94352Z
 - native USB3
 - native audio with AppleHDA
 - built-in mic
 - built-in camera
 - native power management
 - battery status
 - backlight controls with smooth transitions, save/restore across restart
 - accelerated graphics for HD4600
 - wired Ethernet
 - retina scaling
 - Sleep/Wake
 - Auto Brightness Sensors
 - iMessage & Facetime
 - Brightness keys on keyboard (Fixed by migrating from ApplePS2SmartTouchPad.kext to VoodooPS2Controller.kext)
 
 
 


Notes: 
- In order to use iMessage and Facetime you need to change your SMBIOS, with GenSMBIOS.<br>
Link: https://github.com/corpnewt/GenSMBIOS <br>
- For those having issues with the display color, for some users the display color have a light brownish tint. <br>
In order to fix this you need to calibrate your display colors, by going into display settings from system preferences, then click calibrate from the color tab.

