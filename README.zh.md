# Lenovo Asphalt 固件

[English](README.md)

本仓库存放 Lenovo Legion Y700 2023（TB320FC，Asphalt）当前使用的 41 个二进制文件，复制自 [`nixos-android-devices` 的 `492e0c1` 提交](https://git2.pardinus.net/dianqk/nixos-android-devices/src/commit/492e0c14a14ce9ecd7fdcb8c58b9c2db454b0b78/firmware)。目录结构与原件相同，便于直接比较。NixOS 软件包目前仍读取原仓库中的文件，尚未切换到本仓库。

| 路径 | 文件数 | 来源 | 用途 |
| --- | ---: | --- | --- |
| `lenovo/tb320fc/firmware` | 8 | 保存的 TB320FC Android 固件镜像 | 触摸屏、Adreno GPU、视频解码 |
| `lenovo/tb320fc/audio` | 29 | 保存的 TB320FC Android `modem_b` 与 `vendor` 镜像 | ADSP、CS35L45 扬声器 |
| `lenovo/tb320fc/wifi` | 1 | 从原厂 `qca6490/bdwlang.elf` 封装的 `board-2.bin` | WCN6855 板级数据 |
| `oneplus/negroni/WCN6855/hw2.1` | 3 | [Xlie-Electronic-Customs/linux-firmware-oplus-negroni 的 `5a4116c` 提交](https://github.com/Xlie-Electronic-Customs/linux-firmware-oplus-negroni/tree/5a4116cd5eecebec5db4b4a85d4781dd1168e619/oplus-negroni/ath11k/WCN6855/hw2.1) | WCN6855 的 `amss.bin`、`m3.bin`、`regdb.bin` |

TB320FC 原始 ROM 构建编号及完整镜像哈希尚未确定；`SHA256SUMS` 准确标识每个文件。CS35L45 的 `spk1` 和 `spk2` `.wmfw` 内容相同，因此只存一份，Nix 软件包为第二个运行时文件名创建符号链接。本仓库不包含设备 Wi-Fi／蓝牙地址。

在本目录运行 `sha256sum -c SHA256SUMS` 校验文件。Lenovo 来源镜像与 OnePlus 集合未为所选文件提供经过核实的再分发授权；原权利人保留其权利。
