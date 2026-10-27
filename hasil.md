$ node uji.js
node uji_tahap2.js
node uji_tahap2_kondisional.js
node percobaan_tahap2.js 10
node percobaan_tahap2_kondisional.js 10
Mesin langkah
  ok   cara dasar tambah benar untuk semua a,b 0..10 dan biayanya 3b+2 (0 ms)
  ok   pengulangan tanpa pengurang berhenti oleh batas langkah, bukan menggantung (1 ms)
Pencarian cara
  ok   dari kasus saja ditemukan cara dasar tambah pada ukuran 4 (7 ms)
  ok   pada ukuran 6 ditemukan cara yang lebih hemat (menukar bila a<b) (417 ms)
  ok   tidak ada cara lebih murah => mengembalikan null (3 ms)
Penyimpan
  ok   lupa menghapus yang kuatnya < 0,05 dan indeks ikut bersih (1 ms)
  ok   kapasitas: yang dibuang adalah yang paling lemah, kejadian salah dipertahankan (0 ms)
  ok   tiga jalur tercatat: tulis, panggil, ulang (1 ms)
  ok   pilihUlang mode galat memilih kejadian salah jauh lebih sering daripada seragam (2 ms)
Sistem
  ok   tanpa belajar sepi: tidak pernah menemukan cara (kontrol) (1 ms)
  ok   dengan belajar sepi: satu malam menemukan cara tambah yang benar pada soal baru (304 ms)
  ok   kesalahan menjadi pelajaran: cara yang gagal di luar rentang dipersempit lalu diganti (301 ms)
  ok   gerbang pembuktian menolak cara yang cocok pada kasus tapi gagal pada soal segar (1 ms)
  ok   kapasitas ingatan tidak pernah terlampaui selama 14 hari (1519 ms)
  ok   deterministik: seed sama => hasil sama (1348 ms)
  ok   soal ukur tidak pernah memuat pasangan yang ada di jadwal latihan (0 ms)
  ok   belajar sepi tanpa masukan baru memperbaiki kinerja (akurasi 0,x -> 1,0) (682 ms)

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
Tahap 2 — perbandingan baseline vs konsep
Seed: 10; soal/seed: 5
Baseline tahap 1 lulus: 0/50
Runner konsep lulus:    50/50
Konsep terbentuk:        10/10
Langkah kognitif/soal:   6
Ekuivalen primitif/soal: 334595.6
Detail: C:\Users\putra\Downloads\MKV\hasil_tahap2.json
Tahap 2.1 — induksi transisi berkondisi
Seed: 10; soal/seed: 5
Baseline lulus: 0/50
Runner konsep lulus: 50/50
Seed dengan dua konsep: 10/10
Langkah kognitif/soal: 7.6
Ekuivalen primitif/soal: 907757.2
Detail: C:\Users\putra\Downloads\MKV\hasil_tahap2_kondisional.json :

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
