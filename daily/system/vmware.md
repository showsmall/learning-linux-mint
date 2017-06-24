# Vmware

Vmware 支持 linux。对于某些需要使用 windows 软件的场景，安装 vmware 后使用虚拟机安装 windows 可以用来解决一些特别的场景。

## 下载

linux 版本的 vmware workstation 下载地址：

https://www.vmware.com/products/workstation-for-linux.html

当前最新版本是 12.5.6-5528349，下载下来的文件为 `VMware-Workstation-Full-12.5.6-5528349.x86_64.bundle` 。

> 注： vmware 官网直接下载的速度非常慢，建议从其他下载网站下载，或者用百度云离线下载。

## 安装

执行下面命令开始安装：

```bash
sudo chmod +x VMware-Workstation-Full-12.5.6-5528349.x86_64.bundle
sudo ./VMware-Workstation-Full-12.5.6-5528349.x86_64.bundle
```

然后在打开的图形界面中，开始安装：

1. 接受两个协议
2. 是否要检查更新，这里选no，本来我们下载的就是最新的
3. ......
4. 安装序列号：1F04Z-6D111-7Z029-AV0Q4-3AEH8 或者 5A02H-AU243-TZJ49-GTC7K-3C61N。

等待安装完成。

## 配置

### 显卡 3D 加速

如果 vmware 虚拟机启动后报错:

	“No 3D support is available from the host”

这里需要开启对显卡的硬件支持，打开用户 home 目录下的文件 `.vmware/preferences`，增加这样配置：

```bash
mks.gl.allowBlacklistedDrivers = "TRUE"
```

切记不一定是驱动的问题，我当时就是被 vmware 的报错信息误导，折腾了半天搞定 amd 显卡的官方驱动，然后最后发现其实只是这里的设置。

参考文章：

1. [Enable 3D HW acceleration on VMWare Workstation 10 on Ubuntu 14.04](https://askubuntu.com/questions/537787/enable-3d-hw-acceleration-on-vmware-workstation-10-on-ubuntu-14-04)
