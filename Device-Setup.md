# Device Setup

##IMPORTANT

Add the following to your auth.json file to not overwrite your current custom device information: "DevicePackageName": "custom", **USING YOUR OWN PERSONAL INFORMATION ON NECROBOT REQUIRES AN ANDROID DEVICE**

## This release features automatic random device generation!

You can now opt to leave the device values static and your device will not be the same as everyone else's. This means that your account will not look like the exact same as other people using Necrobot.

If you still prefer to use your own device, you can do that as well! If you do you use your own device info, note that it will look the exact same as when you are signed into PoGo on your phone

## Use your own device info

To change the device information in /Config/auth.json to YOUR personal device, you will need android-sdk with adb (and drivers for your phone). Here are the correlating values with the command to run to grab the value off your phone:
`"DeviceId": "", // adb.exe shell settings get secure android_id`   
`"AndroidBoardName": "", // adb.exe shell getprop ro.product.board`   
`"AndroidBootloader": "", // adb.exe shell getprop ro.boot.bootloader`   
`"DeviceBrand": "", // adb.exe shell getprop ro.product.brand`   
`"DeviceModel": "", // adb.exe shell getprop ro.product.model`   
`"DeviceModelIdentifier": "", // adb.exe shell getprop ro.product.name`   
`"DeviceModelBoot": "qcom",`   
`"HardwareManufacturer": "", // adb.exe shell getprop ro.product.manufacturer`   
`"HardwareModel": "", // adb.exe shell getprop ro.product.model`   
`"FirmwareBrand": "", // adb.exe shell getprop ro.product.name`   
`"FirmwareTags": "", // adb.exe shell getprop ro.build.tags`   
`"FirmwareType": "", // adb.exe shell getprop ro.build.type`   
`"FirmwareFingerprint": "" // adb.exe shell getprop ro.build.fingerprint`   

_https://github.com/DNA64/NecroBotWiki_
