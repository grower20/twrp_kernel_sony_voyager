# twrp_kernel_sony_voyager
- This is the stock kernel for the Sony XA2 Plus (50.1.A.11.40) from https://developer.sony.com/develop/open-devices/downloads/open-source-archives with slight modifications to work with TWRP (https://twrp.me/).
- Original [README](../master/README) and [COPYING](../master/COPYING) notices.

## Compile
- https://source.android.com/setup/build/building-kernels
- Use [nile_defconfig](../master/arch/arm64/configs/nile_defconfig)
- For CAF kernels it's needed to use a separate output directory for `make`. E.g. `make O=foo ...`

### Using provided Docker image
- Build image: `docker build -t android_kernel_builder docker`
- Create and enter container (mount project dir to /build): `docker run --rm -ti -v `pwd`:/build android_kernel_builder`
- Build environment is preconfigured in the container
- Clean output directory: `[CONTAINER] cd /build && rm -r out`
- Load kernel config: `[CONTAINER] cd /build && make O=out nile_defconfig`
- Compile kernel: `[CONTAINER] cd /build && make O=out -j9` (Adjust `-j` for your CPU (Cores + 1))
- Exit build container
- New kernel is located at `arch/arm64/boot/Image.gz-dtb`
