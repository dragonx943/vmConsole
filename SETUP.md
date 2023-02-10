![](./images/banner.png)

# vmConsole
## 下载并安装APK
  [下载APK](https://github.com/sylirre/vmConsole/releases/download/v1.10.1/vmConsole-v1.10.1-release.apk)
## 初始化
### 1.设置docker自动启动
  ```bash
  service docker start
  rc-update add docker
  ```
### 2.设置显示开机日志
  ```bash
  sed -i -E 's/(local kernel_opts)=.*/\1="console=ttyS0"/' /sbin/setup-disk
  ```
### 3.设置启动盘
  ```bash
  ~#setup-disk （输入setup-disk 回车,进入设置启动盘）
  Available disks are:
    sda   (34.4 GB QEMU     QEMU HARDDISK   )
    sdb   (34.4 GB QEMU     QEMU HARDDISK   )
  Which disk(s) would you like to use? (or '?' for help or 'none') [sda]（回车,使用默认值）
  The following disk is selected:
    sda   (34.4 GB QEMU     QEMU HARDDISK   )
  How would you like to use it? ('sys', 'data', 'crypt', 'lvm' or '?' for help) [?] sys （输入sys回车）
  WARNING: The following disk(s) will be erased:
    sda   (34.4 GB QEMU     QEMU HARDDISK   )
  WARNING: Erase the above disk(s) and continue? (y/n) [n] y（输入y回车）
  Creating file systems...
  Installing system on /dev/sda3:
  /mnt/boot is device /dev/sda1
  100% ███████████████████████████████████████████████████████████████████████████==> initramfs: creating /boot/initramfs-virt
  /boot is device /dev/sda1
  Installation is complete. Please reboot.
  ~#reboot （输入reboot 回车等待重启完成）
  ```
### 4.登录系统

  输入用户名`root`即可进入系统，至此你拥有了一台包含docker服务的linux主机

## 提示
1.程序映射了`22,80,443,5244,5678,6000`端口，通过长按屏幕，点击更多，可查看对外映射的端口号

2.关机指令`poweroff`,或者长按屏幕，点击更多，点击关机
