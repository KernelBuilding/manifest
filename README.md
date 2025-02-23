![SHRP-Reborn](banner.png)

# Requirements:
- Around 50GB disk space.
- A computer with at least 16GB RAM running Linux (recommended) or MacOS.
- Build environment [setup](https://github.com/akhilnarang/scripts).

### Create SHRP Folder ###
```bash
mkdir SHRP
cd SHRP
```

### Sync our source ###
```bash
repo init -u https://github.com/KernelBuilding/manifest.git -b shrp-12.1
```
```bash
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
```

### Build our source ###
```bash
. build/envsetup.sh
lunch twrp_$codename-eng
make $recoverytypeimage -j$(nproc --all)
```

To get started with the building process, you'll need to get familiar with [Git and Repo](http://source.android.com/source/using-repo.html).
