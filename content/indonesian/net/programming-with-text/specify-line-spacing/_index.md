---
title: Tentukan Spasi Baris Dalam File PDF
linktitle: Tentukan Spasi Baris Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menentukan spasi baris dalam berkas PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 510
url: /id/net/programming-with-text/specify-line-spacing/
---
Tutorial ini menjelaskan cara menentukan spasi baris dalam file PDF menggunakan Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan proses tersebut langkah demi langkah.

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
using Aspose.Pdf.Text;
using System.IO;
```

## Langkah 3: Tetapkan jalur ke direktori dokumen

 Atur jalur ke direktori dokumen Anda menggunakan`dataDir` variabel:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 4: Muat file PDF masukan

 Muat file PDF masukan menggunakan`Document` kelas:

```csharp
Document doc = new Document();
```

## Langkah 5: Buat TextFormattingOptions

 Membuat sebuah`TextFormattingOptions` objek dan atur mode spasi baris ke`FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## Langkah 6: Buat TextFragment

 Membuat sebuah`TextFragment` objek dan tentukan konten teks:

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## Langkah 7: Muat file font (opsional)

 Jika Anda ingin menggunakan font tertentu untuk teks, muat file font TrueType ke dalam`FileStream` obyek:

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

 Mengganti`"HPSimplified.TTF"` dengan nama berkas font sebenarnya.

## Langkah 8: Tentukan posisi teks dan spasi baris

 Atur posisi untuk fragmen teks dan tetapkan`TextFormattingOptions` ke`TextState.FormattingOptions` milik:

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## Langkah 9: Tambahkan teks ke dokumen

 Tambahkan fragmen teks ke dokumen, baik dengan menambahkannya ke`TextBuilder` atau langsung ke halaman`Paragraphs` koleksi:

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

## Langkah 10: Simpan dokumen PDF yang dihasilkan

Simpan dokumen PDF yang dimodifikasi:

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

 Pastikan untuk mengganti`"SpecifyLineSpacing_out.pdf"` dengan nama file keluaran yang diinginkan.

### Contoh kode sumber untuk Menentukan Spasi Baris menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
// Muat file PDF masukan
Document doc = new Document();
//Buat TextFormattingOptions dengan LineSpacingMode.FullSize
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
// Buat objek pembuat teks untuk halaman pertama dokumen
//Pembuat Teks textBuilder = new TextBuilder(doc.Halaman[1]);
// Buat fragmen teks dengan contoh string
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	// Muat font TrueType ke objek aliran
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		// Mengatur nama font untuk string teks
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		//Tentukan posisi untuk Fragmen Teks
		textFragment.Position = new Position(100, 600);
		//Tetapkan TextFormattingOptions dari fragmen saat ini ke yang telah ditetapkan sebelumnya (yang menunjuk ke LineSpacingMode.FullSize)
		textFragment.TextState.FormattingOptions = formattingOptions;
		// Tambahkan teks ke TextBuilder sehingga dapat ditempatkan di atas file PDF
		//textBuilder.AppendText(fragmenteks);
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	// Simpan dokumen PDF yang dihasilkan
	doc.Save(dataDir);
}
```

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara menentukan spasi baris dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Tutorial ini menyediakan panduan langkah demi langkah, mulai dari menyiapkan proyek hingga menyimpan dokumen yang dimodifikasi. Kini Anda dapat memasukkan kode ini ke dalam proyek C# Anda sendiri untuk menyesuaikan spasi baris teks dalam file PDF.

### Pertanyaan yang Sering Diajukan

#### T: Apa tujuan dari tutorial "Tentukan Spasi Baris Dalam Berkas PDF"?

J: Tutorial "Tentukan Spasi Baris dalam File PDF" bertujuan untuk memandu pengguna tentang cara menggunakan pustaka Aspose.PDF untuk .NET guna menyesuaikan spasi baris teks dalam dokumen PDF. Tutorial ini menyediakan petunjuk langkah demi langkah dan contoh kode C# untuk menunjukkan prosesnya.

#### T: Bagaimana tutorial ini membantu dalam menentukan spasi baris dalam dokumen PDF?

J: Tutorial ini membantu pengguna memahami cara memanfaatkan kemampuan Aspose.PDF for .NET untuk menentukan spasi baris untuk teks dalam dokumen PDF. Dengan mengikuti langkah-langkah dan contoh kode yang diberikan, pengguna dapat menyesuaikan spasi baris sesuai dengan preferensi mereka.

#### T: Prasyarat apa yang diperlukan untuk mengikuti tutorial ini?

J: Sebelum memulai tutorial ini, Anda harus memiliki pemahaman dasar tentang bahasa pemrograman C#. Selain itu, Anda perlu menginstal pustaka Aspose.PDF for .NET. Anda dapat memperolehnya dari situs web Aspose atau menginstalnya di proyek Anda menggunakan NuGet.

#### T: Bagaimana cara menyiapkan proyek saya untuk mengikuti tutorial ini?

J: Untuk memulai, buat proyek C# baru di lingkungan pengembangan terpadu (IDE) pilihan Anda dan tambahkan referensi ke pustaka Aspose.PDF untuk .NET. Ini memungkinkan Anda memanfaatkan fitur pustaka untuk bekerja dengan dokumen PDF dan menyesuaikan spasi baris.

#### T: Dapatkah saya menggunakan tutorial ini untuk menentukan spasi baris untuk jenis teks apa pun?

A: Ya, tutorial ini menyediakan petunjuk tentang cara menentukan spasi baris untuk konten teks apa pun dalam dokumen PDF menggunakan Aspose.PDF for .NET. Anda dapat menggunakan contoh kode yang disediakan untuk menyesuaikan spasi baris teks sesuai dengan kebutuhan Anda.

#### T: Bagaimana cara menentukan mode spasi baris dalam tutorial?

 A: Tutorial ini menunjukkan cara membuat`TextFormattingOptions` objek dan mengaturnya`LineSpacing` properti untuk`TextFormattingOptions.LineSpacingMode.FullSize`Mode ini menentukan spasi baris penuh untuk konten teks.

#### T: Bagaimana cara memuat font tertentu untuk teks?

 A: Jika Anda ingin menggunakan font tertentu untuk konten teks, tutorial ini menyediakan panduan tentang cara memuat file font TrueType ke dalam`FileStream` objek dan mengaturnya sebagai font untuk`TextFragment`Ini memungkinkan Anda untuk menyesuaikan jenis huruf teks beserta spasi barisnya.

#### T: Bagaimana cara menyesuaikan posisi teks dalam dokumen PDF?

 A: Untuk menyesuaikan posisi teks, buat`TextFragment` objek dan mengaturnya`Position`properti ke koordinat yang diinginkan (X dan Y). Ini memungkinkan Anda untuk mengontrol di mana teks akan ditempatkan dalam dokumen PDF.

#### T: Dapatkah saya menerapkan modifikasi spasi baris ini ke dokumen PDF yang ada?

 A: Ya, Anda dapat mengubah spasi baris untuk teks dalam dokumen PDF yang ada. Tutorial ini menunjukkan cara membuat spasi baris.`TextFragment` dengan spasi dan posisi baris yang ditentukan, lalu menambahkannya ke halaman`Paragraphs` koleksi.