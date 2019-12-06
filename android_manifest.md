# Manifest属性

    <manifest
        xmlns:android="http://schemas.android.com/apk/res/android"
            package="com.th"
            android:sharedUerId="string"
            android:sharedUerLabel="string resource"
            android:versionCode="integer"
            android:versionName="string"
            andriod:installLocation=["auto" | "internalOnly " | "preferExternal"] >
    </manifest>
| 属性 | 解析 |
| :-: | :-: |
| xmlns:android | 定义android命名空间，以上固定写法，使得Android中各种标准属性能在文件中使用，提供了大部分元素中的数据|
| package | 应用包名，应用进程的默认名称，当我们通过ComponentName来启动某个Activity时，所用的包名一定是这个应用的包名，而不是当前Activity的包名 |
| shareUserLabel | 共享的用户名，需先设置sharedUserId属性 |
| versionCode | app更新次数 |
| versionNmae | 用户可查 |
| installLocation | 安装参数，Android 2.2新增。包含三个属性：internalOnly、auto、preferExternal。preferExternal：优先考虑将APK安装到SD卡上，最终决定权在用户；auto：系统自动判断；internalOnly：必须安装到内部内存中 |
# Application属性
    <application>
        android:allowClearUserData=["true" | "false"]
        android:allowTaskReparenting=["true" | "false"]
        android:backupAgent="string"
        android:debuggable=["true" | "false"]
        android:description="string resource"
        android:enabled=["true" | "false"]
        android:hasCode=["true" | "false"]
        android:icon="drawable resource"
        android:killAfterRestore=["true" | "false"]
        android:label="string resource"
        android:manageSpaceActivity="string"
        android:name="string"
        android:permission="string"
        android:persistent=["true" | "false"]
        android:process="string"
        android:restoreAnyVersion=["true" | "false"]
        android:taskAffinity="string"
        android:theme="resource or theme" >
    </application>
|属性|解析|
|:-:|:-:|
|allowClearUserData|用户是否能选择自行清除数据，默认true(在应用详情中的“清除数据”按钮)|
|allowTaskReparenting|是否允许activity更换从属的任务，如从短信息任务切换到浏览器任务|
|backupAgent|Android2.2新特性，设置该APP的备份，一般设置为类名。不设置时，不备份|
|debuggable|是否可被调试，默认false。如设置为false的情况下进行调试会报错：Device XXX requires that applications explicitely declare themselves as debuggable in their manifest.Application XXX does not have the attribute ‘debuggable’ set to TRUE in its manifest and cannot be debugged.|
|description\label|许可相关，label为许可列表，description为许可详细信息|
|enabled|Android系统是否能够实例化该应用程序的组件。true：每个组件的enabled属性决定那个组件是否可以被实例化。false：所有组件均不能实例化|
|hasCode|是否加载java代码。Android2.3后可用标准C来开发APP|
|icon|APP的图标|
|killAfterRestore||
|manageSpaceActivity||
|name|注册自定义类继承Application类。如该自定义类在package下，则直接声明，如：android:name=”MyApplication”。否则使用全路径，如：android:name=”package名称.子包名.MyApplication”|
|permission|设置各组件默认许可名，因此可以被各组件设置的许可名所覆盖|
|presisitent|设置是否一直保持运行状态，默认false。|
|process|进程名，如不设置，则默认包名。在两个或多个应用程序共享一个用户ID及被赋予了相同证书的时候可以设置相同的进程名。可以被各组件设置的进程名所覆盖|
|restoreAnyVersion|android2.2新特性，是否准备尝试恢复所有的备份，默认false|
|taskAffinity|拥有相同的affinity的Activity理论上属于相同的Task。具体见Activity的加载原理|
|theme|默认的主题风格，各Activity可覆盖|

# Activity属性
    <activity 
	android:allowTaskReparenting=["true" | "false"]
	android:alwaysRetainTaskState=["true" | "false"]
	android:clearTaskOnLaunch=["true" | "false"]
	android:configChanges=["mcc", "mnc", "locale",
	                       "touchscreen", "keyboard", "keyboardHidden",
	                       "navigation", "orientation", "screenLayout",
	                       "fontScale", "uiMode"]
	android:enabled=["true" | "false"]
	android:excludeFromRecents=["true" | "false"]
	android:exported=["true" | "false"]
	android:finishOnTaskLaunch=["true" | "false"]
	android:icon="drawable resource"
	android:label="string resource"
	android:launchMode=["multiple" | "singleTop" |
	                    "singleTask" | "singleInstance"]
	android:multiprocess=["true" | "false"]
	android:name="string"
	android:noHistory=["true" | "false"]  
	android:permission="string"
	android:process="string"
	android:screenOrientation=["unspecified" | "user" | "behind" |
	                           "landscape" | "portrait" |
	                           "sensor" | "nosensor"]
	android:stateNotNeeded=["true" | "false"]
	android:taskAffinity="string"
	android:theme="resource or theme"
	android:windowSoftInputMode=["stateUnspecified",
	                             "stateUnchanged", "stateHidden",
	                             "stateAlwaysHidden", "stateVisible",
	                             "stateAlwaysVisible", "adjustUnspecified",
	                             "adjustResize", "adjustPan"] >   
    </activity>
| 属性 | 解析 |
|:-:|:-:|
|alwaysRetainTaskState|是否保留状态不变，如切屏|
|clearTaskOnLaunch|重新回到Activity中时，是否显示跳转过程。如：ActivityA启动ActivityB后，回到home，再回到ActivityB，是否显示ActivityA跳转到ActviityB的过程|
|configChnages|当配置list发生修改时， 调用onConfigurationChanged()|
|excludeFromRecents|是否可被显示在最近打开的activity列表里，默认false|
|finishOnTaskLaunch|重启任务时，是否显示已打开的Activity，默认false。与allowTaskReparenting配合使用|
|launchMode|加载模式|
|multiprocess|是否允许多进程，默认false|
|noHistory|Activity不可见时，是否从Activity stack中清除并结束，默认false|
|screenOrientation|屏幕显示模式。unspecified：系统自动判断|
|landscape|横屏|
|portrait|竖屏|
|user|用户当前首选方向|
|behind|与跳转的Activity一致|
|sensor|由物理感应起决定|
|nosensor|忽略物理感应器|
|stateNotNeeded|activity被销毁或者成功重启时是否保存状态|
|windowSoftInputMode| 软键盘交互模式，Android1.5新特性|
|stateUnspecified|软键盘的状态并没有指定，系统将选择一个合适的状态或依赖于主题的设置|
|stateUnchanged|当这个activity出现时，软键盘将一直保持在上一个activity里的状态，无论是隐藏还是显示|
|stateHidden|用户选择activity时，软键盘总是被隐藏|
|stateAlwaysHidden|当该Activity主窗口获取焦点时，软键盘也总是被隐藏的|
|stateVisible|软键盘通常是可见的|
|stateAlwaysVisible|用户选择activity时，软键盘总是显示的状态|
|adjustUnspecified|默认设置，通常由系统自行决定是隐藏还是显示|
|adjustResize|该Activity总是调整屏幕的大小以便留出软键盘的空间|
|adjustPan|当前窗口的内容将自动移动以便当前焦点从不被键盘覆盖和用户能总是看到输入内容的部分|
# intent-filter属性


