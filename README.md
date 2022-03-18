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
* [**AOSPExtended**](https://github.com/AospExtended)
* [**ProtonAOSP**](https://github.com/ProtonAOSP)
* [**GrapheneOS**](https://github.com/GrapheneOS)
* [**OctaviOS**](https://github.com/Octavi-OS)
* [**SparkOS**](https://github.com/Spark-rom)
* [**ProjectXtended**](https://github.com/Project-Xtended)
* [**PixelExperience**](https://github.com/PixelExperience)
* [**AOSP-Krypton**](https://github.com/AOSP-Krypton)
* [**exTHmUI**](https://github.com/exthmui)
* [**YAAP**](https://github.com/yaap)
* [**Evolution-X**](https://github.com/Evolution-X)
* [**ProjectRadiant**](https://github.com/ProjectRadiant)
* [**ProjectStreak**](https://github.com/ProjectStreak)
* [**WaveOS**](https://github.com/)
* [**Project Kaleidoscope**](https://github.com/Project-Kaleidoscope)
* [**Descendant-XI**](https://github.com/Descendant-XI)

And the list goes on....
