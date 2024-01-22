---
title: Ubah Bidang Formulir Dalam Dokumen PDF
linktitle: Ubah Bidang Formulir Dalam Dokumen PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Edit kolom formulir dengan mudah di dokumen PDF dengan Aspose.PDF untuk .NET.
type: docs
weight: 190
url: /id/net/programming-with-forms/modify-form-field/
---
Dalam tutorial ini, kami akan menunjukkan cara mengedit kolom formulir di dokumen PDF menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber C# langkah demi langkah untuk memandu Anda melalui proses ini.

## Langkah 1: Persiapan

Pastikan Anda telah mengimpor perpustakaan yang diperlukan dan mengatur jalur ke direktori dokumen Anda:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Muat dokumen

Muat dokumen PDF yang ada:

```csharp
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
```

## Langkah 3: Dapatkan bidang formulir

Dapatkan bidang formulir yang ingin Anda edit:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Langkah 4: Ubah nilai bidang

Ubah nilai bidang formulir:

```csharp
textBoxField.Value = "New Value";
```

## Langkah 5: Edit Properti Bidang

Ubah properti bidang formulir tambahan sesuai kebutuhan. Misalnya, Anda dapat menjadikannya hanya-baca:

```csharp
textBoxField.ReadOnly = true;
```

## Langkah 6: Simpan dokumen yang telah diedit

Simpan dokumen PDF yang dimodifikasi:

```csharp
dataDir = dataDir + "ModifyFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Contoh kode sumber untuk Memodifikasi Bidang Formulir menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
// Dapatkan lapangan
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Ubah nilai bidang
textBoxField.Value = "New Value";
textBoxField.ReadOnly = true;
dataDir = dataDir + "ModifyFormField_out.pdf";
// Simpan dokumen yang diperbarui
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field modified successfully.\nFile saved at " + dataDir);
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara mengedit kolom formulir di dokumen PDF menggunakan Aspose.PDF untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah menavigasi ke bidang tertentu, mengubah nilainya, dan menyesuaikan propertinya sesuai kebutuhan.


### FAQ

#### T: Dapatkah saya mengedit beberapa bidang formulir dalam satu dokumen PDF menggunakan Aspose.PDF untuk .NET?

J: Ya, Anda dapat mengedit beberapa bidang formulir dalam satu dokumen PDF menggunakan Aspose.PDF untuk .NET. Cukup ulangi proses untuk setiap bidang formulir yang ingin Anda modifikasi.

#### T: Apakah Aspose.PDF untuk .NET kompatibel dengan semua versi .NET Framework?

J: Ya, Aspose.PDF untuk .NET kompatibel dengan semua versi .NET Framework, termasuk .NET Core dan .NET Standard.

#### T: Dapatkah saya mengubah jenis bidang formulir lainnya, seperti kotak centang atau tombol radio, menggunakan Aspose.PDF untuk .NET?

J: Ya, Aspose.PDF untuk .NET mendukung modifikasi berbagai jenis bidang formulir, termasuk kotak centang, tombol radio, dan banyak lagi.

#### T: Bagaimana cara menambahkan kolom formulir baru ke dokumen PDF menggunakan Aspose.PDF untuk .NET?

 J: Untuk menambahkan kolom formulir baru ke dokumen PDF, Anda dapat menggunakan`Form` properti dari`Document` kelas untuk mengakses`Field` koleksi dan kemudian menambahkan bidang formulir baru secara terprogram.

#### T: Apakah Aspose.PDF untuk .NET mendukung bahasa pemrograman lain selain C#?

A: Ya, Aspose.PDF untuk .NET mendukung berbagai bahasa pemrograman, seperti VB.NET dan ASP.NET, selain C#.