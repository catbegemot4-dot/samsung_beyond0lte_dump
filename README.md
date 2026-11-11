# Samsung Galaxy S10e (`SM-G970F` / `beyond0lte`) Firmware Dump

Full stock firmware partition dump extracted from official Samsung firmware for **Samsung Galaxy S10e** (`SM-G970F`, Exynos 9820). Intended for Linux porting (`postmarketOS`, `Halium`, `Arch Linux ARM`) and custom ROM development.

---

## Firmware Metadata

| Parameter | Value |
| :--- | :--- |
| **Manufacturer** | Samsung |
| **Device Name** | Galaxy S10e |
| **Model** | `SM-G970F` |
| **Codename** | `beyond0lte` |
| **SoC / Platform** | Samsung Exynos 9820 (`exynos9820`) |
| **Architecture** | `arm64-v8a` (`aarch64`) |
| **Region / CSC** | `SEK` (`OXM` Multi-CSC) |
| **OS Version** | Android 11 (One UI 3.0) |
| **PDA / AP Version** | `G970FXXU9ETLJ` |
| **CSC Version** | `G970FOXM9ETLJ` |
| **Baseband / CP Version** | `G970FXXU9ETLJ` (`CP17827799`) |
| **Bootloader / BL Version** | `G970FXXU9ETLJ` (Binary / BIT `9`) |
| **Changelist** | `20607146` |
| **Build ID** | `QB37057163` |
| **A/B Partition Scheme** | `false` (A-only) |
| **Source Package** | `SAMFW.COM_SM-G970F_SEK_G970FXXU9ETLJ_fac` |

---

## Repository Structure

* `boot/` & `boot.img` — Unpacked kernel, ramdisk, and raw boot partition image.
* `recovery/` & `recovery.img` — Unpacked recovery ramdisk and raw recovery image.
* `dtbo.img` — Device Tree Blob Overlay image.
* `system/` — Full `/system` partition root filesystem.
* `vendor/` — Proprietary HAL libraries, firmware blobs (`/vendor/firmware`), and init scripts.
* `product/` — `/product` partition contents.
* `all_files.txt` — Complete list of extracted files and paths.

---

## Reassembling Split Files

Due to GitHub's 100 MB file size limit, files exceeding 95 MB (such as large APKs in `system/system/priv-app/`) are split into `.part00`, `.part01`, etc.

To reassemble them after cloning:

```bash
find . -name '*.part00' -exec sh -c 'cat "${1%.part00}".part* > "${1%.part00}"' _ {} \;
```

---

## Related Repositories

* **Standalone Linux Firmware Blobs (`postmarketOS` / `Arch Linux ARM`):** `catbegemot4-dot/firmware-samsung-beyond0lte`

---

## Disclaimer & Licensing

All binary files, libraries, and firmware images in this repository are the proprietary intellectual property of **Samsung Electronics Co., Ltd.** and respective third-party hardware vendors (Broadcom, ARM, etc.). Provided strictly for interoperability, research, and open-source OS porting purposes.
