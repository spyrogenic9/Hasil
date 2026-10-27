$ node uji.js
node uji_tahap2.js
node uji_tahap2_kondisional.js
node uji_representasi.js

node percobaan_tahap2.js 10
node percobaan_tahap2_kondisional.js 10
node percobaan_representasi.js 10
Mesin langkah
  ok   cara dasar tambah benar untuk semua a,b 0..10 dan biayanya 3b+2 (1 ms)
  ok   pengulangan tanpa pengurang berhenti oleh batas langkah, bukan menggantung (0 ms)
Pencarian cara
  ok   dari kasus saja ditemukan cara dasar tambah pada ukuran 4 (7 ms)
  ok   pada ukuran 6 ditemukan cara yang lebih hemat (menukar bila a<b) (433 ms)
  ok   tidak ada cara lebih murah => mengembalikan null (3 ms)
Penyimpan
  ok   lupa menghapus yang kuatnya < 0,05 dan indeks ikut bersih (1 ms)
  ok   kapasitas: yang dibuang adalah yang paling lemah, kejadian salah dipertahankan (0 ms)
  ok   tiga jalur tercatat: tulis, panggil, ulang (1 ms)
  ok   pilihUlang mode galat memilih kejadian salah jauh lebih sering daripada seragam (2 ms)
Sistem
  ok   tanpa belajar sepi: tidak pernah menemukan cara (kontrol) (1 ms)
  ok   dengan belajar sepi: satu malam menemukan cara tambah yang benar pada soal baru (327 ms)
  ok   kesalahan menjadi pelajaran: cara yang gagal di luar rentang dipersempit lalu diganti (311 ms)
  ok   gerbang pembuktian menolak cara yang cocok pada kasus tapi gagal pada soal segar (1 ms)
  ok   kapasitas ingatan tidak pernah terlampaui selama 14 hari (1534 ms)
  ok   deterministik: seed sama => hasil sama (1355 ms)
  ok   soal ukur tidak pernah memuat pasangan yang ada di jadwal latihan (1 ms)
  ok   belajar sepi tanpa masukan baru memperbaiki kinerja (akurasi 0,x -> 1,0) (690 ms)

17 lulus, 0 gagal
Pembentukan konsep
  ok   kamus baru tidak berisi konsep tambah, kali, basis 10, atau nilai tempat
  ok   program didapat dari pencarian tahap 1, lalu konsep diinferensikan dari dua transisi
  ok   konsep disimpan dan dapat dimuat kembali tanpa kode konsep khusus

Generalisasi di luar jangkauan langkah
  ok   tanpa konsep, soal besar melampaui batas 20.000 langkah
  ok   setelah latihan kecil, satu konsep memecahkan soal besar yang belum dilihat
  ok   generalisasi berlaku pada beberapa pasangan besar, bukan hafalan pasangan
  ok   konsep menghormati batas register dan tidak melompati perubahan yang jenuh di nol
  ok   lapisan konsep terintegrasi ke sistem dan dipakai pada soal baru besar
  ok   seed/eksekusi deterministik; hasil tidak bergantung pada jawaban oracle

9 lulus, 0 gagal
Pembentukan konsep berkondisi
  ok   badan loop dengan kondisi dapat diamati tanpa aturan khusus maksimum atau selisih
  ok   hipotesis tidak aktif sebelum tiga pengamatan yang konsisten
  ok   dua tanda tangan kondisi berbeda membentuk dua konsep berbeda
  ok   uji suntik menolak konsep yang delta-nya bertentangan dengan transisi
  ok   transisi non-afin memunculkan kontra-contoh alami dan hipotesis ditolak
  ok   konsep hanya mempercepat selama cabang kondisi tetap sama
  ok   pola kondisional menyelesaikan input besar yang melewati batas baseline
  ok   runner konsep berkondisi terhubung ke sistem dua-otak untuk cara yang tersedia
  ok   konsep aktif tetap dapat digunakan setelah model diekspor dan dimuat ulang

9 lulus, 0 gagal
Induksi representasi dari pengalaman
  ok   lingkungan tidak mengirim metadata radix atau nama posisi
  ok   menemukan bobot keadaan dari jejak penghitung radix 10 tanpa konstanta 10 di pembelajar
  ok   menemukan radix alternatif 7, bukan menganggap semua lingkungan berbasis 10
  ok   menemukan radix alternatif 6
  ok   memilih tidak mengekstrapolasi jika rasio bobot tidak konsisten
  ok   menggeneralisasi ke keadaan yang tidak ada di jejak latihan
  ok   rasio yang dipelajari memprediksi bobot slot yang belum aktif saat latihan
  ok   holdout sesudah rentang latihan tepat tanpa melatih ulang model
  ok   orkestrator menolak keadaan yang belum dapat didekode
  ok   model dapat diekspor dan dimuat tanpa mengubah hasil
  ok   menolak target yang tidak muat pada kapasitas observasi tanpa jawaban palsu
  ok   konsep representasi membantu cara tambah yang dipelajari menyelesaikan soal besar baru

12 lulus, 0 gagal
Tahap 2 — perbandingan baseline vs konsep
Seed: 10; soal/seed: 5
Baseline tahap 1 lulus: 0/50
Runner konsep lulus:    50/50
Konsep terbentuk:        10/10
Langkah kognitif/soal:   6
Ekuivalen primitif/soal: 334595.6
Detail: C:\Users\putra\Downloads\MKV\Berkembang_Tahap2_2\hasil_tahap2.json
Tahap 2.1 — induksi transisi berkondisi
Seed: 10; soal/seed: 5
Baseline lulus: 0/50
Runner konsep lulus: 50/50
Seed dengan dua konsep: 10/10
Langkah kognitif/soal: 7.6
Ekuivalen primitif/soal: 907757.2
Detail: C:\Users\putra\Downloads\MKV\Berkembang_Tahap2_2\hasil_tahap2_kondisional.json
Tahap 2.2 — induksi representasi dari pengalaman
Seed/base: 10; soal/seed/base: 5
Radix lingkungan 10: bobot [1,10,100,1000], rasio 10
  Model decode: 50/50; hafalan: 0/50
  Baseline hafalan + hitung: 0/50; baseline angka saja: 0/50; sistem dengan konsep: 50/50
  Langkah kognitif: 6; ekuivalen primitif: 217326.5
Radix lingkungan 7: bobot [1,7,49,343], rasio 7
  Model decode: 50/50; hafalan: 0/50
  Baseline hafalan + hitung: 0/50; baseline angka saja: 0/50; sistem dengan konsep: 50/50
  Langkah kognitif: 6; ekuivalen primitif: 217326.5
Radix lingkungan 6: bobot [1,6,36,216], rasio 6
  Model decode: 50/50; hafalan: 0/50
  Baseline hafalan + hitung: 0/50; baseline angka saja: 0/50; sistem dengan konsep: 50/50
  Langkah kognitif: 6; ekuivalen primitif: 217326.5
Detail: C:\Users\putra\Downloads\MKV\Berkembang_Tahap2_2\hasil_representasi.json

hasil_tahap2.json:
{
  "tahap": 2,
  "seed": 10,
  "soalPerSeed": 5,
  "baselineSoalLulusDariTotal": "0/50",
  "konsepSoalLulusDariTotal": "50/50",
  "seedDenganKonsepTerbentuk": "10/10",
  "rataLangkahKognitifPerSoal": 6,
  "rataEkuivalenLangkahPrimitifPerSoal": 334595.6,
  "catatan": "Langkah kognitif menghitung pemakaian konsep sebagai satu langkah; langkah primitif adalah biaya ekuivalen tanpa kompresi. Ini simulasi deterministik, bukan pengukuran waktu CPU atau bukti kecerdasan umum.",
  "hasil": [
    {
      "seed": "seed-0",
      "program": "salin; selama b ≠ 0 { naik; turunB }",
      "konsep": {
        "jumlah": 1,
        "dipelajari": 1,
        "konsep": [
          {
            "id": "K2a3a90f8",
            "jenis": "transisi-keadaan-berulang",
            "pola": "naik; turunB",
            "delta": {
              "a": 0,
              "b": -1,
              "r": 1
            },
            "pengamatan": 2
          }
        ]
      },
      "nUji": 5,
      "baselineLulus": 0,
      "konsepLulus": 5,
      "akurasiKonsep": 1,
      "rataLangkahKognitif": 6,
      "rataLangkahPrimitif": 334595.6,
      "detail": [
        {
          "a": 50000,
          "b": 70000,
          "benar": 120000,
          "baseline": {
            "jawab": 56667,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 120000,
            "langkah": 6,
            "langkahPrimitif": 210002,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 69999
              }
            ]
          }
        },
        {
          "a": 1234,
          "b": 87654,
          "benar": 88888,
          "baseline": {
            "jawab": 7901,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 88888,
            "langkah": 6,
            "langkahPrimitif": 262964,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 87653
              }
            ]
          }
        },
        {
          "a": 999999,
          "b": 123456,
          "benar": 1123455,
          "baseline": {
            "jawab": 1006666,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 1123455,
            "langkah": 6,
            "langkahPrimitif": 370370,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 123455
              }
            ]
          }
        },
        {
          "a": 200000,
          "b": 200003,
          "benar": 400003,
          "baseline": {
            "jawab": 206667,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 400003,
            "langkah": 6,
            "langkahPrimitif": 600011,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 200002
              }
            ]
          }
        },
        {
          "a": 12,
          "b": 76543,
          "benar": 76555,
          "baseline": {
            "jawab": 6679,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 76555,
            "langkah": 6,
            "langkahPrimitif": 229631,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 76542
              }
            ]
          }
        }
      ]
    },
    {
      "seed": "seed-1",
      "program": "salin; selama b ≠ 0 { naik; turunB }",
      "konsep": {
        "jumlah": 1,
        "dipelajari": 1,
        "konsep": [
          {
            "id": "K2a3a90f8",
            "jenis": "transisi-keadaan-berulang",
            "pola": "naik; turunB",
            "delta": {
              "a": 0,
              "b": -1,
              "r": 1
            },
            "pengamatan": 2
          }
        ]
      },
      "nUji": 5,
      "baselineLulus": 0,
      "konsepLulus": 5,
      "akurasiKonsep": 1,
      "rataLangkahKognitif": 6,
      "rataLangkahPrimitif": 334595.6,
      "detail": [
        {
          "a": 50000,
          "b": 70000,
          "benar": 120000,
          "baseline": {
            "jawab": 56667,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 120000,
            "langkah": 6,
            "langkahPrimitif": 210002,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 69999
              }
            ]
          }
        },
        {
          "a": 1234,
          "b": 87654,
          "benar": 88888,
          "baseline": {
            "jawab": 7901,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 88888,
            "langkah": 6,
            "langkahPrimitif": 262964,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 87653
              }
            ]
          }
        },
        {
          "a": 999999,
          "b": 123456,
          "benar": 1123455,
          "baseline": {
            "jawab": 1006666,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 1123455,
            "langkah": 6,
            "langkahPrimitif": 370370,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 123455
              }
            ]
          }
        },
        {
          "a": 200000,
          "b": 200003,
          "benar": 400003,
          "baseline": {
            "jawab": 206667,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 400003,
            "langkah": 6,
            "langkahPrimitif": 600011,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 200002
              }
            ]
          }
        },
        {
          "a": 12,
          "b": 76543,
          "benar": 76555,
          "baseline": {
            "jawab": 6679,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 76555,
            "langkah": 6,
            "langkahPrimitif": 229631,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 76542
              }
            ]
          }
        }
      ]
    },
    {
      "seed": "seed-2",
      "program": "salin; selama b ≠ 0 { naik; turunB }",
      "konsep": {
        "jumlah": 1,
        "dipelajari": 1,
        "konsep": [
          {
            "id": "K2a3a90f8",
            "jenis": "transisi-keadaan-berulang",
            "pola": "naik; turunB",
            "delta": {
              "a": 0,
              "b": -1,
              "r": 1
            },
            "pengamatan": 2
          }
        ]
      },
      "nUji": 5,
      "baselineLulus": 0,
      "konsepLulus": 5,
      "akurasiKonsep": 1,
      "rataLangkahKognitif": 6,
      "rataLangkahPrimitif": 334595.6,
      "detail": [
        {
          "a": 50000,
          "b": 70000,
          "benar": 120000,
          "baseline": {
            "jawab": 56667,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 120000,
            "langkah": 6,
            "langkahPrimitif": 210002,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 69999
              }
            ]
          }
        },
        {
          "a": 1234,
          "b": 87654,
          "benar": 88888,
          "baseline": {
            "jawab": 7901,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 88888,
            "langkah": 6,
            "langkahPrimitif": 262964,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 87653
              }
            ]
          }
        },
        {
          "a": 999999,
          "b": 123456,
          "benar": 1123455,
          "baseline": {
            "jawab": 1006666,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 1123455,
            "langkah": 6,
            "langkahPrimitif": 370370,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 123455
              }
            ]
          }
        },
        {
          "a": 200000,
          "b": 200003,
          "benar": 400003,
          "baseline": {
            "jawab": 206667,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 400003,
            "langkah": 6,
            "langkahPrimitif": 600011,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 200002
              }
            ]
          }
        },
        {
          "a": 12,
          "b": 76543,
          "benar": 76555,
          "baseline": {
            "jawab": 6679,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 76555,
            "langkah": 6,
            "langkahPrimitif": 229631,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 76542
              }
            ]
          }
        }
      ]
    },
    {
      "seed": "seed-3",
      "program": "salin; selama b ≠ 0 { naik; turunB }",
      "konsep": {
        "jumlah": 1,
        "dipelajari": 1,
        "konsep": [
          {
            "id": "K2a3a90f8",
            "jenis": "transisi-keadaan-berulang",
            "pola": "naik; turunB",
            "delta": {
              "a": 0,
              "b": -1,
              "r": 1
            },
            "pengamatan": 2
          }
        ]
      },
      "nUji": 5,
      "baselineLulus": 0,
      "konsepLulus": 5,
      "akurasiKonsep": 1,
      "rataLangkahKognitif": 6,
      "rataLangkahPrimitif": 334595.6,
      "detail": [
        {
          "a": 50000,
          "b": 70000,
          "benar": 120000,
          "baseline": {
            "jawab": 56667,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 120000,
            "langkah": 6,
            "langkahPrimitif": 210002,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 69999
              }
            ]
          }
        },
        {
          "a": 1234,
          "b": 87654,
          "benar": 88888,
          "baseline": {
            "jawab": 7901,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 88888,
            "langkah": 6,
            "langkahPrimitif": 262964,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 87653
              }
            ]
          }
        },
        {
          "a": 999999,
          "b": 123456,
          "benar": 1123455,
          "baseline": {
            "jawab": 1006666,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 1123455,
            "langkah": 6,
            "langkahPrimitif": 370370,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 123455
              }
            ]
          }
        },
        {
          "a": 200000,
          "b": 200003,
          "benar": 400003,
          "baseline": {
            "jawab": 206667,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 400003,
            "langkah": 6,
            "langkahPrimitif": 600011,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 200002
              }
            ]
          }
        },
        {
          "a": 12,
          "b": 76543,
          "benar": 76555,
          "baseline": {
            "jawab": 6679,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 76555,
            "langkah": 6,
            "langkahPrimitif": 229631,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 76542
              }
            ]
          }
        }
      ]
    },
    {
      "seed": "seed-4",
      "program": "salin; selama b ≠ 0 { naik; turunB }",
      "konsep": {
        "jumlah": 1,
        "dipelajari": 1,
        "konsep": [
          {
            "id": "K2a3a90f8",
            "jenis": "transisi-keadaan-berulang",
            "pola": "naik; turunB",
            "delta": {
              "a": 0,
              "b": -1,
              "r": 1
            },
            "pengamatan": 2
          }
        ]
      },
      "nUji": 5,
      "baselineLulus": 0,
      "konsepLulus": 5,
      "akurasiKonsep": 1,
      "rataLangkahKognitif": 6,
      "rataLangkahPrimitif": 334595.6,
      "detail": [
        {
          "a": 50000,
          "b": 70000,
          "benar": 120000,
          "baseline": {
            "jawab": 56667,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 120000,
            "langkah": 6,
            "langkahPrimitif": 210002,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 69999
              }
            ]
          }
        },
        {
          "a": 1234,
          "b": 87654,
          "benar": 88888,
          "baseline": {
            "jawab": 7901,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 88888,
            "langkah": 6,
            "langkahPrimitif": 262964,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 87653
              }
            ]
          }
        },
        {
          "a": 999999,
          "b": 123456,
          "benar": 1123455,
          "baseline": {
            "jawab": 1006666,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 1123455,
            "langkah": 6,
            "langkahPrimitif": 370370,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 123455
              }
            ]
          }
        },
        {
          "a": 200000,
          "b": 200003,
          "benar": 400003,
          "baseline": {
            "jawab": 206667,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 400003,
            "langkah": 6,
            "langkahPrimitif": 600011,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 200002
              }
            ]
          }
        },
        {
          "a": 12,
          "b": 76543,
          "benar": 76555,
          "baseline": {
            "jawab": 6679,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 76555,
            "langkah": 6,
            "langkahPrimitif": 229631,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 76542
              }
            ]
          }
        }
      ]
    },
    {
      "seed": "seed-5",
      "program": "salin; selama b ≠ 0 { naik; turunB }",
      "konsep": {
        "jumlah": 1,
        "dipelajari": 1,
        "konsep": [
          {
            "id": "K2a3a90f8",
            "jenis": "transisi-keadaan-berulang",
            "pola": "naik; turunB",
            "delta": {
              "a": 0,
              "b": -1,
              "r": 1
            },
            "pengamatan": 2
          }
        ]
      },
      "nUji": 5,
      "baselineLulus": 0,
      "konsepLulus": 5,
      "akurasiKonsep": 1,
      "rataLangkahKognitif": 6,
      "rataLangkahPrimitif": 334595.6,
      "detail": [
        {
          "a": 50000,
          "b": 70000,
          "benar": 120000,
          "baseline": {
            "jawab": 56667,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 120000,
            "langkah": 6,
            "langkahPrimitif": 210002,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 69999
              }
            ]
          }
        },
        {
          "a": 1234,
          "b": 87654,
          "benar": 88888,
          "baseline": {
            "jawab": 7901,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 88888,
            "langkah": 6,
            "langkahPrimitif": 262964,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 87653
              }
            ]
          }
        },
        {
          "a": 999999,
          "b": 123456,
          "benar": 1123455,
          "baseline": {
            "jawab": 1006666,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 1123455,
            "langkah": 6,
            "langkahPrimitif": 370370,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 123455
              }
            ]
          }
        },
        {
          "a": 200000,
          "b": 200003,
          "benar": 400003,
          "baseline": {
            "jawab": 206667,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 400003,
            "langkah": 6,
            "langkahPrimitif": 600011,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 200002
              }
            ]
          }
        },
        {
          "a": 12,
          "b": 76543,
          "benar": 76555,
          "baseline": {
            "jawab": 6679,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 76555,
            "langkah": 6,
            "langkahPrimitif": 229631,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 76542
              }
            ]
          }
        }
      ]
    },
    {
      "seed": "seed-6",
      "program": "salin; selama b ≠ 0 { naik; turunB }",
      "konsep": {
        "jumlah": 1,
        "dipelajari": 1,
        "konsep": [
          {
            "id": "K2a3a90f8",
            "jenis": "transisi-keadaan-berulang",
            "pola": "naik; turunB",
            "delta": {
              "a": 0,
              "b": -1,
              "r": 1
            },
            "pengamatan": 2
          }
        ]
      },
      "nUji": 5,
      "baselineLulus": 0,
      "konsepLulus": 5,
      "akurasiKonsep": 1,
      "rataLangkahKognitif": 6,
      "rataLangkahPrimitif": 334595.6,
      "detail": [
        {
          "a": 50000,
          "b": 70000,
          "benar": 120000,
          "baseline": {
            "jawab": 56667,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 120000,
            "langkah": 6,
            "langkahPrimitif": 210002,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 69999
              }
            ]
          }
        },
        {
          "a": 1234,
          "b": 87654,
          "benar": 88888,
          "baseline": {
            "jawab": 7901,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 88888,
            "langkah": 6,
            "langkahPrimitif": 262964,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 87653
              }
            ]
          }
        },
        {
          "a": 999999,
          "b": 123456,
          "benar": 1123455,
          "baseline": {
            "jawab": 1006666,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 1123455,
            "langkah": 6,
            "langkahPrimitif": 370370,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 123455
              }
            ]
          }
        },
        {
          "a": 200000,
          "b": 200003,
          "benar": 400003,
          "baseline": {
            "jawab": 206667,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 400003,
            "langkah": 6,
            "langkahPrimitif": 600011,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 200002
              }
            ]
          }
        },
        {
          "a": 12,
          "b": 76543,
          "benar": 76555,
          "baseline": {
            "jawab": 6679,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 76555,
            "langkah": 6,
            "langkahPrimitif": 229631,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 76542
              }
            ]
          }
        }
      ]
    },
    {
      "seed": "seed-7",
      "program": "salin; selama b ≠ 0 { naik; turunB }",
      "konsep": {
        "jumlah": 1,
        "dipelajari": 1,
        "konsep": [
          {
            "id": "K2a3a90f8",
            "jenis": "transisi-keadaan-berulang",
            "pola": "naik; turunB",
            "delta": {
              "a": 0,
              "b": -1,
              "r": 1
            },
            "pengamatan": 2
          }
        ]
      },
      "nUji": 5,
      "baselineLulus": 0,
      "konsepLulus": 5,
      "akurasiKonsep": 1,
      "rataLangkahKognitif": 6,
      "rataLangkahPrimitif": 334595.6,
      "detail": [
        {
          "a": 50000,
          "b": 70000,
          "benar": 120000,
          "baseline": {
            "jawab": 56667,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 120000,
            "langkah": 6,
            "langkahPrimitif": 210002,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 69999
              }
            ]
          }
        },
        {
          "a": 1234,
          "b": 87654,
          "benar": 88888,
          "baseline": {
            "jawab": 7901,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 88888,
            "langkah": 6,
            "langkahPrimitif": 262964,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 87653
              }
            ]
          }
        },
        {
          "a": 999999,
          "b": 123456,
          "benar": 1123455,
          "baseline": {
            "jawab": 1006666,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 1123455,
            "langkah": 6,
            "langkahPrimitif": 370370,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 123455
              }
            ]
          }
        },
        {
          "a": 200000,
          "b": 200003,
          "benar": 400003,
          "baseline": {
            "jawab": 206667,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 400003,
            "langkah": 6,
            "langkahPrimitif": 600011,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 200002
              }
            ]
          }
        },
        {
          "a": 12,
          "b": 76543,
          "benar": 76555,
          "baseline": {
            "jawab": 6679,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 76555,
            "langkah": 6,
            "langkahPrimitif": 229631,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 76542
              }
            ]
          }
        }
      ]
    },
    {
      "seed": "seed-8",
      "program": "salin; selama b ≠ 0 { naik; turunB }",
      "konsep": {
        "jumlah": 1,
        "dipelajari": 1,
        "konsep": [
          {
            "id": "K2a3a90f8",
            "jenis": "transisi-keadaan-berulang",
            "pola": "naik; turunB",
            "delta": {
              "a": 0,
              "b": -1,
              "r": 1
            },
            "pengamatan": 2
          }
        ]
      },
      "nUji": 5,
      "baselineLulus": 0,
      "konsepLulus": 5,
      "akurasiKonsep": 1,
      "rataLangkahKognitif": 6,
      "rataLangkahPrimitif": 334595.6,
      "detail": [
        {
          "a": 50000,
          "b": 70000,
          "benar": 120000,
          "baseline": {
            "jawab": 56667,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 120000,
            "langkah": 6,
            "langkahPrimitif": 210002,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 69999
              }
            ]
          }
        },
        {
          "a": 1234,
          "b": 87654,
          "benar": 88888,
          "baseline": {
            "jawab": 7901,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 88888,
            "langkah": 6,
            "langkahPrimitif": 262964,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 87653
              }
            ]
          }
        },
        {
          "a": 999999,
          "b": 123456,
          "benar": 1123455,
          "baseline": {
            "jawab": 1006666,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 1123455,
            "langkah": 6,
            "langkahPrimitif": 370370,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 123455
              }
            ]
          }
        },
        {
          "a": 200000,
          "b": 200003,
          "benar": 400003,
          "baseline": {
            "jawab": 206667,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 400003,
            "langkah": 6,
            "langkahPrimitif": 600011,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 200002
              }
            ]
          }
        },
        {
          "a": 12,
          "b": 76543,
          "benar": 76555,
          "baseline": {
            "jawab": 6679,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 76555,
            "langkah": 6,
            "langkahPrimitif": 229631,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 76542
              }
            ]
          }
        }
      ]
    },
    {
      "seed": "seed-9",
      "program": "salin; selama b ≠ 0 { naik; turunB }",
      "konsep": {
        "jumlah": 1,
        "dipelajari": 1,
        "konsep": [
          {
            "id": "K2a3a90f8",
            "jenis": "transisi-keadaan-berulang",
            "pola": "naik; turunB",
            "delta": {
              "a": 0,
              "b": -1,
              "r": 1
            },
            "pengamatan": 2
          }
        ]
      },
      "nUji": 5,
      "baselineLulus": 0,
      "konsepLulus": 5,
      "akurasiKonsep": 1,
      "rataLangkahKognitif": 6,
      "rataLangkahPrimitif": 334595.6,
      "detail": [
        {
          "a": 50000,
          "b": 70000,
          "benar": 120000,
          "baseline": {
            "jawab": 56667,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 120000,
            "langkah": 6,
            "langkahPrimitif": 210002,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 69999
              }
            ]
          }
        },
        {
          "a": 1234,
          "b": 87654,
          "benar": 88888,
          "baseline": {
            "jawab": 7901,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 88888,
            "langkah": 6,
            "langkahPrimitif": 262964,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 87653
              }
            ]
          }
        },
        {
          "a": 999999,
          "b": 123456,
          "benar": 1123455,
          "baseline": {
            "jawab": 1006666,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 1123455,
            "langkah": 6,
            "langkahPrimitif": 370370,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 123455
              }
            ]
          }
        },
        {
          "a": 200000,
          "b": 200003,
          "benar": 400003,
          "baseline": {
            "jawab": 206667,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 400003,
            "langkah": 6,
            "langkahPrimitif": 600011,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 200002
              }
            ]
          }
        },
        {
          "a": 12,
          "b": 76543,
          "benar": 76555,
          "baseline": {
            "jawab": 6679,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 76555,
            "langkah": 6,
            "langkahPrimitif": 229631,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "K2a3a90f8",
                "blok": 76542
              }
            ]
          }
        }
      ]
    }
  ]
}

hasil_tahap2_kondisional.json:
{
  "eksperimen": "induksi transisi berkondisi tahap 2.1",
  "seed": 10,
  "soalPerSeed": 5,
  "baselineLulus": "0/50",
  "konsepLulus": "50/50",
  "seedDenganDuaKonsep": "10/10",
  "rataLangkahKognitif": 7.6,
  "rataEkuivalenLangkahPrimitif": 907757.2,
  "batasBaseline": 20000,
  "batasRunnerKonsep": 100,
  "catatan": [
    "Program uji sengaja disediakan untuk mengisolasi induksi konsep; pencarian program belum diuji dalam benchmark ini.",
    "Jawaban benar hanya dipakai harness untuk penilaian, bukan untuk belajar konsep.",
    "Sistem mempelajari delta terpisah berdasarkan tanda tangan cabang, kemudian membatasi akselerasi sebelum kondisi berubah.",
    "Langkah kognitif dan ekuivalen primitif adalah biaya simulasi internal, bukan waktu CPU atau bukti kecerdasan umum."
  ],
  "hasil": [
    {
      "seed": 0,
      "program": "salin; selama b ≠ 0 { jika a < b { naik }; turunB }",
      "latihan": [
        {
          "a": 4,
          "b": 21,
          "hasilSistem": 21,
          "tepat": true,
          "langkah": 27
        },
        {
          "a": 8,
          "b": 20,
          "hasilSistem": 20,
          "tepat": true,
          "langkah": 7
        },
        {
          "a": 3,
          "b": 23,
          "hasilSistem": 23,
          "tepat": true,
          "langkah": 7
        }
      ],
      "konsepTerbentuk": 2,
      "tandaTangan": [
        {
          "tanda": "jika:1|op:naik|turunB:1",
          "delta": {
            "a": 0,
            "b": -1,
            "r": 1
          },
          "pengamatan": 4
        },
        {
          "tanda": "jika:0|turunB:1",
          "delta": {
            "a": 0,
            "b": -1,
            "r": 0
          },
          "pengamatan": 11
        }
      ],
      "baselineLulus": 0,
      "konsepLulus": 5,
      "rataLangkahKognitif": 7.6,
      "rataLangkahPrimitif": 907757.2,
      "detail": [
        {
          "a": 50000,
          "b": 70000,
          "benar": 70000,
          "baseline": {
            "jawab": 55000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 70000,
            "langkah": 7,
            "langkahPrimitif": 230002,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 20000,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 49999,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 90000,
          "b": 123456,
          "benar": 123456,
          "baseline": {
            "jawab": 95000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 123456,
            "langkah": 7,
            "langkahPrimitif": 403826,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 33456,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 89999,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 999999,
          "b": 1000000,
          "benar": 1000000,
          "baseline": {
            "jawab": 1000000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 1000000,
            "langkah": 10,
            "langkahPrimitif": 3000003,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 999998,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 100000,
          "b": 200003,
          "benar": 200003,
          "baseline": {
            "jawab": 105000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 200003,
            "langkah": 7,
            "langkahPrimitif": 700014,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 100003,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 99999,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 12345,
          "b": 54321,
          "benar": 54321,
          "baseline": {
            "jawab": 17345,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 54321,
            "langkah": 7,
            "langkahPrimitif": 204941,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 41976,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 12344,
                "pemakaian": 1
              }
            ]
          }
        }
      ]
    },
    {
      "seed": 1,
      "program": "salin; selama b ≠ 0 { jika a < b { naik }; turunB }",
      "latihan": [
        {
          "a": 4,
          "b": 10,
          "hasilSistem": 10,
          "tepat": true,
          "langkah": 27
        },
        {
          "a": 13,
          "b": 29,
          "hasilSistem": 29,
          "tepat": true,
          "langkah": 7
        },
        {
          "a": 3,
          "b": 18,
          "hasilSistem": 18,
          "tepat": true,
          "langkah": 7
        }
      ],
      "konsepTerbentuk": 2,
      "tandaTangan": [
        {
          "tanda": "jika:1|op:naik|turunB:1",
          "delta": {
            "a": 0,
            "b": -1,
            "r": 1
          },
          "pengamatan": 4
        },
        {
          "tanda": "jika:0|turunB:1",
          "delta": {
            "a": 0,
            "b": -1,
            "r": 0
          },
          "pengamatan": 11
        }
      ],
      "baselineLulus": 0,
      "konsepLulus": 5,
      "rataLangkahKognitif": 7.6,
      "rataLangkahPrimitif": 907757.2,
      "detail": [
        {
          "a": 50000,
          "b": 70000,
          "benar": 70000,
          "baseline": {
            "jawab": 55000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 70000,
            "langkah": 7,
            "langkahPrimitif": 230002,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 20000,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 49999,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 90000,
          "b": 123456,
          "benar": 123456,
          "baseline": {
            "jawab": 95000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 123456,
            "langkah": 7,
            "langkahPrimitif": 403826,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 33456,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 89999,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 999999,
          "b": 1000000,
          "benar": 1000000,
          "baseline": {
            "jawab": 1000000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 1000000,
            "langkah": 10,
            "langkahPrimitif": 3000003,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 999998,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 100000,
          "b": 200003,
          "benar": 200003,
          "baseline": {
            "jawab": 105000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 200003,
            "langkah": 7,
            "langkahPrimitif": 700014,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 100003,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 99999,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 12345,
          "b": 54321,
          "benar": 54321,
          "baseline": {
            "jawab": 17345,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 54321,
            "langkah": 7,
            "langkahPrimitif": 204941,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 41976,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 12344,
                "pemakaian": 1
              }
            ]
          }
        }
      ]
    },
    {
      "seed": 2,
      "program": "salin; selama b ≠ 0 { jika a < b { naik }; turunB }",
      "latihan": [
        {
          "a": 8,
          "b": 30,
          "hasilSistem": 30,
          "tepat": true,
          "langkah": 28
        },
        {
          "a": 19,
          "b": 35,
          "hasilSistem": 35,
          "tepat": true,
          "langkah": 7
        },
        {
          "a": 14,
          "b": 35,
          "hasilSistem": 35,
          "tepat": true,
          "langkah": 7
        }
      ],
      "konsepTerbentuk": 2,
      "tandaTangan": [
        {
          "tanda": "jika:1|op:naik|turunB:1",
          "delta": {
            "a": 0,
            "b": -1,
            "r": 1
          },
          "pengamatan": 4
        },
        {
          "tanda": "jika:0|turunB:1",
          "delta": {
            "a": 0,
            "b": -1,
            "r": 0
          },
          "pengamatan": 11
        }
      ],
      "baselineLulus": 0,
      "konsepLulus": 5,
      "rataLangkahKognitif": 7.6,
      "rataLangkahPrimitif": 907757.2,
      "detail": [
        {
          "a": 50000,
          "b": 70000,
          "benar": 70000,
          "baseline": {
            "jawab": 55000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 70000,
            "langkah": 7,
            "langkahPrimitif": 230002,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 20000,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 49999,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 90000,
          "b": 123456,
          "benar": 123456,
          "baseline": {
            "jawab": 95000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 123456,
            "langkah": 7,
            "langkahPrimitif": 403826,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 33456,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 89999,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 999999,
          "b": 1000000,
          "benar": 1000000,
          "baseline": {
            "jawab": 1000000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 1000000,
            "langkah": 10,
            "langkahPrimitif": 3000003,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 999998,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 100000,
          "b": 200003,
          "benar": 200003,
          "baseline": {
            "jawab": 105000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 200003,
            "langkah": 7,
            "langkahPrimitif": 700014,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 100003,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 99999,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 12345,
          "b": 54321,
          "benar": 54321,
          "baseline": {
            "jawab": 17345,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 54321,
            "langkah": 7,
            "langkahPrimitif": 204941,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 41976,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 12344,
                "pemakaian": 1
              }
            ]
          }
        }
      ]
    },
    {
      "seed": 3,
      "program": "salin; selama b ≠ 0 { jika a < b { naik }; turunB }",
      "latihan": [
        {
          "a": 9,
          "b": 18,
          "hasilSistem": 18,
          "tepat": true,
          "langkah": 28
        },
        {
          "a": 10,
          "b": 18,
          "hasilSistem": 18,
          "tepat": true,
          "langkah": 7
        },
        {
          "a": 9,
          "b": 22,
          "hasilSistem": 22,
          "tepat": true,
          "langkah": 7
        }
      ],
      "konsepTerbentuk": 2,
      "tandaTangan": [
        {
          "tanda": "jika:1|op:naik|turunB:1",
          "delta": {
            "a": 0,
            "b": -1,
            "r": 1
          },
          "pengamatan": 4
        },
        {
          "tanda": "jika:0|turunB:1",
          "delta": {
            "a": 0,
            "b": -1,
            "r": 0
          },
          "pengamatan": 11
        }
      ],
      "baselineLulus": 0,
      "konsepLulus": 5,
      "rataLangkahKognitif": 7.6,
      "rataLangkahPrimitif": 907757.2,
      "detail": [
        {
          "a": 50000,
          "b": 70000,
          "benar": 70000,
          "baseline": {
            "jawab": 55000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 70000,
            "langkah": 7,
            "langkahPrimitif": 230002,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 20000,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 49999,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 90000,
          "b": 123456,
          "benar": 123456,
          "baseline": {
            "jawab": 95000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 123456,
            "langkah": 7,
            "langkahPrimitif": 403826,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 33456,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 89999,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 999999,
          "b": 1000000,
          "benar": 1000000,
          "baseline": {
            "jawab": 1000000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 1000000,
            "langkah": 10,
            "langkahPrimitif": 3000003,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 999998,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 100000,
          "b": 200003,
          "benar": 200003,
          "baseline": {
            "jawab": 105000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 200003,
            "langkah": 7,
            "langkahPrimitif": 700014,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 100003,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 99999,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 12345,
          "b": 54321,
          "benar": 54321,
          "baseline": {
            "jawab": 17345,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 54321,
            "langkah": 7,
            "langkahPrimitif": 204941,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 41976,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 12344,
                "pemakaian": 1
              }
            ]
          }
        }
      ]
    },
    {
      "seed": 4,
      "program": "salin; selama b ≠ 0 { jika a < b { naik }; turunB }",
      "latihan": [
        {
          "a": 8,
          "b": 14,
          "hasilSistem": 14,
          "tepat": true,
          "langkah": 28
        },
        {
          "a": 12,
          "b": 29,
          "hasilSistem": 29,
          "tepat": true,
          "langkah": 7
        },
        {
          "a": 22,
          "b": 32,
          "hasilSistem": 32,
          "tepat": true,
          "langkah": 7
        }
      ],
      "konsepTerbentuk": 2,
      "tandaTangan": [
        {
          "tanda": "jika:1|op:naik|turunB:1",
          "delta": {
            "a": 0,
            "b": -1,
            "r": 1
          },
          "pengamatan": 4
        },
        {
          "tanda": "jika:0|turunB:1",
          "delta": {
            "a": 0,
            "b": -1,
            "r": 0
          },
          "pengamatan": 11
        }
      ],
      "baselineLulus": 0,
      "konsepLulus": 5,
      "rataLangkahKognitif": 7.6,
      "rataLangkahPrimitif": 907757.2,
      "detail": [
        {
          "a": 50000,
          "b": 70000,
          "benar": 70000,
          "baseline": {
            "jawab": 55000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 70000,
            "langkah": 7,
            "langkahPrimitif": 230002,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 20000,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 49999,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 90000,
          "b": 123456,
          "benar": 123456,
          "baseline": {
            "jawab": 95000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 123456,
            "langkah": 7,
            "langkahPrimitif": 403826,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 33456,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 89999,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 999999,
          "b": 1000000,
          "benar": 1000000,
          "baseline": {
            "jawab": 1000000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 1000000,
            "langkah": 10,
            "langkahPrimitif": 3000003,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 999998,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 100000,
          "b": 200003,
          "benar": 200003,
          "baseline": {
            "jawab": 105000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 200003,
            "langkah": 7,
            "langkahPrimitif": 700014,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 100003,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 99999,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 12345,
          "b": 54321,
          "benar": 54321,
          "baseline": {
            "jawab": 17345,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 54321,
            "langkah": 7,
            "langkahPrimitif": 204941,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 41976,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 12344,
                "pemakaian": 1
              }
            ]
          }
        }
      ]
    },
    {
      "seed": 5,
      "program": "salin; selama b ≠ 0 { jika a < b { naik }; turunB }",
      "latihan": [
        {
          "a": 5,
          "b": 15,
          "hasilSistem": 15,
          "tepat": true,
          "langkah": 30
        },
        {
          "a": 8,
          "b": 17,
          "hasilSistem": 17,
          "tepat": true,
          "langkah": 7
        },
        {
          "a": 18,
          "b": 31,
          "hasilSistem": 31,
          "tepat": true,
          "langkah": 7
        }
      ],
      "konsepTerbentuk": 2,
      "tandaTangan": [
        {
          "tanda": "jika:1|op:naik|turunB:1",
          "delta": {
            "a": 0,
            "b": -1,
            "r": 1
          },
          "pengamatan": 4
        },
        {
          "tanda": "jika:0|turunB:1",
          "delta": {
            "a": 0,
            "b": -1,
            "r": 0
          },
          "pengamatan": 12
        }
      ],
      "baselineLulus": 0,
      "konsepLulus": 5,
      "rataLangkahKognitif": 7.6,
      "rataLangkahPrimitif": 907757.2,
      "detail": [
        {
          "a": 50000,
          "b": 70000,
          "benar": 70000,
          "baseline": {
            "jawab": 55000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 70000,
            "langkah": 7,
            "langkahPrimitif": 230002,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 20000,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 49999,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 90000,
          "b": 123456,
          "benar": 123456,
          "baseline": {
            "jawab": 95000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 123456,
            "langkah": 7,
            "langkahPrimitif": 403826,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 33456,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 89999,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 999999,
          "b": 1000000,
          "benar": 1000000,
          "baseline": {
            "jawab": 1000000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 1000000,
            "langkah": 10,
            "langkahPrimitif": 3000003,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 999998,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 100000,
          "b": 200003,
          "benar": 200003,
          "baseline": {
            "jawab": 105000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 200003,
            "langkah": 7,
            "langkahPrimitif": 700014,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 100003,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 99999,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 12345,
          "b": 54321,
          "benar": 54321,
          "baseline": {
            "jawab": 17345,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 54321,
            "langkah": 7,
            "langkahPrimitif": 204941,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 41976,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 12344,
                "pemakaian": 1
              }
            ]
          }
        }
      ]
    },
    {
      "seed": 6,
      "program": "salin; selama b ≠ 0 { jika a < b { naik }; turunB }",
      "latihan": [
        {
          "a": 3,
          "b": 15,
          "hasilSistem": 15,
          "tepat": true,
          "langkah": 24
        },
        {
          "a": 11,
          "b": 33,
          "hasilSistem": 33,
          "tepat": true,
          "langkah": 7
        },
        {
          "a": 21,
          "b": 27,
          "hasilSistem": 27,
          "tepat": true,
          "langkah": 7
        }
      ],
      "konsepTerbentuk": 2,
      "tandaTangan": [
        {
          "tanda": "jika:1|op:naik|turunB:1",
          "delta": {
            "a": 0,
            "b": -1,
            "r": 1
          },
          "pengamatan": 4
        },
        {
          "tanda": "jika:0|turunB:1",
          "delta": {
            "a": 0,
            "b": -1,
            "r": 0
          },
          "pengamatan": 10
        }
      ],
      "baselineLulus": 0,
      "konsepLulus": 5,
      "rataLangkahKognitif": 7.6,
      "rataLangkahPrimitif": 907757.2,
      "detail": [
        {
          "a": 50000,
          "b": 70000,
          "benar": 70000,
          "baseline": {
            "jawab": 55000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 70000,
            "langkah": 7,
            "langkahPrimitif": 230002,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 20000,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 49999,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 90000,
          "b": 123456,
          "benar": 123456,
          "baseline": {
            "jawab": 95000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 123456,
            "langkah": 7,
            "langkahPrimitif": 403826,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 33456,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 89999,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 999999,
          "b": 1000000,
          "benar": 1000000,
          "baseline": {
            "jawab": 1000000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 1000000,
            "langkah": 10,
            "langkahPrimitif": 3000003,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 999998,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 100000,
          "b": 200003,
          "benar": 200003,
          "baseline": {
            "jawab": 105000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 200003,
            "langkah": 7,
            "langkahPrimitif": 700014,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 100003,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 99999,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 12345,
          "b": 54321,
          "benar": 54321,
          "baseline": {
            "jawab": 17345,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 54321,
            "langkah": 7,
            "langkahPrimitif": 204941,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 41976,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 12344,
                "pemakaian": 1
              }
            ]
          }
        }
      ]
    },
    {
      "seed": 7,
      "program": "salin; selama b ≠ 0 { jika a < b { naik }; turunB }",
      "latihan": [
        {
          "a": 9,
          "b": 25,
          "hasilSistem": 25,
          "tepat": true,
          "langkah": 28
        },
        {
          "a": 14,
          "b": 23,
          "hasilSistem": 23,
          "tepat": true,
          "langkah": 7
        },
        {
          "a": 18,
          "b": 26,
          "hasilSistem": 26,
          "tepat": true,
          "langkah": 7
        }
      ],
      "konsepTerbentuk": 2,
      "tandaTangan": [
        {
          "tanda": "jika:1|op:naik|turunB:1",
          "delta": {
            "a": 0,
            "b": -1,
            "r": 1
          },
          "pengamatan": 4
        },
        {
          "tanda": "jika:0|turunB:1",
          "delta": {
            "a": 0,
            "b": -1,
            "r": 0
          },
          "pengamatan": 11
        }
      ],
      "baselineLulus": 0,
      "konsepLulus": 5,
      "rataLangkahKognitif": 7.6,
      "rataLangkahPrimitif": 907757.2,
      "detail": [
        {
          "a": 50000,
          "b": 70000,
          "benar": 70000,
          "baseline": {
            "jawab": 55000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 70000,
            "langkah": 7,
            "langkahPrimitif": 230002,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 20000,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 49999,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 90000,
          "b": 123456,
          "benar": 123456,
          "baseline": {
            "jawab": 95000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 123456,
            "langkah": 7,
            "langkahPrimitif": 403826,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 33456,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 89999,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 999999,
          "b": 1000000,
          "benar": 1000000,
          "baseline": {
            "jawab": 1000000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 1000000,
            "langkah": 10,
            "langkahPrimitif": 3000003,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 999998,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 100000,
          "b": 200003,
          "benar": 200003,
          "baseline": {
            "jawab": 105000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 200003,
            "langkah": 7,
            "langkahPrimitif": 700014,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 100003,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 99999,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 12345,
          "b": 54321,
          "benar": 54321,
          "baseline": {
            "jawab": 17345,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 54321,
            "langkah": 7,
            "langkahPrimitif": 204941,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 41976,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 12344,
                "pemakaian": 1
              }
            ]
          }
        }
      ]
    },
    {
      "seed": 8,
      "program": "salin; selama b ≠ 0 { jika a < b { naik }; turunB }",
      "latihan": [
        {
          "a": 9,
          "b": 12,
          "hasilSistem": 12,
          "tepat": true,
          "langkah": 27
        },
        {
          "a": 4,
          "b": 18,
          "hasilSistem": 18,
          "tepat": true,
          "langkah": 7
        },
        {
          "a": 12,
          "b": 29,
          "hasilSistem": 29,
          "tepat": true,
          "langkah": 7
        }
      ],
      "konsepTerbentuk": 2,
      "tandaTangan": [
        {
          "tanda": "jika:1|op:naik|turunB:1",
          "delta": {
            "a": 0,
            "b": -1,
            "r": 1
          },
          "pengamatan": 4
        },
        {
          "tanda": "jika:0|turunB:1",
          "delta": {
            "a": 0,
            "b": -1,
            "r": 0
          },
          "pengamatan": 11
        }
      ],
      "baselineLulus": 0,
      "konsepLulus": 5,
      "rataLangkahKognitif": 7.6,
      "rataLangkahPrimitif": 907757.2,
      "detail": [
        {
          "a": 50000,
          "b": 70000,
          "benar": 70000,
          "baseline": {
            "jawab": 55000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 70000,
            "langkah": 7,
            "langkahPrimitif": 230002,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 20000,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 49999,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 90000,
          "b": 123456,
          "benar": 123456,
          "baseline": {
            "jawab": 95000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 123456,
            "langkah": 7,
            "langkahPrimitif": 403826,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 33456,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 89999,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 999999,
          "b": 1000000,
          "benar": 1000000,
          "baseline": {
            "jawab": 1000000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 1000000,
            "langkah": 10,
            "langkahPrimitif": 3000003,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 999998,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 100000,
          "b": 200003,
          "benar": 200003,
          "baseline": {
            "jawab": 105000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 200003,
            "langkah": 7,
            "langkahPrimitif": 700014,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 100003,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 99999,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 12345,
          "b": 54321,
          "benar": 54321,
          "baseline": {
            "jawab": 17345,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 54321,
            "langkah": 7,
            "langkahPrimitif": 204941,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 41976,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 12344,
                "pemakaian": 1
              }
            ]
          }
        }
      ]
    },
    {
      "seed": 9,
      "program": "salin; selama b ≠ 0 { jika a < b { naik }; turunB }",
      "latihan": [
        {
          "a": 16,
          "b": 25,
          "hasilSistem": 25,
          "tepat": true,
          "langkah": 28
        },
        {
          "a": 20,
          "b": 31,
          "hasilSistem": 31,
          "tepat": true,
          "langkah": 7
        },
        {
          "a": 9,
          "b": 15,
          "hasilSistem": 15,
          "tepat": true,
          "langkah": 7
        }
      ],
      "konsepTerbentuk": 2,
      "tandaTangan": [
        {
          "tanda": "jika:1|op:naik|turunB:1",
          "delta": {
            "a": 0,
            "b": -1,
            "r": 1
          },
          "pengamatan": 4
        },
        {
          "tanda": "jika:0|turunB:1",
          "delta": {
            "a": 0,
            "b": -1,
            "r": 0
          },
          "pengamatan": 11
        }
      ],
      "baselineLulus": 0,
      "konsepLulus": 5,
      "rataLangkahKognitif": 7.6,
      "rataLangkahPrimitif": 907757.2,
      "detail": [
        {
          "a": 50000,
          "b": 70000,
          "benar": 70000,
          "baseline": {
            "jawab": 55000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 70000,
            "langkah": 7,
            "langkahPrimitif": 230002,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 20000,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 49999,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 90000,
          "b": 123456,
          "benar": 123456,
          "baseline": {
            "jawab": 95000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 123456,
            "langkah": 7,
            "langkahPrimitif": 403826,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 33456,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 89999,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 999999,
          "b": 1000000,
          "benar": 1000000,
          "baseline": {
            "jawab": 1000000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 1000000,
            "langkah": 10,
            "langkahPrimitif": 3000003,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 999998,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 100000,
          "b": 200003,
          "benar": 200003,
          "baseline": {
            "jawab": 105000,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 200003,
            "langkah": 7,
            "langkahPrimitif": 700014,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 100003,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 99999,
                "pemakaian": 1
              }
            ]
          }
        },
        {
          "a": 12345,
          "b": 54321,
          "benar": 54321,
          "baseline": {
            "jawab": 17345,
            "langkah": 20001,
            "habis": true
          },
          "konsep": {
            "jawab": 54321,
            "langkah": 7,
            "langkahPrimitif": 204941,
            "habis": false,
            "konsepDipakai": [
              {
                "id": "GK5c40145a",
                "tanda": "jika:1|op:naik|turunB:1",
                "blok": 41976,
                "pemakaian": 1
              },
              {
                "id": "GKbc960749",
                "tanda": "jika:0|turunB:1",
                "blok": 12344,
                "pemakaian": 1
              }
            ]
          }
        }
      ]
    }
  ]
}

hasil_representasi.json:
{
  "tahap": "2.2",
  "tujuan": "induksi bobot representasi yang tidak diberi label dan pemakaian pada soal penjumlahan tak dikenal",
  "catatan": "Penghitung adalah lingkungan uji yang aturannya ditetapkan harness. Pembelajar hanya menerima vektor keadaan dan hitungan langkah dari tindakannya. Model kandidat adalah jumlah berbobot koordinat dengan hipotesis rasio berulang; ini bias induksi eksplisit, bukan penemuan tanpa batas.",
  "hasil": [
    {
      "radix": 10,
      "trainThrough": 1020,
      "trainSamples": 1021,
      "model": {
        "bobot": [
          1,
          10,
          100,
          1000
        ],
        "rasio": 10,
        "status": "tervalidasi-pada-pengalaman",
        "bukti": {
          "jumlahPengamatan": 1021,
          "bobotTerverifikasi": 4,
          "galatMaks": 0,
          "rasioTerkonfirmasi": 10,
          "pengamatanTerwakili": 1021
        }
      },
      "seed": 10,
      "soalPerSeed": 5,
      "totals": {
        "decodeModel": "50/50",
        "decodeHafalan": "0/50",
        "baselineEndToEnd": "0/50",
        "baselineNumericOnly": "0/50",
        "learnedEndToEnd": "50/50",
        "rataLangkahKognitif": 6,
        "rataEkuivalenPrimitif": 217326.5
      },
      "rows": [
        {
          "radix": 10,
          "seed": 0,
          "soal": 0,
          "stateA": [
            0,
            0,
            0,
            0,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            0,
            0,
            0,
            0,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 50000,
          "nilaiB": 70000,
          "benar": 120000,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 50000,
            "b": 70000,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 56667,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 56667,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 120000,
            "langkah": 6,
            "langkahPrimitif": 210002,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 0,
          "soal": 1,
          "stateA": [
            7,
            3,
            1,
            0,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            9,
            8,
            0,
            0,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 50137,
          "nilaiB": 70089,
          "benar": 120226,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 50137,
            "b": 70089,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 56804,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 56804,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 120226,
            "langkah": 6,
            "langkahPrimitif": 210269,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 0,
          "soal": 2,
          "stateA": [
            4,
            7,
            2,
            0,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            8,
            7,
            1,
            0,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 50274,
          "nilaiB": 70178,
          "benar": 120452,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 50274,
            "b": 70178,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 56941,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 56941,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 120452,
            "langkah": 6,
            "langkahPrimitif": 210536,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 0,
          "soal": 3,
          "stateA": [
            1,
            1,
            4,
            0,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            7,
            6,
            2,
            0,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 50411,
          "nilaiB": 70267,
          "benar": 120678,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 50411,
            "b": 70267,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 57078,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 57078,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 120678,
            "langkah": 6,
            "langkahPrimitif": 210803,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 0,
          "soal": 4,
          "stateA": [
            8,
            4,
            5,
            0,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            6,
            5,
            3,
            0,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 50548,
          "nilaiB": 70356,
          "benar": 120904,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 50548,
            "b": 70356,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 57215,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 57215,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 120904,
            "langkah": 6,
            "langkahPrimitif": 211070,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 1,
          "soal": 0,
          "stateA": [
            9,
            0,
            0,
            1,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            3,
            0,
            5,
            0,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 51009,
          "nilaiB": 70503,
          "benar": 121512,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 51009,
            "b": 70503,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 57676,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 57676,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 121512,
            "langkah": 6,
            "langkahPrimitif": 211511,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 1,
          "soal": 1,
          "stateA": [
            6,
            4,
            1,
            1,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            2,
            9,
            5,
            0,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 51146,
          "nilaiB": 70592,
          "benar": 121738,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 51146,
            "b": 70592,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 57813,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 57813,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 121738,
            "langkah": 6,
            "langkahPrimitif": 211778,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 1,
          "soal": 2,
          "stateA": [
            3,
            8,
            2,
            1,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            1,
            8,
            6,
            0,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 51283,
          "nilaiB": 70681,
          "benar": 121964,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 51283,
            "b": 70681,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 57950,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 57950,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 121964,
            "langkah": 6,
            "langkahPrimitif": 212045,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 1,
          "soal": 3,
          "stateA": [
            0,
            2,
            4,
            1,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            0,
            7,
            7,
            0,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 51420,
          "nilaiB": 70770,
          "benar": 122190,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 51420,
            "b": 70770,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 58087,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 58087,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 122190,
            "langkah": 6,
            "langkahPrimitif": 212312,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 1,
          "soal": 4,
          "stateA": [
            7,
            5,
            5,
            1,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            9,
            5,
            8,
            0,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 51557,
          "nilaiB": 70859,
          "benar": 122416,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 51557,
            "b": 70859,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 58224,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 58224,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 122416,
            "langkah": 6,
            "langkahPrimitif": 212579,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 2,
          "soal": 0,
          "stateA": [
            8,
            1,
            0,
            2,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            6,
            0,
            0,
            1,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 52018,
          "nilaiB": 71006,
          "benar": 123024,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 52018,
            "b": 71006,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 58685,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 58685,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 123024,
            "langkah": 6,
            "langkahPrimitif": 213020,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 2,
          "soal": 1,
          "stateA": [
            5,
            5,
            1,
            2,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            5,
            9,
            0,
            1,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 52155,
          "nilaiB": 71095,
          "benar": 123250,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 52155,
            "b": 71095,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 58822,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 58822,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 123250,
            "langkah": 6,
            "langkahPrimitif": 213287,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 2,
          "soal": 2,
          "stateA": [
            2,
            9,
            2,
            2,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            4,
            8,
            1,
            1,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 52292,
          "nilaiB": 71184,
          "benar": 123476,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 52292,
            "b": 71184,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 58959,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 58959,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 123476,
            "langkah": 6,
            "langkahPrimitif": 213554,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 2,
          "soal": 3,
          "stateA": [
            9,
            2,
            4,
            2,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            3,
            7,
            2,
            1,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 52429,
          "nilaiB": 71273,
          "benar": 123702,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 52429,
            "b": 71273,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 59096,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 59096,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 123702,
            "langkah": 6,
            "langkahPrimitif": 213821,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 2,
          "soal": 4,
          "stateA": [
            6,
            6,
            5,
            2,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            2,
            6,
            3,
            1,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 52566,
          "nilaiB": 71362,
          "benar": 123928,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 52566,
            "b": 71362,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 59233,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 59233,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 123928,
            "langkah": 6,
            "langkahPrimitif": 214088,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 3,
          "soal": 0,
          "stateA": [
            7,
            2,
            0,
            3,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            9,
            0,
            5,
            1,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 53027,
          "nilaiB": 71509,
          "benar": 124536,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 53027,
            "b": 71509,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 59694,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 59694,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 124536,
            "langkah": 6,
            "langkahPrimitif": 214529,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 3,
          "soal": 1,
          "stateA": [
            4,
            6,
            1,
            3,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            8,
            9,
            5,
            1,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 53164,
          "nilaiB": 71598,
          "benar": 124762,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 53164,
            "b": 71598,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 59831,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 59831,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 124762,
            "langkah": 6,
            "langkahPrimitif": 214796,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 3,
          "soal": 2,
          "stateA": [
            1,
            0,
            3,
            3,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            7,
            8,
            6,
            1,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 53301,
          "nilaiB": 71687,
          "benar": 124988,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 53301,
            "b": 71687,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 59968,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 59968,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 124988,
            "langkah": 6,
            "langkahPrimitif": 215063,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 3,
          "soal": 3,
          "stateA": [
            8,
            3,
            4,
            3,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            6,
            7,
            7,
            1,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 53438,
          "nilaiB": 71776,
          "benar": 125214,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 53438,
            "b": 71776,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 60105,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 60105,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 125214,
            "langkah": 6,
            "langkahPrimitif": 215330,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 3,
          "soal": 4,
          "stateA": [
            5,
            7,
            5,
            3,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            5,
            6,
            8,
            1,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 53575,
          "nilaiB": 71865,
          "benar": 125440,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 53575,
            "b": 71865,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 60242,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 60242,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 125440,
            "langkah": 6,
            "langkahPrimitif": 215597,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 4,
          "soal": 0,
          "stateA": [
            6,
            3,
            0,
            4,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            2,
            1,
            0,
            2,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 54036,
          "nilaiB": 72012,
          "benar": 126048,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 54036,
            "b": 72012,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 60703,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 60703,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 126048,
            "langkah": 6,
            "langkahPrimitif": 216038,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 4,
          "soal": 1,
          "stateA": [
            3,
            7,
            1,
            4,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            1,
            0,
            1,
            2,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 54173,
          "nilaiB": 72101,
          "benar": 126274,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 54173,
            "b": 72101,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 60840,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 60840,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 126274,
            "langkah": 6,
            "langkahPrimitif": 216305,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 4,
          "soal": 2,
          "stateA": [
            0,
            1,
            3,
            4,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            0,
            9,
            1,
            2,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 54310,
          "nilaiB": 72190,
          "benar": 126500,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 54310,
            "b": 72190,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 60977,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 60977,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 126500,
            "langkah": 6,
            "langkahPrimitif": 216572,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 4,
          "soal": 3,
          "stateA": [
            7,
            4,
            4,
            4,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            9,
            7,
            2,
            2,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 54447,
          "nilaiB": 72279,
          "benar": 126726,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 54447,
            "b": 72279,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 61114,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 61114,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 126726,
            "langkah": 6,
            "langkahPrimitif": 216839,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 4,
          "soal": 4,
          "stateA": [
            4,
            8,
            5,
            4,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            8,
            6,
            3,
            2,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 54584,
          "nilaiB": 72368,
          "benar": 126952,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 54584,
            "b": 72368,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 61251,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 61251,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 126952,
            "langkah": 6,
            "langkahPrimitif": 217106,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 5,
          "soal": 0,
          "stateA": [
            5,
            4,
            0,
            5,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            5,
            1,
            5,
            2,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 55045,
          "nilaiB": 72515,
          "benar": 127560,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 55045,
            "b": 72515,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 61712,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 61712,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 127560,
            "langkah": 6,
            "langkahPrimitif": 217547,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 5,
          "soal": 1,
          "stateA": [
            2,
            8,
            1,
            5,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            4,
            0,
            6,
            2,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 55182,
          "nilaiB": 72604,
          "benar": 127786,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 55182,
            "b": 72604,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 61849,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 61849,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 127786,
            "langkah": 6,
            "langkahPrimitif": 217814,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 5,
          "soal": 2,
          "stateA": [
            9,
            1,
            3,
            5,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            3,
            9,
            6,
            2,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 55319,
          "nilaiB": 72693,
          "benar": 128012,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 55319,
            "b": 72693,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 61986,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 61986,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 128012,
            "langkah": 6,
            "langkahPrimitif": 218081,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 5,
          "soal": 3,
          "stateA": [
            6,
            5,
            4,
            5,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            2,
            8,
            7,
            2,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 55456,
          "nilaiB": 72782,
          "benar": 128238,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 55456,
            "b": 72782,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 62123,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 62123,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 128238,
            "langkah": 6,
            "langkahPrimitif": 218348,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 5,
          "soal": 4,
          "stateA": [
            3,
            9,
            5,
            5,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            1,
            7,
            8,
            2,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 55593,
          "nilaiB": 72871,
          "benar": 128464,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 55593,
            "b": 72871,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 62260,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 62260,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 128464,
            "langkah": 6,
            "langkahPrimitif": 218615,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 6,
          "soal": 0,
          "stateA": [
            4,
            5,
            0,
            6,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            8,
            1,
            0,
            3,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 56054,
          "nilaiB": 73018,
          "benar": 129072,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 56054,
            "b": 73018,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 62721,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 62721,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 129072,
            "langkah": 6,
            "langkahPrimitif": 219056,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 6,
          "soal": 1,
          "stateA": [
            1,
            9,
            1,
            6,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            7,
            0,
            1,
            3,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 56191,
          "nilaiB": 73107,
          "benar": 129298,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 56191,
            "b": 73107,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 62858,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 62858,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 129298,
            "langkah": 6,
            "langkahPrimitif": 219323,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 6,
          "soal": 2,
          "stateA": [
            8,
            2,
            3,
            6,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            6,
            9,
            1,
            3,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 56328,
          "nilaiB": 73196,
          "benar": 129524,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 56328,
            "b": 73196,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 62995,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 62995,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 129524,
            "langkah": 6,
            "langkahPrimitif": 219590,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 6,
          "soal": 3,
          "stateA": [
            5,
            6,
            4,
            6,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            5,
            8,
            2,
            3,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 56465,
          "nilaiB": 73285,
          "benar": 129750,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 56465,
            "b": 73285,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 63132,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 63132,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 129750,
            "langkah": 6,
            "langkahPrimitif": 219857,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 6,
          "soal": 4,
          "stateA": [
            2,
            0,
            6,
            6,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            4,
            7,
            3,
            3,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 56602,
          "nilaiB": 73374,
          "benar": 129976,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 56602,
            "b": 73374,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 63269,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 63269,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 129976,
            "langkah": 6,
            "langkahPrimitif": 220124,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 7,
          "soal": 0,
          "stateA": [
            3,
            6,
            0,
            7,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            1,
            2,
            5,
            3,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 57063,
          "nilaiB": 73521,
          "benar": 130584,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 57063,
            "b": 73521,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 63730,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 63730,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 130584,
            "langkah": 6,
            "langkahPrimitif": 220565,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 7,
          "soal": 1,
          "stateA": [
            0,
            0,
            2,
            7,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            0,
            1,
            6,
            3,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 57200,
          "nilaiB": 73610,
          "benar": 130810,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 57200,
            "b": 73610,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 63867,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 63867,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 130810,
            "langkah": 6,
            "langkahPrimitif": 220832,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 7,
          "soal": 2,
          "stateA": [
            7,
            3,
            3,
            7,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            9,
            9,
            6,
            3,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 57337,
          "nilaiB": 73699,
          "benar": 131036,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 57337,
            "b": 73699,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 64004,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 64004,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 131036,
            "langkah": 6,
            "langkahPrimitif": 221099,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 7,
          "soal": 3,
          "stateA": [
            4,
            7,
            4,
            7,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            8,
            8,
            7,
            3,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 57474,
          "nilaiB": 73788,
          "benar": 131262,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 57474,
            "b": 73788,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 64141,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 64141,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 131262,
            "langkah": 6,
            "langkahPrimitif": 221366,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 7,
          "soal": 4,
          "stateA": [
            1,
            1,
            6,
            7,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            7,
            7,
            8,
            3,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 57611,
          "nilaiB": 73877,
          "benar": 131488,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 57611,
            "b": 73877,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 64278,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 64278,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 131488,
            "langkah": 6,
            "langkahPrimitif": 221633,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 8,
          "soal": 0,
          "stateA": [
            2,
            7,
            0,
            8,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            4,
            2,
            0,
            4,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 58072,
          "nilaiB": 74024,
          "benar": 132096,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 58072,
            "b": 74024,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 64739,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 64739,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 132096,
            "langkah": 6,
            "langkahPrimitif": 222074,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 8,
          "soal": 1,
          "stateA": [
            9,
            0,
            2,
            8,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            3,
            1,
            1,
            4,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 58209,
          "nilaiB": 74113,
          "benar": 132322,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 58209,
            "b": 74113,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 64876,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 64876,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 132322,
            "langkah": 6,
            "langkahPrimitif": 222341,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 8,
          "soal": 2,
          "stateA": [
            6,
            4,
            3,
            8,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            2,
            0,
            2,
            4,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 58346,
          "nilaiB": 74202,
          "benar": 132548,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 58346,
            "b": 74202,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 65013,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 65013,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 132548,
            "langkah": 6,
            "langkahPrimitif": 222608,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 8,
          "soal": 3,
          "stateA": [
            3,
            8,
            4,
            8,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            1,
            9,
            2,
            4,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 58483,
          "nilaiB": 74291,
          "benar": 132774,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 58483,
            "b": 74291,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 65150,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 65150,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 132774,
            "langkah": 6,
            "langkahPrimitif": 222875,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 8,
          "soal": 4,
          "stateA": [
            0,
            2,
            6,
            8,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            0,
            8,
            3,
            4,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 58620,
          "nilaiB": 74380,
          "benar": 133000,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 58620,
            "b": 74380,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 65287,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 65287,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 133000,
            "langkah": 6,
            "langkahPrimitif": 223142,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 9,
          "soal": 0,
          "stateA": [
            1,
            8,
            0,
            9,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            7,
            2,
            5,
            4,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 59081,
          "nilaiB": 74527,
          "benar": 133608,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 59081,
            "b": 74527,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 65748,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 65748,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 133608,
            "langkah": 6,
            "langkahPrimitif": 223583,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 9,
          "soal": 1,
          "stateA": [
            8,
            1,
            2,
            9,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            6,
            1,
            6,
            4,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 59218,
          "nilaiB": 74616,
          "benar": 133834,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 59218,
            "b": 74616,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 65885,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 65885,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 133834,
            "langkah": 6,
            "langkahPrimitif": 223850,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 9,
          "soal": 2,
          "stateA": [
            5,
            5,
            3,
            9,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            5,
            0,
            7,
            4,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 59355,
          "nilaiB": 74705,
          "benar": 134060,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 59355,
            "b": 74705,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 66022,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 66022,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 134060,
            "langkah": 6,
            "langkahPrimitif": 224117,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 9,
          "soal": 3,
          "stateA": [
            2,
            9,
            4,
            9,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            4,
            9,
            7,
            4,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 59492,
          "nilaiB": 74794,
          "benar": 134286,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 59492,
            "b": 74794,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 66159,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 66159,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 134286,
            "langkah": 6,
            "langkahPrimitif": 224384,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 10,
          "seed": 9,
          "soal": 4,
          "stateA": [
            9,
            2,
            6,
            9,
            5,
            0,
            0,
            0
          ],
          "stateB": [
            3,
            8,
            8,
            4,
            7,
            0,
            0,
            0
          ],
          "nilaiA": 59629,
          "nilaiB": 74883,
          "benar": 134512,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 59629,
            "b": 74883,
            "lulus": true,
            "bobot": [
              1,
              10,
              100,
              1000
            ],
            "rasio": 10
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 66296,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 66296,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 134512,
            "langkah": 6,
            "langkahPrimitif": 224651,
            "status": "terjawab",
            "lulus": true
          }
        }
      ]
    },
    {
      "radix": 7,
      "trainThrough": 357,
      "trainSamples": 358,
      "model": {
        "bobot": [
          1,
          7,
          49,
          343
        ],
        "rasio": 7,
        "status": "tervalidasi-pada-pengalaman",
        "bukti": {
          "jumlahPengamatan": 358,
          "bobotTerverifikasi": 4,
          "galatMaks": 0,
          "rasioTerkonfirmasi": 7,
          "pengamatanTerwakili": 358
        }
      },
      "seed": 10,
      "soalPerSeed": 5,
      "totals": {
        "decodeModel": "50/50",
        "decodeHafalan": "0/50",
        "baselineEndToEnd": "0/50",
        "baselineNumericOnly": "0/50",
        "learnedEndToEnd": "50/50",
        "rataLangkahKognitif": 6,
        "rataEkuivalenPrimitif": 217326.5
      },
      "rows": [
        {
          "radix": 7,
          "seed": 0,
          "soal": 0,
          "stateA": [
            6,
            2,
            5,
            5,
            6,
            2,
            0,
            0
          ],
          "stateB": [
            0,
            4,
            0,
            1,
            1,
            4,
            0,
            0
          ],
          "nilaiA": 50000,
          "nilaiB": 70000,
          "benar": 120000,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 50000,
            "b": 70000,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 56667,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 56667,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 120000,
            "langkah": 6,
            "langkahPrimitif": 210002,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 0,
          "soal": 1,
          "stateA": [
            3,
            1,
            1,
            6,
            6,
            2,
            0,
            0
          ],
          "stateB": [
            5,
            2,
            2,
            1,
            1,
            4,
            0,
            0
          ],
          "nilaiA": 50137,
          "nilaiB": 70089,
          "benar": 120226,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 50137,
            "b": 70089,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 56804,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 56804,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 120226,
            "langkah": 6,
            "langkahPrimitif": 210269,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 0,
          "soal": 2,
          "stateA": [
            0,
            0,
            4,
            6,
            6,
            2,
            0,
            0
          ],
          "stateB": [
            3,
            1,
            4,
            1,
            1,
            4,
            0,
            0
          ],
          "nilaiA": 50274,
          "nilaiB": 70178,
          "benar": 120452,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 50274,
            "b": 70178,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 56941,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 56941,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 120452,
            "langkah": 6,
            "langkahPrimitif": 210536,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 0,
          "soal": 3,
          "stateA": [
            4,
            5,
            6,
            6,
            6,
            2,
            0,
            0
          ],
          "stateB": [
            1,
            0,
            6,
            1,
            1,
            4,
            0,
            0
          ],
          "nilaiA": 50411,
          "nilaiB": 70267,
          "benar": 120678,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 50411,
            "b": 70267,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 57078,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 57078,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 120678,
            "langkah": 6,
            "langkahPrimitif": 210803,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 0,
          "soal": 4,
          "stateA": [
            1,
            4,
            2,
            0,
            0,
            3,
            0,
            0
          ],
          "stateB": [
            6,
            5,
            0,
            2,
            1,
            4,
            0,
            0
          ],
          "nilaiA": 50548,
          "nilaiB": 70356,
          "benar": 120904,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 50548,
            "b": 70356,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 57215,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 57215,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 120904,
            "langkah": 6,
            "langkahPrimitif": 211070,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 1,
          "soal": 0,
          "stateA": [
            0,
            0,
            5,
            1,
            0,
            3,
            0,
            0
          ],
          "stateB": [
            6,
            5,
            3,
            2,
            1,
            4,
            0,
            0
          ],
          "nilaiA": 51009,
          "nilaiB": 70503,
          "benar": 121512,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 51009,
            "b": 70503,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 57676,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 57676,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 121512,
            "langkah": 6,
            "langkahPrimitif": 211511,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 1,
          "soal": 1,
          "stateA": [
            4,
            5,
            0,
            2,
            0,
            3,
            0,
            0
          ],
          "stateB": [
            4,
            4,
            5,
            2,
            1,
            4,
            0,
            0
          ],
          "nilaiA": 51146,
          "nilaiB": 70592,
          "benar": 121738,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 51146,
            "b": 70592,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 57813,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 57813,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 121738,
            "langkah": 6,
            "langkahPrimitif": 211778,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 1,
          "soal": 2,
          "stateA": [
            1,
            4,
            3,
            2,
            0,
            3,
            0,
            0
          ],
          "stateB": [
            2,
            3,
            0,
            3,
            1,
            4,
            0,
            0
          ],
          "nilaiA": 51283,
          "nilaiB": 70681,
          "benar": 121964,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 51283,
            "b": 70681,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 57950,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 57950,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 121964,
            "langkah": 6,
            "langkahPrimitif": 212045,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 1,
          "soal": 3,
          "stateA": [
            5,
            2,
            6,
            2,
            0,
            3,
            0,
            0
          ],
          "stateB": [
            0,
            2,
            2,
            3,
            1,
            4,
            0,
            0
          ],
          "nilaiA": 51420,
          "nilaiB": 70770,
          "benar": 122190,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 51420,
            "b": 70770,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 58087,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 58087,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 122190,
            "langkah": 6,
            "langkahPrimitif": 212312,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 1,
          "soal": 4,
          "stateA": [
            2,
            1,
            2,
            3,
            0,
            3,
            0,
            0
          ],
          "stateB": [
            5,
            0,
            4,
            3,
            1,
            4,
            0,
            0
          ],
          "nilaiA": 51557,
          "nilaiB": 70859,
          "benar": 122416,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 51557,
            "b": 70859,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 58224,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 58224,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 122416,
            "langkah": 6,
            "langkahPrimitif": 212579,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 2,
          "soal": 0,
          "stateA": [
            1,
            4,
            4,
            4,
            0,
            3,
            0,
            0
          ],
          "stateB": [
            5,
            0,
            0,
            4,
            1,
            4,
            0,
            0
          ],
          "nilaiA": 52018,
          "nilaiB": 71006,
          "benar": 123024,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 52018,
            "b": 71006,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 58685,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 58685,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 123024,
            "langkah": 6,
            "langkahPrimitif": 213020,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 2,
          "soal": 1,
          "stateA": [
            5,
            2,
            0,
            5,
            0,
            3,
            0,
            0
          ],
          "stateB": [
            3,
            6,
            1,
            4,
            1,
            4,
            0,
            0
          ],
          "nilaiA": 52155,
          "nilaiB": 71095,
          "benar": 123250,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 52155,
            "b": 71095,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 58822,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 58822,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 123250,
            "langkah": 6,
            "langkahPrimitif": 213287,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 2,
          "soal": 2,
          "stateA": [
            2,
            1,
            3,
            5,
            0,
            3,
            0,
            0
          ],
          "stateB": [
            1,
            5,
            3,
            4,
            1,
            4,
            0,
            0
          ],
          "nilaiA": 52292,
          "nilaiB": 71184,
          "benar": 123476,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 52292,
            "b": 71184,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 58959,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 58959,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 123476,
            "langkah": 6,
            "langkahPrimitif": 213554,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 2,
          "soal": 3,
          "stateA": [
            6,
            6,
            5,
            5,
            0,
            3,
            0,
            0
          ],
          "stateB": [
            6,
            3,
            5,
            4,
            1,
            4,
            0,
            0
          ],
          "nilaiA": 52429,
          "nilaiB": 71273,
          "benar": 123702,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 52429,
            "b": 71273,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 59096,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 59096,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 123702,
            "langkah": 6,
            "langkahPrimitif": 213821,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 2,
          "soal": 4,
          "stateA": [
            3,
            5,
            1,
            6,
            0,
            3,
            0,
            0
          ],
          "stateB": [
            4,
            2,
            0,
            5,
            1,
            4,
            0,
            0
          ],
          "nilaiA": 52566,
          "nilaiB": 71362,
          "benar": 123928,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 52566,
            "b": 71362,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 59233,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 59233,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 123928,
            "langkah": 6,
            "langkahPrimitif": 214088,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 3,
          "soal": 0,
          "stateA": [
            2,
            1,
            4,
            0,
            1,
            3,
            0,
            0
          ],
          "stateB": [
            4,
            2,
            3,
            5,
            1,
            4,
            0,
            0
          ],
          "nilaiA": 53027,
          "nilaiB": 71509,
          "benar": 124536,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 53027,
            "b": 71509,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 59694,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 59694,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 124536,
            "langkah": 6,
            "langkahPrimitif": 214529,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 3,
          "soal": 1,
          "stateA": [
            6,
            6,
            6,
            0,
            1,
            3,
            0,
            0
          ],
          "stateB": [
            2,
            1,
            5,
            5,
            1,
            4,
            0,
            0
          ],
          "nilaiA": 53164,
          "nilaiB": 71598,
          "benar": 124762,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 53164,
            "b": 71598,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 59831,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 59831,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 124762,
            "langkah": 6,
            "langkahPrimitif": 214796,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 3,
          "soal": 2,
          "stateA": [
            3,
            5,
            2,
            1,
            1,
            3,
            0,
            0
          ],
          "stateB": [
            0,
            0,
            0,
            6,
            1,
            4,
            0,
            0
          ],
          "nilaiA": 53301,
          "nilaiB": 71687,
          "benar": 124988,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 53301,
            "b": 71687,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 59968,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 59968,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 124988,
            "langkah": 6,
            "langkahPrimitif": 215063,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 3,
          "soal": 3,
          "stateA": [
            0,
            4,
            5,
            1,
            1,
            3,
            0,
            0
          ],
          "stateB": [
            5,
            5,
            1,
            6,
            1,
            4,
            0,
            0
          ],
          "nilaiA": 53438,
          "nilaiB": 71776,
          "benar": 125214,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 53438,
            "b": 71776,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 60105,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 60105,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 125214,
            "langkah": 6,
            "langkahPrimitif": 215330,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 3,
          "soal": 4,
          "stateA": [
            4,
            2,
            1,
            2,
            1,
            3,
            0,
            0
          ],
          "stateB": [
            3,
            4,
            3,
            6,
            1,
            4,
            0,
            0
          ],
          "nilaiA": 53575,
          "nilaiB": 71865,
          "benar": 125440,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 53575,
            "b": 71865,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 60242,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 60242,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 125440,
            "langkah": 6,
            "langkahPrimitif": 215597,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 4,
          "soal": 0,
          "stateA": [
            3,
            5,
            3,
            3,
            1,
            3,
            0,
            0
          ],
          "stateB": [
            3,
            4,
            6,
            6,
            1,
            4,
            0,
            0
          ],
          "nilaiA": 54036,
          "nilaiB": 72012,
          "benar": 126048,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 54036,
            "b": 72012,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 60703,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 60703,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 126048,
            "langkah": 6,
            "langkahPrimitif": 216038,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 4,
          "soal": 1,
          "stateA": [
            0,
            4,
            6,
            3,
            1,
            3,
            0,
            0
          ],
          "stateB": [
            1,
            3,
            1,
            0,
            2,
            4,
            0,
            0
          ],
          "nilaiA": 54173,
          "nilaiB": 72101,
          "benar": 126274,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 54173,
            "b": 72101,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 60840,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 60840,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 126274,
            "langkah": 6,
            "langkahPrimitif": 216305,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 4,
          "soal": 2,
          "stateA": [
            4,
            2,
            2,
            4,
            1,
            3,
            0,
            0
          ],
          "stateB": [
            6,
            1,
            3,
            0,
            2,
            4,
            0,
            0
          ],
          "nilaiA": 54310,
          "nilaiB": 72190,
          "benar": 126500,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 54310,
            "b": 72190,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 60977,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 60977,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 126500,
            "langkah": 6,
            "langkahPrimitif": 216572,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 4,
          "soal": 3,
          "stateA": [
            1,
            1,
            5,
            4,
            1,
            3,
            0,
            0
          ],
          "stateB": [
            4,
            0,
            5,
            0,
            2,
            4,
            0,
            0
          ],
          "nilaiA": 54447,
          "nilaiB": 72279,
          "benar": 126726,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 54447,
            "b": 72279,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 61114,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 61114,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 126726,
            "langkah": 6,
            "langkahPrimitif": 216839,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 4,
          "soal": 4,
          "stateA": [
            5,
            6,
            0,
            5,
            1,
            3,
            0,
            0
          ],
          "stateB": [
            2,
            6,
            6,
            0,
            2,
            4,
            0,
            0
          ],
          "nilaiA": 54584,
          "nilaiB": 72368,
          "benar": 126952,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 54584,
            "b": 72368,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 61251,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 61251,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 126952,
            "langkah": 6,
            "langkahPrimitif": 217106,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 5,
          "soal": 0,
          "stateA": [
            4,
            2,
            3,
            6,
            1,
            3,
            0,
            0
          ],
          "stateB": [
            2,
            6,
            2,
            1,
            2,
            4,
            0,
            0
          ],
          "nilaiA": 55045,
          "nilaiB": 72515,
          "benar": 127560,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 55045,
            "b": 72515,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 61712,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 61712,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 127560,
            "langkah": 6,
            "langkahPrimitif": 217547,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 5,
          "soal": 1,
          "stateA": [
            1,
            1,
            6,
            6,
            1,
            3,
            0,
            0
          ],
          "stateB": [
            0,
            5,
            4,
            1,
            2,
            4,
            0,
            0
          ],
          "nilaiA": 55182,
          "nilaiB": 72604,
          "benar": 127786,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 55182,
            "b": 72604,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 61849,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 61849,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 127786,
            "langkah": 6,
            "langkahPrimitif": 217814,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 5,
          "soal": 2,
          "stateA": [
            5,
            6,
            1,
            0,
            2,
            3,
            0,
            0
          ],
          "stateB": [
            5,
            3,
            6,
            1,
            2,
            4,
            0,
            0
          ],
          "nilaiA": 55319,
          "nilaiB": 72693,
          "benar": 128012,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 55319,
            "b": 72693,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 61986,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 61986,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 128012,
            "langkah": 6,
            "langkahPrimitif": 218081,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 5,
          "soal": 3,
          "stateA": [
            2,
            5,
            4,
            0,
            2,
            3,
            0,
            0
          ],
          "stateB": [
            3,
            2,
            1,
            2,
            2,
            4,
            0,
            0
          ],
          "nilaiA": 55456,
          "nilaiB": 72782,
          "benar": 128238,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 55456,
            "b": 72782,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 62123,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 62123,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 128238,
            "langkah": 6,
            "langkahPrimitif": 218348,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 5,
          "soal": 4,
          "stateA": [
            6,
            3,
            0,
            1,
            2,
            3,
            0,
            0
          ],
          "stateB": [
            1,
            1,
            3,
            2,
            2,
            4,
            0,
            0
          ],
          "nilaiA": 55593,
          "nilaiB": 72871,
          "benar": 128464,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 55593,
            "b": 72871,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 62260,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 62260,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 128464,
            "langkah": 6,
            "langkahPrimitif": 218615,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 6,
          "soal": 0,
          "stateA": [
            5,
            6,
            2,
            2,
            2,
            3,
            0,
            0
          ],
          "stateB": [
            1,
            1,
            6,
            2,
            2,
            4,
            0,
            0
          ],
          "nilaiA": 56054,
          "nilaiB": 73018,
          "benar": 129072,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 56054,
            "b": 73018,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 62721,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 62721,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 129072,
            "langkah": 6,
            "langkahPrimitif": 219056,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 6,
          "soal": 1,
          "stateA": [
            2,
            5,
            5,
            2,
            2,
            3,
            0,
            0
          ],
          "stateB": [
            6,
            6,
            0,
            3,
            2,
            4,
            0,
            0
          ],
          "nilaiA": 56191,
          "nilaiB": 73107,
          "benar": 129298,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 56191,
            "b": 73107,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 62858,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 62858,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 129298,
            "langkah": 6,
            "langkahPrimitif": 219323,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 6,
          "soal": 2,
          "stateA": [
            6,
            3,
            1,
            3,
            2,
            3,
            0,
            0
          ],
          "stateB": [
            4,
            5,
            2,
            3,
            2,
            4,
            0,
            0
          ],
          "nilaiA": 56328,
          "nilaiB": 73196,
          "benar": 129524,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 56328,
            "b": 73196,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 62995,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 62995,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 129524,
            "langkah": 6,
            "langkahPrimitif": 219590,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 6,
          "soal": 3,
          "stateA": [
            3,
            2,
            4,
            3,
            2,
            3,
            0,
            0
          ],
          "stateB": [
            2,
            4,
            4,
            3,
            2,
            4,
            0,
            0
          ],
          "nilaiA": 56465,
          "nilaiB": 73285,
          "benar": 129750,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 56465,
            "b": 73285,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 63132,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 63132,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 129750,
            "langkah": 6,
            "langkahPrimitif": 219857,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 6,
          "soal": 4,
          "stateA": [
            0,
            1,
            0,
            4,
            2,
            3,
            0,
            0
          ],
          "stateB": [
            0,
            3,
            6,
            3,
            2,
            4,
            0,
            0
          ],
          "nilaiA": 56602,
          "nilaiB": 73374,
          "benar": 129976,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 56602,
            "b": 73374,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 63269,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 63269,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 129976,
            "langkah": 6,
            "langkahPrimitif": 220124,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 7,
          "soal": 0,
          "stateA": [
            6,
            3,
            2,
            5,
            2,
            3,
            0,
            0
          ],
          "stateB": [
            0,
            3,
            2,
            4,
            2,
            4,
            0,
            0
          ],
          "nilaiA": 57063,
          "nilaiB": 73521,
          "benar": 130584,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 57063,
            "b": 73521,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 63730,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 63730,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 130584,
            "langkah": 6,
            "langkahPrimitif": 220565,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 7,
          "soal": 1,
          "stateA": [
            3,
            2,
            5,
            5,
            2,
            3,
            0,
            0
          ],
          "stateB": [
            5,
            1,
            4,
            4,
            2,
            4,
            0,
            0
          ],
          "nilaiA": 57200,
          "nilaiB": 73610,
          "benar": 130810,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 57200,
            "b": 73610,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 63867,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 63867,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 130810,
            "langkah": 6,
            "langkahPrimitif": 220832,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 7,
          "soal": 2,
          "stateA": [
            0,
            1,
            1,
            6,
            2,
            3,
            0,
            0
          ],
          "stateB": [
            3,
            0,
            6,
            4,
            2,
            4,
            0,
            0
          ],
          "nilaiA": 57337,
          "nilaiB": 73699,
          "benar": 131036,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 57337,
            "b": 73699,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 64004,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 64004,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 131036,
            "langkah": 6,
            "langkahPrimitif": 221099,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 7,
          "soal": 3,
          "stateA": [
            4,
            6,
            3,
            6,
            2,
            3,
            0,
            0
          ],
          "stateB": [
            1,
            6,
            0,
            5,
            2,
            4,
            0,
            0
          ],
          "nilaiA": 57474,
          "nilaiB": 73788,
          "benar": 131262,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 57474,
            "b": 73788,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 64141,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 64141,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 131262,
            "langkah": 6,
            "langkahPrimitif": 221366,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 7,
          "soal": 4,
          "stateA": [
            1,
            5,
            6,
            6,
            2,
            3,
            0,
            0
          ],
          "stateB": [
            6,
            4,
            2,
            5,
            2,
            4,
            0,
            0
          ],
          "nilaiA": 57611,
          "nilaiB": 73877,
          "benar": 131488,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 57611,
            "b": 73877,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 64278,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 64278,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 131488,
            "langkah": 6,
            "langkahPrimitif": 221633,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 8,
          "soal": 0,
          "stateA": [
            0,
            1,
            2,
            1,
            3,
            3,
            0,
            0
          ],
          "stateB": [
            6,
            4,
            5,
            5,
            2,
            4,
            0,
            0
          ],
          "nilaiA": 58072,
          "nilaiB": 74024,
          "benar": 132096,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 58072,
            "b": 74024,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 64739,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 64739,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 132096,
            "langkah": 6,
            "langkahPrimitif": 222074,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 8,
          "soal": 1,
          "stateA": [
            4,
            6,
            4,
            1,
            3,
            3,
            0,
            0
          ],
          "stateB": [
            4,
            3,
            0,
            6,
            2,
            4,
            0,
            0
          ],
          "nilaiA": 58209,
          "nilaiB": 74113,
          "benar": 132322,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 58209,
            "b": 74113,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 64876,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 64876,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 132322,
            "langkah": 6,
            "langkahPrimitif": 222341,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 8,
          "soal": 2,
          "stateA": [
            1,
            5,
            0,
            2,
            3,
            3,
            0,
            0
          ],
          "stateB": [
            2,
            2,
            2,
            6,
            2,
            4,
            0,
            0
          ],
          "nilaiA": 58346,
          "nilaiB": 74202,
          "benar": 132548,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 58346,
            "b": 74202,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 65013,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 65013,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 132548,
            "langkah": 6,
            "langkahPrimitif": 222608,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 8,
          "soal": 3,
          "stateA": [
            5,
            3,
            3,
            2,
            3,
            3,
            0,
            0
          ],
          "stateB": [
            0,
            1,
            4,
            6,
            2,
            4,
            0,
            0
          ],
          "nilaiA": 58483,
          "nilaiB": 74291,
          "benar": 132774,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 58483,
            "b": 74291,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 65150,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 65150,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 132774,
            "langkah": 6,
            "langkahPrimitif": 222875,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 8,
          "soal": 4,
          "stateA": [
            2,
            2,
            6,
            2,
            3,
            3,
            0,
            0
          ],
          "stateB": [
            5,
            6,
            5,
            6,
            2,
            4,
            0,
            0
          ],
          "nilaiA": 58620,
          "nilaiB": 74380,
          "benar": 133000,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 58620,
            "b": 74380,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 65287,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 65287,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 133000,
            "langkah": 6,
            "langkahPrimitif": 223142,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 9,
          "soal": 0,
          "stateA": [
            1,
            5,
            1,
            4,
            3,
            3,
            0,
            0
          ],
          "stateB": [
            5,
            6,
            1,
            0,
            3,
            4,
            0,
            0
          ],
          "nilaiA": 59081,
          "nilaiB": 74527,
          "benar": 133608,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 59081,
            "b": 74527,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 65748,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 65748,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 133608,
            "langkah": 6,
            "langkahPrimitif": 223583,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 9,
          "soal": 1,
          "stateA": [
            5,
            3,
            4,
            4,
            3,
            3,
            0,
            0
          ],
          "stateB": [
            3,
            5,
            3,
            0,
            3,
            4,
            0,
            0
          ],
          "nilaiA": 59218,
          "nilaiB": 74616,
          "benar": 133834,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 59218,
            "b": 74616,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 65885,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 65885,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 133834,
            "langkah": 6,
            "langkahPrimitif": 223850,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 9,
          "soal": 2,
          "stateA": [
            2,
            2,
            0,
            5,
            3,
            3,
            0,
            0
          ],
          "stateB": [
            1,
            4,
            5,
            0,
            3,
            4,
            0,
            0
          ],
          "nilaiA": 59355,
          "nilaiB": 74705,
          "benar": 134060,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 59355,
            "b": 74705,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 66022,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 66022,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 134060,
            "langkah": 6,
            "langkahPrimitif": 224117,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 9,
          "soal": 3,
          "stateA": [
            6,
            0,
            3,
            5,
            3,
            3,
            0,
            0
          ],
          "stateB": [
            6,
            2,
            0,
            1,
            3,
            4,
            0,
            0
          ],
          "nilaiA": 59492,
          "nilaiB": 74794,
          "benar": 134286,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 59492,
            "b": 74794,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 66159,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 66159,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 134286,
            "langkah": 6,
            "langkahPrimitif": 224384,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 7,
          "seed": 9,
          "soal": 4,
          "stateA": [
            3,
            6,
            5,
            5,
            3,
            3,
            0,
            0
          ],
          "stateB": [
            4,
            1,
            2,
            1,
            3,
            4,
            0,
            0
          ],
          "nilaiA": 59629,
          "nilaiB": 74883,
          "benar": 134512,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 59629,
            "b": 74883,
            "lulus": true,
            "bobot": [
              1,
              7,
              49,
              343
            ],
            "rasio": 7
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 66296,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 66296,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 134512,
            "langkah": 6,
            "langkahPrimitif": 224651,
            "status": "terjawab",
            "lulus": true
          }
        }
      ]
    },
    {
      "radix": 6,
      "trainThrough": 228,
      "trainSamples": 229,
      "model": {
        "bobot": [
          1,
          6,
          36,
          216
        ],
        "rasio": 6,
        "status": "tervalidasi-pada-pengalaman",
        "bukti": {
          "jumlahPengamatan": 229,
          "bobotTerverifikasi": 4,
          "galatMaks": 0,
          "rasioTerkonfirmasi": 6,
          "pengamatanTerwakili": 229
        }
      },
      "seed": 10,
      "soalPerSeed": 5,
      "totals": {
        "decodeModel": "50/50",
        "decodeHafalan": "0/50",
        "baselineEndToEnd": "0/50",
        "baselineNumericOnly": "0/50",
        "learnedEndToEnd": "50/50",
        "rataLangkahKognitif": 6,
        "rataEkuivalenPrimitif": 217326.5
      },
      "rows": [
        {
          "radix": 6,
          "seed": 0,
          "soal": 0,
          "stateA": [
            2,
            5,
            2,
            3,
            2,
            0,
            1,
            0
          ],
          "stateB": [
            4,
            2,
            0,
            0,
            0,
            3,
            1,
            0
          ],
          "nilaiA": 50000,
          "nilaiB": 70000,
          "benar": 120000,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 50000,
            "b": 70000,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 56667,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 56667,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 120000,
            "langkah": 6,
            "langkahPrimitif": 210002,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 0,
          "soal": 1,
          "stateA": [
            1,
            4,
            0,
            4,
            2,
            0,
            1,
            0
          ],
          "stateB": [
            3,
            5,
            2,
            0,
            0,
            3,
            1,
            0
          ],
          "nilaiA": 50137,
          "nilaiB": 70089,
          "benar": 120226,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 50137,
            "b": 70089,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 56804,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 56804,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 120226,
            "langkah": 6,
            "langkahPrimitif": 210269,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 0,
          "soal": 2,
          "stateA": [
            0,
            3,
            4,
            4,
            2,
            0,
            1,
            0
          ],
          "stateB": [
            2,
            2,
            5,
            0,
            0,
            3,
            1,
            0
          ],
          "nilaiA": 50274,
          "nilaiB": 70178,
          "benar": 120452,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 50274,
            "b": 70178,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 56941,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 56941,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 120452,
            "langkah": 6,
            "langkahPrimitif": 210536,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 0,
          "soal": 3,
          "stateA": [
            5,
            1,
            2,
            5,
            2,
            0,
            1,
            0
          ],
          "stateB": [
            1,
            5,
            1,
            1,
            0,
            3,
            1,
            0
          ],
          "nilaiA": 50411,
          "nilaiB": 70267,
          "benar": 120678,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 50411,
            "b": 70267,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 57078,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 57078,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 120678,
            "langkah": 6,
            "langkahPrimitif": 210803,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 0,
          "soal": 4,
          "stateA": [
            4,
            0,
            0,
            0,
            3,
            0,
            1,
            0
          ],
          "stateB": [
            0,
            2,
            4,
            1,
            0,
            3,
            1,
            0
          ],
          "nilaiA": 50548,
          "nilaiB": 70356,
          "benar": 120904,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 50548,
            "b": 70356,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 57215,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 57215,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 120904,
            "langkah": 6,
            "langkahPrimitif": 211070,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 1,
          "soal": 0,
          "stateA": [
            3,
            5,
            0,
            2,
            3,
            0,
            1,
            0
          ],
          "stateB": [
            3,
            2,
            2,
            2,
            0,
            3,
            1,
            0
          ],
          "nilaiA": 51009,
          "nilaiB": 70503,
          "benar": 121512,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 51009,
            "b": 70503,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 57676,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 57676,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 121512,
            "langkah": 6,
            "langkahPrimitif": 211511,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 1,
          "soal": 1,
          "stateA": [
            2,
            4,
            4,
            2,
            3,
            0,
            1,
            0
          ],
          "stateB": [
            2,
            5,
            4,
            2,
            0,
            3,
            1,
            0
          ],
          "nilaiA": 51146,
          "nilaiB": 70592,
          "benar": 121738,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 51146,
            "b": 70592,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 57813,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 57813,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 121738,
            "langkah": 6,
            "langkahPrimitif": 211778,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 1,
          "soal": 2,
          "stateA": [
            1,
            3,
            2,
            3,
            3,
            0,
            1,
            0
          ],
          "stateB": [
            1,
            2,
            1,
            3,
            0,
            3,
            1,
            0
          ],
          "nilaiA": 51283,
          "nilaiB": 70681,
          "benar": 121964,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 51283,
            "b": 70681,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 57950,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 57950,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 121964,
            "langkah": 6,
            "langkahPrimitif": 212045,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 1,
          "soal": 3,
          "stateA": [
            0,
            2,
            0,
            4,
            3,
            0,
            1,
            0
          ],
          "stateB": [
            0,
            5,
            3,
            3,
            0,
            3,
            1,
            0
          ],
          "nilaiA": 51420,
          "nilaiB": 70770,
          "benar": 122190,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 51420,
            "b": 70770,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 58087,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 58087,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 122190,
            "langkah": 6,
            "langkahPrimitif": 212312,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 1,
          "soal": 4,
          "stateA": [
            5,
            0,
            4,
            4,
            3,
            0,
            1,
            0
          ],
          "stateB": [
            5,
            1,
            0,
            4,
            0,
            3,
            1,
            0
          ],
          "nilaiA": 51557,
          "nilaiB": 70859,
          "benar": 122416,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 51557,
            "b": 70859,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 58224,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 58224,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 122416,
            "langkah": 6,
            "langkahPrimitif": 212579,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 2,
          "soal": 0,
          "stateA": [
            4,
            5,
            4,
            0,
            4,
            0,
            1,
            0
          ],
          "stateB": [
            2,
            2,
            4,
            4,
            0,
            3,
            1,
            0
          ],
          "nilaiA": 52018,
          "nilaiB": 71006,
          "benar": 123024,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 52018,
            "b": 71006,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 58685,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 58685,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 123024,
            "langkah": 6,
            "langkahPrimitif": 213020,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 2,
          "soal": 1,
          "stateA": [
            3,
            4,
            2,
            1,
            4,
            0,
            1,
            0
          ],
          "stateB": [
            1,
            5,
            0,
            5,
            0,
            3,
            1,
            0
          ],
          "nilaiA": 52155,
          "nilaiB": 71095,
          "benar": 123250,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 52155,
            "b": 71095,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 58822,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 58822,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 123250,
            "langkah": 6,
            "langkahPrimitif": 213287,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 2,
          "soal": 2,
          "stateA": [
            2,
            3,
            0,
            2,
            4,
            0,
            1,
            0
          ],
          "stateB": [
            0,
            2,
            3,
            5,
            0,
            3,
            1,
            0
          ],
          "nilaiA": 52292,
          "nilaiB": 71184,
          "benar": 123476,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 52292,
            "b": 71184,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 58959,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 58959,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 123476,
            "langkah": 6,
            "langkahPrimitif": 213554,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 2,
          "soal": 3,
          "stateA": [
            1,
            2,
            4,
            2,
            4,
            0,
            1,
            0
          ],
          "stateB": [
            5,
            4,
            5,
            5,
            0,
            3,
            1,
            0
          ],
          "nilaiA": 52429,
          "nilaiB": 71273,
          "benar": 123702,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 52429,
            "b": 71273,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 59096,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 59096,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 123702,
            "langkah": 6,
            "langkahPrimitif": 213821,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 2,
          "soal": 4,
          "stateA": [
            0,
            1,
            2,
            3,
            4,
            0,
            1,
            0
          ],
          "stateB": [
            4,
            1,
            2,
            0,
            1,
            3,
            1,
            0
          ],
          "nilaiA": 52566,
          "nilaiB": 71362,
          "benar": 123928,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 52566,
            "b": 71362,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 59233,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 59233,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 123928,
            "langkah": 6,
            "langkahPrimitif": 214088,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 3,
          "soal": 0,
          "stateA": [
            5,
            5,
            2,
            5,
            4,
            0,
            1,
            0
          ],
          "stateB": [
            1,
            2,
            0,
            1,
            1,
            3,
            1,
            0
          ],
          "nilaiA": 53027,
          "nilaiB": 71509,
          "benar": 124536,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 53027,
            "b": 71509,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 59694,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 59694,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 124536,
            "langkah": 6,
            "langkahPrimitif": 214529,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 3,
          "soal": 1,
          "stateA": [
            4,
            4,
            0,
            0,
            5,
            0,
            1,
            0
          ],
          "stateB": [
            0,
            5,
            2,
            1,
            1,
            3,
            1,
            0
          ],
          "nilaiA": 53164,
          "nilaiB": 71598,
          "benar": 124762,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 53164,
            "b": 71598,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 59831,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 59831,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 124762,
            "langkah": 6,
            "langkahPrimitif": 214796,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 3,
          "soal": 2,
          "stateA": [
            3,
            3,
            4,
            0,
            5,
            0,
            1,
            0
          ],
          "stateB": [
            5,
            1,
            5,
            1,
            1,
            3,
            1,
            0
          ],
          "nilaiA": 53301,
          "nilaiB": 71687,
          "benar": 124988,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 53301,
            "b": 71687,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 59968,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 59968,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 124988,
            "langkah": 6,
            "langkahPrimitif": 215063,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 3,
          "soal": 3,
          "stateA": [
            2,
            2,
            2,
            1,
            5,
            0,
            1,
            0
          ],
          "stateB": [
            4,
            4,
            1,
            2,
            1,
            3,
            1,
            0
          ],
          "nilaiA": 53438,
          "nilaiB": 71776,
          "benar": 125214,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 53438,
            "b": 71776,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 60105,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 60105,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 125214,
            "langkah": 6,
            "langkahPrimitif": 215330,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 3,
          "soal": 4,
          "stateA": [
            1,
            1,
            0,
            2,
            5,
            0,
            1,
            0
          ],
          "stateB": [
            3,
            1,
            4,
            2,
            1,
            3,
            1,
            0
          ],
          "nilaiA": 53575,
          "nilaiB": 71865,
          "benar": 125440,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 53575,
            "b": 71865,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 60242,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 60242,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 125440,
            "langkah": 6,
            "langkahPrimitif": 215597,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 4,
          "soal": 0,
          "stateA": [
            0,
            0,
            1,
            4,
            5,
            0,
            1,
            0
          ],
          "stateB": [
            0,
            2,
            2,
            3,
            1,
            3,
            1,
            0
          ],
          "nilaiA": 54036,
          "nilaiB": 72012,
          "benar": 126048,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 54036,
            "b": 72012,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 60703,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 60703,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 126048,
            "langkah": 6,
            "langkahPrimitif": 216038,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 4,
          "soal": 1,
          "stateA": [
            5,
            4,
            4,
            4,
            5,
            0,
            1,
            0
          ],
          "stateB": [
            5,
            4,
            4,
            3,
            1,
            3,
            1,
            0
          ],
          "nilaiA": 54173,
          "nilaiB": 72101,
          "benar": 126274,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 54173,
            "b": 72101,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 60840,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 60840,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 126274,
            "langkah": 6,
            "langkahPrimitif": 216305,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 4,
          "soal": 2,
          "stateA": [
            4,
            3,
            2,
            5,
            5,
            0,
            1,
            0
          ],
          "stateB": [
            4,
            1,
            1,
            4,
            1,
            3,
            1,
            0
          ],
          "nilaiA": 54310,
          "nilaiB": 72190,
          "benar": 126500,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 54310,
            "b": 72190,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 60977,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 60977,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 126500,
            "langkah": 6,
            "langkahPrimitif": 216572,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 4,
          "soal": 3,
          "stateA": [
            3,
            2,
            0,
            0,
            0,
            1,
            1,
            0
          ],
          "stateB": [
            3,
            4,
            3,
            4,
            1,
            3,
            1,
            0
          ],
          "nilaiA": 54447,
          "nilaiB": 72279,
          "benar": 126726,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 54447,
            "b": 72279,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 61114,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 61114,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 126726,
            "langkah": 6,
            "langkahPrimitif": 216839,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 4,
          "soal": 4,
          "stateA": [
            2,
            1,
            4,
            0,
            0,
            1,
            1,
            0
          ],
          "stateB": [
            2,
            1,
            0,
            5,
            1,
            3,
            1,
            0
          ],
          "nilaiA": 54584,
          "nilaiB": 72368,
          "benar": 126952,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 54584,
            "b": 72368,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 61251,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 61251,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 126952,
            "langkah": 6,
            "langkahPrimitif": 217106,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 5,
          "soal": 0,
          "stateA": [
            1,
            0,
            5,
            2,
            0,
            1,
            1,
            0
          ],
          "stateB": [
            5,
            1,
            4,
            5,
            1,
            3,
            1,
            0
          ],
          "nilaiA": 55045,
          "nilaiB": 72515,
          "benar": 127560,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 55045,
            "b": 72515,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 61712,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 61712,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 127560,
            "langkah": 6,
            "langkahPrimitif": 217547,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 5,
          "soal": 1,
          "stateA": [
            0,
            5,
            2,
            3,
            0,
            1,
            1,
            0
          ],
          "stateB": [
            4,
            4,
            0,
            0,
            2,
            3,
            1,
            0
          ],
          "nilaiA": 55182,
          "nilaiB": 72604,
          "benar": 127786,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 55182,
            "b": 72604,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 61849,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 61849,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 127786,
            "langkah": 6,
            "langkahPrimitif": 217814,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 5,
          "soal": 2,
          "stateA": [
            5,
            3,
            0,
            4,
            0,
            1,
            1,
            0
          ],
          "stateB": [
            3,
            1,
            3,
            0,
            2,
            3,
            1,
            0
          ],
          "nilaiA": 55319,
          "nilaiB": 72693,
          "benar": 128012,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 55319,
            "b": 72693,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 61986,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 61986,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 128012,
            "langkah": 6,
            "langkahPrimitif": 218081,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 5,
          "soal": 3,
          "stateA": [
            4,
            2,
            4,
            4,
            0,
            1,
            1,
            0
          ],
          "stateB": [
            2,
            4,
            5,
            0,
            2,
            3,
            1,
            0
          ],
          "nilaiA": 55456,
          "nilaiB": 72782,
          "benar": 128238,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 55456,
            "b": 72782,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 62123,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 62123,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 128238,
            "langkah": 6,
            "langkahPrimitif": 218348,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 5,
          "soal": 4,
          "stateA": [
            3,
            1,
            2,
            5,
            0,
            1,
            1,
            0
          ],
          "stateB": [
            1,
            1,
            2,
            1,
            2,
            3,
            1,
            0
          ],
          "nilaiA": 55593,
          "nilaiB": 72871,
          "benar": 128464,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 55593,
            "b": 72871,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 62260,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 62260,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 128464,
            "langkah": 6,
            "langkahPrimitif": 218615,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 6,
          "soal": 0,
          "stateA": [
            2,
            0,
            3,
            1,
            1,
            1,
            1,
            0
          ],
          "stateB": [
            4,
            1,
            0,
            2,
            2,
            3,
            1,
            0
          ],
          "nilaiA": 56054,
          "nilaiB": 73018,
          "benar": 129072,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 56054,
            "b": 73018,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 62721,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 62721,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 129072,
            "langkah": 6,
            "langkahPrimitif": 219056,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 6,
          "soal": 1,
          "stateA": [
            1,
            5,
            0,
            2,
            1,
            1,
            1,
            0
          ],
          "stateB": [
            3,
            4,
            2,
            2,
            2,
            3,
            1,
            0
          ],
          "nilaiA": 56191,
          "nilaiB": 73107,
          "benar": 129298,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 56191,
            "b": 73107,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 62858,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 62858,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 129298,
            "langkah": 6,
            "langkahPrimitif": 219323,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 6,
          "soal": 2,
          "stateA": [
            0,
            4,
            4,
            2,
            1,
            1,
            1,
            0
          ],
          "stateB": [
            2,
            1,
            5,
            2,
            2,
            3,
            1,
            0
          ],
          "nilaiA": 56328,
          "nilaiB": 73196,
          "benar": 129524,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 56328,
            "b": 73196,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 62995,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 62995,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 129524,
            "langkah": 6,
            "langkahPrimitif": 219590,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 6,
          "soal": 3,
          "stateA": [
            5,
            2,
            2,
            3,
            1,
            1,
            1,
            0
          ],
          "stateB": [
            1,
            4,
            1,
            3,
            2,
            3,
            1,
            0
          ],
          "nilaiA": 56465,
          "nilaiB": 73285,
          "benar": 129750,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 56465,
            "b": 73285,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 63132,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 63132,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 129750,
            "langkah": 6,
            "langkahPrimitif": 219857,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 6,
          "soal": 4,
          "stateA": [
            4,
            1,
            0,
            4,
            1,
            1,
            1,
            0
          ],
          "stateB": [
            0,
            1,
            4,
            3,
            2,
            3,
            1,
            0
          ],
          "nilaiA": 56602,
          "nilaiB": 73374,
          "benar": 129976,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 56602,
            "b": 73374,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 63269,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 63269,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 129976,
            "langkah": 6,
            "langkahPrimitif": 220124,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 7,
          "soal": 0,
          "stateA": [
            3,
            0,
            1,
            0,
            2,
            1,
            1,
            0
          ],
          "stateB": [
            3,
            1,
            2,
            4,
            2,
            3,
            1,
            0
          ],
          "nilaiA": 57063,
          "nilaiB": 73521,
          "benar": 130584,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 57063,
            "b": 73521,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 63730,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 63730,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 130584,
            "langkah": 6,
            "langkahPrimitif": 220565,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 7,
          "soal": 1,
          "stateA": [
            2,
            5,
            4,
            0,
            2,
            1,
            1,
            0
          ],
          "stateB": [
            2,
            4,
            4,
            4,
            2,
            3,
            1,
            0
          ],
          "nilaiA": 57200,
          "nilaiB": 73610,
          "benar": 130810,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 57200,
            "b": 73610,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 63867,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 63867,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 130810,
            "langkah": 6,
            "langkahPrimitif": 220832,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 7,
          "soal": 2,
          "stateA": [
            1,
            4,
            2,
            1,
            2,
            1,
            1,
            0
          ],
          "stateB": [
            1,
            1,
            1,
            5,
            2,
            3,
            1,
            0
          ],
          "nilaiA": 57337,
          "nilaiB": 73699,
          "benar": 131036,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 57337,
            "b": 73699,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 64004,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 64004,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 131036,
            "langkah": 6,
            "langkahPrimitif": 221099,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 7,
          "soal": 3,
          "stateA": [
            0,
            3,
            0,
            2,
            2,
            1,
            1,
            0
          ],
          "stateB": [
            0,
            4,
            3,
            5,
            2,
            3,
            1,
            0
          ],
          "nilaiA": 57474,
          "nilaiB": 73788,
          "benar": 131262,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 57474,
            "b": 73788,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 64141,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 64141,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 131262,
            "langkah": 6,
            "langkahPrimitif": 221366,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 7,
          "soal": 4,
          "stateA": [
            5,
            1,
            4,
            2,
            2,
            1,
            1,
            0
          ],
          "stateB": [
            5,
            0,
            0,
            0,
            3,
            3,
            1,
            0
          ],
          "nilaiA": 57611,
          "nilaiB": 73877,
          "benar": 131488,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 57611,
            "b": 73877,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 64278,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 64278,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 131488,
            "langkah": 6,
            "langkahPrimitif": 221633,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 8,
          "soal": 0,
          "stateA": [
            4,
            0,
            5,
            4,
            2,
            1,
            1,
            0
          ],
          "stateB": [
            2,
            1,
            4,
            0,
            3,
            3,
            1,
            0
          ],
          "nilaiA": 58072,
          "nilaiB": 74024,
          "benar": 132096,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 58072,
            "b": 74024,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 64739,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 64739,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 132096,
            "langkah": 6,
            "langkahPrimitif": 222074,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 8,
          "soal": 1,
          "stateA": [
            3,
            5,
            2,
            5,
            2,
            1,
            1,
            0
          ],
          "stateB": [
            1,
            4,
            0,
            1,
            3,
            3,
            1,
            0
          ],
          "nilaiA": 58209,
          "nilaiB": 74113,
          "benar": 132322,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 58209,
            "b": 74113,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 64876,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 64876,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 132322,
            "langkah": 6,
            "langkahPrimitif": 222341,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 8,
          "soal": 2,
          "stateA": [
            2,
            4,
            0,
            0,
            3,
            1,
            1,
            0
          ],
          "stateB": [
            0,
            1,
            3,
            1,
            3,
            3,
            1,
            0
          ],
          "nilaiA": 58346,
          "nilaiB": 74202,
          "benar": 132548,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 58346,
            "b": 74202,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 65013,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 65013,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 132548,
            "langkah": 6,
            "langkahPrimitif": 222608,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 8,
          "soal": 3,
          "stateA": [
            1,
            3,
            4,
            0,
            3,
            1,
            1,
            0
          ],
          "stateB": [
            5,
            3,
            5,
            1,
            3,
            3,
            1,
            0
          ],
          "nilaiA": 58483,
          "nilaiB": 74291,
          "benar": 132774,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 58483,
            "b": 74291,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 65150,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 65150,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 132774,
            "langkah": 6,
            "langkahPrimitif": 222875,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 8,
          "soal": 4,
          "stateA": [
            0,
            2,
            2,
            1,
            3,
            1,
            1,
            0
          ],
          "stateB": [
            4,
            0,
            2,
            2,
            3,
            3,
            1,
            0
          ],
          "nilaiA": 58620,
          "nilaiB": 74380,
          "benar": 133000,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 58620,
            "b": 74380,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 65287,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 65287,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 133000,
            "langkah": 6,
            "langkahPrimitif": 223142,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 9,
          "soal": 0,
          "stateA": [
            5,
            0,
            3,
            3,
            3,
            1,
            1,
            0
          ],
          "stateB": [
            1,
            1,
            0,
            3,
            3,
            3,
            1,
            0
          ],
          "nilaiA": 59081,
          "nilaiB": 74527,
          "benar": 133608,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 59081,
            "b": 74527,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 65748,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 65748,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 133608,
            "langkah": 6,
            "langkahPrimitif": 223583,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 9,
          "soal": 1,
          "stateA": [
            4,
            5,
            0,
            4,
            3,
            1,
            1,
            0
          ],
          "stateB": [
            0,
            4,
            2,
            3,
            3,
            3,
            1,
            0
          ],
          "nilaiA": 59218,
          "nilaiB": 74616,
          "benar": 133834,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 59218,
            "b": 74616,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 65885,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 65885,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 133834,
            "langkah": 6,
            "langkahPrimitif": 223850,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 9,
          "soal": 2,
          "stateA": [
            3,
            4,
            4,
            4,
            3,
            1,
            1,
            0
          ],
          "stateB": [
            5,
            0,
            5,
            3,
            3,
            3,
            1,
            0
          ],
          "nilaiA": 59355,
          "nilaiB": 74705,
          "benar": 134060,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 59355,
            "b": 74705,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 66022,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 66022,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 134060,
            "langkah": 6,
            "langkahPrimitif": 224117,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 9,
          "soal": 3,
          "stateA": [
            2,
            3,
            2,
            5,
            3,
            1,
            1,
            0
          ],
          "stateB": [
            4,
            3,
            1,
            4,
            3,
            3,
            1,
            0
          ],
          "nilaiA": 59492,
          "nilaiB": 74794,
          "benar": 134286,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 59492,
            "b": 74794,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 66159,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 66159,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 134286,
            "langkah": 6,
            "langkahPrimitif": 224384,
            "status": "terjawab",
            "lulus": true
          }
        },
        {
          "radix": 6,
          "seed": 9,
          "soal": 4,
          "stateA": [
            1,
            2,
            0,
            0,
            4,
            1,
            1,
            0
          ],
          "stateB": [
            3,
            0,
            4,
            4,
            3,
            3,
            1,
            0
          ],
          "nilaiA": 59629,
          "nilaiB": 74883,
          "benar": 134512,
          "hafalan": {
            "a": null,
            "b": null,
            "lulus": false
          },
          "model": {
            "a": 59629,
            "b": 74883,
            "lulus": true,
            "bobot": [
              1,
              6,
              36,
              216
            ],
            "rasio": 6
          },
          "baseline": {
            "decodeDidahului": false,
            "jawab": 66296,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "baselineAngkaSaja": {
            "jawab": 66296,
            "langkah": 20001,
            "habis": true,
            "lulus": false
          },
          "konsep": {
            "jawab": 134512,
            "langkah": 6,
            "langkahPrimitif": 224651,
            "status": "terjawab",
            "lulus": true
          }
        }
      ]
    }
  ]
}
