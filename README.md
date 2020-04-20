# Xiaomi DuoKan E-reader ADB commands list.
```Disclaimer
* Your warranty is now void (maybe, ADB doesn't always void warranty. Check with your manufacturer).
* I'm not responsible for bricked devices, thermonuclear war, or you failing the test because the ebook won't open. Please
  do some research if you have any concerns about this guide before trying it! 
* YOU are choosing to make these modifications, and any problems are your reponsibility.
```
The following commands have been tested on the Xiaomi DuoKan E-Reader.

```Requirements:
* Windows PC ( It's possible to do the same in Mac or Linux but I have not mentioned the steps here. The commands will be similar.)
* Xiaomi Suokan E-Reader
* Stable internet
* USB cables
```

### Step 1: Install ADB
All the commands listed below require ADB. If you don't have ADB installed, you can install it from here: [Minimal ADB and Fastboot](https://forum.xda-developers.com/showthread.php?t=2317790).

It's preferred to use default settings. It might be helpful to note the installation location.

### Step 2: Open ADB shell
Navigate to the installation location. Usually this directory would be `C:\Program Files (x86)\Minimal ADB and Fastboot`.
Click on `cmd-here`. Once the command prompt opens, use the below command to check if the device is listed:
```shell
adb devices
```
