# Insatll Evlution X [ROM13] on Oneplus 7pro DETAILED VERSION


> **Words ahead**:This is a detailed instruction, the developer&maintainer is [@mhmdeveloper](https://forum.xda-developers.com/m/mhmdeveloper.7512771/) on XDA.by the way, this customized ROM is actually called **"PixelPlusUI"**, because you can't find it on the Evolution X official website, but still kept many Evlution X customizable features, anyway I think it's better than pixel experience.

## Preparation:

**System** :Make sure the phone is runing **Android 11**,whatever Oxygen OS or Hydrogen OS;If not,use local upgrade(or downgrade) pack or 9008 MSMdownload tool to downgrade(upgrade).

> Most of the time, the **Bootloader** of Oneplus 7pro could **ONLY be Unlocked in Oxygen OS11**;If you're using Hydrogen OS or Color OS , no problem

**TOOLS**:[**ADB platform tools**](https://developer.android.com/tools/releases/platform-tools) ;Mac OS、Windows、Linux are all supported,**[Windows](https://developer.android.com/tools/releases/platform-tools#:~:text=Download%20SDK%20Platform%2DTools%20for%20Windows) is recomended**

**Firmware&recovery**:Download these two files then copy them to the root folder of ADB tools

**External devices**:a **USB drive with Type-C port** or normal USB drive +**a Type-C adapter**.(Copy the recovery.img & firmware.zip to the root folder of the drive in advance)

> You may wanna try to sideload it but not to use an external drive, I tried that, too. But I face some problems.so, you'd better follow my way.

## Unlock the Bootloader

1. go to "settings" >> about phone >> "build version", and tap on **7** times, until it shows"You 're already a developer".
  
2. Go to "system settings" >> "Developer Option" >>turn on "**OEM**",>> go to "**USB debuging**" and turn it on.
  
3. Plug in your phone to the PC, Choose a USB connection for "Files transferring" in the pop-up window or swipe down to check it out.
  
4. Go to the "ADB platform-tools" folder, and type"**cmd**" in the search bar upon the folder. The program will run in the PowerShell that popped up.
  
5. adb devices //Check the pop-up window on your phone that asks "Allow USB debugging? Tap on check and yes" adb reboot bootloader //Make sure the USB connection is configured for File Transfering, once the command is executed, the phone will reboot to bootloaderfastboot devices
  

> //Once executed, if the devices are connected on, it'll show some serial number.**Once The device is on Fastboot mode, whatever how you plug it in or out, once plugged in, it'll be connected. If you are not sure, just type"fastboot devices" again.

fastboot flash boot <recovery>.img

> // the author's codes are `fastboot boot <boot>.img`, I've tried that, When I formatted the devices and tapped reboot to recovery, it just stuck in the original bootloader interface. So I just flash it into the other inactive slot "Oneplus 7pro is an A/B partition model, so when your phone gets bricked, you can go to fastboot mode, then type:`fastboot --set-slot=active` (remember to check your current slot), then reboot to recovery, it'd be working.Therefore you don't need to do all of that again"

    fastboot reboot recovery

> When recovery flashed, reboot to recovery

6. Swipe right the block to the bar, tap on"Wipe" >> "format"...then keep going, You need to type "yes" to proceed with the action, anyway just follow the instructions on the screen.
  
7. Tap the navigation button to go back to the home menu.tap "reboot", choose "recovery"
  
8. When rebooted, plug in the USB drive, the tap on"**Mount**">>choose "**USB storage**">>choose your USB drive
  
9. Go back to home menu,tap on **Install**,tap on the firmware.zip file>>then remember to choose **Automatically Install TWRP after Installation**,swipe right to install
  
10. When it shows done, remember to choose "**wipe Davltik cache**", when over, tap reboot device,**Done!**
  

## Known issues & bugs

* Google assistant can't follow the system theme(it doesn't a matter)
  
* When swiping left&right on the home screen, it looks a little bit laggy. (I solved that by turning on"force high flash rate")
  
* fingerprint not avaliable('The autor said it works good once reboot **2 or 3** times,I tried that,not working.Maybe it can be done by entering engineering mode from the dialer interface, and then redebugging the fingerprint sensor, I haven't tried it, don't know yet. However, the color of the mask should be accurate and the texture should be smooth)
