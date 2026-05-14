# Praktikum Visualisasi Data - Pertemuan 5

## Identitas Praktikan

| **Nama** | Thoriq Dzaki |
|----------|--------------|
| **NIM** | 2300018216 |
| **Mata Kuliah** | Praktikum Visualisasi Data |
| **Hari/Jam** | Kamis, 16.45 WIB |
| **Pertemuan ke-** | 5 |

---

## Deskripsi Program

Program ini berisi **dua versi diagram batang (bar chart) interaktif** menggunakan library **D3.js** yang menampilkan 10 bahasa pemrograman paling dicintai berdasarkan survey Stack Overflow 2018.

| File | Versi | Fitur Utama |
|------|-------|-------------|
| `prak5.html` | Versi dasar | Hover effect, garis pembanding, selisih nilai |
| `post5.html` | Versi lanjutan | Sorting ASC/DESC + Tooltip modern |

---

## Data yang Digunakan

```javascript
const sample = [
  { language: "Rust",       value: 78.9, color: "#cba6f7" },
  { language: "Kotlin",     value: 75.1, color: "#89b4fa" },
  { language: "Python",     value: 68.0, color: "#a6e3a1" },
  { language: "TypeScript", value: 67.0, color: "#89dceb" },
  { language: "Go",         value: 65.6, color: "#94e2d5" },
  { language: "Swift",      value: 65.1, color: "#fab387" },
  { language: "JavaScript", value: 61.9, color: "#f9e2af" },
  { language: "C#",         value: 60.4, color: "#f38ba8" },
  { language: "F#",         value: 59.6, color: "#74c7ec" },
  { language: "Clojure",    value: 59.6, color: "#b4befe" },
];
```

---

## Penjelasan Kode (Gabungan dari prak5.html dan post5.html)

| Bagian Kode | Penjelasan |
|-------------|------------|
| `const sample` | Menyimpan 10 bahasa dengan persentase dan warna |
| `d3.select("svg")` | Memilih elemen SVG sebagai tempat menggambar grafik |
| `margin = 80` | Memberi jarak antara grafik dengan tepi SVG |
| `scaleBand()` | Mengatur posisi batang di sumbu X (per bahasa) |
| `scaleLinear()` | Mengatur tinggi batang di sumbu Y (nilai 0-100%) |
| `d3.axisBottom()` | Membuat sumbu X (nama bahasa) |
| `d3.axisLeft()` | Membuat sumbu Y (persentase) |
| `.grid` | Membuat garis bantu horizontal agar mudah membaca nilai |
| `barGroups.append("rect")` | Menggambar batang-batang grafik |
| `.on("mouseenter")` | Efek saat kursor di atas batang (membesar, highlight, garis pembanding, selisih nilai) |
| `.on("mouseleave")` | Efek saat kursor meninggalkan batang (kembali normal) |
| `.append("text")` | Menampilkan angka persentase di atas batang |
| `#limit` | Garis pembanding horizontal (putus-putus) |
| `.divergence` | Menampilkan selisih nilai antar bahasa (+X% / -X%) |
| `.tooltip` | Kotak info yang muncul saat hover (nama bahasa + persentase) - khusus post5.html |
| `#sortForm` | Dropdown dan tombol untuk mengurutkan data - khusus post5.html |
| `sortedData` | Method untuk mengurutkan ASC (kecil ke besar) atau DESC (besar ke kecil) - khusus post5.html |
| `xScale.domain(sortedData.map(...))` | Memperbarui urutan sumbu X setelah sorting - khusus post5.html |
| `.sort()` dari D3 | Mengurutkan ulang posisi batang dan label - khusus post5.html |

---

## Perbandingan Kedua Versi

| Fitur | prak5.html | post5.html |
|-------|------------|------------|
| Hover effect (batang membesar) | ✅ | ❌ (ganti warna putih) |
| Garis pembanding (limit) | ✅ | ✅ |
| Selisih nilai (divergence) | ✅ | ✅ |
| Tooltip modern | ❌ | ✅ |
| Sorting ASC/DESC | ❌ | ✅ |
| Warna batang berubah saat hover | ❌ | ✅ |
| Tema gelap (dark mode) | ❌ | ✅ |

---

## Cara Menjalankan

1. Buka file `prak5.html` atau `post5.html` di browser
2. Diagram batang akan tampil otomatis
3. **Hover** mouse di atas batang untuk melihat interaksi
4. Pada `post5.html`: pilih ASC/DESC lalu klik untuk sorting bar

---

## Hasil Visualisasi (Data Asli)

| Peringkat | Bahasa | Persentase |
|-----------|--------|------------|
| 1 | Rust | 78.9% |
| 2 | Kotlin | 75.1% |
| 3 | Python | 68.0% |
| 4 | TypeScript | 67.0% |
| 5 | Go | 65.6% |
| 6 | Swift | 65.1% |
| 7 | JavaScript | 61.9% |
| 8 | C# | 60.4% |
| 9 | F# | 59.6% |
| 10 | Clojure | 59.6% |

---

## Tema Tampilan

- **prak5.html**: Tema terang (default browser)
- **post5.html**: Tema gelap (dark mode) dengan background `#1e1e2e` dan text `#cdd6f4`

---

## Sumber Data

Stack Overflow Developer Survey, 2018

---

*Dibuat untuk memenuhi tugas Praktikum Visualisasi Data*
```
