# twrp_kernel_sony_voyager

- This is the stock kernel for the Sony XA2 Plus from https://developer.sony.com/develop/open-devices/downloads/open-source-archives with slight modifications to work with TWRP (https://twrp.me/).
- Original [README](../master/README) and [COPYING](../master/COPYING) notices.

## Compile
- https://source.android.com/setup/build/building-kernels
- Use [nile_defconfig](../master/arch/arm64/configs/nile_defconfig)
- For CAF kernels it's needed to set a separate output directory for `make`.
