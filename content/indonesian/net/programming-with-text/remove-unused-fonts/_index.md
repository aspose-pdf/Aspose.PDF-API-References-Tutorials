---
title: Hapus Font yang Tidak Digunakan Dalam File PDF
linktitle: Hapus Font yang Tidak Digunakan Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menghapus font yang tidak digunakan dalam file PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 300
url: /id/net/programming-with-text/remove-unused-fonts/
---
Dalam tutorial ini, kami akan menjelaskan cara menghapus font yang tidak digunakan dalam file PDF menggunakan perpustakaan Aspose.PDF untuk .NET. Kami akan melalui proses langkah demi langkah memuat PDF, mengidentifikasi dan menghapus font yang tidak digunakan, dan menyimpan PDF yang diperbarui menggunakan kode sumber C# yang disediakan.

## Persyaratan

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Pustaka Aspose.PDF untuk .NET diinstal.
- Pemahaman dasar tentang pemrograman C#.

## Langkah 1: Siapkan Direktori Dokumen

 Pertama, Anda perlu mengatur jalur ke direktori tempat file PDF Anda berada. Mengganti`"YOUR DOCUMENT DIRECTORY"` dalam`dataDir` variabel dengan jalur ke file PDF Anda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Muat PDF Sumber

 Selanjutnya, kami memuat dokumen PDF sumber menggunakan`Document` kelas dari perpustakaan Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Langkah 3: Identifikasi dan Hapus Font yang Tidak Digunakan

 Kami membuat`TextFragmentAbsorber` keberatan dengan`TextEditOptions` parameter disetel ke`TextEditOptions.FontReplace.RemoveUnusedFonts` . Opsi ini memungkinkan kami mengidentifikasi dan menghapus font yang tidak digunakan dalam dokumen PDF. Kami kemudian mengulangi semuanya`TextFragments` dan atur font ke font yang diinginkan.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## Langkah 4: Simpan PDF yang Diperbarui

Terakhir, kami menyimpan dokumen PDF yang diperbarui ke file keluaran yang ditentukan.

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### Contoh kode sumber untuk Menghapus Font yang Tidak Digunakan menggunakan Aspose.PDF untuk .NET 
```csharp
try
{
	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Muat file PDF sumber
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	// Ulangi semua TextFragments
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
	}
	dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
	// Simpan dokumen yang diperbarui
	doc.Save(dataDir);
	Console.WriteLine("\nUnused fonts removed successfully from pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara menghapus font yang tidak digunakan dari dokumen PDF menggunakan perpustakaan Aspose.PDF untuk .NET. Dengan mengikuti panduan langkah demi langkah dan menjalankan kode C# yang disediakan, Anda dapat memuat PDF, mengidentifikasi dan menghapus font yang tidak digunakan, dan menyimpan PDF yang diperbarui.

### FAQ

#### Q: Apa tujuan dari tutorial "Menghapus Font yang Tidak Digunakan di File PDF"?

J: Tutorial "Menghapus Font yang Tidak Digunakan Dalam File PDF" menjelaskan cara menggunakan perpustakaan Aspose.PDF untuk .NET untuk menghapus font yang tidak digunakan dari dokumen PDF. Tutorial ini memandu Anda melalui proses memuat PDF, mengidentifikasi dan menghapus font yang tidak digunakan, dan menyimpan PDF yang diperbarui.

#### T: Mengapa saya ingin menghapus font yang tidak digunakan dari dokumen PDF?

J: Menghapus font yang tidak digunakan dari dokumen PDF dapat membantu mengurangi ukuran file dan mengoptimalkan dokumen untuk performa yang lebih baik. Hal ini sangat berguna ketika menangani PDF yang berisi font tertanam yang sebenarnya tidak digunakan dalam konten dokumen.

#### T: Bagaimana cara mengatur direktori dokumen?

A: Untuk mengatur direktori dokumen:

1.  Mengganti`"YOUR DOCUMENT DIRECTORY"` dalam`dataDir` variabel dengan jalur ke direktori tempat file PDF Anda berada.

#### T: Bagaimana cara menghapus font yang tidak digunakan dari dokumen PDF menggunakan perpustakaan Aspose.PDF?

J: Tutorial memandu Anda melalui proses langkah demi langkah:

1.  Buka dokumen PDF menggunakan`Document` kelas.
2.  Membuat`TextFragmentAbsorber` objek dengan`TextEditOptions` mulai`FontReplace.RemoveUnusedFonts`.
3. Terima penyerap untuk mengidentifikasi dan menghapus font yang tidak digunakan dari PDF.
4.  Ulangi semuanya`TextFragments` dan atur font ke font yang diinginkan.
5. Simpan dokumen PDF yang diperbarui.

####  T: Apa tujuan dari`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

 J: Itu`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter menginstruksikan`TextFragmentAbsorber` untuk mengidentifikasi dan menghapus font yang tidak digunakan dari dokumen PDF.

#### Q: Bisakah saya mengganti font yang tidak terpakai dengan font pilihan saya?

A: Ya, Anda dapat memodifikasi kode untuk mengganti font yang tidak terpakai dengan font pilihan Anda. Dalam contoh kode yang disediakan, font "Arial, Bold" digunakan sebagai pengganti.

####  T: Bagaimana caranya`TextFragmentAbsorber` work to remove unused fonts?

 J: Itu`TextFragmentAbsorber` dikonfigurasi dengan`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter, yang mengidentifikasi font yang tidak digunakan dalam fragmen teks PDF. Setelah penyerapan, Anda dapat mengulanginya`TextFragments` dan atur fontnya ke font pengganti yang diinginkan.

#### T: Apa hasil yang diharapkan dari mengeksekusi kode yang diberikan?

J: Dengan mengikuti tutorial dan menjalankan kode C# yang disediakan, Anda akan menghapus font yang tidak digunakan dari dokumen PDF masukan dan menyimpan versi terbaru sebagai file PDF keluaran.

#### T: Bisakah saya mengubah kode untuk menghapus font hanya dari halaman atau area tertentu?

J: Kode yang diberikan berfokus pada penghapusan font yang tidak digunakan dari seluruh dokumen PDF. Jika Anda ingin menargetkan halaman atau wilayah tertentu untuk penghapusan font, Anda perlu mengubah pendekatan dan menggunakan logika yang lebih kompleks untuk mengidentifikasi font yang tidak digunakan di area tersebut.