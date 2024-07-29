# DJI Mobile SDK for Android V5 Latest Alpha Version 5.10.0-a3

[中文版](README_CN.md)

##  Alpha Version Announcement

1. To improve the problem-solving efficiency of developers' feedback, we will fix the serious problems first. And we will release the alpha version immediately after the regression test.
2. For letting developers experience and test the MSDK functions that have been developed but not officially released, we will also release the alpha version immediately after the product acceptance test and functional test.
3. The alpha version is not strictly tested before the release. There might exist some unstable problems. Please judge and choose whether to use this version according to the release note. If you have other problems, please contact us immediately.
4. All changes in the alpha version will be merged into the official version and will be strictly tested before the release.
5. It is not suggested that developers directly merge the MSDK alpha version and released it as an official version.

## Release Date
2024.07.29

## Release Notes
- Support `LiveStreamManager` to set scale type: `setLiveStreamScaleType`

### Bug fixes
- On Matrice 350 RTK, Matrice 300 RTK and Mini 3, using Ground coordinates in the virtual joystick would cause drift: fixed

# DJI Mobile SDK for Android V5 Alpha Version 5.10.0-a2

## Release Date
2024.07.11

## Release Notes
- Support MSDK log: `enableMSDKLog`

### Bug fixes
- The resolution obtained by calling `LiveStreamStatus` for the livestream function is always -1: Fixed
- On Mini 3 and Mini 3 Pro, MSDK startup crashes occasionally in the EU region: Fixed
- On Mavic 3M and Mavic 3T, calling `deleteMediaFiles` to delete photos fails: Fixed
- On Mavic 3M, `BatterySettingWidget` does not update data: Fixed
- On Mavic 3T, the infrared image in split screen mode becomes smaller in video mode: Fixed
- On Mavic 3T megaphone, the opus audio file generated by DJI Pilot cannot be played in MSDK: Fixed
- On Mavic 3T, `MediaFile.getResolution` cannot get the resolution: Fixed
- On Mavic 3E, taking photos by pressing the physical buttons of the remote controller on the default layout page does not work: Fixed
- On Matrice 30T, `KeyPhotoSize` cannot obtain the photo size by setting the lens type: Fixed
- On Matrice 30T, the `LensControlWidget` on the default layout page does not display properly: Fixed
- On Matrice 30T, the `CameraVisiblePanelWidget` on the default layout page does not display properly: Fixed
- On Mtrice 30T, the `CameraControlsWidget` on the default layout page does not display properly: Fixed
- On Matrice 30T, the `HorizontalSituationIndicatorWidget` on the default layout page does not display properly: Fixed
- On Matrice 350 RTK, the horizontal obstacle avoidance data cannot be obtained after the obstacle avoidance switch is turned off: Fixed
- On Matrice 350 RTK, the `CameraControlsWidget` fails to take photos if the camera button is clicked quickly and continuously: Fixed
- On Matrice 300 RTK, after calling the pause interface to pause the route mission multiple times, the mission status changes to `READY`: Fixed
- On Matrice 300 RTK, `CameraKey.KeyVideoResolutionFrameRate` gets the resolution incorrectly: Fixed
- On DJI RC Plus, `REMOTE_DISCONNECTION` is prompted after switching the remote controller firmware: Fixed

## Offline Documentation

- /Docs/Android_API/en/index.html

## AAR Explanation

> **Notice:** sdkVersion = 5.10.0-a3

| SDK package  <div style="width: 150pt">  | Explanation  <div style="width: 200pt">   | How to use <div style="width: 300pt">|
| :---------------: | :-----------------:  | :---------------: |
|     dji-sdk-v5-aircraft-alpha      | Aircraft main package, which provides support for MSDK to control the aircraft. | implementation 'com.dji:dji-sdk-v5-aircraft-alpha:{sdkVersion}' |
| dji-sdk-v5-aircraft-provided-alpha | Aircraft compilation package, which provides interfaces related to the aircraft package. | compileOnly 'com.dji:dji-sdk-v5-aircraft-provided-alpha:{sdkVersion}' |
| dji-sdk-v5-networkImp-alpha | Network library package, which provides network connection ability for MSDK. Without this dependency, all network functions of MSDK will not work, but the interfaces of hardware control can be used normally. | runtimeOnly 'com.dji:dji-sdk-v5-networkImp-alpha:{sdkVersion}' |

- If only the aircraft product is in need to support, please use:
  ```groovy
  implementation "com.dji:dji-sdk-v5-aircraft-alpha:{sdkVersion}"
  compileOnly "com.dji:dji-sdk-v5-aircraft-provided-alpha:{sdkVersion}"
  ```

- If the MSDK have to use network(required by default), please use:
  ```groovy
  runtimeOnly "com.dji:dji-sdk-v5-networkImp-alpha:{sdkVersion}"
  ```