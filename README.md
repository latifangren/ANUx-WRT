# ANUx-WRT

<p align="center">
  <img src="https://img.shields.io/badge/OPENWRT-00B7EB?style=for-the-badge&logo=openwrt&logoColor=white" alt="OpenWrt">
  <img src="https://img.shields.io/badge/IMMORTALWRT-FF6B35?style=for-the-badge&logo=openwrt&logoColor=white" alt="ImmortalWrt">
  <br>
  <img src="https://img.shields.io/badge/24.10.8-FF6B35?style=for-the-badge" alt="OpenWrt 24.10">
  <img src="https://img.shields.io/badge/25.12.5-00B7EB?style=for-the-badge" alt="OpenWrt 25.12">
  <br>
  <img src="https://img.shields.io/badge/IMAGEBUILDER-9C27B0?style=for-the-badge&logo=linux&logoColor=white" alt="ImageBuilder">
  <img src="https://img.shields.io/badge/STATUS-Active-brightgreen?style=for-the-badge" alt="Status">
</p>

---

<p align="center">
  <img src="https://img.shields.io/github/downloads/latifangren/ANUx-WRT/total?style=for-the-badge&logo=openwrt&labelColor=blue" alt="Downloads">
  <br>
  <a href="https://github.com/latifangren/ANUx-WRT">
    <img src="https://img.shields.io/badge/ANUxWRT-REPO-orange?style=for-the-badge&logo=github" alt="ANUxWRT REPO">
  </a>
  <a href="https://github.com/latifangren/ANUx-WRT/blob/main/LICENSE">
    <img src="https://img.shields.io/github/license/latifangren/ANUx-WRT?style=for-the-badge" alt="License">
  </a>
</p>

---

## 📌 Tentang ANUx-WRT

**ANUx-WRT** adalah firmware custom berbasis **OpenWrt** dan **ImmortalWrt** yang dirancang untuk kebutuhan konektivitas tinggi, tunneling VPN multi-protokol, dan manajemen modem 4G/5G modern. Dibangun menggunakan GitHub Actions ImageBuilder otomatis untuk puluhan perangkat (x86_64, TV Box Amlogic, Rockchip, Allwinner, dan Raspberry Pi).

---

## ✨ Fitur Unggulan

### 🎨 Antarmuka Modern & Cepat
* **Default Theme — [Footstrap](https://github.com/VizzleTF/luci-theme-footstrap)**: Antarmuka Single Page Application (SPA) yang 2× lebih cepat, responsif di HP/desktop, dan dilengkapi diagram visual **Network Topology & Client Path**.
* **Konsol Cerdas — [Vantage](https://github.com/anothaDev/luci-theme-vantage)**: Dilengkapi command palette (`Ctrl + K`), flyout sidebar, dan live status stasiun/sinyal dBm per-klien.
* **Tema Alternatif**: Didukung tema **Argon** ([jerrykuku](https://github.com/jerrykuku/luci-theme-argon)).

### 📶 Ekosistem Modem 4G/5G Terpadu
* Ditenagai oleh **[luci-app-5gmodem](https://github.com/fildunsky/luci-app-5gmodem)**:
  - Pembacaan sinyal real-time & **Carrier Aggregation (CA)** multi-band (misal `B1 + B3 + B40`).
  - **Lock Band** frekuensi LTE & 5G SA/NSA.
  - SMS Inbox, Kirim SMS, dan USSD terintegrasi.
  - Terminal AT Command langsung di web LuCI.
  - **Fix TTL / Hop-Limit** otomatis via `nftables` (fw4).
  - Peta BTS (Cell Tower Map) dan pembacaan sensor suhu modem.
  - Dukungan luas: Fibocom FM350-GL, Intel XMM (L850/L860 via `xmm-modem`), Snapdragon X55/X62/X20, Quectel, SIMCom, MeigLink, dll.

### 💾 Manajemen File & Diagnostik
* **File Manager**: **`luci-app-filebrowser`** — file manager web berbasis Go, hemat RAM (~15-25 MB), dengan web code editor untuk mengubah skrip dan konfigurasi YAML tanpa SSH. Tersedia di feed Kiddin9, tanpa bloatware PHP.
* **Diagnostik Jaringan**: `vnstat2` / `vnstati2` (feed resmi OpenWrt) untuk statistik trafik antarmuka, `luci-app-ramfree` untuk monitoring RAM, dan `luci-app-eqosplus` untuk manajemen bandwidth QoS per-klien.

### ⚡ Optimalisasi Kernel & Stabilitas Sistem
* **Google BBR** (`kmod-tcp-bbr`): Algoritma *congestion control* untuk koneksi VPN dan browsing yang jauh lebih responsif.
* **ZRAM ZSTD** (`zram-swap` + `kmod-lib-zstd`): Swap terkompresi agar router tidak mudah *Out-Of-Memory*.
* **Hardware Monitor** (`autocore`, basis ImmortalWrt): Pembacaan beban CPU dan suhu hardware di overview LuCI.
* **Web Server Tuning**: `uhttpd` *max concurrent requests* dinaikkan ke 20 dan `rpcd timeout` diperpanjang ke 120 detik untuk mencegah error *"Gateway Timeout"*.
* **Auto-Repair Filesystem** (`repair_ro`): Otomatis mendeteksi dan memperbaiki partisi ext4 yang terkunci *Read-Only* akibat router mati lampu mendadak.

### 🚀 Siap Multi-Tunnel
* Mendukung instalasi terintegrasi: **OpenClash (Mihomo Core)**, **Nikki (Zashboard UI)**, **PassWall**, **FusionTunX**, **Clashoo**, dan **Tailscale**.

---

## 🔑 Informasi Default Firmware

| Parameter | Setelan Default |
|---|---|
| **IP Address Gateway** | `192.168.1.1` |
| **Username Web LuCI / SSH** | `root` |
| **Password Web LuCI / SSH** | `root` |
| **Wi-Fi 2.4 GHz SSID** | `ANUx` |
| **Wi-Fi 5 GHz SSID** | `ANUx_5G` |
| **Wi-Fi Password** | `ANUx2026` |
| **Protokol Wi-Fi** | WPA2-PSK (AES) |

---

## 📟 Perangkat yang Didukung (Supported Devices)

<p align="center">
  <img src="https://img.shields.io/badge/OrangePi-FF6600?style=for-the-badge&logo=raspberrypi&logoColor=white" alt="Orange Pi">
  <img src="https://img.shields.io/badge/RaspberryPi-C51A4A?style=for-the-badge&logo=raspberrypi&logoColor=white" alt="Raspberry Pi">
  <br>
  <img src="https://img.shields.io/badge/NanoPi-00A859?style=for-the-badge&logo=raspberrypi&logoColor=white" alt="NanoPi">
  <img src="https://img.shields.io/badge/Amlogic-1976D2?style=for-the-badge&logo=microchip&logoColor=white" alt="Amlogic">
  <br>
  <img src="https://img.shields.io/badge/Rockchip-E91E63?style=for-the-badge&logo=microchip&logoColor=white" alt="Rockchip">
  <img src="https://img.shields.io/badge/Allwinner-FF9800?style=for-the-badge&logo=microchip&logoColor=white" alt="Allwinner">
  <br>
  <img src="https://img.shields.io/badge/X86-000000?style=for-the-badge&logo=windows&logoColor=white" alt="X86">
</p>

* **PC / Mini PC**: x86_64, x86 Generic.
* **Raspberry Pi**: Raspberry Pi 2B, 3B, 4B, 5.
* **TV Box / STB Amlogic**: S905X (B860H v1/v2, HG680P), S905X2 (B860H v5, HG680-FJ), S905X3, S905X4, S912, S922X, TX3 Mini, X96 Mini.
* **Rockchip**: NanoPi R2S, R3S, R4S, R5S, M5, Orange Pi 5 / 5B / 5 Plus, RK3328, RK3399.
* **Allwinner**: Orange Pi 3 / 3 LTS, Orange Pi Zero 2 / Zero 3, H5 Orange Pi Zero Plus.
* **Mangopi / Widora**: Mangopi M28C, M28K.

---

## 📖 Dokumentasi Teknis

* Pemetaan lengkap repositori & feed eksternal yang ditarik oleh builder ini dapat dibaca di:  
  👉 **[docs/EXTERNAL_REPOSITORIES.md](docs/EXTERNAL_REPOSITORIES.md)**

---

## 🤝 Credits & Acknowledgments

Proyek ini dibangun di atas karya, ide, dan kontribusi hebat komunitas Open Source:

* **[OpenWrt](https://openwrt.org)** & **[ImmortalWrt](https://immortalwrt.org)** — Fondasi sistem operasi router.
* **[de-quenx/XIDZs-WRT](https://github.com/de-quenx/XIDZs-WRT)** — Upstream repositori basis fork awal.
* **[fildunsky/luci-app-5gmodem](https://github.com/fildunsky/luci-app-5gmodem)** — Aplikasi modem 4G/5G serbabisa.
* **[VizzleTF/luci-theme-footstrap](https://github.com/VizzleTF/luci-theme-footstrap)** — Pengembang tema Footstrap SPA.
* **[anothaDev/luci-theme-vantage](https://github.com/anothaDev/luci-theme-vantage)** — Pengembang tema Vantage & live dashboard.
* **[jerrykuku/luci-theme-argon](https://github.com/jerrykuku/luci-theme-argon)** — Pengembang tema Argon LuCI.
* **[FileBrowser](https://github.com/filebrowser/filebrowser)** — File manager modern berbasis Golang.
* **[Kiddin9 / openwrt.ai](https://openwrt.ai)** — Penyedia feed paket pihak ketiga (`dl.openwrt.ai`).
* **[rizkikotet-dev/RTA-WRT](https://github.com/rizkikotet-dev/RTA-WRT)** — Builder RTA & skrip mod-boot-sdcard.
* **[frizkyiman/friWrt-MyWrtBuilder](https://github.com/frizkyiman/friWrt-MyWrtBuilder)** — Skrip `repair_ro` penyelamat filesystem ext4.
* **[Ophub](https://github.com/ophub)** — Kernel packaging dan toolchain STB Amlogic.
* **[syntax-xidz](https://github.com/syntax-xidz)** — ULO-Builder dan Amlogic s9xxx packaging.
* **[MetaCubeX](https://github.com/MetaCubeX)** — Core Mihomo & aset aturan GeoIP/GeoSite.

---

<p align="center">
  <img src="https://img.shields.io/badge/©-2026-blue?style=for-the-badge" alt="Copyright">
  <img src="https://img.shields.io/badge/ANUx-WRT-FF6B35?style=for-the-badge&logo=github&logoColor=white" alt="ANUx-WRT">
</p>
