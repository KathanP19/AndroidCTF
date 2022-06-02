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
- 

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


