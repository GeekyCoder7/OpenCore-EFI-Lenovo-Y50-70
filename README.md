## OpenCore EFI for Lenovo Y50-70 (FHD-1080p and UHD 4K) updated for Big Sur

### For installing BigSur use PRE-EFI.
### After installation, use POST-EFI.


### Updated to OpenCore 0.6.4

**Specs:**
  - Intel Core i7-4710HQ
  - Intel HD4600 integrated GPU
  - Nvidia GTX 860M 4GB (unsupported)
  - 16GB DDR4 Ram
  - Broadcom BCM94352Z (Network card)
  
  
  ### For UHD users ONLY:
  - If you wish to use "Config-UHD.plist", you need to delete "Config.plist" and rename "Config-UHD.plist" to "Config.plist"
  
  
  ### For Dual Boot Users ONLY:

 - Download  [OpenCore Configurator](https://mackie100projects.altervista.org/download-opencore-configurator) (OCC) 
 - Open your Config.plist with OCC
 - Go to Misc and click Entries tab
 - Click '+' button on the right bottom. A new entry will be created and you will see a browse button
 - Click the browse button and for windows users, go to your EFI folder  and locate bootmgfw.efi  (\EFI\Microsoft\Boot\bootmgfw.efi) and click open
 - Change the entry name from bootmgfw to Windows

  
 
 Before updating any kext create pendrive copy of actual EFI so if something wont
 work you can restore it.
 
 **What works:**
 
- Dual Boot with Windows
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
 - accelerated graphics for HD4600 (both 1080p and 4K)
 - wired Ethernet
 - retina scaling
 - Sleep/Wake
 - Auto Brightness Sensors
 - iMessage & Facetime
 - Brightness keys on keyboard (Fixed by migrating from ApplePS2SmartTouchPad.kext to VoodooPS2Controller.kext)



### Notes: 
- In order to use iMessage and Facetime you need to change your SMBIOS, with GenSMBIOS.<br>
Link: https://github.com/corpnewt/GenSMBIOS <br>
- For those having issues with the display color, for some users the display color have a light brownish tint. <br>
In order to fix this you need to calibrate your display colors, by going into display settings from system preferences, then click calibrate from the color tab. <br>
- You may need to modify keys for the keyboard. For me the command was swapped with alt button (windows button on keyboard). So in order to fix this do the following: <br>
  1.) Go to System Preferences -> Keyboard -> Modifier Keys <br>
  2.) Change "Option Key" to "Command" <br>
  3.) Change  "Command Key" to "Option" <br>

