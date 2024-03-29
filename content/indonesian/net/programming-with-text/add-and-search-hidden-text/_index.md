---
title: Tambahkan Dan Cari Teks Tersembunyi Dalam File PDF
linktitle: Tambahkan Dan Cari Teks Tersembunyi Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Panduan langkah demi langkah untuk menambahkan dan mencari teks tersembunyi dalam file PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 20
url: /id/net/programming-with-text/add-and-search-hidden-text/
---
Dalam tutorial ini, kami akan memandu Anda tentang cara menambahkan dan mencari teks tersembunyi di file PDF menggunakan Aspose.PDF untuk .NET. Ikuti langkah-langkah berikut untuk melakukan operasi ini dengan mudah.

## 1. Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau lingkungan pengembangan lainnya diinstal dan dikonfigurasi.
- Pengetahuan dasar tentang bahasa pemrograman C#.
- Pustaka Aspose.PDF untuk .NET diinstal. Anda dapat mendownloadnya dari situs resmi Aspose.

## 2. Membuat dokumen PDF dengan teks tersembunyi

Untuk memulai, gunakan kode berikut untuk membuat dokumen PDF baru yang berisi teks tersembunyi:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Buat dokumen
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
// Setel properti teks - tidak terlihat
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

Pastikan untuk memberikan jalur dan nama file yang diinginkan untuk dokumen PDF.

## 3. Cari teks dalam dokumen

Selanjutnya, kita akan mencari teks tersembunyi di dokumen PDF. Gunakan kode berikut:

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb.Visit(doc.Pages[1]);
foreach(TextFragment fragment in absorber.TextFragments)
{
//Lakukan sesuatu dengan pecahannya
Console.WriteLine("Text '{0}' at position {1}, invisibility: {2} ",
fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

Ini akan mencari teks tersembunyi di halaman kedua dokumen PDF dan menampilkan informasi yang relevan.

### Contoh kode sumber untuk Tambah dan Cari Teks Tersembunyi menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Buat dokumen dengan teks tersembunyi
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
//Setel properti teks - tidak terlihat
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
//Cari teks dalam dokumen
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
foreach (TextFragment fragment in absorber.TextFragments)
{
	//Lakukan sesuatu dengan pecahan
	Console.WriteLine("Text '{0}' on pos {1} invisibility: {2} ",
	fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

## Kesimpulan

Selamat! Anda telah berhasil menambahkan dan menemukan teks tersembunyi dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Anda sekarang dapat menerapkan metode ini pada proyek Anda sendiri untuk memanipulasi dan mencari teks tersembunyi dalam file PDF.

### FAQ

#### T: Apa itu Aspose.PDF untuk .NET?

J: Aspose.PDF untuk .NET adalah perpustakaan tangguh yang memberdayakan pengembang untuk membuat, memanipulasi, dan mengubah dokumen PDF dalam aplikasi .NET.

#### T: Apakah teks tersembunyi dapat digunakan untuk tujuan watermarking?

J: Tentu saja! Teks tersembunyi dapat berfungsi sebagai cara efektif untuk memberi tanda air pada dokumen PDF, sehingga menambah lapisan keamanan ekstra.

#### T: Apakah mungkin untuk mengungkap teks tersembunyi dalam dokumen PDF?

J: Ya, proses pencarian dan pengungkapan teks tersembunyi dalam dokumen PDF dapat dilakukan dengan menggunakan teknik yang diuraikan dalam tutorial ini.

#### T: Apa fungsi lain yang ditawarkan Aspose.PDF untuk .NET?

J: Selain manipulasi teks tersembunyi, Aspose.PDF untuk .NET menyediakan beragam fitur, termasuk pembuatan PDF, konversi, enkripsi, dan banyak lagi.