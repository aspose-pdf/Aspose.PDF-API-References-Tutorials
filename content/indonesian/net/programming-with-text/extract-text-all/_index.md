---
title: Ekstrak Semua Teks Dalam File PDF
linktitle: Ekstrak Teks File PDF AllIn
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mengekstrak semua teks dalam berkas PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 180
url: /id/net/programming-with-text/extract-text-all/
---
Tutorial ini akan memandu Anda melalui proses mengekstrak semua teks dalam file PDF menggunakan Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan.

## Persyaratan
Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau kompiler C# lainnya terinstal di komputer Anda.
- Aspose.PDF untuk pustaka .NET. Anda dapat mengunduhnya dari situs web resmi Aspose atau menggunakan pengelola paket seperti NuGet untuk menginstalnya.

## Langkah 1: Siapkan proyek
1. Buat proyek C# baru di lingkungan pengembangan pilihan Anda.
2. Tambahkan referensi ke pustaka Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan
Pada berkas kode tempat Anda ingin mengekstrak teks, tambahkan perintah penggunaan berikut di bagian atas berkas:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Langkah 3: Mengatur direktori dokumen
 Dalam kode, temukan baris yang bertuliskan`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur ke direktori tempat dokumen Anda disimpan.

## Langkah 4: Buka dokumen PDF
 Buka dokumen PDF yang ada menggunakan`Document`konstruktor dan meneruskan jalur ke berkas PDF masukan.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## Langkah 5: Ekstrak semua teks
 Membuat sebuah`TextAbsorber`objek untuk mengekstrak teks dari dokumen. Kemudian, terima penyerap untuk semua halaman.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
```

## Langkah 6: Dapatkan teks yang diekstraksi
 Akses teks yang diekstrak dari`TextAbsorber` obyek.

```csharp
string extractedText = textAbsorber.Text;
```

## Langkah 7: Simpan teks yang diekstrak
 Membuat sebuah`TextWriter` dan buka berkas tempat Anda ingin menyimpan teks yang diekstrak. Tulis teks yang diekstrak ke berkas dan tutup aliran.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Contoh kode sumber untuk Ekstrak Semua Teks menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Buat objek TextAbsorber untuk mengekstrak teks
TextAbsorber textAbsorber = new TextAbsorber();
// Terima penyerap untuk semua halaman
pdfDocument.Pages.Accept(textAbsorber);
// Dapatkan teks yang diekstraksi
string extractedText = textAbsorber.Text;
// Buat penulis dan buka file
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Tuliskan baris teks ke dalam file
tw.WriteLine(extractedText);
// Tutup alirannya
tw.Close();
```

## Kesimpulan
Anda telah berhasil mengekstrak semua teks dari dokumen PDF menggunakan Aspose.PDF untuk .NET. Teks yang diekstrak telah disimpan ke berkas keluaran yang ditentukan.

### Pertanyaan yang Sering Diajukan

#### T: Apa tujuan dari tutorial ini?

J: Tutorial ini berfungsi sebagai panduan untuk membantu Anda mengekstrak semua teks dari file PDF menggunakan Aspose.PDF for .NET. Kode sumber C# yang disertakan menyediakan petunjuk langkah demi langkah untuk menyelesaikan tugas ini.

#### T: Namespace apa yang harus saya impor?

A: Pada berkas kode tempat Anda ingin mengekstrak teks, sertakan perintah penggunaan berikut di awal berkas:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### T: Bagaimana cara menentukan direktori dokumen?

 A: Temukan garisnya`string dataDir = "YOUR DOCUMENT DIRECTORY";` dalam kode dan ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

#### T: Bagaimana cara membuka dokumen PDF yang sudah ada?

 A: Pada Langkah 4, Anda akan membuka dokumen PDF yang ada menggunakan`Document` konstruktor dan menyediakan jalur ke berkas PDF masukan.

#### T: Bagaimana cara mengekstrak semua teks dari dokumen?

 A: Langkah 5 melibatkan pembuatan`TextAbsorber` objek untuk mengekstrak teks dari dokumen PDF. Kemudian, Anda akan menerima penyerap untuk semua halaman.

#### T: Bagaimana cara mengakses teks yang diekstrak?

 A: Langkah 6 memandu Anda mengakses teks yang diekstrak dari`TextAbsorber` obyek.

#### T: Bagaimana cara menyimpan teks yang diekstrak ke dalam berkas?

 A: Pada Langkah 7, Anda akan membuat`TextWriter`, buka berkas tempat Anda ingin menyimpan teks yang diekstrak, tulis teks yang diekstrak ke berkas, lalu tutup aliran.

#### T: Apa inti sari dari tutorial ini?

A: Dengan mengikuti tutorial ini, Anda telah mempelajari cara mengekstrak semua teks dari dokumen PDF menggunakan Aspose.PDF for .NET. Teks yang diekstrak telah disimpan ke file keluaran tertentu, sehingga Anda dapat menganalisis dan memanipulasi konten tekstual dokumen.