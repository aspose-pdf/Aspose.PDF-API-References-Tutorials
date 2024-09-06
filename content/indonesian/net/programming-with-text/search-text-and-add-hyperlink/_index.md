---
title: Cari Teks dan Tambahkan Hyperlink
linktitle: Cari Teks dan Tambahkan Hyperlink
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mencari teks dalam PDF, menambahkan hyperlink ke teks yang ditemukan, dan menyimpan dokumen yang dimodifikasi menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 450
url: /id/net/programming-with-text/search-text-and-add-hyperlink/
---
Tutorial ini menjelaskan cara menggunakan Aspose.PDF untuk .NET guna mencari teks tertentu dalam dokumen PDF, menambahkan hyperlink ke teks yang ditemukan, dan menyimpan dokumen yang dimodifikasi. Kode sumber C# yang disediakan menunjukkan proses tersebut langkah demi langkah.

## Prasyarat

Sebelum melanjutkan tutorial, pastikan Anda memiliki hal berikut:

- Pengetahuan dasar tentang bahasa pemrograman C#.
- Pustaka Aspose.PDF untuk .NET telah terinstal. Anda dapat memperolehnya dari situs web Aspose atau menggunakan NuGet untuk menginstalnya di proyek Anda.

## Langkah 1: Siapkan proyek

Mulailah dengan membuat proyek C# baru di lingkungan pengembangan terintegrasi (IDE) pilihan Anda dan tambahkan referensi ke pustaka Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan

Tambahkan perintah berikut di awal file C# Anda untuk mengimpor namespace yang diperlukan:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## Langkah 3: Tetapkan jalur ke direktori dokumen

 Atur jalur ke direktori dokumen Anda menggunakan`dataDir` variabel:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 4: Buat TextFragmentAbsorber

 Membuat sebuah`TextFragmentAbsorber` objek untuk menemukan semua contoh frasa pencarian input:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 Mengganti`"\\d{4}-\\d{4}"` dengan pola ekspresi reguler yang Anda inginkan.

## Langkah 5: Aktifkan pencarian ekspresi reguler

 Aktifkan pencarian ekspresi reguler dengan menyetel`TextSearchOptions` properti penyerap:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## Langkah 6: Buka dan ikat dokumen PDF

 Membuat sebuah`PdfContentEditor` objek dan mengikatnya ke file PDF sumber:

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Mengganti`"SearchRegularExpressionPage.pdf"` dengan nama sebenarnya berkas PDF Anda.

## Langkah 7: Terima penyerap untuk halaman tersebut

Terima penyerap untuk halaman dokumen yang diinginkan:

```csharp
editor.Document.Pages[1].Accept(absorber);
```

 Mengganti`1` dengan nomor halaman yang diinginkan.

## Langkah 8: Tambahkan hyperlink ke teks yang ditemukan

Ulangi fragmen teks yang diambil dan tambahkan hyperlink ke dalamnya:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // Buat persegi panjang berdasarkan posisi fragmen teks
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    //Tambahkan tautan web ke persegi panjang
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, Sistem.Gambar.Warna.Biru);
}
```

 Mengganti`"http://www.aspose.com"` dengan URL hyperlink yang diinginkan.

## Langkah 9: Simpan dan tutup dokumen yang dimodifikasi

Simpan dokumen yang dimodifikasi dan tutup editor:

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

 Pastikan untuk mengganti`"SearchTextAndAddHyperlink_out.pdf"` dengan nama file keluaran yang diinginkan.

### Contoh kode sumber untuk Pencarian Teks dan Tambah Hyperlink menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buat objek penyerap untuk menemukan semua contoh frasa pencarian input
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// Aktifkan pencarian ekspresi reguler
absorber.TextSearchOptions = new TextSearchOptions(true);
// Buka dokumen
PdfContentEditor editor = new PdfContentEditor();
// Mengikat file PDF sumber
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// Terima penyerap untuk halaman tersebut
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
// Ulangi melalui fragmen
foreach (TextFragment textFragment in absorber.TextFragments)
{
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
		(int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
		(int)Math.Round(textFragment.Rectangle.Height + 1));
	Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
	editor.CreateWebLink(rect, "http:// Www.aspose.com", 1, biru, namatindakan);
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara mencari teks tertentu dalam dokumen PDF, menambahkan hyperlink ke teks yang ditemukan, dan menyimpan dokumen yang dimodifikasi menggunakan Aspose.PDF untuk .NET. Tutorial ini menyediakan panduan langkah demi langkah, mulai dari menyiapkan proyek hingga melakukan tindakan yang diperlukan. Anda sekarang dapat memasukkan kode ini ke dalam proyek C# Anda sendiri untuk memanipulasi teks dan menambahkan hyperlink dalam file PDF.

### Pertanyaan yang Sering Diajukan

#### T: Apa tujuan dari tutorial "Cari Teks dan Tambahkan Hyperlink"?

J: Tutorial "Cari Teks dan Tambahkan Hyperlink" bertujuan untuk menunjukkan cara menggunakan pustaka Aspose.PDF untuk .NET guna mencari teks tertentu dalam dokumen PDF, menambahkan hyperlink ke teks yang ditemukan, lalu menyimpan dokumen yang dimodifikasi. Tutorial ini menyediakan panduan lengkap dan contoh kode C# untuk mengilustrasikan proses langkah demi langkah.

#### T: Bagaimana tutorial ini membantu dalam menambahkan hyperlink ke teks tertentu dalam dokumen PDF?

J: Tutorial ini memandu Anda melalui proses penggunaan pustaka Aspose.PDF untuk menemukan teks tertentu dalam dokumen PDF, menerapkan hyperlink ke teks yang diidentifikasi, dan menyimpan PDF yang dimodifikasi. Tutorial ini mencakup langkah-langkah penting seperti menyiapkan proyek, memuat dokumen, mengaktifkan pencarian ekspresi reguler, dan menambahkan hyperlink ke teks yang ditemukan.

#### T: Prasyarat apa yang dibutuhkan untuk mengikuti tutorial ini?

J: Sebelum memulai, Anda harus memiliki pemahaman dasar tentang bahasa pemrograman C#. Selain itu, Anda perlu menginstal pustaka Aspose.PDF for .NET, yang dapat diperoleh dari situs web Aspose atau diinstal menggunakan NuGet di proyek Anda.

#### T: Bagaimana cara menyiapkan proyek saya untuk mengikuti tutorial ini?

J: Mulailah dengan membuat proyek C# baru di lingkungan pengembangan terpadu (IDE) pilihan Anda. Kemudian, tambahkan referensi ke pustaka Aspose.PDF for .NET, yang akan memungkinkan Anda memanfaatkan kemampuan pustaka tersebut dalam proyek Anda.

#### T: Dapatkah saya menambahkan hyperlink ke teks tertentu menggunakan tutorial ini?

J: Ya, tutorial ini secara khusus berfokus pada penambahan hyperlink ke teks tertentu dalam dokumen PDF. Tutorial ini menunjukkan cara menemukan dan mengekstrak teks yang diinginkan menggunakan ekspresi reguler, membuat hyperlink yang terkait dengan fragmen teks, dan menyimpan PDF yang dimodifikasi.

#### T: Bagaimana cara menentukan teks yang ingin saya cari dan menambahkan hyperlink?

 A: Untuk menentukan teks yang ingin Anda cari dan menambahkan hyperlink, buatlah`TextFragmentAbsorber` objek dan mengatur polanya menggunakan`Text` parameter. Ganti pola default`"\\d{4}-\\d{4}"` dalam kode tutorial dengan pola ekspresi reguler yang Anda inginkan.

#### T: Bagaimana cara mengaktifkan pencarian ekspresi reguler untuk teks?

 A: Pencarian ekspresi reguler diaktifkan dengan membuat`TextSearchOptions` objek dan mengatur nilainya ke`true` . Tetapkan objek ini ke`TextSearchOptions` milik`TextFragmentAbsorber` contoh. Ini memastikan bahwa pola ekspresi reguler diterapkan selama pencarian teks.

#### T: Bagaimana cara menambahkan hyperlink ke teks yang ditemukan?

 A: Setelah mengidentifikasi fragmen teks menggunakan`TextFragmentAbsorber` , tutorial menyediakan loop untuk mengulang fragmen-fragmen ini. Untuk setiap fragmen teks, tutorial menunjukkan cara mengatur warna teks menjadi biru dan membuat hyperlink menggunakan`CreateWebLink` metode.

#### T: Apa saja langkah untuk menyimpan PDF yang dimodifikasi dengan hyperlink?

 A: Setelah menambahkan hyperlink ke fragmen teks yang diinginkan, gunakan`PdfContentEditor` kelas untuk menyimpan dokumen yang dimodifikasi. Contoh kode tutorial menunjukkan cara menyimpan PDF yang diedit, menutup editor, dan menampilkan pesan sukses.