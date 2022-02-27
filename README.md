# android_device_xiaomi_raphael
For building TWRP for Xiaomi Redmi K20 Pro / Mi 9T Pro

TWRP device tree for Xiaomi Redmi K20 Pro / Mi 9T Pro

## Features

Works:

- ADB
- Screen brightness settings
- Correct screenshot color
- MTP
- Flashing (opengapps, roms, images and so on)
- Backup/Restore (Needs more testing)
- USB OTG
- Android R Support
- Vibration support

To-do:

- Decryption of /data (policy V2)

## Compile

First checkout minimal twrp with omnirom tree:

```
repo init -u git@github.com:minimal-manifest-twrp/platform_manifest_twrp_aosp.git -b twrp-11
repo sync
```

Then add these projects to .repo/manifest.xml:

```xml
<project path="device/xiaomi/raphael" name="mauronofrio/android_device_xiaomi_raphael" remote="github" revision="android-11.0" />
```

Finally execute these:

```
. build/envsetup.sh
lunch omni_raphael-eng
mka recoveryimage
```

To test it:

```
fastboot boot out/target/product/raphael/recovery.img
```

## Thanks
@mauronofrio
@PIPIPIG233666
