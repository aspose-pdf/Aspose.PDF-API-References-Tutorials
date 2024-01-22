---
title: XPS Ke PDF
linktitle: XPS Ke PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Panduan langkah demi langkah untuk mengonversi file XPS ke PDF dengan Aspose.PDF untuk .NET.
type: docs
weight: 350
url: /id/net/document-conversion/xps-to-pdf/
---
Dalam tutorial ini, kami akan memandu Anda tentang cara mengonversi file XPS ke PDF menggunakan perpustakaan Aspose.PDF untuk .NET langkah demi langkah. Kami akan merinci kode sumber C# yang disediakan dan menunjukkan cara mengimplementasikannya dalam proyek Anda sendiri. Di akhir tutorial ini, Anda akan dapat dengan mudah mengonversi file XPS ke dokumen PDF.

## Langkah 1: Tetapkan Direktori Dokumen
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 Mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan jalur tempat Anda menyimpan file Anda.

## Langkah 2: Buat Instansiasi Objek LoadOptions Menggunakan Opsi Pemuatan XPS
```csharp
Aspose.Pdf.LoadOptions options = new XpsLoadOptions();
```
Buat instance objek LoadOptions menggunakan opsi pemuatan XPS.

## Langkah 3: Buat Objek Dokumen
```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);
```
Buat objek Dokumen yang menentukan input file XPS dan opsi pemuatan.

## Langkah 4: Simpan Dokumen PDF yang Dihasilkan
```csharp
document.Save(dataDir + "XPSToPDF_out.pdf");
```
Simpan dokumen PDF yang dihasilkan ke direktori yang ditentukan.

### Contoh kode sumber untuk XPS ke PDF menggunakan Aspose.PDF untuk .NET

```csharp
try
{
	
	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	//Buat instance objek LoadOption menggunakan opsi pemuatan XPS
	Aspose.Pdf.LoadOptions options = new XpsLoadOptions();

	// Buat objek dokumen
	Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);

	// Simpan dokumen PDF yang dihasilkan
	document.Save(dataDir + "XPSToPDF_out.pdf");
	
}
catch(Exception ex)
   
{
	Console.WriteLine(ex.Message);
}
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara mengonversi file XPS ke PDF menggunakan perpustakaan Aspose.PDF untuk .NET. Dengan mengikuti langkah-langkah yang disediakan, Anda dapat dengan mudah melakukan konversi ini di aplikasi Anda sendiri. Dapatkan hasil yang akurat dan profesional saat mengonversi file XPS ke PDF.

### FAQ

#### T: Apa itu XPS dan mengapa saya ingin mengonversinya ke PDF?

J: XPS (Spesifikasi Kertas XML) adalah format dokumen tata letak tetap yang dikembangkan oleh Microsoft. Mengonversi XPS ke PDF memungkinkan Anda membuat dokumen lebih mudah diakses dan kompatibel secara luas, karena PDF adalah format yang didukung secara universal di berbagai platform dan perangkat.

#### T: Apakah pustaka Aspose.PDF mendukung format file lain selain XPS?

J: Ya, Aspose.PDF untuk .NET mendukung berbagai format file lain untuk konversi, seperti HTML, EPUB, SVG, XML, dan lainnya. Ini juga memungkinkan Anda membuat dan memanipulasi dokumen PDF secara terprogram.

#### T: Dapatkah saya menyesuaikan proses konversi PDF, seperti mengatur ukuran halaman, margin, atau opsi lainnya?

J: Ya, Anda dapat menyesuaikan proses konversi PDF menggunakan Aspose.PDF untuk .NET. Perpustakaan menyediakan berbagai pilihan untuk mengontrol ukuran halaman, margin, kompresi gambar, penyematan font, dan pengaturan terkait PDF lainnya untuk memenuhi kebutuhan spesifik Anda.

#### T: Apakah ada versi uji coba Aspose.PDF untuk .NET yang tersedia untuk pengujian?

A: Ya, Anda dapat mengunduh dan mencoba versi uji coba Aspose.PDF untuk .NET dari situs resmi Aspose. Versi uji coba memungkinkan Anda menjelajahi fitur perpustakaan sebelum melakukan pembelian.

#### T: Dapatkah saya mengonversi beberapa file XPS ke PDF dalam proses batch?

J: Ya, Anda dapat mengonversi beberapa file XPS ke PDF dalam proses batch dengan menerapkan loop atau mengulangi daftar file XPS dan mengonversi setiap file ke PDF menggunakan kode yang disediakan.