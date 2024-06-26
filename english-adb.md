## Change Inkpalm 5 Language to English via ADB

### Install ADB

[Download and install ADB for macOS/Linux/Windows from Android.com](https://developer.android.com/studio/releases/platform-tools) 

### Turn on ADB on device
Follow the given instructions carefully. If you don't understand Chinese, use the image translate feature from Google. I've marked the buttons in red, if you go through them as shown, it'll be easy. 

1. Go to the settings page on the device.
![home](https://github.com/epodegrid/epd106-ADB/blob/master/images/home.png)

2. Click on the device information page.
![build](https://github.com/epodegrid/epd106-ADB/blob/master/images/build.png)

3. Keep tapping on the version number about 10 times until developer options is activated.
![version](https://github.com/epodegrid/epd106-ADB/blob/master/images/version.png)

4. Go back to settings and navigate to device options.
![setting](https://github.com/epodegrid/epd106-ADB/blob/master/images/setting.png)

5. If developer options are activated, you'll find a fourth menu there as shown. Select that menu.
![debug](https://github.com/epodegrid/epd106-ADB/blob/master/images/debug.png)

6. Scroll down and go to USB debugging. Keep the option ticked.
![adb](https://github.com/epodegrid/epd106-ADB/blob/master/images/adb.png)

### Open ADB shell
Move back to  your PC. Navigate to the installation location. Usually this directory would be `C:\Program Files (x86)\Minimal ADB and Fastboot`.
Click on `cmd-here`. Once the command prompt opens, use the below command to check if the device is listed:
```shell
adb devices
```

If the MiReader is connected to the computer and all above steps are followed correctly, the serial number of the device will be shown. I would advice not connecting any other android device to the computer during the whole process. 

DO NOT CLOSE THE ADB SHELL/COMMAND PROMPT.

### Change the language
Skip this step if you don't want to change the language.
It won't change 100% of the interface to English but a major section of the Xiaomi MiReader could be in changed to English.

Once the above step lists your device, and is back to normal command prompt, type the following:
```shell
adb shell am start -a android.settings.LOCALE_SETTINGS
```
On your device, the following screen will be shown:
1. Select the + button.
![locale](https://github.com/epodegrid/epd106-ADB/blob/master/images/locale/locale.png)

2. Choose English if that's what you want to set as language.
![english](https://github.com/epodegrid/epd106-ADB/blob/master/images/locale/locale-english.png)

3.Select US as the option.
![eng-US](https://github.com/epodegrid/epd106-ADB/blob/master/images/locale/locale-english-US.png)

4. Drag the :hamburger: icon next to English upwards, to make English the primary language. 

![setting](https://github.com/epodegrid/epd106-ADB/blob/master/images/locale/locale-setting-1.png)

5.Once you move the selected language up, the system begins to change the language, give it few seconds.
![setting-2](https://github.com/epodegrid/epd106-ADB/blob/master/images/locale/locale-setting-2.png)

DO NOT CLOSE THE ADB SHELL/COMMAND PROMPT.

Now reboot the device by holding the power button. Voila! You have changed the Xiaomi MiReader to English!

Note that the home screen and main settings screen is not in English. Continue reading this guide for more on that. The quick tiles and internal settings menu should have changed. Something like this!

![eng](https://github.com/epodegrid/epd106-ADB/blob/master/images/locale/settings-english.png)

