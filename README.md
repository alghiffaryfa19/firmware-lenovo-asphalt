# Lenovo Asphalt firmware

[中文](README.zh.md)

This repository holds the 41 binary files currently used for the Lenovo Legion Y700 2023 (TB320FC, Asphalt). They were copied from [`nixos-android-devices` at `492e0c1`](https://git2.pardinus.net/dianqk/nixos-android-devices/src/commit/492e0c14a14ce9ecd7fdcb8c58b9c2db454b0b78/firmware). Paths match those original copies so they can be compared directly. The NixOS packages still read the copies in that repository; this repository is not yet a package input.

| Path | Files | Provenance | Use |
| --- | ---: | --- | --- |
| `lenovo/tb320fc/firmware` | 8 | Saved TB320FC Android firmware images | Touchscreen, Adreno GPU, video decoder |
| `lenovo/tb320fc/audio` | 29 | Saved TB320FC Android `modem_b` and `vendor` images | ADSP and CS35L45 speakers |
| `lenovo/tb320fc/wifi` | 1 | `board-2.bin` encoded from stock `qca6490/bdwlang.elf` | WCN6855 board data |
| `oneplus/negroni/WCN6855/hw2.1` | 3 | [Xlie-Electronic-Customs/linux-firmware-oplus-negroni at `5a4116c`](https://github.com/Xlie-Electronic-Customs/linux-firmware-oplus-negroni/tree/5a4116cd5eecebec5db4b4a85d4781dd1168e619/oplus-negroni/ath11k/WCN6855/hw2.1) | WCN6855 `amss.bin`, `m3.bin`, `regdb.bin` |

The original TB320FC ROM build identifier and full image hashes are unknown. `SHA256SUMS` identifies every included file exactly. The identical `spk1` and `spk2` CS35L45 `.wmfw` payload is stored once; the Nix package creates the second runtime name as a symlink. Device Wi-Fi/Bluetooth addresses are not included.

Verify the copy from this directory with `sha256sum -c SHA256SUMS`. The Lenovo source images and OnePlus collection supplied no verified redistribution grant for these selected files; their original owners retain their rights.
