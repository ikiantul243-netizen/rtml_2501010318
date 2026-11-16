Akuisisi Data Rumah Adat dan Arsitektur Tradisional Nusa Tenggara Timur
1. Identitas Proyek
- Mata kuliah: Akuisisi dan Manajemen Data (BIFP-243)
- Judul: Akuisisi Data Rumah Adat dan Arsitektur Tradisional Nusa Tenggara Timur
- Nama: [Mikael Gunawan Antul]
- NIM: [2501010318]
- Program studi: Informatika, INSTIKI
- Cakupan wilayah: Provinsi Nusa Tenggara Timur
- Format dataset: CSV dan JSON
2. Sumber Data
Dataset awal ini disusun dengan merujuk pada dokumen publik pemerintah berjudul Data Daya Tarik Wisata Provinsi Nusa Tenggara Timur.
- Penerbit/sumber: Pemerintah Provinsi Nusa Tenggara Timur dan instansi daerah yang dicantumkan dalam dokumen.
- Tahun dokumen: 2016.
- URL sumber: https://ppidutama.nttprov.go.id/storage/dokumen/WDacFPO6HVIKeTNP9FxTCVRWQwbGl2b9LXzJZIEZ.pdf
- Tanggal dan jam akses: [16 november 2026 jam 15:35]
- Jenis sumber: Dokumen PDF publik, bukan endpoint API.
Catatan penting: Berkas yang tersedia saat ini merupakan dataset awal hasil penataan informasi dari dokumen PDF. Proses ini bukan pengambilan melalui API atau web scraping. Oleh karena itu, README ini tidak menyatakan bahwa persyaratan metode API/scraping pada Tugas 1 telah terpenuhi. Jika tugas akhir wajib menggunakan API atau scraping, lakukan proses akuisisi tersebut dari sumber yang mengizinkan dan dokumentasikan prosesnya secara terpisah.
3. Metode Akuisisi dan Batasan
Informasi yang relevan dengan rumah adat/arsitektur tradisional diidentifikasi dari dokumen sumber, kemudian disusun menjadi baris dan kolom terstruktur.
- Metode pada dataset awal: ekstraksi/penataan informasi dari dokumen PDF publik.
- Endpoint API: tidak ada.
- Halaman dan selector scraping: tidak ada.
- Robots.txt: tidak berlaku untuk proses penataan dokumen PDF ini.
- Lisensi/ketentuan: periksa ketentuan penggunaan yang melekat pada dokumen dan situs penerbit sebelum mendistribusikan ulang. Cantumkan atribusi sumber.
- Data pribadi: dataset ini tidak ditujukan untuk mengumpulkan nama pribadi, nomor telepon, alamat email, foto individu, atau akun media sosial pribadi.
- Batasan: dokumen bersumber dari tahun 2016 sehingga tidak dapat dianggap sebagai inventaris terkini. Ejaan nama dan rincian lokasi perlu dicocokkan kembali dengan dokumen asli.
Jika proses berikutnya memakai API atau scraping, dokumentasikan endpoint/halaman, parameter atau selector, User-Agent, timeout, penanganan status code, jeda minimal satu detik antar-request, hasil pemeriksaan izin, dan tanggal/jam akuisisi.
4. Isi Dataset
Berkas dataset awal:
- data/raw/rumah_adat_ntt_data_awal.csv
- data/raw/rumah_adat_ntt_data_awal.json
Dataset awal berisi 58 record dan 10 kolom. Jumlah ini belum memenuhi target minimal 100 record pada petunjuk Tugas 1. Jangan menggandakan record atau membuat data yang tidak didukung sumber untuk mengejar target.
Kolom	Penjelasan
id_sumber	Kode atau penanda baris yang dicatat pada dataset. Kode FT merupakan penanda baris untuk entri yang tidak memiliki kode sumber yang terlihat.
nama_objek	Nama rumah adat atau objek arsitektur tradisional sebagaimana dicatat/diringkas dari sumber.
kabupaten_kota	Kabupaten/kota di Nusa Tenggara Timur.
kecamatan	Kecamatan jika tersedia pada sumber.
desa_kelurahan	Desa/kelurahan jika tersedia pada sumber.
kategori	Kategori kerja untuk rumah adat/arsitektur tradisional.
keterangan_sumber	Catatan tambahan untuk mempertahankan konteks entri.
sumber	Judul dokumen rujukan.
tahun_sumber	Tahun dokumen sumber, yaitu 2016.
url_sumber	URL dokumen sumber.


Kolom yang tidak tersedia pada sumber dibiarkan kosong. Sebagian entri menunjukkan lokasi/objek rumah adat, bukan selalu tipe rumah adat yang berbeda. Karena itu, jumlah record tidak boleh ditafsirkan sebagai jumlah 58 jenis rumah adat yang berbeda.
5. Struktur Folder
Susunan folder repository yang disarankan:
rtm1_NIM/
├── notebooks/
│   └── akuisisi_rumah_adat_ntt.ipynb
├── data/
│   └── raw/
│       ├── rumah_adat_ntt_data_awal.csv
│       └── rumah_adat_ntt_data_awal.json
├── docs/
│   ├── provenance.json
│   └── data_ethics_checklist.csv
└── README.md
Ganti NIM dengan NIM mahasiswa. Pastikan nama file di repository sama dengan nama file yang benar-benar tersedia.
6. Cara Membuka Dataset
Membuka CSV dengan Python
import pandas as pd

df = pd.read_csv("data/raw/rumah_adat_ntt_data_awal.csv")

print("Jumlah record:", len(df))
print("Jumlah kolom:", len(df.columns))
display(df.head())
Membuka JSON dengan Python
import json

with open(
    "data/raw/rumah_adat_ntt_data_awal.json",
    "r",
    encoding="utf-8"
) as file:
    data = json.load(file)

print("Jumlah record:", data["jumlah_record"])
print("Status:", data["status"])
Menjalankan di Google Colab
1. Unggah file CSV dan JSON ke Google Colab, atau simpan keduanya pada folder Google Drive proyek.
2. Jika menggunakan Google Drive, hubungkan Drive melalui google.colab.drive.mount.
3. Sesuaikan path file pada kode Python.
4. Jalankan sel notebook dari atas ke bawah.
5. Periksa jumlah record, nama kolom, dan beberapa contoh data.
6. Simpan notebook dengan seluruh output yang diperlukan.
7. Status dan Pekerjaan yang Masih Harus Diselesaikan
Sebelum dikumpulkan sebagai Tugas 1, lakukan hal berikut:
- [ ] Verifikasi seluruh nama objek dan lokasi terhadap dokumen sumber.
- [ ] Catat tanggal dan jam akses sumber yang sebenarnya.
- [ ] Tentukan sumber dan metode API atau web scraping yang diizinkan sesuai instruksi dosen.
- [ ] Lakukan akuisisi yang dapat diulang dan upayakan minimal 100 record dari satu sumber, tanpa data rekaan atau duplikasi.
- [ ] Simpan data mentah hasil akuisisi ke folder data/raw/.
- [ ] Buat provenance.json berdasarkan file final, termasuk ukuran file dan hash MD5 yang dihitung dari file tersebut.
- [ ] Isi 9 butir data_ethics_checklist.csv sesuai Modul 04 dan sertakan bukti.
- [ ] Pastikan notebook dapat dijalankan ulang dari awal dan tidak memuat API key.
- [ ] Periksa kembali struktur folder dan unggah repository/ZIP ke ELSA INSTIKI.
Status dataset saat ini: DATA AWAL, 58 record. Belum memenuhi target minimal 100 record dan belum membuktikan akuisisi melalui API atau web scraping.
