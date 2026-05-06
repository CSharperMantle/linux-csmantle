# linux-csmantle

AUR repo for *attended* compilation and packaging of Linux kernels.

"Attended" means that you are expected to monitor `menuconfig` during the process.

Patches are tracked in the respective branches at <https://github.com/CSharperMantle/linux-arch>. If you are interested in this repo, you may also want to checkout [my other AURs for LoongArch](https://github.com/CSharperMantle?tab=repositories&q=aur+loonggpu).

## Target platform

This repo is for personal use, so the patches and tunes are cherry-picked for my specific platform:

* **Platform:** Loongson-3B6000x1-7A2000x1-EVB
* **CPU:** Loongson-3B6000 (24) @ 2.20 GHz *(MB mounted)*
* **GPU:** AMD Radeon Pro WX 5100
* **NIC:**
  * MEDIATEK Corp. MT7925 (RZ717) Wi-Fi 7 160MHz
  * Motorcomm Microelectronics. YT6801 Gigabit Ethernet Controller (rev 01) *(MB mounted)*

## Variants

* **16kB (3 level) paging:** <https://github.com/CSharperMantle/linux-csmantle/tree/csmantle>
* **4kB (4 level) paging:** <https://github.com/CSharperMantle/linux-csmantle/tree/csmantle-4k>

## Acknowledgements

* <https://gitlab.archlinux.org/archlinux/packaging/packages/linux.git>
* <https://github.com/lcpu-club/loongarch-packages/tree/master/linux>
* <https://github.com/AOSC-Dev/aosc-os-abbs/tree/stable/runtime-kernel/linux-kernel>
