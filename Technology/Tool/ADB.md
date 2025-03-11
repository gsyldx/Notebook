|描述|命令|备注|
|---|---|---|
|截图|adb shell screencap -p /sdcard/screen.png||
|拉取截图|adb pull /sdcard/screen.png||
|所有应用包名|adb shell pm list packages||
|根据包名查询应用信息|adb shell dumpsys package com.xxx.xxx||
|查看应用版本号|adb shell pm dump com.jidouauto.refule \| findstr version||
|查看签名|keytool -list -v -keystore||
|CPU架构|adb shell getprop ro.product.cpu.abi||
|系统版本|adb shell getprop ro.build.version.sdk||
|清除日志|adb logcat -c||
|打印日志|adb logcat -v time > 640||
|查看电量|adb shell dumpsys battery||
|模拟输入|adb shell input keyevent||
|清缓存|adb shell pm clear --user current com.jidouauto.refule||
|关闭应用|adb shell am force-stop com.jidouauto.refule||
|查看当前activity|adb shell dumpsys activity activities||
|打开语言设置|adb shell am start -a android.settings.LOCALE_SETTINGS||
|系统版本|getprop \| grep finger||
|模拟发送广播|adb shell am broadcast -a <action>|--es 字符串类型参数 --ei int类型参数 --ez boolean类型参数 --el long类型的参数 --esal string类型的数据|
|查看mac地址|adb shell cat /sys/class/net/wlan0/address||
|切换白天黑夜|adb shell "su 0 cmd uimode night no"||

- 开机广播
adb shell am broadcast -a android.intent.action.BOOT_COMPLETED

- P 档
adb shell am broadcast -a com.hsae.auto.ACTION_PARKING

### 线连设备

网络和internet设置

状态

更改适配器设置

选择以太网

属性

internet 协议版本4

手动输入ip地址

ip 最后一位150-200之间

子网掩码随便

adb connect xxx.xxx.xxx.248

### 删除系统预装

1）通过命令：adb shell pm list packages -s 列出的应用包列表中找到要删除的包名

2）获取此要卸载的包名的地址：adb shell pm path com.xx.xx

3）挂载系统读写权限：adb remount

4）删除包：adb shell rm /system/app/xxxxxx/xxxxxx.apk

5）最后adb reboot重启即可

### hcp3车机驾驶模式

开启驾驶：adb shell dumpsys activity service com.android.car inject-vhal-event 0x11400400 8

关闭驾驶：adb shell dumpsys activity service com.android.car inject-vhal-event 0x11400400 4

### hcp3主副屏切换

使用副屏

Passenger seat right occupied: adb shell dumpsys activity service com.android.car inject-vhal-event 356518832 0x0004 2

Passenger seat right vacant: adb shell dumpsys activity service com.android.car inject-vhal-event 356518832 0x0004 1

副屏幕 scrcpy.exe --display 3