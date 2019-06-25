   

---------------------------------------------------------------------退出程序方式的两种方式------------------------------------------------------------------------
第一种：
	android.os.Process.killProcess(android.os.Process.myPid());
	这样就可以从操作系统中结束掉当前程序的进程。
注意：
	android中所有的activity都在主进程中，在Androidmanifest.xml中可以设置成启动不同进程，Service不是一个单独的进程也不是一个线程。
	当你Kill掉当前程序的进程时也就是说整个程序的所有线程都会结束，Service也会停止，整个程序完全退出。
第二种：
	System.exit(0),System.exit(1)
	退出程序，并清除后台缓存的本进程
注意：
	参数0和1代表退出的状态，0表示正常退出，1表示异常退出
	参数0和1代表退出的状态，0表示正常退出，1表示异常退出(只要是非0的都为异常退出)，即使不传0来执行也可以退出，该参数只是通知操作系统该程序是否是正常退出。

-----------------------一个app启动另外一个app------------------------
/**
  * 主要代码
  */
String packname = "com.gyy.ryd.factorytest8829";
PackageManager packageManager = getPackageManager();

if (checkPackInfo(packname)) {
    Intent intent = packageManager.getLaunchIntentForPackage(packname);
    startActivity(intent);
} else {
	//没有安装app要做的事情
    Toast.makeText(MainActivity.this, "没有安装" + packname, LENGTH_SHORT).show();
}


/**
  * 检查包是否存在(存在：true  不存在：false)
  */
 private boolean checkPackInfo(String packname) {
     PackageInfo packageInfo = null;
     try {
         packageInfo = getPackageManager().getPackageInfo(packname, 0);
     } catch (PackageManager.NameNotFoundException e) {
         e.printStackTrace();
     }
     return packageInfo != null;
 }


-----------------------一个app启动另外一个app的某个Activity------------------------
第一步：目标Activity必须是android:exported="true"（可被外部程序访问）
第二步：目标包名 + 目标Activity
Intent in = new Intent();
in.setClassName("com.gyy.ryd.factorytest8829", "com.gyy.ryd.factorytest8829.StabilityNewActivity");
startActivity(in); //启动app B