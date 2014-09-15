assistant
=========

手机助手


项目名称：手机助手

项目所属行业: Android手机应用

开发周期：4周

开发工具：Eclipse + Android SDK API 19

项目介绍： 本项目是实现了手机助手的部分功能：硬件检测、软件管理，闹钟，电池维护以及通讯录等功能。

项目实现方法：

硬件检测：

使用Build类获取手机设备硬件信息，TelephonyManager类获取与SIM卡相关的电话信息，获取CPU与内存信息是通过读取相关文件得到，DisplayMetrics类可以获取分辨率，Camera类和Parameters获取与摄像头相关的信息，像素、照片尺寸等，WifiManager和BluetoothAdapter分别获取与WI-FI、蓝牙相关信息：连接SSID、地址、速率等。

软件管理：

PackageManager包管理类的getInstalledPackages()方法来获取设备中已安装的应用程序包信息PackageInfo对象集合，再根据ApplicationInfo类循环遍历判断每个程序以区分系统应用还是用户程序，最后分别通过网格布局和列表布局展示给用户。

闹钟：

闹钟则是通过AlarmManager定时管理服务类将定制的时间以PendingIntent待定意图的方式传递给系统由系统触发执行

电池维护：

电池监控是通过监听电池变化广播以收集电池状态、电量、温度以及接口状态等信息；电池维护是通过判断当前电池电量并且以动画和文本的形式提醒用户健康充电。

通讯录：

通过ContentProvider内容提供者读取系统通讯录的内容并以列表的形式展示，借助ContentResolver内容解析器对通讯录实现增删改查等功能
