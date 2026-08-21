# 🦅 Manuk Bulan Toolset

**Ultimate PS2 Modding Kit untuk God Hand & Resident Evil 4 (Game lain mendatang)**

Sebuah *toolset* komprehensif, cerdas, dan otomatis untuk melakukan ekstraksi (*Unpack*) dan pengemasan kembali (*Repack*) berbagai format arsip dari game **God Hand (PS2)** dan **Resident Evil 4 (PS2)**. Dikembangkan khusus untuk mempermudah alur kerja *modding* dengan dukungan antarmuka Command Line (CLI) dan *Drag & Drop* yang praktis.

---

## 🌟 Fitur Utama

*   **🧠 Smart Hex Detection:** Secara otomatis mendeteksi dan mengoreksi ekstensi file berdasarkan *hex signature* atau *header* aslinya (misal: otomatis mengenali `.BIN` sebagai `.TM2`, `.T32`, `.SLD`, `.EST`, `.MOD`, dll).
*   **📂 Recursive Batch Unpack:** Mampu memindai dan mengekstrak file yang bersarang di dalam file lain hingga ke akarnya secara otomatis.
*   **🏗️ Bottom-Up Batch Repack:** Fitur pintar untuk melakukan *repack* masal beruntun dari susunan folder terdalam hingga terluar, memastikan arsip modifikasi Anda terbungkus aman tanpa *error*.
*   **⚡ Hybrid Batch Scripts (.bat):** Dilengkapi dengan kumpulan *script* pendamping fungsional ganda:
    *   **Klik 2x (Double-Click):** Menyapu (*scan*) seluruh folder untuk memproses semua format secara otomatis.
    *   **Seret & Lepas (Drag & Drop):** Memproses satu file spesifik secara instan.
*   **🎯 Akurasi 1:1 Original:** Algoritma penyelarasan (*alignment*) dan *padding* (termasuk *padding* khas RE4) yang didesain secara presisi untuk memastikan struktur file *repack* identik dengan arsip original, sehingga terhindar dari *freeze* di dalam game.

---

## 🎮 Format yang Didukung

### 👊 God Hand (PS2)
*   `.BIN` *(Binary Archive)*
*   `.D` *(Data Archive)*
*   `.DA` *(Data Archive)*
*   `.DAT` *(Data Archive)*
*   `.EFF` *(Effect File)*
*   `.EFM` *(Effect Model)*
*   `.EMD` *(Enemy/Entity Model Data)*
*   `.I` *(Interface/Image Archive)*
*   `.ID` *(ID Data Archive)*
*   `.IDD` *(ID Data)*
*   `.PAC` *(Package Archive)*
*   `.SCP` *(Script/Screen Data)*
*   `.TBL` *(Table Data)*
*   `.TM3` *(Texture Data - Includes Name/Header Fix)*

### 🧟 Resident Evil 4 (PS2)
*   `.DAT` *(Core Archive)*
*   `.BIN` *(3D Mesh Data)*
*   `.TPL` *(Texture Splitter & Merger)*

---

## 🚀 Panduan Penggunaan

*Tool* ini sangat fleksibel dan dapat digunakan melalui 3 cara berbeda:

### 1. Mode Drag & Drop (Paling Direkomendasikan)
Cara termudah menggunakan *tool* ini adalah menggunakan file `.bat` yang telah disediakan. Pastikan file `.bat` berada di folder yang sama dengan `manukbulan_toolset_v1.00.exe`.
1. Tarik file asli (contoh: `pl00.dat`) ke file **`GH_Unpack_DAT.bat`** (untuk God Hand) atau **`RE4_Unpack_DAT.bat`** (untuk RE4).
2. Setelah diedit, tarik file manifest `.txt` hasil ekstrak ke file **`GH_Repack_DAT.bat`** atau **`RE4_Repack_DAT.bat`**.

### 2. Mode Auto-Batch (Pemrosesan Massal)
Sangat berguna jika Anda ingin mengekstrak atau membungkus ulang puluhan file sekaligus di dalam satu direktori.
*   **Unpack Semua:** Klik 2x pada `GH_01_Unpack_SEMUA_Otomatis.bat` (Otomatis menyapu hingga ke *sub-folder*).
*   **Repack Semua:** Klik 2x pada `GH_02_Repack_SEMUA_Otomatis.bat` (Otomatis mem- *build* dari dalam ke luar).

### 3. Mode Command Line (CLI)
Bagi *Power User*, *tool* ini mendukung perintah CLI dengan format: `exe -<engine> -<mode> -<format> <target> [-o]`

**Engine Flags:**
*   `-gh` (God Hand)
*   `-re4` (Resident Evil 4)

**Contoh Perintah:**
```bash
# Unpack satu file EMD God Hand
manukbulan_toolset_v1.00.exe -gh -u -emd pl00.emd

# Repack RE4 DAT menjadi file baru (default)
manukbulan_toolset_v1.00.exe -re4 -r -dat pl00.txt -n

# Repack RE4 TPL dan TIMPA (Overwrite) file asli
manukbulan_toolset_v1.00.exe -re4 -r -tpl pl00.txt -o

# Batch Unpack semua file RE4 di dalam folder saat ini
manukbulan_toolset_v1.00.exe -re4 -u
