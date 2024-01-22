---
title: Formulir Bidang Font 14
linktitle: Formulir Bidang Font 14
second_title: Aspose.PDF untuk Referensi .NET API
description: Konfigurasikan font bidang formulir dengan mudah di dokumen PDF Anda dengan Aspose.PDF untuk .NET.
type: docs
weight: 110
url: /id/net/programming-with-forms/form-field-font-14/
---
Dalam tutorial ini, kami akan menunjukkan cara mengonfigurasi font bidang formulir menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber C# langkah demi langkah untuk memandu Anda melalui proses ini.

## Langkah 1: Persiapan

Pertama, pastikan Anda telah mengimpor perpustakaan yang diperlukan dan mengatur jalur ke direktori dokumen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Buka dokumen

Buka dokumen PDF yang ada:

```csharp
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
```

## Langkah 3: Dapatkan bidang formulir tertentu

Dapatkan kolom formulir yang diinginkan (dalam contoh ini, kami menggunakan kolom "kotak teks1"):

```csharp
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
```

## Langkah 4: Buat objek font

Buat objek font untuk font baru yang ingin Anda gunakan (misalnya, "ComicSansMS"):

```csharp
Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
```

## Langkah 5: Konfigurasikan informasi font untuk bidang formulir

Konfigurasikan informasi font untuk bidang formulir menggunakan font yang dibuat sebelumnya:

```csharp
field.DefaultAppearance = new Aspose.Pdf.Forms.DefaultAppearance(font, 14, System.Drawing.Color.Black);
```

## Langkah 6: Simpan dokumen yang diperbarui

Simpan dokumen PDF yang diperbarui:

```csharp
dataDir = dataDir + "FormFieldFont14_out.pdf";
pdfDocument.Save(dataDir);
```


### Contoh kode sumber untuk Form Field Font 14 menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
// Dapatkan bidang formulir tertentu dari dokumen
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
// Buat objek font
Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
// Atur informasi font untuk bidang formulir
// Field.DefaultAppearance = Aspose.Pdf.Forms.in.DefaultAppearance baru (font, 10, System.Drawing.Color.Black);
dataDir = dataDir + "FormFieldFont14_out.pdf";
// Simpan dokumen yang diperbarui
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field font setup successfully.\nFile saved at " + dataDir);
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara mengonfigurasi font bidang formulir menggunakan Aspose.PDF untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah menentukan font dan ukuran font untuk bidang formulir di dokumen PDF Anda menggunakan Aspose.PDF.

### FAQ

#### T: Dapatkah saya menggunakan font apa pun untuk bidang formulir di Aspose.PDF untuk .NET?

J: Ya, Anda dapat menggunakan font TrueType atau OpenType apa pun untuk bidang formulir di Aspose.PDF untuk .NET. Selama font tersedia dan diinstal pada sistem atau dapat diakses melalui FontRepository, Anda dapat menggunakannya untuk menyesuaikan tampilan teks bidang formulir.

#### T: Bagaimana cara menemukan font yang tersedia di Aspose.PDF untuk .NET?

 J: Untuk menemukan font yang tersedia di Aspose.PDF untuk .NET, Anda dapat menggunakan`FontRepository.GetAvailableFonts()`metode. Metode ini mengembalikan serangkaian font yang tersedia yang bisa Anda gunakan untuk bidang formulir atau operasi terkait teks lainnya di dokumen PDF Anda.

#### T: Dapatkah saya mengubah ukuran font untuk bidang formulir ke nilai apa pun?

J: Ya, Anda dapat mengubah ukuran font untuk bidang formulir ke nilai numerik positif apa pun menggunakan Aspose.PDF untuk .NET. Namun, penting untuk memastikan bahwa ukuran font sesuai untuk bidang formulir tertentu dan tidak menyebabkan teks terpotong atau tumpang tindih dengan elemen lain dalam dokumen.

#### T: Bisakah saya mengubah warna font untuk kolom formulir?

J: Ya, Anda dapat mengubah warna font untuk kolom formulir menggunakan Aspose.PDF untuk .NET. Dalam kode sumber C# yang disediakan, warna font diatur menjadi hitam (`System.Drawing.Color.Black`), namun Anda dapat menyesuaikannya dengan nilai warna valid lainnya.

#### T: Bagaimana cara menyelaraskan teks dalam bidang formulir?

 J: Untuk menyelaraskan teks dalam bidang formulir, Anda dapat menggunakan`Multiline`properti bidang formulir dan atur ke true. Properti ini mengaktifkan teks multibaris dalam bidang formulir, memungkinkan Anda mengontrol perataan teks dengan jeda baris dan kembalinya baris.