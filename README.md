# coreos-install-pc
Installing CoreOS Container Linux to disk
Install script

There is a simple installer that will destroy everything on the given target disk and install Container Linux. Essentially it downloads an image, verifies it with gpg, and then copies it bit for bit to disk. An installation requires at least 8 GB of usable space on the device.

The script is self-contained and located on GitHub here and can be run from any Linux distribution. You cannot normally install Container Linux to the same device that is currently booted. However, the Container Linux ISO or any Linux liveCD will allow Container Linux to install to a non-active device.

If you boot Container Linux via PXE, the install script is already installed. By default the install script will attempt to install the same version and channel that was PXE-booted:

coreos-install -d /dev/sda -c cloud-config.yaml

The Stable channel should be used by production clusters. Versions of Container Linux are battle-tested within the Beta and Alpha channels before being promoted. The current version is Container Linux 1409.7.0.

If you want to ensure you are installing the latest stable version, use the -C option:
coreos-install -d /dev/sda -C stable -c cloud-config.yaml

