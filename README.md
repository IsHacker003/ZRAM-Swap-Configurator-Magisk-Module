# ZRAM Swap Configurator Magisk Module

## Description

- Enables ZRAM swap and resizes it to 100% of RAM by default
- Want to tweak it? See [Optionals](#optionals)
- New to ZRAM? Read [What is ZRAM Swap?](Docs/what-is-zram-swap.md), or the Android and Linux kernel docs for the full picture

> [!WARNING]
> This module is for advanced users. It makes no recommendations and enforces no limits, so you're responsible for what you set. If you don't know what ZRAM is, don't use it. Use at your own risk.

## Requirements

Magisk, Kitsune Mask, KernelSU or APatch

## Installation

1. Download the latest zip from [Releases](https://github.com/IsHacker003/ZRAM-Swap-Configurator-Magisk-Module/releases).
2. Install it from your root manager app, or from recovery if you use Magisk or Kitsune Mask.
3. Reboot. Changes to `/proc/sys/vm/` and LMK settings apply without a reboot.
4. Tap **Action** (or run `action.sh`) to see the results.

## Optionals

See [Docs/zram-configurator.md](Docs/zram-configurator.md).

## Bug Reports

Open an issue using the bug report template. Reports missing the required logs may be closed.

## Changelog

### v3.7
- Fix swappiness failing to set at boot on some ROMs

### v3.6
- Stop setting swappiness to 100 by default
- Add optionals to unset LMK values that are set by default

### v3.5
- Add `zram.scrd` and `zram.low` optionals
- Prefer `persist.device_config.lmkd_native.` over `ro.lmk.` when supported

### v3.4
- Add `zram.med` optional
- Fix logic for storing default values when they don't exist yet
- Remove unneeded files

### v3.3
- Apply ZRAM without waiting for boot completion, fixing lag on boot
- Remove `zram.fix` optional

### v3.2
- Store default values in `/data/adb/modules/$MODID/debug.log` if they don't exist yet

### v3.1
- Retry `swapoff` up to 20 times
- Fix `swapon` failing
- Show `/proc/swaps`
- Restore `swap_*` values without a reboot when optionals are `def` or unset

### v3.0
- Add BOOTMODE detection
- Add parameter support detection
- `swap_free_low_percentage`, `swap_util_max` and `swap_compression_ratio` changes no longer need a reboot
- Restore defaults without a reboot when optionals are `def` or unset
- Remove loop service
- Reset module folder/file permissions at post-fs-data
- Move `_uninstall.log` to `/data/adb/logs/`

### v2.9
- Fix percentage-based swap sizing
- Retry up to 10 times if `swapoff` fails
- Set ZRAM size to 100% of RAM by default
- Only set swappiness by default, leave other swap settings alone
- Add new optionals

### v2.8
- Add a new optional
- Stop changing `swap_ratio_enable` and `swap_ratio` by default
- `zram.swpr` now requires `zram.swpre=1`
- Set `swap_compression_ratio` to 0 by default

## Credits

- Original module by [reiryuki](https://github.com/reiryuki)
- https://t.me/androidryukimodsdiscussions
- https://t.me/androidappsportdevelopment
