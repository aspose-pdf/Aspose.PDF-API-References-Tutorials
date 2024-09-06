---
title: Dapatkan Tujuan Hyperlink Dalam File PDF
linktitle: Dapatkan Tujuan Hyperlink Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mengekstrak tujuan hyperlink dalam berkas PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 60
url: /id/net/programming-with-links-and-actions/get-hyperlink-destinations/
---
Aspose.PDF untuk .NET adalah pustaka yang hebat untuk memanipulasi dan mengekstrak informasi dalam berkas PDF menggunakan bahasa pemrograman C#. Dalam tutorial ini, kami akan fokus pada ekstraksi tujuan hyperlink dari berkas PDF menggunakan Aspose.PDF untuk .NET.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Lingkungan pengembangan terpadu (IDE) seperti Visual Studio.
- Pustaka Aspose.PDF untuk .NET terinstal di komputer Anda.

## Langkah 1: Menyiapkan lingkungan pengembangan

Sebelum Anda mulai menulis kode, Anda perlu menyiapkan lingkungan pengembangan Anda dengan membuat proyek C# baru di IDE favorit Anda.

## Langkah 2: Impor referensi Aspose.PDF

Untuk menggunakan Aspose.PDF untuk .NET, Anda perlu menambahkan referensi yang sesuai ke proyek Anda. Ikuti langkah-langkah di bawah ini untuk mengimpor referensi yang diperlukan:

1. Di proyek Anda, klik kanan "Referensi" dan pilih "Tambahkan Referensi".
2. Di jendela "Tambahkan Referensi", temukan dan pilih file DLL Aspose.PDF untuk .NET.
3. Klik "OK" untuk mengimpor referensi ke proyek Anda.

## Langkah 3: Memuat File PDF

Sebelum Anda dapat mengekstrak tujuan hyperlink, Anda harus memuat berkas PDF ke dalam aplikasi Anda. Gunakan kode berikut untuk memuat berkas PDF:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Muat file PDF
Document document = new Document(dataDir + "input.pdf");
```

Pastikan untuk menentukan jalur yang benar ke direktori dokumen Anda dan berkas PDF yang ingin Anda proses.

## Langkah 4: Menavigasi halaman dokumen

Sekarang setelah file PDF dimuat, Anda perlu menelusuri semua halaman dokumen. Ini akan memungkinkan Anda untuk mendapatkan

ir anotasi hyperlink yang ada di setiap halaman. Gunakan kode berikut untuk mengulang melalui halaman dokumen:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     // Dapatkan anotasi tautan dari halaman tertentu
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     // Buat daftar untuk menyimpan semua tautan
     IList<Annotation> list = selector. Selected;
     // Ulangi setiap item dalam daftar
     foreach(LinkAnnotation a in list)
     {
         // Cetak URL tujuan
         Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
     }
}
```

Kode ini akan menelusuri setiap halaman dokumen dan memilih anotasi hyperlink yang ada di setiap halaman. Kemudian, kode ini akan menyimpan anotasi ini dalam sebuah daftar dan mencetak URL tujuan untuk setiap tautan.

## Langkah 5: Mendapatkan Tujuan Hyperlink

Langkah terakhir adalah mengekstrak tujuan hyperlink dari anotasi hyperlink. Kode berikut menunjukkan cara melakukannya:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     IList<Annotation> list = selector. Selected;
     foreach(LinkAnnotation a in list)
     {
         string destination = (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI;
         // Gunakan tujuan sesuai keinginan Anda
     }
}
```

Dalam kode ini, kita mendapatkan setiap tujuan hyperlink dari anotasi tautan dan menyimpan tujuan tersebut dalam sebuah variabel. Anda kemudian dapat menggunakan tujuan ini sesuai keinginan dalam aplikasi Anda.

### Contoh kode sumber untuk Mendapatkan Tujuan Hyperlink menggunakan Aspose.PDF untuk .NET 
```csharp
try
{
	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Muat file PDF
	Document document = new Document(dataDir + "input.pdf");
	// Melintasi semua halaman PDF
	foreach (Aspose.Pdf.Page page in document.Pages)
	{
		// Dapatkan anotasi tautan dari halaman tertentu
		AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
		page.Accept(selector);
		// Buat daftar yang berisi semua tautan
		IList<Annotation> list = selector.Selected;
		// Beriterasi melalui item individual di dalam daftar
		foreach (LinkAnnotation a in list)
		{
			// Cetak URL tujuan
			Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

### FAQ untuk mendapatkan tujuan hyperlink dalam file PDF

#### T: Apa tujuan hyperlink dalam berkas PDF?

J: Tujuan hyperlink dalam file PDF adalah lokasi atau target tertentu yang dituju hyperlink. Bisa berupa URL, halaman dalam dokumen yang sama, atau dokumen eksternal.

#### T: Bagaimana ekstraksi tujuan hyperlink dapat bermanfaat bagi analisis dokumen PDF saya?

A: Mengekstrak tujuan hyperlink memungkinkan Anda mengidentifikasi dan membuat katalog semua target yang dituju hyperlink dalam dokumen PDF. Informasi ini dapat berguna untuk validasi konten, verifikasi tautan, dan analisis data.

#### T: Bagaimana Aspose.PDF untuk .NET membantu dalam mengekstrak tujuan hyperlink?

A: Aspose.PDF untuk .NET menyediakan API yang canggih untuk mengekstrak tujuan hyperlink dengan mudah. Tutorial ini menunjukkan langkah demi langkah cara mengekstrak tujuan hyperlink menggunakan C#.

#### T: Dapatkah saya mengekstrak tujuan hyperlink secara selektif berdasarkan kriteria tertentu?

A: Ya, Anda dapat mengekstrak tujuan hyperlink secara selektif dengan mengulangi halaman-halaman dokumen PDF dan memfilter anotasi hyperlink yang diinginkan berdasarkan kriteria Anda.

#### T: Apakah mungkin untuk mengekstrak tujuan hyperlink dari dokumen PDF yang dilindungi kata sandi?

A: Aspose.PDF untuk .NET dapat mengekstrak tujuan hyperlink dari dokumen PDF yang dilindungi kata sandi selama Anda memberikan kredensial autentikasi yang diperlukan saat membuka dokumen tersebut.

#### T: Bagaimana saya dapat memanfaatkan tujuan hyperlink yang diekstrak dalam aplikasi saya?

A: Setelah Anda mengekstrak tujuan hyperlink, Anda dapat menggunakannya untuk melakukan berbagai tindakan, seperti memvalidasi URL tautan, membuat laporan, atau menerapkan navigasi khusus.

#### T: Apakah ada batasan saat mengekstrak tujuan hyperlink?

J: Meskipun ekstraksi tujuan hyperlink sangat ampuh, penting untuk mempertimbangkan struktur dokumen PDF. Hyperlink yang disematkan dalam grafik kompleks atau konten multimedia mungkin memerlukan penanganan tambahan.

#### T: Dapatkah saya mengekstrak atribut hyperlink lainnya, seperti jenis tautan atau koordinat?

J: Tutorial ini berfokus pada ekstraksi tujuan hyperlink. Namun, Anda dapat merujuk ke dokumentasi resmi Aspose.PDF untuk menjelajahi fitur-fitur lanjutan, termasuk mengekstrak jenis dan koordinat tautan.