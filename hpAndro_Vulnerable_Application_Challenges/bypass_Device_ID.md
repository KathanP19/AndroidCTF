# Device ID Challenges

## SSAID/ANDROID_ID. (Points 100)

- Tools
  1. Frida
  2. Jd-gui
  3. Genymotion

- Android API : [android.provider.Settings$Secure](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID)

- device_id.js
```
Java.perform( function () {
    var device_id = Java.use('android.provider.Settings$Secure');
  device_id.getString.implementation = function(a, b) {
    if (b == "android_id") {
      return "FFFF0000FFFF1337";
    }
    return this.getString(a, b);
  }
});
```
- Steps:
```
1. Use Frida: "frida -l device_id.js -U -f com.hpandro.androidsecurity --no-pause"
2. Go to Device ID Menu -> SSID/ANDROID_ID 
3. Click task -> Click "Check SSID/ANDROID_ID Flag" 
4. Done, Copy Flag
```

- Flag: `hpandro{SSAID.WSPR1Ueb2nhpx3JzVMDTMn15qAZcOeUQ}`

# References:
- https://gist.github.com/jacopo-j/6a6a0e3c4e2fe974955ce41878f6df5b
