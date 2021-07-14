# 小米-Ruby-15.6-UMA-only

##### 本套EFI的源文件皆来源于 [XenOriginal](https://github.com/XenOriginal)所制作的

##### 因为他所制作的EFI并不支持我所购买的DW1820A网卡，故自己按照他原先的文件进行一定程度的修改

##  警告

此配置仅适用于没有 Nvidia 显卡的 i5-8250U 本人所使用的网卡为DW1820A 目前咸鱼价格在100以内

性价比较高

## 安装过程

1.使用脚本解锁CFG并设置DVMT，若为解锁，则可能出现跑码过程中卡死的现象

2.打开DVM文件夹详细的安装过程都在内部的MD文件中

1. 在对BIOS做进一步修改之前运行 `bios_unlock.cmd`。你需要重启否则脚本将不会生效。你不能一股脑运行完所有脚本再重启，因为只有关机前最后一个脚本生效。

2. 运行 `DVMT_set.cmd` 让帧缓存=64mb。

3. 运行 `CFG_unlock.cmd`，再次重启。

4. 运行 `bios_lock.cmd` 来给BIOS重新上锁，让电脑更安全。

## 特征

1. Opencore Bootloader 和所有 Hotpatch ACPI 表
2. 解锁CFG和DVMT限制，mac更原创
3. 99% 硬件是完美的，即使是 FN 背光按钮
4. 声卡完美运行
5. 未开启随行模式，只因本人无设备测试
6. 尽量减少使用触摸板，因为触摸板并未完美驱动，无法触摸点按

## 硬件

要在小米-Ruby-15.6-UMA-only 上获得 99% 完美的 Hackintosh，您需要执行以下操作。

1.更换Realtek无线网卡到DW1820A - 必备

2. 将显示器从 45% NTSC 更换为 72% NTSC (N156HCE-EN1) - 可选

3. 将您的 m2 ssd 从 SATA 更换为 NVME - 可选

4. 升级您的内存 - 可选


## BIOS 设置

1.设置bios密码并禁用scurity boot - 必要

2.使用脚本解锁CFG并设置DVMT - 推荐（您可以通过恢复bios设置回滚）

    您可以在 Opencore 启动页面中进行测试

## 工作不顺利

1. Realtek SD 读卡器

    您可以将其传递给 VirtualMachine，因为它是一个 USB 设备！

## 生成你自己的 SMbios

  平台信息

目前本套EFI自带一份Mac信息，如需自行设置请按照一下步骤进行

  为了设置 SMBIOS 信息，我们将使用 CorpNewt 的 GenSMBIOS 和 ProperTree 应用程序。 https://github.com/corpnewt/GenSMBIOS https://github.com/corpnewt/ProperTree

  由于 KabyLake R，我们将选择 MacBookPro14,2 SMBIOS：

  运行 GenSMBIOS，选择选项 1 下载 MacSerial 和选项 3 选择 SMBIOS。这将为我们提供类似于以下内容的输出：

  类型：MacBookPro14,2

  序列号：C02WXAY2HV2N

  主板序列号：C02826303CDHRPC8C

  SmUUID：88AA1336-8DF9-477A-A39F-03D016ED0809

  订单是产品 |系列 |板串行 (MLB)

  Type 部分被复制到 Generic -> SystemProductName。

  Serial 部分被复制到 Generic -> SystemSerialNumber。

  Board Serial 部分被复制到 Generic -> MLB。

  SmUUID 部分被复制到 Generic -> SystemUUID。

  我们将 Generic -> ROM 设置为 Apple ROM（从真实 Mac 转储）、您的 NIC MAC 地址或任何随机 MAC 地址（可能只是 6 个随机字节，对于本指南，我们将使用 11223300 0000。安装后遵循关于如何找到您的真实 MAC 地址的修复 iServices 页面）

  提醒您想要无效序列号或有效序列号但未使用的序列号，您希望收到一条消息，例如：“序列号无效”或“购买日期未验证”

  Apple Check Coverage 页面 https://checkcoverage.apple.com/cn/zh/

## 捐赠

![s](https://i.loli.net/2021/07/14/SecNU3HOmFfdhzM.png)

