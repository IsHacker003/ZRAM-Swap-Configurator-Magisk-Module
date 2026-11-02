ZRAM Swap Configurator: Optional Settings

New to ZRAM? Start here: [What is ZRAM Swap?](what-is-zram-swap.md)
For full details, see the Android and Linux kernel docs.

This module is for advanced users. It makes no recommendations and enforces no limits, so you're responsible for what you set. If you don't know what a setting does, leave it alone.

HOW TO USE
1. Create /data/media/0/optionals.prop (replace 0 with your user ID if you're not the main user).
2. Add any settings below, one per line.
3. Install or reinstall the module, then reboot.

Any setting you leave out keeps your ROM/kernel default.

ZRAM
zram.resize   ZRAM size. Default 100% of RAM.
              Percent (75%, 150%), fixed size (768M, 4G), or 0 to disable.
zram.algo     Compression algorithm, if your kernel supports it.
              zstd (best ratio), lz4 (fastest), lzo, deflate.
zram.prio     Swap priority. Default 0.

VM
zram.swps     vm.swappiness (e.g. 60)
zram.mfkb     vm.min_free_kbytes (e.g. 32768)
zram.efkb     vm.extra_free_kbytes (e.g. 32768)
zram.swpre    vm.swap_ratio_enable, 1 or 0 (vendor kernels only)
zram.swpr     vm.swap_ratio (e.g. 90), needs zram.swpre=1

LOW MEMORY KILLER (unset by default; use "unset" to clear)
zram.sflp     swap_free_low_percentage (e.g. 12)
zram.sum      swap_util_max (e.g. 90)
zram.scr      swap_compression_ratio (e.g. 4)
zram.scrd     swap_compression_ratio_div (e.g. 2)
zram.med      medium (e.g. 900)
zram.low      low (e.g. 1000)

EXAMPLE optionals.prop
zram.resize=150%
zram.algo=zstd
zram.swps=100

NOTES
Not every ROM or kernel supports every setting. Unsupported ones are skipped.
On crDroid, RAM Plus overrides swap_free_low_percentage.

(mirrored from https://t.me/ryukinotes/6)
