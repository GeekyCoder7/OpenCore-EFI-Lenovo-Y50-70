# OpenCore EFI for Lenovo Y50-70 (FHD-1080p) updated for Sonama

<h2>Support me if you like my work.<br><a href="https://www.buymeacoffee.com/GeekyCoder7" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/default-orange.png" alt="Buy Me A Coffee" height="41" width="174"></a></h2>

## Updated to OpenCore 0.9.5

### Added FULL support for Sonama

### For installation, use `PRE-EFI`.

### After installation, use `POST-EFI-BEFORE-PATCH`.

### After patching with OCLP, use `POST-EFI-AFTER-PATCH`.

### Steps after installation:

1. Use PRE-EFI for installation.
2. After installation, replace `PRE-EFI` with `POST-EFI-BEFORE-PATCH` before booting, otherwise it won't boot with `PRE-EFI`.
2. If you feel satisfied with your system, you can skip the rest.
3. Download OpenCore Legacy Patcher [(OCLP)](https://github.com/dortania/OpenCore-Legacy-Patcher/releases)
4. Before launching OCLP, make sure the system EFI is updated with `POST-EFI-AFTER-PATCH`. Update also the EFI on your USB just in case booting from EFI partition fails.
5. Launch OCLP, and click on `Post Install Root Patch`.
6. OCLP should detect that your system is Haswell. After that, click on `Start Root Patching`.
7. When the patching is completed, restart your mac.
   Note that if you forgot to update the system EFI with `POST-EFI-AFTER-PATCH` before patching, you will end up having screan tearing. A workaround is to connect to an HDMI monitor.
8. In order to make Wi-Fi working, you need to open OpenCore Legacy Patcher again, and you will see a new patch available for you to install, called `Networking: Modern Wireless`.
9. Install the patch and reboot. Enjoy :)


### Setup SMBIOS after installation:

1. Download [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS)
2. Do the following:

```
cd GenSMBIOS
chmod +x GenSMBIOS.command
./GenSMBIOS.command
```

3. Install MacSerial
4. Generate SMBIOS
5. Type `MacBookPro14,1`
6. You will get your SMBIOS: Type, Serial, Board Serial and SmUUID.
7. Edit your Config.plist either with OCC or Xcode or TextEdit: <br>
   i. `Type` to `Generic -> SystemProductName` <br>
   ii. `Serial` to `Generic -> SystemSerialNumber` <br>
   iii. `Board Serial` to `Generic -> MLB` <br>
   iv. `SmUUID` to `Generic -> SystemUUID` <br>

### Notes:

1. In case the trackpad does not work well for you, you can use RehabMan's build found in `Extras/VoodooPS2Controller.kext`.
2. You can uninstall OCLP root patches anytime. If you uninstall, you will also need to revert the EFI to `POST-EFI-BEFORE-PATCH`.

### What works:

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
- backlight controls with smooth transitions, save/restore across restart
- accelerated graphics for HD4600 (both 1080p and 4K)
- wired Ethernet
- retina scaling
- Sleep/Wake
- Auto Brightness Sensors
- iMessage & Facetime
- Brightness keys on keyboard
- Battery status

### What does not work (yet):

- Internal speakers (Headphones will work)
