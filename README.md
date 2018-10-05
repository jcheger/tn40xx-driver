introduction
============
Fork of TN40XX driver from https://github.com/acooks/tn40xx-driver, with DKMS configuration file

The driver should be installed manually for current kernel, altough new installed kernels should get the driver compiled automatically.

requirements
============

Debian
------
    apt install build-essential git dkms
    
if you have a Debian / Ubuntu stock kernel:

    apt install linux-headers-`uname -r`
    
if you have a Proxmox kernel:

    apt install pve-headers pve-headers-`uname -r`

install
=======
    git clone -b cleanup/v0.3.6.15 https://github.com/jcheger/tn40xx-driver.git /usr/src/tn40xx-0.3.6.15
    dkms add -m tn40xx -v 0.3.6.15

build driver for current kernel
===============================
    dkms install -m tn40xx -v 0.3.6.15
    
build driver for specific kernel version
========================================
    dkms install -m tn40xx -v 0.3.6.15 -k [kernel_version]

uninstall
=========
This will remove module for all kernel versions

    dkms remove -m tn40xx -v 0.3.6.15 --all
