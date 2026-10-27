$ node uji.js
node uji_tahap2.js
node percobaan_tahap2.js 10
Mesin langkah
  ok   cara dasar tambah benar untuk semua a,b 0..10 dan biayanya 3b+2 (0 ms)
  ok   pengulangan tanpa pengurang berhenti oleh batas langkah, bukan menggantung (1 ms)
Pencarian cara
  ok   dari kasus saja ditemukan cara dasar tambah pada ukuran 4 (7 ms)
  ok   pada ukuran 6 ditemukan cara yang lebih hemat (menukar bila a<b) (443 ms)
  ok   tidak ada cara lebih murah => mengembalikan null (3 ms)
Penyimpan
  ok   lupa menghapus yang kuatnya < 0,05 dan indeks ikut bersih (1 ms)
  ok   kapasitas: yang dibuang adalah yang paling lemah, kejadian salah dipertahankan (0 ms)
  ok   tiga jalur tercatat: tulis, panggil, ulang (1 ms)
  ok   pilihUlang mode galat memilih kejadian salah jauh lebih sering daripada seragam (2 ms)
Sistem
  ok   tanpa belajar sepi: tidak pernah menemukan cara (kontrol) (2 ms)
  ok   dengan belajar sepi: satu malam menemukan cara tambah yang benar pada soal baru (325 ms)
  ok   kesalahan menjadi pelajaran: cara yang gagal di luar rentang dipersempit lalu diganti (314 ms)
  ok   gerbang pembuktian menolak cara yang cocok pada kasus tapi gagal pada soal segar (2 ms)
  ok   kapasitas ingatan tidak pernah terlampaui selama 14 hari (1612 ms)
  ok   deterministik: seed sama => hasil sama (1516 ms)
  ok   soal ukur tidak pernah memuat pasangan yang ada di jadwal latihan (1 ms)
  ok   belajar sepi tanpa masukan baru memperbaiki kinerja (akurasi 0,x -> 1,0) (770 ms)

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
Tahap 2 — perbandingan baseline vs konsep
Seed: 10; soal/seed: 5
Baseline tahap 1 lulus: 0/50
Runner konsep lulus:    50/50
Konsep terbentuk:        10/10
Langkah kognitif/soal:   6
Ekuivalen primitif/soal: 334595.6
Detail: C:\Users\putra\Downloads\MKV\hasil_tahap2.json :

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
