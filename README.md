<p align="center">
<img src="https://raw.githubusercontent.com/projectarcana-aosp/manifest/12.x/banner.png" > 
</p>

# Project Arcana #

### Sync ###

```bash

# Initialize local repository
repo init -u git://github.com/projectarcana-aosp/manifest -b 12.x

# Sync
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
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
