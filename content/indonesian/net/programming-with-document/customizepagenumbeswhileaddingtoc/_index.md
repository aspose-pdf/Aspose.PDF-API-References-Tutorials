---
title: Sesuaikan Nomor Halaman Saat Menambahkan Daftar Isi
linktitle: Sesuaikan Nomor Halaman Saat Menambahkan Daftar Isi
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menyesuaikan nomor halaman sambil menambahkan daftar isi (TOC) menggunakan Aspose.PDF untuk .NET dengan panduan langkah demi langkah dan contoh kode ini.
type: docs
weight: 100
url: /id/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---
Dalam tutorial ini, kita akan mempelajari cara menyesuaikan nomor halaman sambil menambahkan daftar isi (TOC) menggunakan Aspose.PDF untuk .NET. Kami akan memberikan panduan langkah demi langkah, bersama dengan contoh kode, untuk membantu Anda mencapai hal ini.

## Langkah 1: Memuat file PDF yang ada

Pertama, kita perlu memuat file PDF yang ada. Untuk tutorial ini, kita akan menggunakan file "42824.pdf" yang terletak di direktori "DIREKTORI DOKUMEN ANDA". Ganti jalur direktori ini dengan jalur sebenarnya ke direktori dokumen Anda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
Document doc = new Document(inFile);
```

## Langkah 2: Menambahkan halaman TOC

 Selanjutnya, kita perlu menambahkan halaman baru di awal dokumen untuk dijadikan halaman TOC. Kita dapat mencapai hal ini dengan menggunakan`Insert()` metode`Pages` koleksi`Document` obyek.

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

## Langkah 3: Membuat objek TOC

 Untuk membuat objek TOC, pertama-tama kita perlu membuat a`TocInfo` objek dan mengatur propertinya. Dalam tutorial ini, kita akan mengatur judul TOC menjadi "Daftar Isi" dan awalan nomor halaman menjadi "P".

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

## Langkah 4: Membuat entri TOC

Untuk membuat entri TOC, kita perlu mengulang semua halaman dokumen, kecuali halaman TOC, dan membuat objek judul untuk setiap halaman. Kita kemudian dapat menambahkan objek judul ke halaman TOC dan menentukan halaman tujuannya.

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    // Buat objek Heading
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    // Tentukan halaman tujuan untuk objek heading
    heading2.DestinationPage = doc.Pages[i + 1];
    // Halaman tujuan
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    // Koordinat tujuan
    segment2.Text = "Page " + i.ToString();
    // Tambahkan judul ke halaman yang berisi TOC
    tocPage.Paragraphs.Add(heading2);
}
```

## Langkah 5: Menyimpan dokumen yang diperbarui

Terakhir, kita perlu menyimpan dokumen yang diperbarui ke file baru. Kita dapat mencapai hal ini dengan menggunakan`Save()` metode`Document` obyek.

```csharp
doc.Save(outFile);
```

### Contoh kode sumber untuk menyesuaikan nomor halaman sambil menambahkan TOC menggunakan Aspose.PDF untuk .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
// Muat file PDF yang ada
Document doc = new Document(inFile);
// Dapatkan akses ke halaman pertama file PDF
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
// Buat objek untuk mewakili informasi TOC
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
// Tetapkan judul TOC
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
for (int i = 1; i<doc.Pages.Count; i++)
{
	// Buat objek Heading
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);
	// Tentukan halaman tujuan untuk objek heading
	heading2.DestinationPage = doc.Pages[i + 1];
	// Halaman tujuan
	heading2.Top = doc.Pages[i + 1].Rect.Height;
	// Koordinat tujuan
	segment2.Text = "Page " + i.ToString();
	// Tambahkan judul ke halaman yang berisi TOC
	tocPage.Paragraphs.Add(heading2);
}

// Simpan dokumen yang diperbarui
doc.Save(outFile);
```

## Kesimpulan

Dalam tutorial ini, kami telah memberikan panduan langkah demi langkah tentang cara menyesuaikan nomor halaman sambil menambahkan TOC menggunakan Aspose.PDF untuk .NET. Kami juga telah menyediakan contoh kode yang dapat Anda gunakan sebagai referensi saat mengimplementasikan fitur ini di

### FAQ

#### Q: Apa yang dimaksud dengan daftar isi (TOC) dalam dokumen PDF?

J: Daftar isi (TOC) dalam dokumen PDF adalah bantuan navigasi yang menyediakan daftar bagian atau bab dokumen yang terorganisir beserta nomor halamannya yang sesuai. Hal ini memungkinkan pembaca untuk dengan cepat menavigasi ke bagian tertentu dalam dokumen.

#### T: Mengapa saya ingin menyesuaikan nomor halaman di TOC?

J: Menyesuaikan nomor halaman dalam TOC dapat berguna ketika Anda ingin menggunakan format penomoran halaman tertentu atau menyertakan informasi tambahan bersama dengan nomor halaman. Ini memungkinkan Anda membuat daftar isi yang lebih personal dan informatif.

#### T: Bisakah saya menyertakan hyperlink di TOC untuk menghubungkan ke bagian atau halaman tertentu dalam dokumen PDF?

J: Ya, Aspose.PDF untuk .NET memungkinkan Anda membuat hyperlink di TOC yang tertaut ke bagian atau halaman tertentu dalam dokumen PDF. Ini meningkatkan interaktivitas dan navigasi dokumen PDF.

#### T: Apakah Aspose.PDF untuk .NET kompatibel dengan standar PDF/A?

J: Ya, Aspose.PDF untuk .NET mendukung standar PDF/A, termasuk PDF/A-1, PDF/A-2, dan PDF/A-3. Ini memungkinkan Anda membuat dokumen PDF yang memenuhi persyaratan pengarsipan dan pelestarian jangka panjang.

#### T: Dapatkah saya menambahkan lebih banyak pemformatan ke entri TOC, seperti gaya atau warna font?

J: Ya, Anda dapat menambahkan pemformatan tambahan ke entri TOC, seperti gaya font, warna, dan ukuran font, menggunakan Aspose.PDF untuk .NET. Ini memungkinkan Anda untuk menyesuaikan tampilan TOC sesuai kebutuhan Anda.
