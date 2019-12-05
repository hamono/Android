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