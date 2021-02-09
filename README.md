# OpenCore EFI for Lenovo Y50-70 (FHD-1080p and UHD 4K) updated for Big Sur
## Updated to OpenCore 0.6.6

### For installing BigSur, use PRE-EFI.
### After installation, use POST-EFI.

#### Before using this EFI, make a copy of your EFI and read [`Notes`](#Notes) section carefully.

### Specs:
  - Intel Core i7-4710HQ
  - Intel HD4600 integrated GPU
  - Nvidia GTX 860M 4GB (unsupported)
  - 16GB DDR4 Ram
  - Broadcom BCM94352Z (Network card)
  
  
  
  ### For UHD:
  - Use `Config-UHD.plist`, but you need to delete `Config.plist` and rename `Config-UHD.plist` to `Config.plist`
  
  
  ### For Dual Boot:
  #### Method 1:
 1. Put the `Microsoft` folder into `OC` folder
 2. Download  [OpenCore Configurator](https://mackie100projects.altervista.org/download-opencore-configurator) (OCC) 
 3. Open your Config.plist with OCC
 4. Go to Misc and click Entries tab
 5. Click `+` button on the right bottom. A new entry will be created and you will see a browse button
 6. Click the browse button and for windows users, go to your EFI folder  and locate `bootmgfw.efi`  (\EFI\Microsoft\Boot\bootmgfw.efi) and click open
 7. Change the entry name from `bootmgfw` to `Windows`<br>
 Note: If you update Windows, Windows will write the files on `EFI\Microsoft`. You will need to move the new files to `EFI\OC\Microsoft`
 
 #### Method 2:
  1. Download [EasyUEFI](https://www.easyuefi.com/index-us.html)
  2. Add a new boot entry with the path `EFI/BOOT/BOOTx64`
  3. If Windows and Big Sur are on the same drive, you will need to add a BlessOveride from Misc using OCC. The BlessOveride entry is the following:<br>
  ```\EFI\Microsoft\Boot\bootmgfw.efi```


  

 
 ### What works:
 
 - Dual Boot with Windows
 - Disabled OC injections with Windows (Fixed the issue with Lenovo Vantage recognizing your Lenovo as a mac)
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
 - Brightness keys on keyboard (Fixed by migrating from `ApplePS2SmartTouchPad.kext` to `VoodooPS2Controller.kext`)
 - Built in Card Reader with Sinetek-rtsx

### Setup SMBIOS:

1. Download [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS)
2. Do the following:
```
cd GenSMBIOS
chmod +x GenSMBIOS.command
./GenSMBIOS.command
```
3. Install MacSerial
4. Generate SMBIOS
5. Type `MacBookPro11,4` (You can use anything from 11,1 to 11,4)
6. You will get your SMBIOS: Type, Serial, Board Serial and SmUUID.
7. Edit your Config.plist either with OCC or Xcode or TextEdit: <br>
  i. `Type` to `Generic -> SystemProductName` <br>
  ii. `Serial` to `Generic -> SystemSerialNumber` <br>
  iii. `Board Serial` to `Generic -> MLB` <br>
  iv. `SmUUID` to `Generic -> SystemUUID` <br>


### Notes: 
- Before creating an issue, please check if there is an open/closed one already related with your issue.<br>
- In order to use iMessage and Facetime, try using `MacPro7,1` or see [#12](https://github.com/GeekyCoder7/OpenCore-EFI-Lenovo-Y50-70/issues/12#issuecomment-754111916), [#17](https://github.com/GeekyCoder7/OpenCore-EFI-Lenovo-Y50-70/issues/17).<br>
- For those having issues with the display color, for some users the display color have a light brownish tint. <br>
In order to fix this you need to calibrate your display colors, by going into display settings from system preferences, then click calibrate from the color tab. <br>
- You may need to modify keys for the keyboard. For me the command was swapped with alt button (windows button on keyboard). So in order to fix this do the following: <br>
  1. Go to `System Preferences -> Keyboard -> Modifier Keys` <br>
  2. Change `Option` Key to `Command` <br>
  3. Change  `Command` Key to `Option` <br>
- If you have ALPS trackpad use the `ALPS-VoodooPS2Controller.kext`, but rename to `VoodooPS2Controller.kext` so that you won't end up having a bootloop. <br>
