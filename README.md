# Prebuilt kernel for Redmi Pad Pro (dizi)

Everything here is taken unmodified from dizi_eea OS3.0.303.0.WNSEUXM:

| File | Source |
|---|---|
| `Image` | `boot.img` kernel (GKI 5.10.246-android12-9, ab15159037) |
| `dtb/parrot.dtb` | `vendor_boot.img` dtb |
| `dtbo.img` | `dtbo.img` |
| `modules/vendor_ramdisk/` | `vendor_boot.img` ramdisk `lib/modules` |
| `modules/vendor_dlkm/` | `vendor_dlkm` partition `lib/modules` |

## Source-built kernel (Phase 6, stage a)

`Image-source` is built from LineageOS android_kernel_xiaomi_sm7435 lineage-23.2
(57dcedf23, plus the local fix ec878c862
"proc: bootconfig: Keep the skip label inside its #ifdef") with plain `gki_defconfig` and the
stock kernel's compiler, clang r416183b (`/build/alex/dizi/kernel/build-gki.sh`):
Linux 5.10.269. Its Module.symvers matches every symbol CRC, and `module_layout`, that the 377
stock modules import, so the stock dtb, dtbo and modules above are used unchanged.
Select it with `DIZI_SOURCE_KERNEL=true` (see BoardConfig.mk). The stock `Image` is the default.
