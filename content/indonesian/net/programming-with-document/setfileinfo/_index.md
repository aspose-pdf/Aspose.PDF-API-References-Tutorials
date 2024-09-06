---
title: Atur Info File Dalam File PDF
linktitle: Atur Info File Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menggunakan Aspose.PDF untuk .NET untuk mengatur info file dalam file PDF dengan panduan langkah demi langkah ini.
type: docs
weight: 310
url: /id/net/programming-with-document/setfileinfo/
---
Jika Anda mengerjakan proyek yang memerlukan pengelolaan berkas PDF menggunakan Aspose.PDF untuk .NET, salah satu fitur yang mungkin ingin Anda manfaatkan adalah kemampuan untuk mengatur informasi berkas untuk dokumen PDF. Informasi berkas mencakup berbagai detail seperti penulis, tanggal pembuatan, kata kunci, tanggal modifikasi, subjek, dan judul. Panduan ini akan memandu Anda melalui proses pengaturan informasi berkas untuk dokumen PDF menggunakan kode sumber C# dengan Aspose.PDF untuk .NET.

## Panduan langkah demi langkah untuk mengatur info file menggunakan Aspose.PDF untuk .NET

1. Buat proyek C# baru di IDE Visual Studio Anda.
2. Tambahkan referensi ke pustaka Aspose.PDF untuk .NET di proyek Anda.
3. Buat objek dokumen PDF baru dengan memberikan jalur ke file PDF yang informasi filenya ingin Anda ubah.

## Langkah 1: Tetapkan jalur ke direktori dokumen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Buka dokumen PDF

```csharp
// Buka dokumen
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## Langkah 3: Gunakan objek DocumentInfo untuk mengakses informasi file dokumen PDF.

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## Langkah 4: Tetapkan nilai informasi file yang diinginkan menggunakan properti objek DocumentInfo.

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## Langkah 5: Simpan dokumen PDF yang diperbarui ke lokasi yang ditentukan.

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## Langkah 6: Verifikasi bahwa informasi berkas telah berhasil diperbarui.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

Anda telah berhasil mengatur informasi file untuk dokumen PDF menggunakan Aspose.PDF untuk .NET.

### Contoh kode sumber untuk Set File Info menggunakan Aspose.PDF untuk .NET


```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buka dokumen
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");

// Tentukan informasi dokumen
DocumentInfo docInfo = new DocumentInfo(pdfDocument);

docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";

dataDir = dataDir + "SetFileInfo_out.pdf";
// Simpan dokumen keluaran
pdfDocument.Save(dataDir);

Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

## Kesimpulan

Sebagai kesimpulan, Aspose.PDF untuk .NET menyediakan cara yang sederhana dan efektif untuk mengatur informasi berkas untuk dokumen PDF. Dengan mengikuti langkah-langkah yang disebutkan di atas, Anda dapat dengan mudah mengatur nilai informasi berkas yang diinginkan untuk dokumen PDF Anda menggunakan kode sumber C#.

### FAQ untuk mengatur info file dalam file PDF

#### T: Dapatkah saya mengatur properti informasi file tambahan yang tidak disebutkan dalam contoh?

 A: Ya, Anda dapat mengatur properti informasi file tambahan menggunakan`DocumentInfo` objek di Aspose.PDF untuk .NET.`DocumentInfo`kelas menyediakan berbagai properti yang memungkinkan Anda mengatur informasi tambahan seperti produsen, versi, dan properti kustom.

#### T: Apakah mungkin untuk mengambil informasi berkas dari dokumen PDF yang ada?

 A: Ya, Anda dapat mengambil informasi file dari dokumen PDF yang ada menggunakan Aspose.PDF untuk .NET. Untuk melakukan ini, Anda dapat menggunakan`DocumentInfo` objek untuk mengakses properti informasi file dan membaca informasi yang disimpan dalam dokumen PDF.

#### T: Apakah pengaturan informasi file akan mengubah dokumen PDF asli?

J: Tidak, pengaturan informasi berkas menggunakan Aspose.PDF untuk .NET tidak akan mengubah dokumen PDF asli. Sebaliknya, dokumen PDF baru akan dibuat dengan informasi berkas yang diperbarui. Dokumen PDF asli tetap tidak berubah.