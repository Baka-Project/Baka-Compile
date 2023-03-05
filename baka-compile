#!/bin/bash

  # Email xealea@proton.me
  # Github github,com/xealea
  # Copyright (c) 2023 xealea <xealea@proton.me>

function usage() {
    version
    cat <<EOHELP
Script build kernel.
Usage:  $(basename $0) [options] All contents
  --clang      set build kernel with toolchain clang
  --gcc        set build kernel with toolchain gcc
  --version    show script builder version
  -h, --help   display this help screen
EOHELP
    exit 0
}

function set_env_vars() {
    msg "Defconfig Kernel!"
    read -e DEFCONFIG

    msg "Host Compiler!"
    read -e HOST

    msg "User Compiler!"
    read -e USER

    export KBUILD_BUILD_USER=$USER
    export KBUILD_BUILD_HOST=$HOST
}

function clang() {
    msg "Path To Folder CLANG!"
    read -e CLANG

    set_env_vars

    make -j$(nproc) O=out ARCH=arm64 $DEFCONFIG
    make -j$(nproc) ARCH=arm64 O=out \
        CC=$CLANG/clang \
        LD=$CLANG/ld.lld \
        AR=$CLANG/llvm-ar \
        NM=$CLANG/llvm-nm \
        OBJCOPY=$CLANG/llvm-objcopy \
        OBJDUMP=$CLANG/llvm-objdump \
        STRIP=$CLANG/llvm-strip \
        CROSS_COMPILE=$CLANG/aarch64-linux-gnu- \
        CROSS_COMPILE_ARM32=$CLANG/arm-linux-gnueabi-
}

function gcc() {
    msg "Path To ARM64 Folder GCC!"
    read -e ARM64

    msg "Path To ARM32 Folder GCC!"
    read -e ARM32

    set_env_vars

    make -j$(nproc) O=out ARCH=arm64 $DEFCONFIG
    make -j$(nproc) ARCH=arm64 O=out \
        CROSS_COMPILE=$ARM64/aarch64-linux-gnu- \
        CROSS_COMPILE_ARM32=$ARM32/arm-linux-androideabi-
}

while [[ "${1:0:1}" = "-" ]]; do
    case $1 in
        -h|--help)
            usage;;
        --clang)
            clang
            exit 0;;
        --gcc)
            gcc
            exit 0;;
        --version)
            version
            exit 0;;
        *)
            echo "Unknown option: $1. Run 'baka-compile --help' for help."
            exit 1;;
    esac
done

if [[ -z "$2" ]]; then
    echo "Not enough arguments. Run 'baka-compile --help' for help."
    exit 1
fi
