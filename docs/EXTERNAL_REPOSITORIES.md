# Daftar Repositori & Ketergantungan Eksternal (External Dependencies)

Dokumen ini memetakan seluruh repositori, feed, API, dan sumber daya eksternal yang saat ini digunakan dan ditarik oleh sistem builder **ANUx-WRT**.

---

## 1. Paket Tema & Plugin LuCI (GitHub Releases API)

Ditarik secara otomatis saat proses build (`compile/build-tools.sh` pada fungsi `run_packages`).

| Paket | Repositori GitHub Asal | Deskripsi & Kegunaan |
|---|---|---|
| `luci-theme-footstrap` | [`VizzleTF/luci-theme-footstrap`](https://github.com/VizzleTF/luci-theme-footstrap) | **Tema default utama** ANUx-WRT: SPA navigation, diagram network topology, support 24.10 (`.ipk`) & 25.12 (`.apk`). |
| `luci-theme-vantage`<br>`luci-app-vantage` | [`anothaDev/luci-theme-vantage`](https://github.com/anothaDev/luci-theme-vantage) | Tema konsol modern dengan live dashboard status Wi-Fi/klien, command palette (Ctrl+K), support 24.10 & 25.12. |
| `luci-theme-argon` | [`jerrykuku/luci-theme-argon`](https://github.com/jerrykuku/luci-theme-argon) | Tema klasik populer OpenWrt dengan custom background login. |
| `luci-theme-luxe` | [`de-quenx/luci-theme-luxe`](https://github.com/de-quenx/luci-theme-luxe) | Tema modern flat alternatif buatan de-quenx. |
| `luci-app-5gmodem` | [`fildunsky/luci-app-5gmodem`](https://github.com/fildunsky/luci-app-5gmodem) | Pengelola lengkap modem 4G/5G: cek sinyal, carrier aggregation, lock band frekuensi, SMS, USSD, AT terminal, fix TTL. |
| `luci-app-tailscale` | [`asvow/luci-app-tailscale`](https://github.com/asvow/luci-app-tailscale) | Antarmuka LuCI untuk VPN mesh Tailscale. |
| `luci-app-eqosplus` | [`sirpdboy/luci-app-eqosplus`](https://github.com/sirpdboy/luci-app-eqosplus) | Manajemen bandwidth QoS IP per-klien. |
| `luci-app-amlogic` | [`ophub/luci-app-amlogic`](https://github.com/ophub/luci-app-amlogic) | Tool backup, restore, dan kernel upgrade khusus TV Box Amlogic. |
| `luci-app-lite-watchdog` | [`4IceG/luci-app-lite-watchdog`](https://github.com/4IceG/luci-app-lite-watchdog) | Watchdog ping auto-reboot koneksi modem jika internet terputus. |
| `luci-app-temp-status` | [`de-quenx/kwrt-packages`](https://github.com/de-quenx/kwrt-packages) | Menampilkan suhu CPU/SoC di navbar LuCI. |
| `luci-app-netmonitor` | [`de-quenx/luci-app-netmonitor`](https://github.com/de-quenx/luci-app-netmonitor) | Visualisasi grafik traffic data real-time berbasis VnStat. |
| `luci-app-ttl` | [`de-quenx/custom-x`](https://github.com/de-quenx/custom-x) | Modul fix TTL via LuCI untuk bypass kuota tethering hotspot. |
| `luci-app-ipinfo` | [`de-quenx/luci-app-ipinfo`](https://github.com/de-quenx/luci-app-ipinfo) | Widget pengecekan IP publik & nama ISP di homepage LuCI. |
| `ookla-speedtest` | [`de-quenx/kwrt-packages`](https://github.com/de-quenx/kwrt-packages) | Binary resmi Ookla Speedtest CLI multi-arsitektur. |
| `luci-app-poweroffdevice`| [`de-quenx/luci-app-poweroffdevice`](https://github.com/de-quenx/luci-app-poweroffdevice) | Tombol shutdown perangkat router dari menu LuCI. |

---

## 2. Core Tunneling & VPN (GitHub Releases)

Ditarik dinamis sesuai opsi tunnel yang dipilih pada GitHub Actions dispatch:

| Komponen | Repositori GitHub Asal | Deskripsi |
|---|---|---|
| **Mihomo (Clash.Meta Core)** | [`MetaCubeX/mihomo`](https://github.com/MetaCubeX/mihomo) | Core engine untuk OpenClash, Nikki, dan FusionTunX. |
| **OpenClash** | [`Yogxx/OpenClash`](https://github.com/Yogxx/OpenClash) | Client proxy rule-based OpenClash untuk OpenWrt. |
| **Nikki** | [`Yogxx/OpenWrt-nikkiku`](https://github.com/Yogxx/OpenWrt-nikkiku) | Client Mihomo modern untuk OpenWrt. |
| **Zashboard** | [`Zephyruso/zashboard`](https://github.com/Zephyruso/zashboard) | Web dashboard UI resmi untuk Nikki. |
| **PassWall** | [`Openwrt-Passwall/openwrt-passwall`](https://github.com/Openwrt-Passwall/openwrt-passwall) | Client proxy multi-protokol (VLESS, VMess, Trojan, Hysteria). |
| **FusionTunX** | [`bobbyunknown/FusionTunX`](https://github.com/bobbyunknown/FusionTunX) | Client tunnel Mihomo buatan BobbyUnknown. |
| **Clashoo** | [`kenzok8/openwrt-clashoo`](https://github.com/kenzok8/openwrt-clashoo) | Client tunnel alternatif berbasis Clash. |
| **Qtun** | [`de-quenx/luci-app-qtun`](https://github.com/de-quenx/luci-app-qtun) | Tunneling client Qtun. |
| **Passwall-SSH** | [`de-quenx/Passwall-SSH`](https://github.com/de-quenx/Passwall-SSH) | Modul SSH tunnel khusus Passwall. |

---

## 3. Driver Modem ATC (Direct GitHub Contents)

* **Repositori**: [`de-quenx/openwrt`](https://github.com/de-quenx/openwrt) (folder `atc/`)
* **File yang ditarik**:
  - `luci-proto-atc`: Protokol interface AT Command untuk dial-up modem Fibocom.
  - `atc-fib-l8x0_gl`: Profil modem Fibocom Intel XMM L850 / L860.
  - `atc-fib-fm350_gl`: Profil modem 5G Fibocom FM350-GL MediaTek.

---

## 4. Skrip Terminal CLI (`contenx`)

* **Repositori Target**: [`latifangren/contenx`](https://github.com/latifangren/contenx)  
  *(Fallback otomatis ke `syntax-xidz/contenx` jika repo belum di-fork)*
* **File yang ditarik**:
  - `xcli/syntax` ➔ `/usr/bin/syntax`: Tampilan banner info CPU, RAM, suhu, dan IP saat login SSH terminal.
  - `xcli/x-gpio` ➔ `/usr/bin/x-gpio`: Kontrol indikator LED koneksi internet STB HG680P & B860H.
  - `xcli/x-gpioled` ➔ `/usr/bin/x-gpioled`: Driver GPIO LED kernel Linux untuk STB Amlogic.
  - `xcli/xdev` ➔ `/usr/bin/xdev`: Menu interaktif terminal untuk pasang tools & tunnel tambahan.
  - `xcli/xidz` ➔ `/usr/bin/xidz`: Engine Telegram Bot remote control router.
  - `xcli/xidzs` ➔ `/etc/init.d/xidzs`: Procd service untuk menjalankan bot Telegram di background.
  - `xmodem/QModem-*.zip`: Tool QModem rakitan *(opsional / dinonaktifkan)*.

---

## 5. Tooling Repack Firmware (Amlogic TV Box & ULO)

Hanya diunduh saat mem-build target firmware berarsitektur khusus (STB TV Box / ULO):

| Tool | Repositori GitHub Asal | Kegunaan |
|---|---|---|
| **Amlogic Repack Tool** | [`syntax-xidz/amlogic-s9xxx-openwrt`](https://github.com/syntax-xidz/amlogic-s9xxx-openwrt) | Tool pengemasan kernel Linux Amlogic untuk TV Box (S905X, S905X2, S905X3, S905X4, B860H, HG680P) berbasis script Ophub. |
| **ULO Builder** | [`syntax-xidz/ULO-Builder`](https://github.com/syntax-xidz/ULO-Builder) | Builder image untuk arsitektur Allwinner H5/H6/H616/H618 (Orange Pi Zero, 3 LTS, dll) berbasis ULO DB-AI. |
| **Mod Boot SDCARD** | [`rizkikotet-dev/mod-boot-sdcard`](https://github.com/rizkikotet-dev/mod-boot-sdcard) | Skrip injeksi bootloader u-boot khusus STB B860H / HG680P agar bisa booting langsung lewat MicroSD card. |

---

## 6. Feed Repositori Paket Eksternal (Package Mirrors)

Digunakan oleh ImageBuilder untuk mengunduh paket binary terkompilasi (.ipk / .apk):

* **Kiddin9 Feed (`dl.openwrt.ai`)**:  
  `https://dl.openwrt.ai/releases/${VEROP}/packages/${ARCH_3}/kiddin9`  
  *Penyedia paket `filebrowser`, `luci-app-filebrowser`, `kmod-tcp-bbr`, `kmod-lib-zstd`, `autocore`, dll.*
* **OpenWrt Official Releases**:  
  `https://downloads.openwrt.org/releases/packages-${VEROP}/${ARCH_3}`
* **ImmortalWrt Official Releases**:  
  `https://downloads.immortalwrt.org/releases/packages-${VEROP}/${ARCH_3}`
* **Russian Modem Feed (`openwrt.132lan.ru`)**:  
  `https://openwrt.132lan.ru/packages/${VEROP}/packages/${ARCH_3}/modemfeed`  
  *Penyedia paket `xmm-modem` dan `luci-proto-xmm` untuk OpenWrt 25.12.*
* **gSpotx2f Packages Mirror**:  
  `https://github.com/gSpotx2f/packages-openwrt/raw/refs/heads/master/current`
* **Dllkids Mirror**:  
  `https://op.dllkids.xyz/packages/${ARCH_3}`

---

## 7. Database GeoIP & Rule Filtering (Tunnel Asset)

File binary offline yang sudah tersimpan di direktori `compile/files/etc/`:

* **GeoIP / GeoSite Database**: [`MetaCubeX/meta-rules-dat`](https://github.com/MetaCubeX/meta-rules-dat) dan [`Loyalsoldier/geoip`](https://github.com/Loyalsoldier/geoip).
* **AdBlock YAML Rules**: [`hillz2/openclash_adblock`](https://raw.githubusercontent.com/hillz2/openclash_adblock/main/oisd_small.yaml).
* **Domain Community Rules**: [`v2fly/domain-list-community`](https://github.com/v2fly/domain-list-community).
