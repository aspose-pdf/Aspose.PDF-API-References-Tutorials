---
title: Kolom tulisan
linktitle: Kolom tulisan
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara membuat bidang teks dalam dokumen PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 290
url: /id/net/programming-with-forms/text-box/
---
Dalam panduan ini, kami akan menjelaskan langkah demi langkah cara menggunakan perpustakaan Aspose.PDF untuk .NET untuk membuat kolom teks dalam dokumen PDF. Kami akan menunjukkan cara membuka dokumen, membuat bidang teks, menyesuaikan propertinya, dan menyimpan PDF yang telah diedit.

## Langkah 1: Mengonfigurasi direktori dokumen

 Langkah pertama adalah mengkonfigurasi direktori dokumen tempat file PDF yang ingin Anda kerjakan berada. Anda dapat menggunakan`dataDir` variabel untuk menentukan jalur direktori.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Pastikan untuk mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 2: Membuka dokumen PDF

Pada langkah ini, kita akan membuka dokumen PDF menggunakan`Document` kelas Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "TextField.pdf");
```

Pastikan file PDF ada di direktori dokumen yang ditentukan.

## Langkah 3: Membuat bidang teks

 Kami akan membuat bidang teks menggunakan`TextBoxField` kelas. Anda dapat menentukan koordinat posisi dan ukuran bidang menggunakan`Rectangle` kelas.

```csharp
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField. PartialName = "textbox1";
textBoxField.Value = "Text Field";
```

Sesuaikan koordinat, ukuran, nama sebagian, dan nilai bidang teks sesuai kebutuhan.

## Langkah 4: Sesuaikan properti bidang teks

Pada langkah ini, kita akan menyesuaikan properti bidang teks seperti batas, warna, dll.

```csharp
Border border = new Border(textBoxField);
border. width = 5;
border. Dash = new Dash(1, 1);
textBoxField. Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```

Sesuaikan properti bidang teks sesuai dengan preferensi Anda.

## Langkah 5: Menambahkan bidang ke dokumen

Sekarang kita telah membuat dan mengkonfigurasi kolom teks, kita dapat menambahkannya ke dokumen PDF.

```csharp
pdfDocument.Form.Add(textBoxField, 1);
```

## Langkah 6: Menyimpan PDF yang dimodifikasi

 Terakhir, kita dapat menyimpan PDF yang telah dimodifikasi menggunakan`Save` metode`Document` kelas.

```csharp
dataDir = dataDir + "TextBox_out.pdf";
pdfDocument.Save(dataDir);
```

Pastikan untuk menentukan jalur lengkap dan nama file untuk PDF yang diedit.

### Contoh kode sumber untuk Kotak Teks menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document pdfDocument = new Document(dataDir + "TextField.pdf");
// Buat bidang
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField.PartialName = "textbox1";
textBoxField.Value = "Text Box";
//TextBoxField.Border = Perbatasan baru(
Border border = new Border(textBoxField);
border.Width = 5;
border.Dash = new Dash(1, 1);
textBoxField.Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
// Tambahkan bidang ke dokumen
pdfDocument.Form.Add(textBoxField, 1);
dataDir = dataDir + "TextBox_out.pdf";
// Simpan PDF yang dimodifikasi
pdfDocument.Save(dataDir);
Console.WriteLine("\nTextbox field added successfully.\nFile saved at " + dataDir);
```

## Kesimpulan

Dalam panduan ini, kita mempelajari cara menggunakan perpustakaan Aspose.PDF untuk .NET untuk membuat bidang teks dalam dokumen PDF. Dengan mengikuti langkah-langkah yang dijelaskan, Anda bisa menyesuaikan properti bidang teks dan menambahkannya ke dokumen sesuai kebutuhan. Jangan ragu untuk menjelajahi lebih jauh fitur Aspose.PDF untuk .NET guna memperluas kemungkinan memanipulasi file PDF.

### FAQ

#### T: Dapatkah saya menggunakan Aspose.PDF untuk .NET untuk membuat beberapa bidang teks dalam satu dokumen PDF?

J: Ya, Anda dapat membuat beberapa bidang teks dalam satu dokumen PDF menggunakan Aspose.PDF untuk .NET. Cukup ulangi proses membuat dan menyesuaikan bidang teks untuk setiap lokasi yang diinginkan dalam dokumen.

#### T: Bagaimana cara menyesuaikan tampilan bidang teks, seperti ukuran dan warna font?

J: Anda dapat menyesuaikan tampilan bidang teks dengan menyesuaikan propertinya, seperti ukuran font, gaya font, warna, gaya batas, warna latar belakang, dan lainnya. Dalam contoh kode sumber yang disediakan, lebar batas, pola garis batas, dan warna teks disesuaikan.

#### T: Apakah mungkin untuk mengekstrak teks yang dimasukkan pengguna dari kolom teks yang dibuat?

J: Ya, Anda dapat mengekstrak teks yang dimasukkan pengguna dari kolom teks yang dibuat. Setelah pengguna mengisi kolom teks di dokumen PDF, Anda dapat mengambil nilai kolom secara terprogram menggunakan Aspose.PDF untuk .NET.

#### T: Bisakah saya menambahkan kolom teks ke dokumen PDF yang sudah ada tanpa membuat yang baru?

J: Ya, Anda dapat menambahkan kolom teks ke dokumen PDF yang sudah ada tanpa membuat yang baru. Aspose.PDF untuk .NET menyediakan kemampuan untuk memodifikasi dokumen PDF yang ada, termasuk menambahkan kolom teks, kotak centang, dan elemen formulir lainnya.

#### T: Apakah Aspose.PDF untuk .NET mendukung jenis bidang formulir lainnya, seperti kotak centang dan tombol radio?

J: Ya, Aspose.PDF untuk .NET mendukung berbagai jenis bidang formulir, termasuk kotak centang, tombol radio, daftar dropdown, dan banyak lagi. Anda bisa menggunakan perpustakaan untuk bekerja dengan berbagai tipe elemen formulir dalam dokumen PDF.