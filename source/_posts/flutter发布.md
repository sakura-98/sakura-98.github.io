---
title: flutter发布
layout: post
date: 2020-10-24
tags: flutter
---

用flutter发布Android app 一般需要以下步骤（不包括发布到应用商店）

<!--more-->

1. 将应用图标放入`<app dir>/android/app/src/main/res/`目录

2. 检查`<app dir>/android/app/src/main/AndroidManifest.xml`，修改`package`，`application-android:label`，`application-android-icon`

3. 修改`<app dir>/android/app/src/main/kotlin`下文件结构，并将其下`MainActivity.kt`第一行修改为包名

4. 把文件 `key.properties` 复制到`<app dir>/android`目录下

5. 修改`<app dir>/android/app/build.gradle`

   1. 替换

      ```groovy
      android{
      ```

      为

      ```groovy
      def keystorePropertiesFile = rootProject.file("key.properties")
      def keystoreProperties = new Properties()
      keystoreProperties.load(new FileInputStream(keystorePropertiesFile))

      android{
      ```

   2. 替换

      ```groovy
      buildTypes {
          release {
              // TODO: Add your own signing config for the release build.
              // Signing with the debug keys for now, so `flutter run --release` works.
              signingConfig signingConfigs.debug
          }
      }
      ```

      为

      ```groovy
      signingConfigs {
          release {
              keyAlias keystoreProperties['keyAlias']
              keyPassword keystoreProperties['keyPassword']
              storeFile file(keystoreProperties['storeFile'])
              storePassword keystoreProperties['storePassword']
          }
      }
      buildTypes {
          release {
              signingConfig signingConfigs.release
          }
      }
      ```

   3. 修改`defaultConfig`中`applicationId`

6. 生成apk文件

   ```bash
   flutter build apk --target-platform android-arm64
   ```

   文件位于`<app dir>/build/app/outputs/apk/app-release.apk`

未签名应用签名方式：

```bash
jarsigner -verbose -keystore C:\Users\yzsu0\key.jks -signedjar signed.apk no_sign.apk key
```
