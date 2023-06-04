# TLabWebViewSample
Sample project to make TLabWebView work on mobile

## Operating Environment
OS: Android 10 ~ 13  
GPU: Qualcomm Adreno 505, 619  
Unity: 2021.23f1  

## Getting Started
### Prerequisites
- Unity 2021.3.23f1
- [TLabVKeyborad](https://github.com/TLabAltoh/TLabVKeyborad)
- [TLabWebView](https://github.com/TLabAltoh/TLabWebView)
- TextMeshPro

### Installing
Clone the repository to any directory with the following command  
```
git clone https://github.com/TLabAltoh/TLabWebViewSample.git
```
Execute the following commands in the cloned project (install necessary submodules)

```
git submodule init
git submodule update
```
### Set up
1. Change platform to Android from Build Settings  
2. Add the following symbols to Project Settings --> Player --> Other Settings (to be used at build time)  
```
UNITYWEBVIEW_ANDROID_USES_CLEARTEXT_TRAFFIC
```
```
UNITYWEBVIEW_ANDROID_ENABLE_CAMERA
```
```
UNITYWEBVIEW_ANDROID_ENABLE_MICROPHONE
```
- Color Space: Linear
- Graphics: OpenGLES3
- Minimux API Level: 23 
3. Open Assets/Scenes/SampleScene.unity
4. Change any parameter of TLabWebView attached to TLabWebView/WebView from the hierarchy  
- Url: URL to load during WebView initialization
- Texture2D size: 512 * 512
- WebView size: 1024 * 1024
5. Create Assets/Plugins/Android/AndroidManifest.xml and copy the following text
```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest
    xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.unity3d.player"
    xmlns:tools="http://schemas.android.com/tools">
    <application>
        <activity android:name="com.unity3d.player.UnityPlayerActivity"
                  android:theme="@style/UnityThemeSelector">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
            <meta-data android:name="unityplayer.UnityActivity" android:value="true" />
        </activity>
    </application>

	<!-- For Unity-WebView -->
	<application android:allowBackup="true"/>
	<application android:supportsRtl="true"/>
	<application android:hardwareAccelerated="true"/>
	<application android:usesCleartextTraffic="true"/>
	
	<uses-permission android:name="android.permission.INTERNET" />
	<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>
	<uses-permission android:name="android.permission.CAMERA" />
	<uses-permission android:name="android.permission.MICROPHONE" />
	<uses-permission android:name="android.permission.MODIFY_AUDIO_SETTINGS" />
	<uses-permission android:name="android.permission.RECORD_AUDIO" />
	
	<uses-feature android:name="android.hardware.camera" />
	<uses-feature android:name="android.hardware.microphone" />
	<!-- For Unity-WebView -->
</manifest>
```
6. Make sure that the canvas of Assets/TLabWebView is the screen space - camera, and attach the camera to be used when manipulating the WebView on the scene

### Use from prefab
Just add Assets/TLab/TLabWebView/TLabWebView.prefab to your scene to run WebView after building (note that the input control is configured for mobile orientation, controlled by TouchEventManager.cs)

## TODO
- Sending input (e.g. key codes) to the browser

## Link
[Source code of the java plugin used](https://github.com/TLabAltoh/TLabWebViewPlugin)
