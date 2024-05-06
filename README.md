# project_flutter

A new Flutter project.

## Getting Started

chú ý 1 số những điều liên quan đến 1 dự án flutter
1./mục địch của file này là gì.
-tạo 1 file chuẩn để khi có bất cứ dự án nào thì clone về và chạy thôi, không cần edit lại nhiều
2./những kỹ thuật cần chú ý trong này
-để tạo 1 notification thì làm theo url sau :https://www.youtube.com/watch?v=r2_AJKpMYlo&list=LL&index=34
chú ý 2 file build.gradle có 2 file này copy đoạn này vào,dưới đây là 2 file build.gradle và file google-services.json( được lấy ra khi tạo 1 dự án mới được lưu trong đường dẫn sau songtoantd18/epur/android/app/google-services.json )
chú ý thay tên dự án ở đây com.example.eprc tên dự án này thay đổi khi up lên chplay nên chú ý thường thì sẽ là com.cbmv.ten_du_an hoặc com.unic.ten_du_an
tên dự án ở trong này là com.example.project_flutter

<!-- songtoantd18/epur/android/build.gradle -->
<!-- buildscript {
    ext.kotlin_version = '1.6.10'
    repositories {
        google()
        mavenCentral()
    }

    dependencies {
        classpath 'com.android.tools.build:gradle:4.1.0'
        classpath "org.jetbrains.kotlin:kotlin-gradle-plugin:$kotlin_version"
        classpath 'com.google.gms:google-services:4.3.13'
    }
}

allprojects {
    repositories {
        google()
        mavenCentral()
    }
}

rootProject.buildDir = '../build'
subprojects {
    project.buildDir = "${rootProject.buildDir}/${project.name}"
}
subprojects {
    project.evaluationDependsOn(':app')
}

tasks.register("clean", Delete) {
    delete rootProject.buildDir
} -->

<!-- songtoantd18/epur/android/app/build.gradle -->

<!-- def localProperties = new Properties()
def localPropertiesFile = rootProject.file('local.properties')
if (localPropertiesFile.exists()) {
    localPropertiesFile.withReader('UTF-8') { reader ->
        localProperties.load(reader)
    }
}

def flutterRoot = localProperties.getProperty('flutter.sdk')
if (flutterRoot == null) {
    throw new GradleException("Flutter SDK not found. Define location with flutter.sdk in the local.properties file.")
}

def flutterVersionCode = localProperties.getProperty('flutter.versionCode')
if (flutterVersionCode == null) {
    flutterVersionCode = '1'
}

def flutterVersionName = localProperties.getProperty('flutter.versionName')
if (flutterVersionName == null) {
    flutterVersionName = '1.0'
}

apply plugin: 'com.android.application'
apply plugin: 'kotlin-android'
apply from: "$flutterRoot/packages/flutter_tools/gradle/flutter.gradle"
apply plugin: 'com.google.gms.google-services'

android {
    compileSdkVersion 34

    compileOptions {
        sourceCompatibility JavaVersion.VERSION_1_8
        targetCompatibility JavaVersion.VERSION_1_8
    }

    kotlinOptions {
        jvmTarget = '1.8'
    }

    sourceSets {
        main.java.srcDirs += 'src/main/kotlin'
    }

    defaultConfig {
        // TODO: Specify your own unique Application ID (https://developer.android.com/studio/build/application-id.html).
        applicationId "com.example.eprc"
        minSdkVersion 21
        targetSdkVersion 33
        versionCode flutterVersionCode.toInteger()
        versionName flutterVersionName
    }

    buildTypes {
        release {
            // TODO: Add your own signing config for the release build.
            // Signing with the debug keys for now, so `flutter run --release` works.
            signingConfig signingConfigs.debug
        }
    }
    namespace 'com.example.eprc'
}

flutter {
    source '../..'
}

dependencies {
    implementation "org.jetbrains.kotlin:kotlin-stdlib-jdk7:$kotlin_version"
    implementation platform('com.google.firebase:firebase-bom:30.4.1')
} -->

3./khi chạy trên thiết bị thật (điện thoại di động android):
kiểm tra đã kết nối chưa adb devices nếu có hiện list of ... là đã có kết nối rồi,(dùng chung wifi nhé )
4.Để thay đổi ảnh logo từ "logo_DMS.png" sang "so2.png" trong cấu hình của bạn, bạn chỉ cần đổi đường dẫn đến tệp hình ảnh mới. Dưới đây là cách bạn có thể sửa đổi cấu hình của bạn:

<!--
yaml
Copy code
flutter_launcher_icons:
  android: "launcher_icon"
  ios: true
  image_path: "assets/so2.png"   # Đường dẫn đến hình ảnh mới là "assets/so2.png"
  min_sdk_android: 21 # android min sdk min:16, default 21
  web:
    generate: true
    image_path: "assets/so2.png"
    background_color: "#hexcode"
    theme_color: "#hexcode"
  windows:
    generate: true
    image_path: "assets/so2.png"
    icon_size: 48 # min:48, max:256, default: 48
  macos:
    generate: true
    image_path: "assets/so2.png" -->

Sau khi bạn đã thay đổi đường dẫn, hãy chạy lại lệnh flutter pub run flutter_launcher_icons:main để cập nhật biểu tượng ứng dụng với hình ảnh mới. Lệnh này sẽ chuyển đổi hình ảnh mới và cập nhật biểu tượng ứng dụng trên tất cả các nền tảng khác nhau theo cấu hình mới. cách thay đổi logo app trong flutter
5./ cách đẩy 1 dự án lên ch play (chú ý trong tài khoản phải có tiền thì mới thành công )
https://www.youtube.com/watch?v=ZxjgV1YaOcQ&list=LL&index=11
6./ chú ý trong file C:\Users\Song Toan\Desktop\demo\flutter-demo\project_flutter\android\app\src\main\AndroidManifest.xml cũng cần thêm 1 số quyền truy cập để có thể chạy được

<!-- <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION"/>
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION"/>
<uses-permission android:name="android.permission.RECEIVE_BOOT_COMPLETED"/>
<uses-permission android:name="android.permission.SCHEDULE_EXACT_ALARM" />
<uses-permission android:name="android.permission.USE_EXACT_ALARM" />
<uses-permission android:name="android.permission.USE_FULL_SCREEN_INTENT" />
<uses-permission android:name="android.permission.VIBRATE" />
<uses-permission android:name="android.permission.INTERNET"/>
<uses-permission android:name="android.permission.POST_NOTIFICATIONS"/> -->

7./ mỗi khi thêm ảnh vào trong dự án cần thêm ở trong file pubspec.yaml dưới đây là 1 đoạn mẫu

<!-- name: eprc_app
description: "E-PURCHASING SYSTEM"
publish_to: "none"

version: 1.0.0+1

environment:
  sdk: ">=3.2.2 <4.0.0"

dependencies:
  flutter:
    sdk: flutter
  cupertino_icons: ^1.0.2
  flutter_dotenv: ^5.1.0
  flutter_easyloading: ^3.0.5
  unorm_dart: ^0.3.0
  remove_diacritic: ^0.9.0
  geolocator: ^10.1.0
  webview_flutter: ^3.0.4
  firebase_core: ^2.24.2
  firebase_messaging: ^14.7.10
  rflutter_alert: ^2.0.7
  google_maps_flutter: ^2.5.3
  google_maps_flutter_android: ^2.7.0
  json_annotation: ^4.8.1
  json_serializable: ^6.7.1
  google_maps_flutter_web: ^0.5.4+3

dev_dependencies:
  flutter_test:
    sdk: flutter
  flutter_lints: ^3.0.1
  flutter_bootstrap5: ^1.1.1+1
  http: ^1.1.2
  characters: ^1.3.0
  flutter_launcher_icons: "^0.13.1"
  permission_handler: ^11.2.0
  flutter_local_notifications: ^16.3.2
  flutter_secure_storage: ^9.0.0
  async: ^2.11.0
  get_storage: ^2.1.1
  shared_preferences: ^2.2.2
  recase: ^4.1.0
  intl: ^0.19.0

flutter_launcher_icons:
  android: "launcher_icon"
  ios: true
  image_path: "assets/favicon.png"
  min_sdk_android: 21 # android min sdk min:16, default 21
  web:
    generate: true
    image_path: "assets/favicon.png"
    background_color: "#hexcode"
    theme_color: "#hexcode"
  windows:
    generate: true
    image_path: "assets/favicon.png"
    icon_size: 48 # min:48, max:256, default: 48
  macos:
    generate: true
    image_path: "assets/favicon.png"

flutter:
  uses-material-design: true
  assets:
    - assets/favicon.png
    - assets/eprc/logo_eprc_white.png
    - assets/eprc/bg1.png
    - assets/eprc/bg_home.png
    - assets/logo--SCG.png
    - assets/splash_img.png
    - assets/logo_UNIC.png
    - assets/splash.png
    - assets/12.png
    - assets/logo_scg.png
    - assets/h4.png
    - assets/unic_logo_large.png
    - assets/noti-bell.png -->
