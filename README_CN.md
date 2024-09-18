# DJI Mobile SDK for Android V5 最新Alpha版本 5.11.0-a1

[English Version](README.md)

## Alpha版本声明

1. 为了提高开发者反馈问题的解决效率，我们会优先修复一些严重的问题，在进行问题回归测试后，会第一时间对外发布我们的Alpha版本。
2. 为了能够让开发者尽快体验和测试到我们开发完成但暂未正式发布的功能，在进行产品验收和功能测试后，我们也会第一时间对外发布我们的Alpha版本。
3. Alpha版本未经过严格发布测试，可能存在一些不稳定问题。请开发者根据版本发布记录，自行判断和选择使用Alpha版本。如果有其他问题请第一时间反馈给我们。
4. Alpha版本的所有改动都会同步到正式版本，进行严格的发布测试后对外发布。
5. 不建议开发者直接集成MSDK Alpha版本作为正式版本进行发布。

## 发布日期
2024.09.18

## 发布记录
- 适配 Android 14
- 为Matrice 350 RTK和Matrice 300 RTK机型支持离线升级功能
- 补充 `IDeviceHealthManager` 错误码

### Bug 修复
- 调用 `ReceiveStreamListener` 偶现 `IllegalStateException` 崩溃: 已修复
- 调用 `sendVirtualStickAdvancedParam` 偶现 `ConcurrentModificationException` 崩溃: 已修复
- 飞行器重连后，调用 `isVirtualStickEnable` 获取状态错误: 已修复
- 在 Matrice 350 RTK 飞行器上，使用 PSDK 负载出现图传卡顿: 已修复
- 在 Matrice 350 RTK 飞行器上，使用 H30 相机调用 `KeyExposureModeRange` 返回为空: 已修复
- 在 Matrice 350 RTK 飞行器上，使用 H30 相机调用 `KeyCameraZoomRatiosRange` 获取到的范围不对: 已修复
- 在 Matrice 300 RTK 飞行器上，使用DJI带屏遥控器在录像模式下切换到拍照模式进行拍照失败: 已修复
- 在 Mini 3 和 Mini 3 Pro 飞行器上，固件信息无法获取: 已修复

> **注意：**
> **Kotlin Android 扩展已被弃用，这意味着使用 Kotlin 合成视图绑定不再受支持。如果您的应用使用 Kotlin 合成技术，请按照如下指南迁移到 Jetpack 视图绑定：
<a href="https://developer.android.com/topic/libraries/view-binding/migration?hl=zh-cn">从 Kotlin 合成迁移到 Jetpack 视图绑定</a>**

## 离线文档

- /Docs/Android_API/cn/index.html

## AAR说明

> **注意：** sdkVersion = 5.11.0-a1

| SDK包  <div style="width: 150pt">  | 说明  <div style="width: 200pt">   | 使用方式 <div style="width: 300pt">|
| :---------------: | :-----------------:  | :---------------: |
|     dji-sdk-v5-aircraft-alpha     | 飞机主包，提供MSDK对飞机控制的支持。 | implementation 'com.dji:dji-sdk-v5-aircraft-alpha:{sdkVersion}' |
| dji-sdk-v5-aircraft-provided-alpha | 飞机编译包，提供飞机包相关接口。 | compileOnly 'com.dji:dji-sdk-v5-aircraft-provided-alpha:{sdkVersion}' |
| dji-sdk-v5-networkImp-alpha | 网络库包，为MSDK提供联网能力（如果不加此依赖，MSDK所有联网功能都会停用，但控制硬件的相关接口还可以正常使用）。 | runtimeOnly 'com.dji:dji-sdk-v5-networkImp-alpha:{sdkVersion}' |

- 如果仅需支持飞机产品，使用：
  ```groovy
  implementation "com.dji:dji-sdk-v5-aircraft-alpha:{sdkVersion}"
  compileOnly "com.dji:dji-sdk-v5-aircraft-provided-alpha:{sdkVersion}"
  ```


- 如果需要MSDK使用网络（默认都需要），使用：
  ```groovy
  runtimeOnly "com.dji:dji-sdk-v5-networkImp-alpha:{sdkVersion}"
  ```

