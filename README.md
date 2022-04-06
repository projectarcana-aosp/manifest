<p align="center">
<img src="https://raw.githubusercontent.com/projectarcana-aosp/manifest/12.x/banner.png" > 
</p>

# Project Arcana #

### Sync ###

```bash

# Initialize local repository
repo init -u https://github.com/projectarcana-aosp/manifest -b 12.x

# Sync
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
```

### for less storage and bandwidth consumption ### 

```bash

# Initialize local repository  (thanks to apon77 for repo init script)
repo init --depth=1 --no-repo-verify -u https://github.com/projectarcana-aosp/manifest -b 12.x -g default,-mips,-darwin,-notdefault

# Sync
repo sync -c --no-clone-bundle --no-tags --optimized-fetch --prune --force-sync -jX
```

### Device bringup ###

```bash

# first, inherit Project Arcana common.mk
$(call inherit-product, vendor/aosp/common.mk)

# do aosp bringup and use these flags to adapt

# maintainer flag
ARCANA_MAINTAINER := maintainer

# pixel build flag, if not define build type is vanilla
WITH_GAPPS := true/false

# disable/enable blur support, default is false
TARGET_SUPPORTS_BLUR := true/false

# prebuilt graphene camera flag, default is false
TARGET_BUILD_GRAPHENEOS_CAMERA := true/false

# whether to copy apns-conf.xml to system
# (for devices having issues with TelephonyProvider: FileNotFoundException)
# default is false (product)
COPY_APN_SYSTEM := true/false

# Misc flags to enable certain features

# UDFPS ICONS/ANIMATIONS
EXTRA_UDFPS_ANIMATIONS := true/false

# Quick tap feature
TARGET_SUPPORTS_QUICK_TAP := true/false

# Face Unlock
TARGET_FACE_UNLOCK_SUPPORTED := true/false

# Bloom and Living Universe Pixel Wallpapers
TARGET_INCLUDE_LIVE_WALLPAPERS := true/false

# Pixel Now playing feature
TARGET_SUPPORTS_NOW_PLAYING := true/false

# Pixel charger animation
USE_PIXEL_CHARGER_IMAGES := true/false

```

### Build ###

```bash

# Set up environment
$ source build/envsetup.sh

# Choose a target
$ lunch aosp_$device-userdebug

# Build the code
$ make bacon -jX
```

Credits
-------
* [**AOSP Extended**](https://github.com/AospExtended)
* [**AOSP-Krypton**](https://github.com/AOSP-Krypton)
* [**ArrowOS**](https://github.com/ArrowOS)
* [**Crdroid**](https://github.com/crdroidandroid)
* [**Descendant-XI**](https://github.com/Descendant-XI)
* [**DotOS**](https://github.com/DotOS)
* [**Evolution-X**](https://github.com/Evolution-X)
* [**exTHmUI**](https://github.com/exthmui)
* [**GrapheneOS**](https://github.com/GrapheneOS)
* [**LineageOS**](https://github.com/LineageOS)
* [**OctaviOS**](https://github.com/Octavi-OS)
* [**Pixel Experience**](https://github.com/PixelExperience)
* [**Project Awaken**](https://github.com/Project-Awaken)
* [**Project Kaleidoscope**](https://github.com/Project-Kaleidoscope)
* [**Project Radiant**](https://github.com/ProjectRadiant)
* [**Project Streak**](https://github.com/ProjectStreak)
* [**Project Xtended**](https://github.com/Project-Xtended)
* [**ProtonAOSP**](https://github.com/ProtonAOSP)
* [**SparkOS**](https://github.com/Spark-rom)
* [**WaveOS**](https://github.com/)
* [**Xdroid OSS**](https://github.com/xdroid-oss)
* [**YAAP**](https://github.com/yaap)

And the list goes on....
