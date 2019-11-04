###  LinuxKernel Note

---

**0x00  前言**

​	OS： 4.15.0-47-generic #50-Ubuntu

**0x01 Linux Kernel 位置目录及子目录 **

​	Linux内核存放位置：`/usr/src/kernel_version`*note:kernel_version indicate  which is the directory  of the correspoding  version of the linux kernel*	

- **arch**

  包含硬件体系结构相关代码，每一种平台独立占用一个目录。

- **block**

  block devices 通用I/O层代码。

- **crypto**

  常用的加密和散列算法，以及一些压缩和CRC检验算法。

- **documennts**

  关于内核各部分通用解释说明。

  首先在我的内核版本目录下，D目录下并没有想想的文本问家，而在lxr网站上看到最新版内核源码中有很多文档供参考。

  ​                                                                           *部分内容*

```shell
===============================================
Block layer statistics in /sys/block/<dev>/stat
===============================================

This file documents the contents of the /sys/block/<dev>/stat file.

The stat file provides several statistics about the state of block
device <dev>.

Q.
   Why are there multiple statistics in a single file?  Doesn't sysfs
   normally contain a single value per file?

A.
   By having a single file, the kernel can guarantee that the statistics
   represent a consistent snapshot of the state of the device.  If the
   statistics were exported as multiple files containing one statistic
   each, it would be impossible to guarantee that a set of readings
   represent a single point in time.
```

- **drivers**

  设备驱动程序，每个驱动占用一个独立目录。

- **firmware**

  使用某些驱动程序而需的设备固件。

- **fs**

  VFS层以及各种具体文件系统，如ext, fat, ntfs.

- **include**

  内核头文件，其与系统相关的头文件放在linux子目录下。

- **init**

  内核初始化代码

- **ipc**

  进程间通信的代码

- **kernel**

  内核最核心部分，包括与体系无关的进程管理和定时器等，与平台相关的一部分放在arch/*/kernel。

- **lib**

  内核通用库，包括各种链表、红黑树和基树等数据结构和操作函数。

- **mm**

  内存管理子系统代码，与平台相关的放在arch/*/mm目录下。

- **net**

  网络相关代码，实现了各种常见的网络协议。

- **samples**

  一些样例。

- **script**

  用于配置和编译内核文件的脚本文件。

- **security**

  主要是SELinux的安全模块。

- **sound**

  常见的音频程序驱动。

- **usr**

  实现了一个cipo。

- **tools**

  Linux 开发中用到的工具

- **virt**

  实现虚拟化的基础代码。

****

**0x02 进程**

​	