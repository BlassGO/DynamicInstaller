# 🚀 Welcome to Dynamic Installer

**Dynamic Installer** is an open-source framework designed to simplify Android customization through a flexible ZIP-based installer. It provides a robust set of utilities for tasks ranging from basic file installation to advanced APK/JAR patching.

Supports both ``Recovery`` and ``Magisk/KSU`` environments.

## Repository

Two branches separate two distinct variants of DI:

- **Main**: Contains shared files common to both variants

- **Standard**:
  
  Optimized for lightweight ZIPs (up to **3.5GB**, using ``unzip``).
- **Z-Variant**
  
  Designed for heavy ROM installations (using ``7zip``).

## How Does It Work?

**DI** uses a simple ZIP structure to package its scripts and tools. Here’s a basic layout:

```
dynamic_installer.zip
├── META-INF
│   ├── com
│   │   └── google
│   │       └── android
│   │           ├── updater-script   # Your Recovery script
│   │           ├── update-binary    # Sets up the environment
│   │           └── magisk           # Magisk space
│   │               ├── customize.sh # Your Module script
│   │               └── module.prop  # Your Module info
│   ├── addons                       # Optional plugins
│   │   └── extra.zip                # Extra binaries
│   └── zbin                         # Internal tools and binaries
│       └── (tools)
|
├── customize.sh        # It is only provisional for modules
├── module.prop         # KSU / Magisk v28+ module info
|
└── (your custom files/folders)
```

### Advantages
- Uses **Bash**, instead of DASH/ASH.
- Supports ``Recovery`` and ``Magisk/KSU ``installations with Dual Mode.
- Supports `arm64-v8a` and `armeabi-v7a` architectures.
- Ensure consistent script logic across any device using **standardized mount points** that abstract away differences in device structure (System_root vs. Traditional).
- Simplifies most Android modding scenarios, including reverse engineering of APKs/JARs (at the **Smali** level).

## Download - Docs

For detailed guides, actions, and configuration options, visit the official documentation:

- [Dynamic Installer Docs](https://blassgo.github.io/DynamicInstaller_Doc/)

## Credits

- [**BlassGO**](https://github.com/BlassGO): Creator of Dynamic Installer.
- [**osm0sis**](https://github.com/osm0sis): Traditional Edify installer functionalities in shell code.
- [**topjohnwu**](https://github.com/topjohnwu): Cool shell script functions.
- [**munjeni**](https://github.com/munjeni): `superrepack` and `superunpack` tools.
- [**xenosaur**](https://xdaforums.com/m/xenosaur.11895643/): 7zip binaries for Z variants.
- **Community**: Thanks to all supporters on Telegram!

## License
> **Dynamic Installer** is distributed under the GNU General Public License version 3.0 (``GPLv3``). This means that anyone can use, modify and distribute the software as long as they comply with the terms of the license.

  **->** See the [LICENSE](./LICENSE) file for more information on the license terms and conditions.