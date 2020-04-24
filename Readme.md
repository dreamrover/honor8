## honor8
华为荣耀8全网通刷入第三方ROM后会导致电信卡通话无声音，因为语音通话使用2G/3G网络，荣耀8对对电信2G/3G（CDMA/CDMA2000）的支持采用的是外挂基带芯片，可能导致了Open Kirin的不支持。若要使用4G网络通话需开启VoLTE，但Open Kirin官方没打算支持VoLTE（貌似荣耀8也不支持VoLTE）。

## Unlock
* adb shell getprop
* adb reboot bootloader
* fastboot oem unlock 9297843358022705

## Honor 8  Android 8.0  EMUI 8.0:
* adb reboot bootloader
* fastboot flash recovery_ramdisk twrp-3.2.1-0.img
* fastboot reboot

erecovery  to newest, then downgrade to EMUI 5.0.1 by HiSuite

## Honor 8  Android 7.0  EMUI 5.0.1:
* adb reboot bootloader
* fastboot flash recovery twrp-3.1.1-1-frd.img
* fastboot reboot

XposedInstaller_*.apk from this thread: Must be installed to manage installed modules, the framework won't work without it.

xposed*.zip from https://dl-xda.xposed.info/framework/: Must be flashed with a custom recovery (e.g. TWRP) to install the framework.

SDK21 is Android 5.0 (Lollipop), SDK22 is Android 5.1 (also Lollipop) and SDK23 is Android 6.0 (Marshmallow).

For Nougat, SDK24 is Android 7.0 and SDK25 is Android 7.1.

For Oreo, SDK26 is Android 8.0 and SDK27 is Android 8.1.

I only support the latest Xposed version per Android release!

xposed-uninstaller*.zip from https://dl-xda.xposed.info/framework/: Can be flashed with a custom recovery (e.g. TWRP) to uninstall the framework.


/system/app

/system/priv-app

/cust/all/cn/app

/product/app

/data/hw_init/system/app

/data/hw_init/version/region_comm/china/app

/data/hw_init/version/special_cust/EVA-AL00/all/cn/app


## 解密Data分区：
* adb reboot bootloader
* fastboot flash recovery_ramdisk huawei-honor-8-em8_0-twrp3.2.1-7to-recovery-8.5.18.img
* fastboot reboot
* adb reboot recovery
三清Dalvik/ART Cache、Cache、Data，格式化Data，高级——移除Data强制加密

## 刷入第三方ROM（须先移除DATA强制加密）：
* adb reboot bootloader
* fastboot flash system openkirin_rros_beta3.img
* fastboot reboot
