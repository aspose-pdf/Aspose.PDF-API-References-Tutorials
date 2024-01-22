---
title: Tambahkan HTML Menggunakan DOM
linktitle: Tambahkan HTML Menggunakan DOM
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menambahkan konten HTML menggunakan DOM di Aspose.PDF untuk .NET.
type: docs
weight: 40
url: /id/net/programming-with-text/add-html-using-dom/
---
Tutorial ini akan memandu Anda melalui proses menambahkan konten HTML menggunakan DOM (Document Object Model) di Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan.

## Persyaratan
Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau kompiler C# lainnya yang diinstal pada mesin Anda.
- Aspose.PDF untuk perpustakaan .NET. Anda dapat mendownloadnya dari situs resmi Aspose atau menggunakan manajer paket seperti NuGet untuk menginstalnya.

## Langkah 1: Siapkan proyek
1. Buat proyek C# baru di lingkungan pengembangan pilihan Anda.
2. Tambahkan referensi ke perpustakaan Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan
Dalam file kode tempat Anda ingin menambahkan konten HTML, tambahkan arahan penggunaan berikut di bagian atas file:

```csharp
using Aspose.Pdf;
```

## Langkah 3: Atur direktori dokumen dan jalur file keluaran
 Dalam kode, temukan baris yang bertuliskan`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur ke direktori tempat dokumen Anda disimpan.

## Langkah 4: Buat objek Dokumen baru
 Buat instance yang baru`Document` objek dengan menambahkan baris kode berikut:

```csharp
Document doc = new Document();
```

## Langkah 5: Tambahkan halaman ke dokumen
 Tambahkan halaman baru ke dokumen dengan menggunakan`Add` metode`Pages`koleksi. Dalam kode yang disediakan, halaman baru ditugaskan ke variabel`page`.

```csharp
Page page = doc.Pages.Add();
```

## Langkah 6: Buat HtmlFragment dengan konten HTML
 Buat contoh sebuah`HtmlFragment` objek dan berikan konten HTML yang diinginkan. Dalam kode yang disediakan, konten HTML ditugaskan ke variabel`titel`. Anda dapat memodifikasi konten HTML sesuai kebutuhan.

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

## Langkah 7: Tetapkan informasi margin
Sesuaikan margin bawah dan atas fragmen HTML jika perlu. Dalam kode yang diberikan, margin bawah diatur ke 10 dan margin atas diatur ke 200.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 200;
```

## Langkah 8: Tambahkan HtmlFragment ke halaman
 Tambahkan`HtmlFragment` keberatan dengan kumpulan paragraf halaman.

```csharp
page.Paragraphs.Add(title);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

## Langkah 9: Simpan dokumen PDF
 Simpan dokumen PDF menggunakan`Save` metode`Document` obyek. Tentukan jalur file keluaran yang Anda atur di Langkah 3.

```csharp
doc.Save(dataDir);
```

## Langkah 10: Tampilkan pesan sukses
Menampilkan pesan sukses beserta jalur penyimpanan file PDF.

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

### Contoh kode sumber untuk Menambahkan HTMLMenggunakan DOM menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buat instance objek Dokumen
Document doc = new Document();
// Tambahkan halaman ke halaman koleksi file PDF
Page page = doc.Pages.Add();
// Buat instance HtmlFragment dengan konten HTML
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
// Tetapkan informasi margin bawah
titel.Margin.Bottom = 10;
// Tetapkan informasi margin atas
titel.Margin.Top = 200;
// Tambahkan Fragmen HTML ke kumpulan paragraf halaman
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
// Simpan berkas PDF
doc.Save(dataDir);
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

## Kesimpulan
Anda telah berhasil menambahkan konten HTML menggunakan DOM di Aspose.PDF untuk .NET. File PDF yang dihasilkan sekarang dapat ditemukan di jalur file keluaran yang ditentukan.

### FAQ

#### T: Apa tujuan dari tutorial ini?

J: Tutorial ini bertujuan untuk memberikan panduan langkah demi langkah tentang cara menambahkan konten HTML ke dokumen PDF menggunakan Document Object Model (DOM) di Aspose.PDF untuk .NET. Ini mencakup cuplikan kode sumber C# untuk membantu Anda memahami dan menerapkan prosesnya.

#### T: Namespace manakah yang perlu saya impor untuk tutorial ini?

J: Dalam file kode tempat Anda berencana menambahkan konten HTML, impor namespace berikut di awal file:

```csharp
using Aspose.Pdf;
```

#### T: Bagaimana cara menentukan direktori dokumen dan jalur file keluaran?

 A: Di dalam kode, temukan barisnya`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

#### T: Bagaimana cara membuat objek Dokumen?

 J: Pada Langkah 4, buat instance yang baru`Document` objek dengan menambahkan baris kode berikut:

```csharp
Document doc = new Document();
```

#### T: Bagaimana cara menambahkan halaman ke dokumen?

 J: Pada Langkah 5, Anda akan menambahkan halaman baru ke dokumen menggunakan`Add` metode`Pages` koleksi:

```csharp
Page page = doc.Pages.Add();
```

#### T: Bagaimana cara menyetel konten HTML menggunakan DOM?

 J: Pada Langkah 6, Anda akan membuat`HtmlFragment` objek dan tetapkan konten HTML yang Anda inginkan ke dalamnya. Konten HTML ditugaskan ke variabel`titel`:

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

#### T: Dapatkah saya menyesuaikan margin konten HTML?

J: Ya, pada Langkah 7, Anda dapat menyesuaikan margin bawah dan atas fragmen HTML sesuai kebutuhan:

```csharp
titel.Margin.Bottom = 10;
titel.Margin.Top = 200;
```

#### T: Bagaimana cara menambahkan HTMLFragment ke dokumen PDF?

 J: Pada Langkah 8, Anda akan menambahkan`HtmlFragment` objek (`titel`) ke kumpulan paragraf halaman:

```csharp
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

#### Q: Bagaimana cara menyimpan dokumen PDF yang dihasilkan?

 J: Setelah menambahkan konten HTML dan menyesuaikan margin, gunakan`Save` metode`Document` keberatan untuk menyimpan dokumen PDF:

```csharp
doc.Save(dataDir);
```

#### T: Apakah ada cara untuk memverifikasi apakah prosesnya berhasil?

A: Tentu saja, pada Langkah 10, pesan sukses ditampilkan bersama dengan jalur penyimpanan file PDF:

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

#### T: Apa inti dari tutorial ini?

J: Dengan mengikuti tutorial ini, Anda telah berhasil mempelajari cara memanfaatkan Model Objek Dokumen (DOM) di Aspose.PDF untuk .NET guna menambahkan konten HTML ke dokumen PDF. Pengetahuan ini memberdayakan Anda untuk meningkatkan kemampuan pembuatan PDF Anda.