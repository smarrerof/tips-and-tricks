# Tips and tricks
Tips and tricks collection for software developers


## NPM
List installed packages
```
> npm list -g --depth=0
```

## Android
Generate debug.keystore
```
> keytool -genkey -v -keystore debug.keystore -storepass android -alias androiddebugkey -keypass android -keyalg RSA -keysize 2048 -validity 10000
```

SHA-1 fingerprint of keystore certificate
```
> keytool -list -v -keystore ~/.android/debug.keystore -alias androiddebugkey -storepass android -keypass android 
```

GET SHA-1 in base64
```
> keytool -exportcert -alias androiddebugkey -keystore debug.keystore > debug.keystore.txt
> openssl sha1 -binary debug.keystore.txt > debug.keystore.sha1.txt
> openssl base64 -in debug.keystore.sha1.txt > debug.keystore.sha1.base64.txt
```

Record screen
```
> adb shell
> screenrecord /sdcard/video.mp4
> CTRL+C to stop recording
```

Google Maps running in Windows (more info [here](https://stackoverflow.com/questions/45121828/android-studio-suddenly-got-gpu-driver-issue-when-running-emulator))
```
> cd C:\Users\<userName>\AppData\Local\Android\sdk\emulator
> emulator -list-avds (Find emulator to run by listing available ones)
> emulator -avd avd_name -gpu host (Run emulator with -gpu host option)
```

Launch android emulator from command line
```
OSX
$ cd %USERPROFILE%\AppData\Local\Android\Sdk\emulator && emulator -gpu host -avd Nexus_5_API_28

WIN
$ cd $HOME/Library/Android/sdk/emulator & emulator -avd Nexus_5_API_28
```
