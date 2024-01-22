---
title: Tambahkan Anotasi lnk
linktitle: Tambahkan Anotasi lnk
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menambahkan fitur Anotasi Tinta ke dokumen PDF di C# menggunakan Aspose.PDF untuk .NET dengan panduan langkah demi langkah dan kode sumber lengkap.
type: docs
weight: 20
url: /id/net/annotations/addlnkannotation/
---
Aspose.PDF untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang melakukan berbagai operasi PDF. Salah satu operasi tersebut adalah menambahkan Anotasi Tinta ke dokumen PDF. Pada artikel ini, kami akan memberikan panduan langkah demi langkah untuk menjelaskan kode sumber C# untuk menambahkan Anotasi Tinta menggunakan Aspose.PDF untuk .NET. Mari kita mulai!

## Memahami Fitur Anotasi Tinta Aspose.PDF untuk .NET

Sebelum mendalami kode sumber C#, mari kita pahami dulu apa itu Anotasi Tinta dan kegunaannya.

Anotasi Tinta adalah cara menggambar anotasi tinta bentuk bebas pada dokumen PDF. Ini memungkinkan Anda membuat anotasi dengan stylus atau mouse. Fitur ini berguna dalam situasi ketika Anda perlu menggambar diagram, sketsa, atau jenis anotasi lainnya.

## Langkah 1: Membuat Dokumen Baru

Langkah pertama dalam menambahkan Anotasi Tinta ke dokumen PDF adalah membuat instance baru dari kelas Dokumen. Hal ini dicapai dengan menggunakan cuplikan kode berikut:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
Page pdfPage = doc.Pages.Add();
```

Di sini, kita membuat instance baru dari kelas Dokumen dan menambahkan halaman baru ke dalamnya.

## Langkah 2: Membuat Anotasi Tinta

Langkah selanjutnya adalah membuat instance kelas InkAnnotation. Ini dilakukan dengan menggunakan cuplikan kode berikut:

```csharp
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(goresan.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);
```

Di sini, pertama-tama kita membuat persegi panjang menggunakan kelas System.Drawing.Rectangle dan mengubahnya menjadi Aspose.Pdf.Rectangle menggunakan metode FromRect. Kami kemudian membuat instance kelas InkAnnotation menggunakan persegi panjang, daftar titik, dan halaman tempat anotasi ditambahkan.

Kami kemudian mengatur berbagai properti InkAnnotation, seperti judul, warna, gaya topi, batas, dan opacity. Terakhir, kami menambahkan anotasi ke halaman menggunakan metode Annotations.Add.

## Langkah 3: Menyimpan Dokumen

Langkah terakhir adalah menyimpan dokumen PDF dengan menambahkan Anotasi Tinta. Hal ini dicapai dengan menggunakan cuplikan kode berikut:

```csharp
dataDir = dataDir + "AddlnkAnnotation_out.pdf";
doc.Save(dataDir);
```

Di sini, kami menggabungkan nama file keluaran ke direktori data dan menyimpan dokumen menggunakan metode Simpan.

### Contoh kode sumber untuk Menambahkan Anotasi Tinta menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DATA DIRECTORY";


Document doc = new Document();
Page pdfPage = doc.Pages.Add();
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(goresan.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);

dataDir = dataDir + "AddlnkAnnotation_out.pdf";
// Simpan file keluaran
doc.Save(dataDir);
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara menambahkan Anotasi Tinta ke dokumen PDF menggunakan Aspose.PDF untuk .NET. Dengan mengikuti panduan langkah demi langkah dan kode sumber C# yang disediakan, pengembang dapat dengan mudah mengimplementasikan fungsionalitas Anotasi Tinta dalam aplikasi pemrosesan PDF mereka.

### FAQ

#### T: Apa yang dimaksud dengan Anotasi Tinta dalam dokumen PDF?

J: Anotasi Tinta dalam dokumen PDF memungkinkan pengguna menggambar anotasi tinta bentuk bebas menggunakan stylus atau mouse. Biasanya digunakan untuk menambahkan sketsa gambar tangan, diagram, atau anotasi tangan lainnya ke PDF.

#### T: Dapatkah saya menyesuaikan tampilan Anotasi Tinta?

J: Ya, Aspose.PDF untuk .NET menyediakan berbagai properti untuk menyesuaikan tampilan Anotasi Tinta, seperti warna, opasitas, gaya batas, lebar tepi, dan lainnya. Pengembang dapat menyesuaikan properti ini untuk memenuhi kebutuhan spesifik mereka.

#### T: Apakah mungkin untuk menambahkan beberapa Anotasi Tinta ke satu halaman PDF?

J: Ya, Anda dapat menambahkan beberapa Anotasi Tinta ke satu halaman PDF menggunakan Aspose.PDF untuk .NET. Setiap Anotasi Tinta dapat memiliki kumpulan poin dan tampilan yang disesuaikan.

#### T: Dapatkah saya menambahkan Anotasi Tinta ke dokumen PDF yang sudah ada?

J: Ya, Aspose.PDF untuk .NET memungkinkan Anda menambahkan Anotasi Tinta ke dokumen PDF yang baru dibuat dan file PDF yang sudah ada. Anda dapat membuka PDF yang sudah ada, menambahkan Anotasi Tinta, dan menyimpan dokumen yang diperbarui.

#### T: Apa saja kasus penggunaan umum Anotasi Tinta dalam dokumen PDF?

J: Anotasi Tinta berguna untuk berbagai aplikasi, termasuk menambahkan tanda tangan atau catatan tulisan tangan ke formulir PDF, memberi anotasi pada cetak biru arsitektur atau gambar teknik, dan menandai dokumen untuk tinjauan kolaboratif.