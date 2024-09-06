---
title: Terapkan Gaya Angka Dalam File PDF
linktitle: Terapkan Gaya Angka Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menerapkan gaya penomoran pada judul dalam berkas PDF menggunakan Aspose.PDF untuk .NET. Panduan langkah demi langkah.
type: docs
weight: 10
url: /id/net/programming-with-headings/apply-number-style/
---
Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# berikut langkah demi langkah untuk menerapkan gaya penomoran dalam berkas PDF menggunakan Aspose.PDF untuk .NET.

Pastikan Anda telah menginstal pustaka Aspose.PDF dan menyiapkan lingkungan pengembangan sebelum memulai. Anda juga harus memiliki pengetahuan dasar tentang pemrograman C#.

### Langkah 1: Pengaturan Direktori Dokumen

Dalam kode sumber yang diberikan, Anda perlu menentukan direktori tempat Anda ingin menyimpan file PDF yang dihasilkan. Ubah variabel "dataDir" ke direktori yang diinginkan.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Langkah 2: Membuat Dokumen PDF

Kami membuat dokumen PDF baru dengan dimensi dan margin yang ditentukan.

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

### Langkah 3: Membuat Halaman dan Wadah Mengambang

Kami menambahkan halaman ke dokumen dan membuat wadah mengambang untuk mengatur konten.

```csharp
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

### Langkah 4: Tambahkan judul dengan penomoran

Kami membuat header dengan penomoran tertentu dan menambahkannya ke wadah mengambang.

```csharp
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading. IsInList = true;
heading. StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading. IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);

Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "Listing 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);

Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "The value, at the effective date of the plan, of the assets to be distributed under the plan

";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

### Langkah 5: Menyimpan Dokumen PDF

Kami menyimpan dokumen PDF yang dihasilkan di direktori yang ditentukan.

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style successfully applied to headers.\nFile saved as: " + dataDir);
```

### Contoh kode sumber untuk Terapkan Gaya Angka menggunakan Aspose.PDF untuk .NET 
```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
TextFragment textFragment = new TextFragment();
TextSegment segment = new TextSegment();
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan onaccount of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);  
          
```

## Kesimpulan

Dalam tutorial ini, kami menjelaskan cara menerapkan gaya penomoran pada judul dalam dokumen PDF menggunakan Aspose.PDF for .NET. Kini Anda dapat menggunakan pengetahuan ini untuk membuat dokumen PDF dengan penomoran khusus untuk judul.

### FAQ untuk menerapkan gaya angka dalam file PDF

#### T: Apa yang dimaksud dengan gaya penomoran dalam dokumen PDF?

J: Gaya penomoran mengacu pada format penomoran judul atau bagian dalam dokumen PDF. Gaya ini dapat mencakup angka, huruf, atau karakter lain untuk menyediakan struktur hierarki.

#### T: Mengapa saya perlu menerapkan gaya penomoran pada judul dalam dokumen PDF?

A: Menerapkan gaya penomoran pada judul meningkatkan keterbacaan dan pengaturan dokumen PDF Anda. Ini membantu pembaca menavigasi dan memahami struktur hierarki konten dengan mudah.

#### T: Apa itu Aspose.PDF untuk .NET?

J: Aspose.PDF untuk .NET adalah pustaka yang memungkinkan pengembang untuk bekerja dengan berkas PDF secara terprogram dalam aplikasi .NET. Pustaka ini menyediakan berbagai fitur untuk membuat, mengedit, mengonversi, dan memanipulasi dokumen PDF.

#### T: Bagaimana cara mengimpor pustaka yang dibutuhkan untuk proyek C# saya?

A: Untuk mengimpor pustaka yang diperlukan untuk proyek C# Anda, sertakan perintah impor berikut:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Arahan ini memungkinkan Anda mengakses kelas dan metode yang diperlukan untuk bekerja dengan dokumen PDF dan menerapkan gaya penomoran.

#### T: Bagaimana cara menentukan direktori untuk menyimpan berkas PDF yang dihasilkan?

A: Pada kode sumber yang disediakan, ubah variabel "dataDir" untuk menentukan direktori tempat Anda ingin menyimpan file PDF yang dihasilkan.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan jalur direktori sebenarnya.

#### T: Bagaimana cara membuat dokumen PDF dengan dimensi dan margin yang ditentukan?

A: Untuk membuat dokumen PDF dengan dimensi dan margin tertentu, gunakan kode berikut:

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

#### T: Bagaimana cara menambahkan judul dengan gaya penomoran ke dokumen PDF?

A: Untuk menambahkan judul dengan gaya penomoran ke dokumen PDF, gunakan contoh kode yang disediakan untuk membuat judul dan menyesuaikan gaya penomorannya. Sesuaikan properti seperti teks, gaya penomoran, nomor awal, dan urutan otomatis sesuai kebutuhan.

#### T: Bagaimana cara menyimpan dokumen PDF yang dihasilkan?

 A: Untuk menyimpan dokumen PDF yang dihasilkan, gunakan`Save` metode dari`pdfDoc` obyek:

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style applied to headers.\nFile saved as: " + dataDir);
```

#### T: Bagaimana saya dapat mengonfirmasi bahwa gaya penomoran telah diterapkan?

A: Buka file PDF yang dihasilkan untuk memverifikasi bahwa gaya penomoran yang ditentukan telah diterapkan pada judul.

#### T: Dapatkah saya menyesuaikan gaya penomoran lebih lanjut?

 A: Ya, Anda dapat menyesuaikan gaya penomoran lebih lanjut dengan menyesuaikan properti`Heading` objek, seperti jenis gaya penomoran, nomor awal, dan urutan otomatis.

#### T: Dapatkah saya menerapkan gaya penomoran yang berbeda pada bagian-bagian dokumen yang berbeda?

 A: Ya, Anda dapat menerapkan gaya penomoran yang berbeda ke bagian dokumen yang berbeda dengan membuat beberapa`Heading` objek dengan gaya dan urutan yang berbeda.