---
title: Tambahkan Daftar Isi ke File PDF
linktitle: Tambahkan Daftar Isi ke File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menambahkan daftar isi ke file PDF menggunakan Aspose.PDF untuk .NET. Panduan langkah demi langkah dengan contoh kode sumber. Tingkatkan navigasi dokumen!
type: docs
weight: 40
url: /id/net/programming-with-document/addtoc/
---
Dalam tutorial ini, kita akan mempelajari cara menggunakan fitur Tambahkan TOC (Daftar Isi) ke file PDF Aspose.PDF untuk .NET untuk menambahkan daftar isi ke dokumen PDF. Kami akan memberikan panduan langkah demi langkah dan menjelaskan kode sumber C# yang diperlukan untuk mencapai hal ini. Di akhir tutorial ini, Anda akan dapat membuat dokumen PDF dengan daftar isi menggunakan Aspose.PDF untuk .NET.


## Langkah 1: Muat file PDF yang ada

 Untuk memulai, kita perlu memuat file PDF yang ada. Mengganti`"YOUR DOCUMENT DIRECTORY"` dalam kode berikut dengan jalur sebenarnya ke file PDF Anda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

## Langkah 2: Buat halaman baru untuk daftar isi

Kami akan membuat halaman baru untuk menampung daftar isi. Kode berikut menyisipkan halaman baru di indeks 1:

```csharp
Page tocPage = doc.Pages.Insert(1);
```

## Langkah 3: Tentukan informasi daftar isi

Selanjutnya, kita perlu mendefinisikan informasi daftar isi. Kita akan mengatur judul dan properti lain dari daftar isi. Tambahkan kode berikut:

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

## Langkah 4: Buat elemen TOC

Sekarang kita akan membuat elemen daftar isi. Dalam tutorial ini, kita akan membuat empat elemen TOC yang sesuai dengan halaman berbeda. Ubah kode berikut sesuai kebutuhan Anda:

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";

for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;

    segment2.Text = titles[i];
    tocPage.Paragraphs.Add(heading2);
}
```

## Langkah 5: Simpan dokumen yang diperbarui

 Terakhir, kita perlu menyimpan dokumen yang dimodifikasi beserta daftar isinya. Mengganti`"YOUR DOCUMENT DIRECTORY"` pada kode di bawah ini dengan jalur file keluaran yang diinginkan:

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

### Contoh kode sumber untuk Menambahkan TOC ke dokumen PDF menggunakan Aspose.PDF untuk .NET

```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Muat file PDF yang ada
Document doc = new Document(dataDir + "AddTOC.pdf");

// Dapatkan akses ke halaman pertama file PDF
Page tocPage = doc.Pages.Insert(1);

// Buat objek untuk mewakili informasi TOC
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

// Tetapkan judul TOC
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;

//Buat objek string yang akan digunakan sebagai elemen TOC
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
for (int i = 0; i < 2; i++)
{
	// Buat objek Heading
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);

	// Tentukan halaman tujuan untuk objek heading
	heading2.DestinationPage = doc.Pages[i + 2];

	// Halaman tujuan
	heading2.Top = doc.Pages[i + 2].Rect.Height;

	// Koordinat tujuan
	segment2.Text = titles[i];

	// Tambahkan judul ke halaman yang berisi TOC
	tocPage.Paragraphs.Add(heading2);
}
dataDir = dataDir + "TOC_out.pdf";
// Simpan dokumen yang diperbarui
doc.Save(dataDir);

Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara menambahkan daftar isi (TOC) ke dokumen PDF menggunakan Aspose.PDF untuk .NET. Dengan mengikuti panduan langkah demi langkah dan memanfaatkan kode sumber C# yang disediakan, Anda dapat dengan mudah membuat dokumen PDF dengan daftar isi. TOC meningkatkan kegunaan dokumen, memungkinkan pengguna menavigasi ke bagian atau halaman tertentu dengan lebih efisien. Aspose.PDF untuk .NET memberikan solusi yang kuat dan mudah digunakan untuk bekerja dengan file PDF di aplikasi .NET, memungkinkan Anda membuat dokumen PDF yang dinamis dan interaktif dengan mudah.

### FAQ untuk menambahkan TOC ke file PDF

#### T: Apa itu Aspose.PDF untuk .NET?

J: Aspose.PDF untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang bekerja dengan file PDF di aplikasi .NET secara efektif. Ini menyediakan berbagai fitur untuk membuat, memanipulasi, dan mengelola dokumen PDF secara terprogram.

#### Q: Apa tujuan menambahkan daftar isi (TOC) ke dokumen PDF?

J: Daftar isi (TOC) memberikan bantuan navigasi bagi pengguna, memungkinkan mereka melompat dengan cepat ke bagian atau halaman tertentu dalam dokumen PDF. Ini meningkatkan kegunaan dokumen dan pengalaman pengguna.

#### T: Bagaimana cara menambahkan daftar isi ke dokumen PDF menggunakan Aspose.PDF untuk .NET?

J: Untuk menambahkan daftar isi ke dokumen PDF menggunakan Aspose.PDF untuk .NET, Anda perlu membuat halaman baru untuk menampung TOC, menentukan informasi daftar isi, lalu membuat elemen TOC yang sesuai dengan halaman atau bagian dalam dokumen.

#### Q: Bisakah saya menyesuaikan tampilan daftar isi?

A: Ya, Anda dapat menyesuaikan tampilan daftar isi dengan mengatur berbagai properti elemen TOC, seperti ukuran font, gaya font, dan perataan. Aspose.PDF untuk .NET memberikan fleksibilitas dalam mendesain TOC agar sesuai dengan tampilan dan nuansa yang Anda inginkan.

#### T: Apakah Aspose.PDF untuk .NET cocok untuk menambahkan fitur lanjutan ke dokumen PDF?

J: Tentu saja, Aspose.PDF untuk .NET adalah perpustakaan kaya fitur yang memungkinkan Anda menambahkan fungsionalitas tingkat lanjut ke dokumen PDF, termasuk elemen interaktif, bidang formulir, tanda tangan digital, dan banyak lagi.