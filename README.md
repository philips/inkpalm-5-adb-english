# Xiaomi DuoKan E-reader ADB commands list.

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
All the commands listed below require ADB. If you don't have ADB installed, you can install it from here: [Minimal ADB and Fastboot](https://forum.xda-developers.com/showthread.php?t=2317790).

It's preferred to use default settings. It might be helpful to note the installation location.

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

### Step 2: Open ADB shell
Move back to  your PC. Navigate to the installation location. Usually this directory would be `C:\Program Files (x86)\Minimal ADB and Fastboot`.
Click on `cmd-here`. Once the command prompt opens, use the below command to check if the device is listed:
```shell
adb devices
```
