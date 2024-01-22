---
title: PDF Ke XLS
linktitle: PDF Ke XLS
second_title: Aspose.PDF untuk Referensi .NET API
description: Panduan langkah demi langkah untuk mengonversi PDF ke XLS menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 200
url: /id/net/document-conversion/pdf-to-xls/
---
Dalam tutorial ini, kami akan memandu Anda melalui proses mengonversi file PDF ke format XLS (Microsoft Excel) menggunakan Aspose.PDF untuk .NET. Dengan mengikuti langkah-langkah di bawah ini, Anda akan dapat mengkonversi file PDF ke format XLS.

## Prasyarat
Sebelum memulai, pastikan Anda memenuhi prasyarat berikut:

- Pengetahuan dasar tentang bahasa pemrograman C#.
- Pustaka Aspose.PDF untuk .NET diinstal di sistem Anda.
- Lingkungan pengembangan seperti Visual Studio.

## Langkah 1: Memuat dokumen PDF
Pada langkah ini kita akan memuat file PDF sumber menggunakan Aspose.PDF untuk .NET. Ikuti kode di bawah ini:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Muat dokumen PDF
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Pastikan untuk mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan direktori sebenarnya tempat file PDF Anda berada.

## Langkah 2: Buat instance opsi cadangan Excel
Setelah memuat file PDF, kami akan membuat contoh opsi penyimpanan Excel. Gunakan kode berikut:

```csharp
// Buat instance objek ExcelSaveOptions
Aspose.Pdf.ExcelSaveOptions excelsave = new ExcelSaveOptions();
```

## Langkah 3: Menyimpan file XLS yang dihasilkan
Sekarang kita akan menyimpan file PDF yang telah dikonversi dalam format XLS. Gunakan kode berikut:

```csharp
// Simpan hasilnya dalam format XLS
pdfDocument.Save("PDFToXLS_out.xls", excelsave);
```

 Kode di atas menyimpan file PDF yang telah dikonversi dalam format XLS dengan nama file`"PDFToXLS_out.xls"`.

### Contoh kode sumber untuk PDF ke XLS menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Muat dokumen PDF
Document pdfDocument = new Document(dataDir + "input.pdf");

// Buat instance objek Opsi ExcelSave
Aspose.Pdf.ExcelSaveOptions excelsave = new ExcelSaveOptions();

// Simpan hasilnya dalam format XLS
pdfDocument.Save("PDFToXLS_out.xls", excelsave);
```

## Kesimpulan
Dalam tutorial ini, kami membahas proses langkah demi langkah mengonversi file PDF ke format XLS menggunakan Aspose.PDF untuk .NET. Dengan mengikuti petunjuk yang diuraikan di atas, Anda sekarang dapat mengonversi file PDF ke format XLS. Fitur ini berguna ketika Anda ingin mengekstrak data tabel dari file PDF dan menggunakannya di Microsoft Excel.

### FAQ

#### T: Dapatkah Aspose.PDF untuk .NET mengonversi PDF dengan tabel kompleks dan pemformatan ke format XLS?

J: Ya, Aspose.PDF untuk .NET dirancang untuk menangani PDF dengan tabel dan format yang rumit. Selama proses konversi ke format XLS, Aspose.PDF untuk .NET mencoba mempertahankan tata letak dan struktur tabel seakurat mungkin, memastikan bahwa data tabel diekstraksi secara efektif.

#### T: Apa yang terjadi jika PDF berisi gambar atau konten non-tabular?

J: Saat mengonversi format PDF ke XLS, Aspose.PDF untuk .NET terutama berfokus pada ekstraksi data tabel. Konten non-tabular, seperti gambar, anotasi, atau teks bentuk bebas, mungkin tidak disimpan dalam file XLS. File XLS yang dihasilkan terutama berisi data tabular yang diekstraksi dari PDF.

#### T: Apakah mungkin untuk menyesuaikan tampilan dan tata letak file XLS selama konversi?

 J: Aspose.PDF untuk .NET menyediakan opsi untuk menyesuaikan tampilan dan tata letak file XLS yang dihasilkan. Anda dapat menyesuaikan berbagai pengaturan menggunakan properti`ExcelSaveOptions` kelas, seperti menentukan sel awal untuk tabel, mengatur pengkodean teks, dan mengontrol opsi terkait keluaran lainnya.

#### T: Bisakah saya mengonversi PDF yang dilindungi kata sandi ke format XLS menggunakan Aspose.PDF untuk .NET?

 J: Ya, Aspose.PDF untuk .NET mendukung konversi PDF yang dilindungi kata sandi ke format XLS. Saat memuat PDF yang dilindungi kata sandi, Anda dapat memberikan kata sandi menggunakan`Document` konstruktor kelas atau dengan mengatur`Password` properti sebelum memuat PDF.