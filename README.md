# Xiaomi DuoKan E-reader ADB commands list.

This document contents instructions to:
1. Change language of Xiaomi MiReader to English
2. Install third-party / sideload apps
3. Add a navigation panel and change the timezone

Disclaimer
```
* Your warranty is now void (maybe, ADB doesn't always void warranty. Check with your manufacturer).
* I'm not responsible for bricked devices, thermonuclear war, or you failing the test because the ebook won't open. Please
  do some research if you have any concerns about this guide before trying it! 
* YOU are choosing to make these modifications, and any problems are your reponsibility.
```

Requirements:
``` 
* Windows PC ( It's possible to do the same in Mac or Linux but I have not mentioned the steps here. The commands will be similar.)
* Xiaomi Duokan E-Reader
* Stable internet
* USB cables
```
The following commands have been tested on the Xiaomi DuoKan E-Reader.

### Step 1: Install ADB


### Step 2: Turn on ADB on device
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

### Step 3: Open ADB shell
Move back to  your PC. Navigate to the installation location. Usually this directory would be `C:\Program Files (x86)\Minimal ADB and Fastboot`.
Click on `cmd-here`. Once the command prompt opens, use the below command to check if the device is listed:
```shell
adb devices
```

If the MiReader is connected to the computer and all above steps are followed correctly, the serial number of the device will be shown. I would advice not connecting any other android device to the computer during the whole process. 

DO NOT CLOSE THE ADB SHELL/COMMAND PROMPT.

### Step 4: Change the language.
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

### Step 4: The launcher
The reason you can't change the language in homescreen is because the launcher itself is not in English. In this step, we'll change the launcher. 

Download app-home-release.apk
 from https://github.com/Modificator/E-Ink-Launcher/releases


```
adb install app-home-release.apk
```

The original e-reader app in still there, it now appears as an app on the launcher.

### Step 4: Naviation button

The Navigation button setting needs to be updated to make a Long Press return to home. It will do a "Back" action by default.

### Step 5: Change the timezone
The device is set to default timezone of China but you can change the timezone with the following command:
```shell
adb shell setprop persist.sys.timezone "Continent/City"
```
You'll find the exact timezone list here: [Wikipedia_TZ_List](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)

For example, I set my timezone with
```shell
adb shell setprop persist.sys.timezone "Europe/Amsterdam"
```

### Step 6: Disable unneeded apps

```
adb shell pm disable-user --user 0 com.duokan.einkreader                                                             
adb shell pm disable-user --user 0 com.moan.appstore
adb shell pm disable-user --user 0 com.zhangyue.read.iReader.eink                                                    
adb shell pm disable-user --user 0 cn.wps.moffice_eng.lite  
```

### Bonus

Now you're all set to install apps via file manager. Just select any apk you transferred from PC. First time, it'll ask for permission, grant ok, and also grant permission to install unknown apps, open the navigation button, press back and select install. The app will be installed.

## End notes

Though I built this document from ground-up, a lot of people need to be thanked for their work which made this possible.
* @Kagami-src for the MiReader launcher. This app lays the foundation of a better system on the MiReader.
* boxqkrtm for the original work on the topic. You can find his work (in Korean) here : [Naver](https://m.cafe.naver.com/ca-fe/web/cafes/xst/articles/403952?useCafeId=false)
* shimp208 for Minimal ADB and Fastboot, the lifeline behind the entire procedure. [XDA Topic](https://forum.xda-developers.com/showthread.php?t=2317790)
* The developers of the Xiaomi Navigation Button / Xuanfuqui. I'm sorry but I don't speak Chinese or Korean so I've no idea who built the app but if you're the developer behind this, please let me know and I'll cite you.
