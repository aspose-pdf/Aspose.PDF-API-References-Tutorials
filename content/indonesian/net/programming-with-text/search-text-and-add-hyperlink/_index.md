---
title: Cari Teks Dan Tambahkan Hyperlink
linktitle: Cari Teks Dan Tambahkan Hyperlink
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara mencari teks dalam PDF, menambahkan hyperlink ke teks yang ditemukan, dan menyimpan dokumen yang dimodifikasi menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 450
url: /id/net/programming-with-text/search-text-and-add-hyperlink/
---
Tutorial ini menjelaskan cara menggunakan Aspose.PDF untuk .NET untuk mencari teks tertentu dalam dokumen PDF, menambahkan hyperlink ke teks yang ditemukan, dan menyimpan dokumen yang dimodifikasi. Kode sumber C# yang disediakan menunjukkan proses langkah demi langkah.

## Prasyarat

Sebelum melanjutkan tutorial, pastikan Anda memiliki hal berikut:

- Pengetahuan dasar bahasa pemrograman C#.
- Aspose.PDF untuk perpustakaan .NET diinstal. Anda dapat memperolehnya dari situs Aspose atau menggunakan NuGet untuk menginstalnya di proyek Anda.

## Langkah 1: Siapkan proyek

Mulailah dengan membuat proyek C# baru di lingkungan pengembangan terintegrasi (IDE) pilihan Anda dan tambahkan referensi ke pustaka Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan

Tambahkan arahan penggunaan berikut di awal file C# Anda untuk mengimpor namespace yang diperlukan:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## Langkah 3: Tetapkan jalur ke direktori dokumen

 Tetapkan jalur ke direktori dokumen Anda menggunakan`dataDir` variabel:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 4: Buat TextFragmentAbsorber

 Membuat`TextFragmentAbsorber` objek untuk menemukan semua contoh frasa pencarian masukan:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 Mengganti`"\\d{4}-\\d{4}"` dengan pola ekspresi reguler yang Anda inginkan.

## Langkah 5: Aktifkan pencarian ekspresi reguler

 Aktifkan pencarian ekspresi reguler dengan mengatur`TextSearchOptions` properti penyerap:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## Langkah 6: Buka dan ikat dokumen PDF

 Membuat`PdfContentEditor` objek dan ikat ke file PDF sumber:

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Mengganti`"SearchRegularExpressionPage.pdf"` dengan nama sebenarnya file PDF Anda.

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

## Langkah 9: Simpan dan tutup dokumen yang diubah

Simpan dokumen yang diubah dan tutup editor:

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

 Pastikan untuk mengganti`"SearchTextAndAddHyperlink_out.pdf"` dengan nama file keluaran yang diinginkan.

### Contoh kode sumber untuk Cari Teks Dan Tambahkan Hyperlink menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buat objek penyerap untuk menemukan semua contoh frasa pencarian masukan
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// Aktifkan pencarian ekspresi reguler
absorber.TextSearchOptions = new TextSearchOptions(true);
// Buka dokumen
PdfContentEditor editor = new PdfContentEditor();
// Ikat file PDF sumber
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// Terima penyerap untuk halaman tersebut
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
// Ulangi fragmennya
foreach (TextFragment textFragment in absorber.TextFragments)
{
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
		(int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
		(int)Math.Round(textFragment.Rectangle.Height + 1));
	Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
	editor.CreateWebLink(rect, "http:// Www.aspose.com", 1, biru, nama tindakan);
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara mencari teks tertentu dalam dokumen PDF, menambahkan hyperlink ke teks yang ditemukan, dan menyimpan dokumen yang dimodifikasi menggunakan Aspose.PDF untuk .NET. Tutorial ini memberikan panduan langkah demi langkah, mulai dari menyiapkan proyek hingga melakukan tindakan yang diperlukan. Anda sekarang dapat memasukkan kode ini ke dalam proyek C# Anda sendiri untuk memanipulasi teks dan menambahkan hyperlink dalam file PDF.

### FAQ

#### Q: Apa tujuan dari tutorial "Mencari Teks Dan Menambahkan Hyperlink"?

J: Tutorial "Cari Teks Dan Tambahkan Hyperlink" bertujuan untuk mendemonstrasikan cara menggunakan perpustakaan Aspose.PDF untuk .NET untuk mencari teks tertentu dalam dokumen PDF, menambahkan hyperlink ke teks yang ditemukan, dan kemudian menyimpan dokumen yang dimodifikasi. Tutorial ini memberikan panduan komprehensif dan contoh kode C# untuk mengilustrasikan proses langkah demi langkah.

#### T: Bagaimana tutorial ini membantu menambahkan hyperlink ke teks tertentu dalam dokumen PDF?

J: Tutorial ini memandu Anda melalui proses penggunaan perpustakaan Aspose.PDF untuk menemukan teks tertentu dalam dokumen PDF, menerapkan hyperlink ke teks yang diidentifikasi, dan menyimpan PDF yang dimodifikasi. Ini mencakup langkah-langkah penting seperti menyiapkan proyek, memuat dokumen, mengaktifkan pencarian ekspresi reguler, dan menambahkan hyperlink ke teks yang ditemukan.

#### Q: Prasyarat apa saja yang diperlukan untuk mengikuti tutorial ini?

A: Sebelum memulai, Anda harus memiliki pemahaman dasar tentang bahasa pemrograman C#. Selain itu, Anda perlu menginstal pustaka Aspose.PDF untuk .NET, yang dapat diperoleh dari situs web Aspose atau diinstal menggunakan NuGet di proyek Anda.

#### T: Bagaimana cara menyiapkan proyek saya untuk mengikuti tutorial ini?

J: Mulailah dengan membuat proyek C# baru di lingkungan pengembangan terintegrasi (IDE) pilihan Anda. Kemudian, tambahkan referensi ke perpustakaan Aspose.PDF untuk .NET, yang akan memungkinkan Anda memanfaatkan kemampuan perpustakaan dalam proyek Anda.

#### T: Dapatkah saya menambahkan hyperlink ke teks tertentu menggunakan tutorial ini?

A: Ya, tutorial ini secara khusus berfokus pada penambahan hyperlink ke teks tertentu dalam dokumen PDF. Ini menunjukkan cara menemukan dan mengekstrak teks yang diinginkan menggunakan ekspresi reguler, membuat hyperlink yang terkait dengan fragmen teks, dan menyimpan PDF yang dimodifikasi.

#### T: Bagaimana cara menentukan teks yang ingin saya cari dan menambahkan hyperlink ke dalamnya?

 A: Untuk menentukan teks yang ingin Anda cari dan tambahkan hyperlink, buat a`TextFragmentAbsorber` objek dan atur polanya menggunakan`Text` parameter. Ganti pola default`"\\d{4}-\\d{4}"` dalam kode tutorial dengan pola ekspresi reguler yang Anda inginkan.

#### T: Bagaimana cara mengaktifkan pencarian ekspresi reguler untuk teks?

 A: Pencarian ekspresi reguler diaktifkan dengan membuat a`TextSearchOptions` objek dan menetapkan nilainya menjadi`true` . Tetapkan objek ini ke`TextSearchOptions` properti dari`TextFragmentAbsorber` contoh. Hal ini memastikan bahwa pola ekspresi reguler diterapkan selama pencarian teks.

#### T: Bagaimana cara menambahkan hyperlink ke teks yang ditemukan?

 A: Setelah mengidentifikasi fragmen teks menggunakan`TextFragmentAbsorber` , tutorial menyediakan perulangan untuk mengulangi fragmen-fragmen ini. Untuk setiap fragmen teks, tutorial menunjukkan cara mengatur warna teks menjadi biru dan membuat hyperlink menggunakan`CreateWebLink` metode.

#### Q: Bagaimana langkah-langkah menyimpan PDF yang dimodifikasi dengan hyperlink?

 J: Setelah menambahkan hyperlink ke fragmen teks yang diinginkan, gunakan`PdfContentEditor` kelas untuk menyimpan dokumen yang dimodifikasi. Kode contoh tutorial menunjukkan cara menyimpan PDF yang telah diedit, menutup editor, dan menampilkan pesan sukses.