---
title: Pindahkan Bidang Formulir
linktitle: Pindahkan Bidang Formulir
second_title: Aspose.PDF untuk Referensi .NET API
description: Pindahkan kolom formulir dengan mudah di dokumen PDF Anda dengan Aspose.PDF untuk .NET.
type: docs
weight: 200
url: /id/net/programming-with-forms/move-form-field/
---
Dalam tutorial ini, kami akan menunjukkan cara memindahkan kolom formulir di dokumen PDF menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber C# langkah demi langkah untuk memandu Anda melalui proses ini.

## Langkah 1: Persiapan

Pastikan Anda telah mengimpor perpustakaan yang diperlukan dan mengatur jalur ke direktori dokumen Anda:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Muat dokumen

Muat dokumen PDF yang ada:

```csharp
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
```

## Langkah 3: Dapatkan bidang formulir

Dapatkan bidang formulir yang ingin Anda pindahkan:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Langkah 4: Ubah Lokasi Bidang

Ubah lokasi bidang formulir dengan menentukan area persegi panjang baru:

```csharp
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
```

## Langkah 5: Simpan dokumen yang telah diedit

Simpan dokumen PDF yang dimodifikasi:

```csharp
dataDir = dataDir + "MoveFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Contoh kode sumber untuk Memindahkan Bidang Formulir menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
// Dapatkan lapangan
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Ubah lokasi bidang
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
dataDir = dataDir + "MoveFormField_out.pdf";
// Simpan dokumen yang dimodifikasi
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field moved successfully to a new location.\nFile saved at " + dataDir);
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara memindahkan bidang formulir dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah menavigasi ke bidang tertentu dan mengubah lokasinya sesuai kebutuhan.


### FAQ

#### T: Dapatkah saya memindahkan beberapa bidang formulir dalam satu dokumen PDF menggunakan Aspose.PDF untuk .NET?

J: Ya, Anda dapat memindahkan beberapa bidang formulir dalam satu dokumen PDF menggunakan Aspose.PDF untuk .NET. Cukup ulangi proses untuk setiap bidang formulir yang ingin Anda pindahkan.

#### T: Apakah memindahkan bidang formulir akan memengaruhi data atau fungsi terkaitnya?

J: Tidak, memindahkan bidang formulir tidak memengaruhi data atau fungsi terkaitnya. Bidang formulir mempertahankan semua properti dan nilainya setelah dipindahkan ke lokasi baru.

#### T: Bagaimana cara menentukan koordinat yang tepat untuk lokasi baru bidang formulir?

 J: Anda dapat menentukan lokasi baru menggunakan`Aspose.Pdf.Rectangle` kelas, dimana Anda menentukan koordinat X dan Y dari sudut kiri atas dan koordinat X dan Y dari sudut kanan bawah dari area persegi panjang.

#### T: Apakah Aspose.PDF untuk .NET kompatibel dengan lingkungan Windows dan Linux?

J: Ya, Aspose.PDF untuk .NET kompatibel dengan lingkungan Windows dan Linux, memberikan fleksibilitas bagi pengembang untuk bekerja di sistem operasi pilihan mereka.