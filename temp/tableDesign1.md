## kelompokPengguna

**tabel kelompokPengguna**
name | type | desc
-----|------|-----
\_id | | `String` | keterangan ...
kelompok | `String` | keterangan ...
nama | | `String` | keterangan ...

<!-- **contoh data**									 -->

| \_id | kelompok | nama |     |     |           |     |
| ---- | -------- | ---- | --- | --- | --------- | --- |
| 1    |          | 0    |     |     | karyawan  |     |
| 2    |          | 0    |     |     | pasien    |     |
| 3    |          | 1    |     |     | medis     |     |
| 4    |          | 1    |     |     | non medis |     |
| 5    |          | 3    |     |     | perawat   |     |
| 6    |          | 3    |     |     | doktor    |     |

## Level Pengguna

**tabel level pengguna**
name type desc
  
\_id `String`   
levelPengguna `String`   

**contoh data**
\_id levelPengguna
1 administrator
2 direktur
3 kasi
4 kabag
5 koordinator
6 pelaksana
7 non struktural

## pengguna

**tabelPengguna**
name type desc
\_id `String` keterangan ...
kelompokPenggunaId `String` ref ke `kelompokPengguna._id` ...
levelPengguna `String` ref ke `levelPengguna._id` ...
nama `String`
tanggalLahir `Date`
tempatLahir `String`
saldoAwal `Number`
saldoAkhir `Number`
**contoh data**
\_id levelPengguna nama tanggalLahir tempatLahir saldoAwal saldoAkhir
1 administrator andi 2020/10/10 pacitan 0 0

## Propinsi

**tabelPropinsi**
name type desc
\_idPropinsi `String` Kode Propinsi sesuai Permendagri
namaPropinsi `String`
**contoh data**
\_idPropinsi namaPropinsi
35 Jawa Timur
##Kabupaten / Kota
**tabelKabKota**
name type desc
\_idKabKota `String` Kode Kabupaten / Kota sesuai Permendagri
\_idPropinsi `String` ref ke tabelpropinsi.\_idPropinsi
namaKabKota `String`
**contoh data**
\_idKabKota \_idPropinsi namaKabKota
1 35 pacitan
2 35 ponorogo
3 35 trenggalek
##Kecamatan
**tabelKecamatan**
name type desc
\_idKecamatan `String` Kode kecamatan sesuai Permendagri
\_idKabKota `String` ref ke tabelKabKota.IdKabKota
namaKecamatan `String`
**contoh data**
\_idKecamatan \_idKabKota namaKecamatan
1 1 donorojo
2 1 punung
3 1 pringkuku
4 1 pacitan
##Kelurahan
**tabelKelurahan**
name type desc
\_idKelurahan `String` kode kelurahan sesuai permendagri
\_idKecamatan `String` ref ke tabelKecamatan.\_idKecamatan
namaKelurahan `String`
**contoh data**
\_idKelurahan \_idKecamatan namaKelurahan
1001 4 sidoharjo
1002 4 ploso
1003 4 kembang
##COA level 1
**tabel klasifikasi akun**
name type desc
\_idKlasifikasi `String` keterangan ...
klasifikasi `String` keterangan ...
level `String` keterangan ...
saldoNormal `String` keterangan ...
**contoh data**
\_id Klasifikasi level saldoNormal
1 Aktiva 1 Debet
2 Hutang 1 Kredit
3 Modal 1 Kredit
4 Pendapatan Usaha 1 Kredit
5 Beban Usaha 1 Debet
6 Pendapatan Lain 1 Kredit
7 Beban Lain 1 Debet
##COA level 2
**tabel subKlasifikasi1**
name type desc
\_idLevel2 `String` PK tabel akun akuntansi
klasifikasiId `String` ref ke tabel klasifikasi akun
namaAkun `String`
level `String`
