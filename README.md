# 关注郭霖大神的微信公众号学习更多技术
致歉郭霖大神：非常感谢你的第一行代码这本书。同时电子书自己在网上找的，现在上传到该项目下，如果郭霖大神不许的话我会尽快删除电子书！

<img src="https://raw.githubusercontent.com/guolindev/booksource/master/qrcode.jpg" width="250" />

如果是对书中源码有疑问，也可以到公众号里给郭霖大神留言。微信扫一扫上方二维码即可关注。



我自己fork从大神的github仓库：https://github.com/guolindev/booksource



本人学习过程中添加自己的理解的注释和一些功能的补充（使用到某些大神的github代码我都注明仓库地址，没有注明的请谅解）


****************
一：
比如限于篇幅，郭霖大神讲解listView RecyclerView中没有下拉刷新上拉加载功能，
我有集成了该功能，RecyclerView方式【booksource\chapter3\ListViewTest】： * https://github.com/niniloveyou/SwipeRecyclerView      * SwipeRefreshLayout + RecyclerView 实现的下拉刷新，上拉加载更多；
                  listView方式    【booksource\chapter3\RecyclerViewTest】：     * https://github.com/chrisbanes/Android-PullToRefresh   * listView 实现的下拉刷新，上拉加载更多；
****************

																	
																	
****************
二：自定义UI组件和利用自定义属性attrs.xml，其中实现了自定UI attrs功能的的仿支付宝和QQ右上角的三个点点的pupmenu效果。
【booksource\chapter3\UIWidgetTest实现了自己定义UI Attrs 】
参考:http://blog.csdn.net/brokge/article/details/9713041/
http://www.cnblogs.com/xch-yang/p/6017685.html
http://www.cnblogs.com/whoislcj/p/5714760.html
************************


*****************************
三：动态权限的最佳实践解决方式之一，参考郭神视频
 * 郭神视频录播地址：http://edu.csdn.net/course/detail/3539
 * 整理的博客地址：http://blog.csdn.net/qq_31715429/article/details/52885787
booksource\chapter7\RuntimePermissionTest
******************************

*******************************
四.只有第一次调用SQLiteOpenHelper.getWritableDatabase或者SQLiteOpenHelper.getReadableDatabase才会创建数据库
*******************************

*******************************************************************************************************
android权限：参见博客http://blog.csdn.net/hijson/article/details/53783217
我们需要在AndroidManifest文件中声明我们所需要的权限(无论是normal permissions还是Dangerous Permission)

正常权限：

ACCESS_LOCATION_EXTRA_COMMANDS
ACCESS_NETWORK_STATE
ACCESS_NOTIFICATION_POLICY
ACCESS_WIFI_STATE
BLUETOOTH
BLUETOOTH_ADMIN
BROADCAST_STICKY
CHANGE_NETWORK_STATE
CHANGE_WIFI_MULTICAST_STATE
CHANGE_WIFI_STATE
DISABLE_KEYGUARD
EXPAND_STATUS_BAR
GET_PACKAGE_SIZE
INSTALL_SHORTCUT
INTERNET
KILL_BACKGROUND_PROCESSES
MODIFY_AUDIO_SETTINGS
NFC
READ_SYNC_SETTINGS
READ_SYNC_STATS
RECEIVE_BOOT_COMPLETED
REORDER_TASKS
REQUEST_IGNORE_BATTERY_OPTIMIZATIONS
REQUEST_INSTALL_PACKAGES
SET_ALARM
SET_TIME_ZONE
SET_WALLPAPER
SET_WALLPAPER_HINTS
TRANSMIT_IR
UNINSTALL_SHORTCUT
USE_FINGERPRINT
VIBRATE
WAKE_LOCK
WRITE_SYNC_SETTINGS

危险权限组和权限：

每个组申请一个权限，这个组的其他权限也一并申请了。
所有危险的 Android 系统权限都属于权限组。如果设备运行的是 Android 6.0（API 级别 23），并且应用的 targetSdkVersion 是 23 或更高版本，则当用户请求危险权限时系统会发生以下行为：

如果应用请求其清单中列出的危险权限，而应用目前在权限组中没有任何权限，则系统会向用户显示一个对话框，描述应用要访问的权限组。对话框不描述该组内的具体权限。例如，如果应用请求READ_CONTACTS 权限，系统对话框只说明该应用需要访问设备的联系信息。如果用户批准，系统将向应用授予其请求的权限。
如果应用请求其清单中列出的危险权限，而应用在同一权限组中已有另一项危险权限，则系统会立即授予该权限，而无需与用户进行任何交互。例如，如果某应用已经请求并且被授予了 READ_CONTACTS 权限，然后它又请求 WRITE_CONTACTS，系统将立即授予该权限。
任何权限都可属于一个权限组，包括正常权限和应用定义的权限。但权限组仅当权限危险时才影响用户体验。可以忽略正常权限的权限组。

如果设备运行的是 Android 5.1（API 级别 22）或更低版本，并且应用的 targetSdkVersion 是 22 或更低版本，则系统会在安装时要求用户授予权限。再次强调，系统只告诉用户应用需要的权限组，而不告知具体权限。

具体的危险权限组和权限如下：

CALENDAR

READ_CALENDAR
WRITE_CALENDAR

CAMERA

CAMERA

CONTACTS

READ_CONTACTS
WRITE_CONTACTS
GET_ACCOUNTS

LOCATION

ACCESS_FINE_LOCATION
ACCESS_COARSE_LOCATION

MICROPHONE

RECORD_AUDIO

PHONE

READ_PHONE_STATE
CALL_PHONE
READ_CALL_LOG
WRITE_CALL_LOG
ADD_VOICEMAIL
USE_SIP
PROCESS_OUTGOING_CALLS

SENSORS

BODY_SENSORS

SMS

SEND_SMS
RECEIVE_SMS
READ_SMS
RECEIVE_WAP_PUSH
RECEIVE_MMS

STORAGE

READ_EXTERNAL_STORAGE
WRITE_EXTERNAL_STORAGE


特殊权限：


SYSTEM_ALERT_WINDOW
WRITE_SETTINGS
有许多权限其行为方式与正常权限及危险权限都不同。SYSTEM_ALERT_WINDOW 和WRITE_SETTINGS 特别敏感，因此大多数应用不应该使用它们。如果某应用需要其中一种权限，必须在清单中声明该权限，并且发送请求用户授权的 intent。系统将向用户显示详细管理屏幕，以响应该 intent。

如需了解有关如何请求这些权限的详情，请参阅 SYSTEM_ALERT_WINDOW 和WRITE_SETTINGS 参考条目。


版权声明：本文为博主原创文章，未经博主允许不得转载。------http://blog.csdn.net/hijson/article/details/53783217
*************************************************************************************************************************																
																																					
