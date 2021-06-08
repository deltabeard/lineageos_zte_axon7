# How to Build Lineage OS 15.1 for the ZTE Axon 7

The process of building Lineage OS 15.1 for the ZTE Axon 7 was complicated for me at first due to a variety of problems that arose with the build system.

## Requirements

Ubuntu 18.04.5 LTS is required, with the following packages installed:

> aapt android-tools-adb android-tools-fastboot aptitude autoconf automake autopoint autotools-dev bc bison brotli build-essential ccache curl debootstrap flex fontconfig gawk gcc-multilib git g++-multilib gnupg gperf htop imagemagick lib32ncurses5-dev lib32readline-dev lib32z1-dev libarchive-zip-perl libc6-dev-i386 libgl1-mesa-dev liblz4-tool libncurses5-dev libsdl1.2-dev libssl-dev libtimedate-perl libtool libwxgtk3.0-dev libx11-dev libxml2-utils lzop make openjdk-8-jdk openssh-server patchelf pngcrush policycoreutils python python2.7 python3-pip python-networkx python-pip schedtool setools software-properties-common squashfs-tools tmux unzip vim x11proto-core-dev xsltproc zip zlib1g-dev zlib1g-dev:i386

## Process

Follow the instructions at https://wiki.lineageos.org/devices/axon7/build . Check out the `lineage-15.1` branch.

Before starting the build (with `brunch`), execute the following commands to fix an [issue with the Jack build system with recent versions of Java](https://stackoverflow.com/a/67426405):

1. Remove TLSv1, TLSv1.1 from jdk.tls.disabledAlgorithms in /etc/java-8-openjdk/security/java.security file
2. Restart the jack server: cd /prebuilts/sdk/tools/ ./jack-admin kill-server ./jack-admin start-server
