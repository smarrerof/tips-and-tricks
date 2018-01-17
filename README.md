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
