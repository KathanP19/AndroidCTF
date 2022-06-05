# Deferent Emulator Detection Bypasses

## Bypass Virtual Phone Number Detection. (Points 100)
- Tools
  1. Frida
  2. Jd-gui
  3. Genymotion

- emulator.js script
```
Java.perform(function () {
  console.log("[.] Test bypass Emulator Detect");
  var EmulatorDetector = Java.use('com.hpandro.androidsecurity.utils.emulatorDetection.EmulatorDetector');
  EmulatorDetector.checkPhoneNumber.implementation = function () {
    return false;
  };
});
```

- Steps:
```
1. Edit emulator.js 5th line "false" to "true"
2. Use Frida: "frida -l emulator.js -U -f com.hpandro.androidsecurity --no-pause"
3. Go to Emulator Detection Menu -> Virtul Phone Number
4. Change the script return value back to "false" and save
5. frida will reload the script if not then "%load" command to reload
6. Done, click task button and click Detect EMulator on new activity you will get flag.
```

- Flag: `hpandro{emuvpn.La9IDR3Lr4Se11mvfbWPiYv0CE0hb9GM}`

## Bypass Hardware Specifications Detection. (Points 100)
- Here, we alter the data from generic VM variables to genuine phone values, making it impossible to identify. (Only need Hardware,Product,BOARD)

- Tools
  1. Frida
  2. Jd-gui
  3. Genymotion

- emulator.js script
```
Java.perform( function () {
    var String = Java.use("java.lang.String");
    var Build = Java.use("android.os.Build");
    Build.HARDWARE.value = String.$new("natsu");
    Build.PRODUCT.value = String.$new("natsu");
    Build.BOARD.value = String.$new("natsu");
});
```

- Steps:
```
1. Edit emulator.js add "//" before 4,5,6 line. 
2. Use Frida: "frida -l emulator.js -U -f com.hpandro.androidsecurity --no-pause"
3. Go to Emulator Detection Menu -> HardWare Specification
5. remove "//" comments frida will reload the script if not then "%load" command to reload
6. Done, click task button and click Detect EMulator on new activity you will get flag.
```
- Flag: `hpandro{emuhws.pPZNkSkud4eK7rLhrV9M7SKvB68FTKgj}`

## Bypass Emulator Files Check Detection. (Points 100)

- Tools
  1. Frida
  2. Jd-gui
  3. Genymotion

- emulator.js script
```
Java.perform( function () {
  console.log("[.] Test bypass Emulator Detect");
  var EmulatorDetector = Java.use('com.hpandro.androidsecurity.ui.activity.task.emulatorDetection.FileBasedCheckingActivity');
  EmulatorDetector.checkFiles.implementation = function (a,b) {
    return false;
  };
});
```

- Steps:
```
1. Edit emulator.js 5th line "false" to "true"
2. Use Frida: "frida -l emulator.js -U -f com.hpandro.androidsecurity --no-pause"
3. Go to Emulator Detection Menu -> Emulator File Check.
4. Change the script return value back to "false" and save
5. frida will reload the script if not then "%load" command to reload
6. Done, click task button and click Detect EMulator on new activity you will get flag.
```

- Flag: `hpandro{emufbc.cWIsJeRRiINM9hsUa1I9U9dcIYxBv21a}`

## Bypass QEmu Detection. (Points 100)

- Tools
  1. Frida
  2. Jd-gui
  3. Genymotion

- emulator.js script
```
Java.perform(function () {
  console.log("[.] Test bypass Emulator Detect");
  var EmulatorDetector = Java.use('com.hpandro.androidsecurity.ui.activity.task.emulatorDetection.QEMUDetectionActivity');
  EmulatorDetector.checkFiles.implementation = function (a,b) {
    return false;
  };
  EmulatorDetector.checkQEmuProps.implementation = function () {
    return false;
  };
   EmulatorDetector.checkQEmuProps.implementation = function () {
    return false;
  };
});
```

- Steps:
```
1. Use Frida: "frida -l emulator.js -U -f com.hpandro.androidsecurity --no-pause"
2. Go to Emulator Detection Menu -> QEMU
3. Done, click task button and click Detect EMulator on new activity you will get flag.
```

- Flag: `hpandro{emuqemu.t1v6xsedyqZa5y9GYT4RqVLJToS7w90W}`

## Bypass Emulator Default IP Check. (Points 100)

- Tools
  1. Frida
  2. Jd-gui
  3. Genymotion

- emulator.js script
```
Java.perform(function () {
  console.log("[.] Test bypass Emulator Detect");
  var EmulatorDetector = Java.use('com.hpandro.androidsecurity.utils.emulatorDetection.EmulatorDetector');
  EmulatorDetector.checkIp.implementation = function () {
    return false;
  };
});
```

- Steps:
```
1. Edit emulator.js 5th line "false" to "true"
2. Use Frida: "frida -l emulator.js -U -f com.hpandro.androidsecurity --no-pause"
3. Go to Emulator Detection Menu -> Default IP Check.
4. Click task button and change the script return value back to "false" and save
5. frida will reload the script if not then "%load" command to reload
6. Done, click Detect EMulator on new activity you will get flag.
```
- Flag: `hpandro{emuipb.LrIAbvZlaaiQtaB3wZ5Dz3a6sjHoQaE1}`

## Bypass Check Package Name. (Points 100)

- Tools
  1. Frida
  2. Jd-gui
  3. Genymotion

- emulator.js script
```
Java.perform(function () {
  console.log("[.] Test bypass Emulator Detect");
  var EmulatorDetector = Java.use('com.hpandro.androidsecurity.utils.emulatorDetection.EmulatorDetector');
  EmulatorDetector.checkPackageNameDetect.implementation = function () {
    return false;
  };
});
```

- Steps:
```
1. Edit emulator.js 5th line "false" to "true"
2. Use Frida: "frida -l emulator.js -U -f com.hpandro.androidsecurity --no-pause"
3. Go to Emulator Detection Menu -> Check Package Name.
4. Click task button and change the script return value back to "false" and save
5. frida will reload the script if not then "%load" command to reload
6. Done, click Detect EMulator on new activity you will get flag.
```

- Flag: `hpandro{emupn.iGvW77WPqhRoFpLvFYovmYZW2jRGRjYC}`

## Bypass Debug Flag. (Points 100)

- Tools
  1. Frida
  2. Jd-gui
  3. Genymotion

- emulator.js script
```
Java.perform( function () {
    var EmulatorDetector = Java.use("com.hpandro.androidsecurity.utils.emulatorDetection.EmulatorDetector");
    EmulatorDetector.isDebug.implementation = function() {
        return false;
    }
});
```

- Steps:
```
1. Edit emulator.js 4th line "false" to "true"
2. Use Frida: "frida -l emulator.js -U -f com.hpandro.androidsecurity --no-pause"
3. Go to Emulator Detection Menu -> Debug Flag.
4. Click task button and change the script return value back to "false" and save
5. frida will reload the script if not then "%load" command to reload
6. Done, click Detect EMulator on new activity you will get flag.
```

- Flag: `hpandro{emudb.EkQUj0oSyYcf8uhJSeCGWuU3X9zofBaT}`

## Bypass Network Operator Name. (Points 100)

- Tools
  1. Frida
  2. Jd-gui
  3. Genymotion

- emulator.js script
```
Java.perform( function () {
    var EmulatorDetector = Java.use("com.hpandro.androidsecurity.ui.activity.task.emulatorDetection.NetworkOperatorNamesActivity");
    EmulatorDetector.checkOperatorNameAndroid.implementation = function() {
        return false;
    }
});
```

- Steps:
```
1. Use Frida: "frida -l emulator.js -U -f com.hpandro.androidsecurity --no-pause"
2. Go to Emulator Detection Menu -> Network Operator Name
3. Done, click task button and click Detect EMulator on new activity you will get flag.
```
- Flag: `hpandro{emunon.OEAOydM2LWnq0VnKZX6o7pRvzN6UHtra}`

## Bypass Device ID based detection. (Points 100)

- Tools
  1. Frida
  2. Jd-gui
  3. Genymotion

- emulator.js script
```
Java.perform( function () {
    var EmulatorDetector = Java.use("com.hpandro.androidsecurity.utils.emulatorDetection.EmulatorDetector");
    EmulatorDetector.checkImsi.implementation = function() {
        return false;
    };
    EmulatorDetector.checkDeviceId.implementation = function() {
        return false;
    }
});
```

- Steps:
```
1. Edit emulator.js all line "false" to "true"
2. Use Frida: "frida -l emulator.js -U -f com.hpandro.androidsecurity --no-pause"
3. Go to Emulator Detection Menu -> Device ID.
4. Click task button and change the script return value back to "false" and save
5. frida will reload the script if not then "%load" command to reload
6. Done, click Detect EMulator on new activity you will get flag.
```

- Flag: `hpandro{emudid.FNvq8tpbMtDweNn7gsgazfz5FuO5rxrg}`
