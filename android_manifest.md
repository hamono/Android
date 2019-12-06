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


