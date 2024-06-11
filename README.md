# TLabWebViewSample
Sample project to make TLabWebView work on mobile

[!["Buy Me A Coffee"](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://www.buymeacoffee.com/tlabaltoh)

## Operating Environment
- Android 10 ~ 13
- Qualcomm Adreno 505, 619
- Unity: 2021.3

## Document
[document is here](https://tlabgames.gitbook.io/tlabwebview)

## Note

<details><summary>please see here</summary>

### Module management policy is updated
- The policy has been changed to manage libraries in the repository as submodules.
- Commit ``` ff4e92a ``` If you cloned the project before, please clone the repository again.
- Use ``` git submodule update --init ``` to adjust the commit of the submodule to the version recommended by the project.

</details>

## Getting Started

### Prerequisites

- Unity 2021.3 LTS
- TextMeshPro
- [TLabVKeyborad](https://github.com/TLabAltoh/TLabVKeyborad)
- [TLabWebView](https://github.com/TLabAltoh/TLabWebView)

### Installing

Clone the repository with the following command

```
git clone https://github.com/TLabAltoh/TLabWebViewSample.git
```

### Set Up
- Build Settings

| Property      | Value   |
| ------------- | ------- |
| Platform      | Android |

- Project Settings

| Property          | Value                                 |
| ----------------- | ------------------------------------- |
| Color Space       | Linear                                |
| Minimum API Level | 26                                    |
| Target API Level  | 30 (Unity 2021), 31 ~ 32 (Unity 2022) |

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
## Sample Scene

``` Assets/Scenes/SampleScene.unity ```

## Link
[Source code of the java plugin used](https://github.com/TLabAltoh/TLabWebViewPlugin)
