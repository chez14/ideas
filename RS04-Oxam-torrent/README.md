## Oxam Torrent

Sekarang kalo deploy soal ujian ato file-file pendukung semua mesti manual, dan karna kirimnya sentralized, jadinya nunggu deploynya lama banget kalo buat file yang ukurannya 100MB keatas.

So dari sistem ini kelemahannya:

- Lemot (karna 1 server yang sibuk ngirim ke klien **SATU PER SATU**)
- Manual (Mesti execute file script satu per satu)
- Nggak ada yang cek error (kecuali nanti yang mau ujian)
- Permission problem (redacted for the sake of our security concerns)
- Form pengumpulan file ujian 
- Pengiriman jawaban yang mesti manual

So dari beberapa poin diatas, gw ngusulin buat pake sistem yang terintegrasi untuk tugas-tugas berikut:

- Masukin daftar anak untuk tiap ujian (format file excel/txt)
- Randomize tempat duduk anak yang ujian
- Generate Daftarnya (+ ngasih API biar BTI bisa ambil daftar tempat duduknya)
- Form permintaan file ujian
- Stopwatch yang terintegrasi untuk tiap ujian
- Pengiriman file ujian (Yang paling utamanya)
- Form pengumpulan file ujian (Known bug: "Waktu ujian telah habis")
- Permission problem (redacted)
- Pengiriman otomatis

Dari yang diatas, yang minor dan merepotkan beberapa udah diperbaiki, dan yang jadi problem utamanya itu pengiriman file ujian. (well kalo bisa gw bakal bikin semua jadi 1 benda)

Dari Analisis diatas, gw nemu caranya, pake torrent. Nah dari situ kita bakal butuh konfigurasi sbb:

- Server untuk seeder
- Server untuk tracker
- Client Agent untuk yang download, ngurusin permission, dan benda-benda lainnya yang urusannya menyangkut nasib ujian banyak orang.

Dari situ gw propose solusi ini akan dikerjakan dengan bahasa & plugin sbb:

- Server Torrent dan Tracker bakal di selesaikan dengan [Webtorrent](https://github.com/webtorrent), dengan Js.
- Client Agent bakal diselesaikan dengan C#, plugin torrent bisa pake [System.Net.Torrent](https://github.com/bizzehdee/System.Net.Torrent).
- Ujian management (pengumpulan, permintaan ujian) bisa selesai dengan PHP / Js.

Oleh karena itu gw bakal masuk ke bagian penelitian.

### Penelitian

Penelitian yang gw ambil sekarang bakal menentukan untuk mengkalkulasi apakah bisa diselesaikan pada saat skripsi. Penelitian yang diambil termasuk:

- Apakah prototype mini solusi dapat menyelesaikan masalah/meningkatkan peforma sebelumnya.
- Apakah solusi tersebut berpotensi memiliki bug yang fatal? Jika ya, list masalah tersebut, dan sebutkan solusinya.

Dari poin poin diatas, maka dibutuhkan data:

- Prototype program
- Data peforma lama:
  - Kecepatan untuk pendeployan file
  - Laporan keamanan (bug, as always: redacted)
- Data peforma baru:
  - Kecepatan pendeployan file
  - Laporan keamanan (solusi bug)
  - Kemugkinan bug yang dapat terjadi

Oleh karena itu pentingnya penelitian ini dilakukan karena sangat amat mempengaruhi jugdement gw untuk mengatasi masalah-masalah yang terjadi selama ujian berlangsung.

### Potensi dijadikan skripsi, dari sudut pandang gw

Software terintegrasi begini menurut gw bisa dijadikan skripsi karena bobot koding yang cukup berat, knowledge terhadap teknologi yang digunakan yang cukup tinggi, judgement potensi bug di masa yang akan datang, serta rumitnya sistem integrasi yang harus di rencakan, hingga diperlukannya penelitian semacem ini.

### Rencana

Dari sini gw berencana ngelakuin penelitian ini untuk 1 ruangan (kemudian 1 lab) selama lab sedang masa liburan (karena SP). Dari situ gw bakal butuh bikin prototyping.

Setiap penilian yang gw lakuin, bakal di log ke catetan di folder ini, mungkin gw bikin folder (?).

Selebihnya, biar waktu yang bantu gw improvise apa aja yang dibutuhin.