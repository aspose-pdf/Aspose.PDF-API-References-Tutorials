---
title: Peningkatan Kinerja TIFF Ke PDF
linktitle: Peningkatan Kinerja TIFF Ke PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Panduan langkah demi langkah untuk meningkatkan kinerja konversi TIFF ke PDF dengan Aspose.PDF untuk .NET.
type: docs
weight: 310
url: /id/net/document-conversion/tiff-to-pdf-performance-improvement/
---
Dalam tutorial ini, kami akan memandu Anda langkah demi langkah cara meningkatkan kinerja mengonversi file TIFF ke PDF menggunakan perpustakaan Aspose.PDF untuk .NET. Kami akan merinci kode sumber C# yang disediakan dan menunjukkan cara mengimplementasikannya dalam proyek Anda sendiri. Di akhir tutorial ini, Anda akan dapat melakukan konversi file TIFF ke PDF dengan lebih cepat dan efisien.

## Langkah 1: Tetapkan Direktori Dokumen
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 Mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan jalur tempat Anda menyimpan file Anda.

## Langkah 2: Dapatkan Daftar File TIFF
```csharp
string[] files = System.IO.Directory.GetFiles(dataDir, "*.tif");
```
Dapatkan daftar file TIFF yang ada di direktori yang ditentukan.

## Langkah 3: Buat instance objek Dokumen
```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```
Buat sebuah instance dari objek Dokumen.

## Langkah 4: Telusuri File dan Tambahkan ke Dokumen PDF
```csharp
foreach (string myFile in files)
{
     FileStream fs = new FileStream(myFile, FileMode.Open, FileAccess.Read);
     byte[] tmpBytes = new byte[fs.Length];
     fs.Read(tmpBytes, 0, Convert.ToInt32(fs.Length));

     MemoryStream mystream = new MemoryStream(tmpBytes);
     Bitmap b = new Bitmap(mystream);
     Aspose.Pdf.Page currpage = doc.Pages.Add();

     currpage.PageInfo.Margin.Top = 5;
     currpage.PageInfo.Margin.Bottom = 5;
     currpage.PageInfo.Margin.Left = 5;
     currpage.PageInfo.Margin.Right = 5;

     currpage.PageInfo.Width = (b.Width / b.HorizontalResolution) * 72;
     currpage.PageInfo.Height = (b.Height / b.VerticalResolution) * 72;

     Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

     currpage.Paragraphs.Add(image1);

     image1.IsBlackWhite = true;
     image1.ImageStream = mystream;
     image1.ImageScale = 0.95F;
}
```
 Telusuri setiap file TIFF, muat sebagai a`Bitmap` objek, lalu tambahkan ke dokumen PDF. Parameter seperti margin, resolusi dan skala gambar juga dikonfigurasi.

## Langkah 5: Simpan File PDF yang Dihasilkan
```csharp
doc.Save(dataDir + "PerformaceImprovement_out.pdf");
```
Simpan dokumen PDF yang dihasilkan ke direktori yang ditentukan.

### Contoh kode sumber untuk Peningkatan Kinerja TIFF ke PDF menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dapatkan daftar file gambar tiff
string[] files = System.IO.Directory.GetFiles(dataDir, "*.tif");

// Buat instance objek Dokumen
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Navigasi melalui file dan file tersebut di file pdf
foreach (string myFile in files)
{

	// Muat semua file tiff dalam array byte
	FileStream fs = new FileStream(myFile, FileMode.Open, FileAccess.Read);
	byte[] tmpBytes = new byte[fs.Length];
	fs.Read(tmpBytes, 0, Convert.ToInt32(fs.Length));

	MemoryStream mystream = new MemoryStream(tmpBytes);
	Bitmap b = new Bitmap(mystream);
	// Buat Halaman baru di dokumen Pdf
	Aspose.Pdf.Page currpage = doc.Pages.Add();

	// Tetapkan margin agar gambar pas, dll.
	currpage.PageInfo.Margin.Top = 5;
	currpage.PageInfo.Margin.Bottom = 5;
	currpage.PageInfo.Margin.Left = 5;
	currpage.PageInfo.Margin.Right = 5;

	currpage.PageInfo.Width = (b.Width / b.HorizontalResolution) * 72;
	currpage.PageInfo.Height = (b.Height / b.VerticalResolution) * 72;

	// Buat objek gambar
	Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

	// Tambahkan gambar ke dalam kumpulan paragraf halaman
	currpage.Paragraphs.Add(image1);

	// Tetapkan properti IsBlackWhite ke true untuk peningkatan kinerja
	image1.IsBlackWhite = true;
	// Atur ImageStream ke objek MemoryStream
	image1.ImageStream = mystream;
	// Atur skala gambar yang diinginkan
	image1.ImageScale = 0.95F;
}

// Simpan Pdfnya
doc.Save(dataDir + "PerformaceImprovement_out.pdf");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara meningkatkan kinerja mengonversi file TIFF ke PDF menggunakan perpustakaan Aspose.PDF untuk .NET. Dengan mengikuti langkah-langkah yang disediakan, Anda akan dapat mencapai konversi file TIFF ke PDF yang lebih cepat dan efisien. Dapatkan hasil yang tepat dan profesional sekaligus mengoptimalkan kinerja aplikasi Anda

### FAQ

#### T: Apa itu Aspose.PDF untuk .NET?

J: Aspose.PDF untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang bekerja dengan dokumen PDF dalam aplikasi C#. Ia menawarkan berbagai fungsi, termasuk mengkonversi file TIFF ke PDF.

#### T: Mengapa saya ingin meningkatkan kinerja konversi TIFF ke PDF?

J: Meningkatkan kinerja konversi TIFF ke PDF dapat meningkatkan efisiensi aplikasi Anda secara signifikan, terutama ketika menangani file TIFF dalam jumlah besar. Konversi yang lebih cepat menghasilkan pengalaman pengguna yang lebih baik dan waktu pemrosesan yang lebih singkat.

#### T: Bagaimana cara mengatur direktori untuk file TIFF?

 A: Anda dapat mengatur direktori untuk file TIFF dengan mengganti`"YOUR DOCUMENTS DIRECTORY"` placeholder dalam kode dengan jalur sebenarnya tempat file TIFF Anda berada.

#### T: Pengoptimalan apa yang diterapkan dalam cuplikan kode untuk meningkatkan kinerja?

 J: Cuplikan kode menggunakan berbagai teknik untuk meningkatkan kinerja konversi, seperti mengatur margin, mengonfigurasi resolusi dan skala gambar, dan mengatur`IsBlackWhite`properti menjadi benar. Pengoptimalan ini membantu menyederhanakan proses konversi.

#### T: Bisakah saya menyesuaikan properti gambar di PDF yang dihasilkan?

J: Ya, Anda dapat menyesuaikan properti gambar dalam PDF yang dihasilkan, seperti skala, resolusi, dan margin, untuk mendapatkan tata letak dan tampilan yang diinginkan.