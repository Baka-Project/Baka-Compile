<p align="center">
<img src="img/baka-compiler.png" />

# Kernel building script

[![Codacy Badge](https://api.codacy.com/project/badge/Grade/470edf0d2b874a7ca06a31cf5b21a41e)](https://app.codacy.com/gh/Baka-Project/Baka-Compile?utm_source=github.com&utm_medium=referral&utm_content=Baka-Project/Baka-Compile&utm_campaign=Badge_Grade_Settings)


**Installasion**
```sh
$ git clone https://github/Baka-Project/Baka-Compile.git
```

* open file and edit
    * DEFCONFIG # defconfig your main kernel
    * HOST      # whatever you need to name
    * USER      # whatever you need to name
    * CLANG     # path the clang folder
    * ARM64     # path the gcc arm64 folder
    * ARM32     # path the gcc arm32 folder

* copy file to your directory kernel
* `bash baka-compile --gcc` for gcc build
* `bash baka-compile --clang` for clang build

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
