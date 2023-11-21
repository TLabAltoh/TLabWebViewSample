# TLabWebViewSample
Sample project to make TLabWebView work on mobile

[!["Buy Me A Coffee"](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://www.buymeacoffee.com/tlabaltoh)

## Operating Environment
- Android 10 ~ 13
- Qualcomm Adreno 505, 619
- Unity: 2021.23f1

## Getting Started
### Prerequisites
- Unity 2021.3.23f1
- TextMeshPro
- [TLabVKeyborad](https://github.com/TLabAltoh/TLabVKeyborad)
- [TLabWebView](https://github.com/TLabAltoh/TLabWebView)

### Installing
Clone the repository with the following command
```
git clone https://github.com/TLabAltoh/TLabWebViewSample.git
```
### Set up
- Change platform to Android from Build Settings  
- Add the following symbols to Project Settings --> Player --> Other Settings (to be used at build time)  
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
- Minimux API Level: 26 
- Target API Level: 30 (Unity 2021), 31 ~ 32 (Unity 2022)
- Open Assets/Scenes/SampleScene.unity
- Change the setting of WebView
Setting items in TLabWebView.cs (located in TLabWebView.prefab/WebView)  
	- Url: URL to load during WebView initialization  
	- DlOption: Whether to download to the application folder or the downloads folder  
	- SubDir: In case of setting download to application folder, it is downloaded to ```{Application folder}/{files}/{SubDir}```  
	- Web (Width/Height):  Web page resolution (default 1024 * 1024)  
	- Tex (Width/Height): Texture2D resolution used within Unity (default 512 * 512)  
- Make sure that the canvas of Assets/TLabWebView is the screen space - camera, and attach the camera to be used when manipulating the WebView on the scene

## Link
[Source code of the java plugin used](https://github.com/TLabAltoh/TLabWebViewPlugin)
