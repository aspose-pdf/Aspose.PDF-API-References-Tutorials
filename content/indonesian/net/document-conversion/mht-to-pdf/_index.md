---
title: MHT Ke PDF
linktitle: MHT Ke PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Panduan langkah demi langkah untuk mengonversi MHT ke PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 70
url: /id/net/document-conversion/mht-to-pdf/
---
Dalam tutorial ini, kami akan memandu Anda melalui proses mengonversi file MHT ke PDF menggunakan Aspose.PDF untuk .NET. MHT (MIME HTML) adalah format yang digunakan untuk menyimpan halaman web lengkap, termasuk gambar dan konten terkait. Dengan mengikuti langkah-langkah di bawah ini, Anda akan dapat mengkonversi file MHT ke format PDF.

## Prasyarat
Sebelum memulai, pastikan Anda memenuhi prasyarat berikut:

- Pengetahuan dasar tentang bahasa pemrograman C#.
- Pustaka Aspose.PDF untuk .NET diinstal di sistem Anda.
- Lingkungan pengembangan seperti Visual Studio.

## Langkah 1: Memuat file MHT
Pada langkah ini kita akan memuat file MHT menggunakan Aspose.PDF untuk .NET. Ikuti kode di bawah ini:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

MhtLoadOptions options = new MhtLoadOptions();

// Muat dokumen
Document document = new Document(dataDir + "test.mht", options);
```

 Pastikan untuk mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan direktori sebenarnya tempat file MHT Anda berada.

## Langkah 2: Konversi MHT ke PDF
Setelah memuat file MHT, kita dapat melanjutkan dengan konversi ke PDF. Gunakan kode berikut:

```csharp
// Simpan hasilnya sebagai dokumen PDF
document.Save(dataDir + "MHTToPDF_out.pdf");
```

 Kode di atas mengubah file MHT ke format PDF dan menyimpannya sebagai nama file`"MHTToPDF_out.pdf"`.

### Contoh kode sumber untuk MHT ke PDF menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
MhtLoadOptions options = new MhtLoadOptions();
// Muat dokumen
Document document = new Document(dataDir  + "test.mht", options);
// Simpan hasilnya sebagai dokumen PDF
document.Save(dataDir + "MHTToPDF_out.pdf");
```

## Kesimpulan
Dalam tutorial ini, kami membahas proses langkah demi langkah mengonversi file MHT ke PDF menggunakan Aspose.PDF untuk .NET. Dengan mengikuti petunjuk yang diuraikan di atas, Anda sekarang dapat mengonversi file MHT ke format PDF. Fitur ini berguna ketika Anda perlu mengubah seluruh halaman web menjadi dokumen PDF.

### FAQ

#### T: Apakah Aspose.PDF untuk .NET mendukung konversi file MHT dengan gambar tersemat ke PDF?

J: Ya, Aspose.PDF untuk .NET mendukung konversi file MHT dengan gambar yang disematkan ke PDF. Perpustakaan dapat menangani konten halaman web lengkap, termasuk gambar dan sumber daya terkait, dan mengubahnya menjadi dokumen PDF.

#### T: Dapatkah saya menyesuaikan keluaran PDF selama proses konversi MHT ke PDF?

J: Ya, Aspose.PDF untuk .NET menyediakan berbagai opsi untuk menyesuaikan keluaran PDF selama proses konversi MHT ke PDF. Anda dapat mengatur properti seperti ukuran halaman, orientasi, margin, dan lainnya untuk mengontrol tampilan dokumen PDF yang dihasilkan.

#### T: Apakah Aspose.PDF untuk .NET mempertahankan hyperlink dan pemformatan dari file MHT asli dalam keluaran PDF?

J: Ya, Aspose.PDF untuk .NET mempertahankan hyperlink dan pemformatan dari file MHT asli dalam keluaran PDF. Perpustakaan memastikan bahwa PDF yang dikonversi mempertahankan tata letak dan konten yang sama dengan file MHT sumber.

#### T: Bisakah saya mengonversi beberapa file MHT menjadi dokumen PDF terpisah menggunakan Aspose.PDF untuk .NET?

J: Ya, Anda dapat mengonversi beberapa file MHT menjadi dokumen PDF terpisah menggunakan Aspose.PDF untuk .NET. Cukup muat setiap file MHT dan simpan sebagai dokumen PDF terpisah dengan nama file unik.