# akomodasi_kintamani_2501010089

# Akuisisi Data Akomodasi di Kecamatan Kintamani

Tugas praktik BIFP-243 Akuisisi dan Manajemen Data.
Pengambil data: I Made Bagus Abiyoga Prawira (2501010089)

## Tujuan
Mengakuisisi data akomodasi (hotel, guest house, villa, dan sejenisnya) di Kecamatan Kintamani secara etis,
menyimpan respons mentah, mengubahnya menjadi dataset tabular terdokumentasi, dan menilai kelengkapannya
terhadap angka resmi BPS.

## Sumber data
- OpenStreetMap melalui Overpass API (https://overpass-api.de/api/interpreter), lisensi ODbL.
- Pembanding: BPS Kabupaten Bangli (BPS KINTAMANI, tahun 2024).

## Tanggal akses
2026-11-11T10:32:39.521966+00:00 (UTC)

## Metode akuisisi
Query Overpass (lihat docs/query_overpass.txt) dikirim dengan Python (requests) dengan timeout dan retry
exponential backoff. Respons mentah disimpan apa adanya di data/raw/, lalu diratakan menjadi
data/interim/akomodasi_kintamani.csv. Jumlah elemen: 32; baris dataset akhir: 32.

## Batasan etika
- Tidak memakai situs OTA, platform pemesanan, maupun halaman Google Maps.
- Tidak mengambil data kontak pribadi (telepon, email, media sosial).
- Batas pemakaian API dihormati; query dijalankan sangat terbatas.
- Data OSM diisi relawan sehingga tidak lengkap; hasilnya tidak boleh dianggap sensus akomodasi.

## Atribusi
Data (c) OpenStreetMap contributors, tersedia di bawah lisensi ODbL.

## Cara menjalankan ulang
1. Buka notebooks/akuisisi_akomodasi.ipynb di Google Colab.
2. Isi NIM dan NAMA di sel Setup.
3. Hapus berkas di data/raw/ (atau set FORCE_DOWNLOAD = True) kalau ingin mengambil data baru.
4. Runtime > Run all.
