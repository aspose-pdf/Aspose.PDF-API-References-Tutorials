---
title: Tambahkan dan Cari Teks Tersembunyi Dalam File PDF
linktitle: Tambahkan dan Cari Teks Tersembunyi Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Panduan langkah demi langkah untuk menambahkan dan mencari teks tersembunyi dalam berkas PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 20
url: /id/net/programming-with-text/add-and-search-hidden-text/
---
Dalam tutorial ini, kami akan memandu Anda untuk menambahkan dan mencari teks tersembunyi dalam file PDF menggunakan Aspose.PDF for .NET. Ikuti langkah-langkah berikut untuk melakukan operasi ini dengan mudah.

## 1. Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau lingkungan pengembangan lainnya terinstal dan dikonfigurasi.
- Pengetahuan dasar tentang bahasa pemrograman C#.
- Pustaka Aspose.PDF untuk .NET telah terinstal. Anda dapat mengunduhnya dari situs web resmi Aspose.

## 2. Membuat dokumen PDF dengan teks tersembunyi

Untuk memulai, gunakan kode berikut untuk membuat dokumen PDF baru yang berisi teks tersembunyi:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Membuat dokumen
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
// Atur properti teks - tidak terlihat
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

Pastikan untuk memberikan jalur dan nama file yang diinginkan untuk dokumen PDF.

## 3. Mencari teks dalam dokumen

Selanjutnya, kita akan mencari teks tersembunyi dalam dokumen PDF. Gunakan kode berikut:

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb.Visit(doc.Pages[1]);
foreach(TextFragment fragment in absorber.TextFragments)
{
//Lakukan sesuatu dengan pecahan-pecahan tersebut
Console.WriteLine("Text '{0}' at position {1}, invisibility: {2} ",
fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

Ini akan mencari teks tersembunyi di halaman kedua dokumen PDF dan menampilkan informasi relevan.

### Contoh kode sumber untuk Menambahkan dan Mencari Teks Tersembunyi menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Buat dokumen dengan teks tersembunyi
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
//Atur properti teks - tidak terlihat
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
//Mencari teks dalam dokumen
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
foreach (TextFragment fragment in absorber.TextFragments)
{
	//Lakukan sesuatu dengan fragmen
	Console.WriteLine("Text '{0}' on pos {1} invisibility: {2} ",
	fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

## Kesimpulan

Selamat! Anda telah berhasil menambahkan dan menemukan teks tersembunyi dalam dokumen PDF menggunakan Aspose.PDF for .NET. Kini Anda dapat menerapkan metode ini ke proyek Anda sendiri untuk memanipulasi dan mencari teks tersembunyi dalam file PDF.

### Pertanyaan yang Sering Diajukan

#### T: Apa itu Aspose.PDF untuk .NET?

J: Aspose.PDF untuk .NET adalah pustaka tangguh yang memberdayakan pengembang untuk membuat, memanipulasi, dan mengubah dokumen PDF dalam aplikasi .NET.

#### T: Bisakah teks tersembunyi digunakan untuk tujuan pemberian tanda air?

A: Tentu saja! Teks tersembunyi dapat berfungsi sebagai cara yang efektif untuk memberi tanda air pada dokumen PDF, dengan menambahkan lapisan keamanan ekstra.

#### T: Apakah mungkin untuk mengungkap teks tersembunyi dalam dokumen PDF?

A: Ya, proses pencarian dan pengungkapan teks tersembunyi dalam dokumen PDF dapat dicapai menggunakan teknik yang diuraikan dalam tutorial ini.

#### T: Fungsionalitas apa lagi yang ditawarkan Aspose.PDF untuk .NET?

A: Selain manipulasi teks tersembunyi, Aspose.PDF untuk .NET menyediakan beragam fitur, termasuk pembuatan PDF, konversi, enkripsi, dan banyak lagi.