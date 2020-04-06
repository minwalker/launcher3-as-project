# launcher3-as-project
a doc for launcher3 as project some problems on adapter


Hello, this is a doc for introducing launcher3 make an Android Studio project may have some problems’s solutions. Now, the launcher3 to make an Android Studio is more easily than before, 2~3 years ago we need to make gradle structure owner, but now isn’t needed. let’s begin!

A) environment:
1.	system: Ubuntu 18.04 + window 10 (if you are using any linux as main system, window 10 isn’t needed, and Ubuntu is just optional, for aosp project need a linux compile only)
2.	Android studio version:v3.5.3

B) To make a launcher3 for android studio project may have the following steps:
1.	download and build aosp project, here we choose an android pie final verison android-9.0.0_r54 (just follow google’s tutorial or some forum, it’s not the focus of this article,we just need launcher3 code, you can download them from this git, so we don’t introduce aosp compile here)

2.	after aosp project source build complete, copy the following path to a backup path:
Launcher3 code:
aosp/packages/apps/Launcher3

3.	open android studio, and open the backup path Launcher3 project, just import it will show follow, click “ok”:
 

4.	change android to project structure, will be more concise
 

5.	after sync index, you may found out fllowing error, because aosp code build.gradle is still using beta version, just change them from 28.0.0-SNAOSHOT to 28.0.0 and change buildToolsVersion ’28.0.3’
     

6.	after solve above problem, you will get sync finish and tell you whether to update the plugin to new version as your Android studio version is new(to me is 3.5.3), click update, sometime will fail, just change it on build.gradle yourself is ok
   

7.	after that sync again, you may find another exception like below, it cause by protobuf-gradle-plugin:0.8.3, just update it to 0.8.8 and sync again
   

8.	finally, build apk you will find success, and install it in a emulated to have try(because other devices if have a com.android.launcher3 you may install fail for you don’t have a signature match before, if you want to try any devices is ok you can try to change packagename, it can work)
 
