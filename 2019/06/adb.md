
source java_environmental.sh

配置系统环境变量adb的路径：H:\sdk\platform-tools  说明：android sdk会自带adb的安装包，只需要配置环境变量即可

命令行读取cpu温度:
root@rk3288:/ # cat sys/devices/ff280000.tsadc/temp1_input                     
root@rk3288:/sys/class/hwmon/hwmon0 # cat temp1_input                                        

进入loader的命令：adb reboot loader

adb命令模拟按键事件：KeyCode
adb shell input keyevent 4  //键值码4代表的是back键

adb获取包名以及当前运行的activity
adb shell dumpsys window | findstr mCurrentFocus

am start启动一个app的MainActivity
adb shell am start -n com.rockchip.devicetest/com.rockchip.devicetest.IndexActivity

查找任意一下app的位置
find ./ -name 'ccc'

linux drwxr-xr-x   r=4,w=2,x=1
第一位表示文件类型。d是目录文件，l是链接文件，-是普通文件，p是管道
第2-4位表示这个文件的属主拥有的权限，r是读，w是写，x是执行。
第5-7位表示和这个文件属主所在同一个组的用户所具有的权限。
第8-10位表示其他用户所具有的权限。
后面9位，分为三组，以drwxr-xr-x为例进行说明：

d:表示目录；

rwx：该文件/目录所在的用户，也就是该用户具有的权限：可读，可写，可执行；

r-x：与该用户同组的其他用户，具有权限：可读，不可写，可执行；（linux系统中，用户会被分在某一个组中）

r-x：与该用户不同组的其他用户，具有权限：可读，不可写，可执行；

which date  查看命令的位置
whereis date 查看哪些目录有用到execRootCmd

date +"%Z"

cat /proc/meminfo
free -h 

com.android.change.rotation

adb shell
dumpsys |grep BroadcastRecord    查看系统发送的广播

busybox:https://www.cnblogs.com/baiduboy/p/6228003.html

adb 获取安卓板的型号：adb shell getprop ro.product.model

内核图片：RockChip Kernel 
uboot图片：RockChip

获取wifi热点密码：adb shell cat /data/misc/wifi/*.conf 

adb控制蓝牙
关闭：adb shell settings put global bluetooth_on 0
打开：adb shell settings put global bluetooth_on 1
查询：adb shell settings get global bluetooth_on


adb uninstall com.xxx.xxx   // 卸载包名为com.xxx.xxx 的 app （非系统应用）

getprop | grep ro.board.platform

//获取app的信息
adb shell dumpsys package com.unilife.fridge.haierbase.tft7

查找app的安装位置：
adb shell
logcat 获取到app的信息，包括包名

dBm =-113+2*asu
dBm值肯定是负数的，越接近0信号就越好，但是不可能为0的，值越大越好,最低是-90
asu的值则相反，是正数，也是值越大越好，10（信号最差），10-30（信号正常），>35（基站附近）

//获取键盘、鼠标、触摸屏等各种输入设备
cat /proc/bus/input/devices

//类设备信息
ls -l /sys/class/input


/dev/input  或者  /sys/class/input

和风天气：wangyuexiu1221
github: 3076633801@qq.com  wangyuexiu1221   felicity520

进入设置的代码：
am start -n com.android.settings/.Settings

获取序列号：
adb shell getprop ro.serialno

使用adb命令设定系统属性：
adb shell setprop [key] [value]
adb shell getprop [key] 

获取CPU类型：
cat /proc/cpuinfo

获取内存消息
cat /proc/meminfo

cat /proc/partitions 可以文件地知道系统本身的分区情况








