# QPU

Quick Pemilihan Umum. A paperless voting solution.

This proposal is in Indonesian languages, if you do want to know, you can use Google Translate or make an issue.

## Abstrak

Voting dengan paper biasanya memakan biaya banyak, karena kita harus memprint kertas dan membeli beberapa peralatan lain. Paperless mungkin dapat jadi solusi, namun sistem yang selama ini ditemukan tidak efisien atau bahkan tidak aman. Oleh karena itu saya mencoba menawarkan proposal sistem voting paperless (lessnya maksudnya sedikit.).

## Kondisi

Sistem yang saya coba ajukan memiliki beberapa kondisi/standar sebelum dapat digunakan:

### Kondisi untuk Panitia

- Setiap spot memiliki komputer untuk pemilih yang terhubung ke internet (100KBps mungkin minimal, research dibutuhkan.)
- Setiap spot memiliki komputer untuk panitia spot tersebut, yang juga harus terhubung ke internet.
- Setiap komputer yang digunakan untuk memilih [secara opsional] membutuhkan barcode scanner (QR Scanner).
- Komputer untuk panitia Spot harus memiliki printer (thermal/lain lain).

### Kondisi untuk Pemilih

- Setiap pemilih harus memiliki KTM sebagai bukti resmi mereka mempunyai hak untuk memilih.

- Setiap memilih harus memiliki token sebagai tanda token tersebut adalah suara yang bersangkutan, **yang dapat diperoleh melalui**:

  - Handphone:

    Pemilih harus menginstall aplikasi QPU, melakukan registrasi, dan secara eksplisit meminta token.

  - Panitia Spot:

    Saat pemilih tidak dapat mengakses handphone karena satu dan lain hal, maka token harus disediakan oleh panitia, dengan syarat:

    - Harus dapat menunjukan bukti keberhakkan
    - Belum pernah menggenerate code lewat panitia sebelumnya (jika pernah, kami akan laporkan insiden ini ke panitia pusat sebagai bahan kajian, beserta attachment bukti insiden dan panitia yang bertanggung jawab.)



## Spesifikasi Keamanan

- Token: Token adalah kode OTP yang digenerate secara langsung untuk setiap user. Kode OTP tersebut memiliki Seeder yang unik untuk setiap pemilih. Kode OTP tersebut hanya akan berlaku 30 detik - 1 menit setiap kali request.
  - Token bersifat sekali pakai.
  - Saat terjadi conflict (pemilih sudah memilih sebelumnya), voting harus dilakukan dengan kode token yang digenerate oleh pihak panitia spot tersebut, setelah membuktikan keberhakkan dia untuk memilih.
  - Saat login, informasi yang diminta adalah NPM dan Kode Token.
  - NPM dan pilihan mahasiswa akan disimpan ke database. Ini sebagai pertanggungjawaban saat terjadi conflict, juga sebagai penanda bahwa mahasiswa tersebut sudah memilih.
  - **Saat terjadi conflict**, suara yang dihitung adalah suara yang terekam terakhir, dengan asumsi bahwa suara sebelumnya tidak valid karena pembuktian keberhakan untuk memilih tidak lebih tinggi dari verifikasi manual.
  - **Token yang digenerate oleh panitia** harus dilengkapi dengan validasi acak tentang data diri mereka. Hal ini dapat dibuktikan dengan secara acak memasukan data singkat (dipilih acak):
    - Kombinasi tanggal, bulan, dan tahun lahir.
    - Nama Orang Tua
    - Golongan Darah (digabung dengan yang lain)
    - Kota Lahir (digabung dengan yang lain)
    - Kota Tinggal (digabung dengan yang lain)
- Setiap panitia Spot akan memiliki informasi login, dan setiap berganti Shift, mereka harus berganti akunnya. Hal ini digunakan untuk memberikan informasi siapa saja yang bertanggung jawab pada setiap spot. Sehingga sewaktu waktu terjadi clash/conflict, keterangan pegenerate code dapat dilacak.
- Setiap komputer yang digunakan untuk memilih akan di authentikasi, authentikasi ini berguna untuk menyambungkan komputer panitia spot tersebut pada komputer pemilih. Digunakan untuk membatasi aktifnya kode token untuk pemilih. 

## Sistematika

TBA

## FAQ

TBA

## in a Nutshell

Pemilih akan memilih di komputer pemilih yang sudah di authentikasi oleh panitia untuk tracking validitas.

Pemilih yang tidak memiliki token akan di dibuatkan token oleh pantia. (Token seharusnya dapat ia peroleh sendiri lewat aplikasi QPU di HPnya).

Pemilih yang sudah memilih sebelumnya akan mengalami conflict. Conflict hanya dapat di resolve oleh pantia.

Panitia yang bertugas akan memiliki kode loginnya masing masing (lagi, digunakan untuk tracking validitas.)