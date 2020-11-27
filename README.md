## OpenCore EFI for Lenovo Y50-70 (SHD-1080p) updated for Big Sur

### For installing BigSur use PRE-EFI.
### After installation, use POST-EFI.

### Updated to OpenCore 0.6.3

**Specs:**
  - Intel Core i7-4710HQ
  - Intel HD4600 integrated GPU
  - Nvidia GTX 860M 4GB (unsupported)
  - 16GB DDR4 Ram
  - Broadcom BCM94352Z (Network card)

 
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
 


Note: In order to use iMessage and Facetime you need to change your SMBIOS, with GenSMBIOS.<br>
Link: https://github.com/corpnewt/GenSMBIOS
