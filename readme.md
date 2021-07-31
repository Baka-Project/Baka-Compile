<p align="center">
<img src="img/baka-compiler.png" />

# Kernel building script
[![Codacy Badge](https://app.codacy.com/project/badge/Grade/1a6455335fe040329a160fad3c6de17c)](https://www.codacy.com?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=Baka-Project/Baka-Compile&amp;utm_campaign=Badge_Grade)

**Installasion**
```sh
$ git clone https://github/Baka-Project/Baka-Compile.git
```
  
  * 1. copy file compile-gcc or compile-clang or both to your directory kernel
  * 2.`bash compile-gcc` for gcc build
  * 3.`bash compile-clang` for clang build

**Features of this script**
```
Building kernel from local
```

**How to use this scripts**
```
This script has most of it's stuffs in "Basic Information" part. In a nutshell,

	DEFCONFIG - To build a kernel, you need a defconfig. It defines the defconfig which
                     you will need to build kernel. In case your source has the defconfig 
                     inside /arch/arm64/configs/vendor , then you need to set it as
                     '/vendor/<name of your defconfig>

	USER      - User builder kernel

	HOST      - Host builder kernel

	CLANG     - Your location folder of clang `clang`

	ARM64     - Your location folder of arm64 `gcc`

	ARM32     - Your location folder of arm `gcc`
```
