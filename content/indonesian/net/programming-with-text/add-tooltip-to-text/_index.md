---
title: Tambahkan Tooltip ke Teks dalam File PDF
linktitle: Tambahkan Tooltip ke Teks dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menambahkan tooltip ke teks dalam berkas PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 90
url: /id/net/programming-with-text/add-tooltip-to-text/
---
Tutorial ini akan memandu Anda melalui proses penambahan tooltip ke teks dalam file PDF menggunakan Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan.

## Persyaratan
Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau kompiler C# lainnya terinstal di komputer Anda.
- Aspose.PDF untuk pustaka .NET. Anda dapat mengunduhnya dari situs web resmi Aspose atau menggunakan pengelola paket seperti NuGet untuk menginstalnya.

## Langkah 1: Siapkan proyek
1. Buat proyek C# baru di lingkungan pengembangan pilihan Anda.
2. Tambahkan referensi ke pustaka Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan
Pada berkas kode tempat Anda ingin menambahkan keterangan alat ke teks, tambahkan perintah penggunaan berikut di bagian atas berkas:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## Langkah 3: Mengatur direktori dokumen
 Dalam kode, temukan baris yang bertuliskan`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur ke direktori tempat dokumen Anda disimpan.

## Langkah 4: Buat dokumen contoh dengan teks
 Buat yang baru`Document` objek dan tambahkan halaman dengan fragmen teks. Dalam kode yang diberikan, dua fragmen teks ditambahkan ke dokumen dengan teks keterangan alat masing-masing.

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## Langkah 5: Buka dokumen dan temukan fragmen teks
 Muat dokumen yang dibuat menggunakan`Document` konstruktor dan temukan fragmen teks yang memerlukan tooltip menggunakan`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## Langkah 6: Tambahkan tooltip ke fragmen teks
 Ulangi fragmen teks yang diekstrak dan buat tombol tak terlihat di posisinya. Tetapkan teks keterangan alat yang diinginkan ke`AlternateName` milik`ButtonField`Tambahkan bidang tombol ke formulir dokumen.

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## Langkah 7: Ulangi untuk fragmen teks tambahan dengan keterangan alat yang panjang
Ulangi langkah 5 dan 6 untuk fragmen teks dengan tooltip yang panjang. Ubah kriteria pencarian dan teks tooltip sesuai kebutuhan.

```csharp
absorb = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorb);
textFragments = absorb.TextFragments;

foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Long tooltip text goes here...";
     document.Form.Add(field);
}
```

## Langkah 8: Simpan dokumen yang dimodifikasi
 Simpan dokumen PDF yang dimodifikasi menggunakan`Save` metode dari`Document` obyek.

```csharp
document. Save(outputFile);
```

### Contoh kode sumber untuk Menambahkan Tooltip ke Teks menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
// Buat contoh dokumen dengan teks
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
// Buka dokumen dengan teks
Document document = new Document(outputFile);
// Buat objek TextAbsorber untuk menemukan semua frasa yang cocok dengan ekspresi reguler
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
// Terima penyerap untuk halaman dokumen
document.Pages.Accept(absorber);
// Dapatkan fragmen teks yang diekstraksi
TextFragmentCollection textFragments = absorber.TextFragments;
// Ulangi melalui fragmen
foreach (TextFragment fragment in textFragments)
{
	// Buat tombol tak terlihat pada posisi fragmen teks
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Nilai AlternateName akan ditampilkan sebagai tooltip oleh aplikasi penampil
	field.AlternateName = "Tooltip for text.";
	// Tambahkan bidang tombol ke dokumen
	document.Form.Add(field);
}
// Berikut ini akan menjadi contoh tooltip yang sangat panjang
absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorber);
textFragments = absorber.TextFragments;
foreach (TextFragment fragment in textFragments)
{
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Tetapkan teks yang sangat panjang
	field.AlternateName = "Lorem ipsum dolor sit amet, consectetur adipiscing elit," +
							" sed do eiusmod tempor incididunt ut labore et dolore magna" +
							" aliqua. Ut enim ad minim veniam, quis nostrud exercitation" +
							" ullamco laboris nisi ut aliquip ex ea commodo consequat." +
							" Duis aute irure dolor in reprehenderit in voluptate velit" +
							" esse cillum dolore eu fugiat nulla pariatur. Excepteur sint" +
							" occaecat cupidatat non proident, sunt in culpa qui officia" +
							" deserunt mollit anim id est laborum.";
	document.Form.Add(field);
}
// Simpan dokumen
document.Save(outputFile);
```

## Kesimpulan
Anda telah berhasil menambahkan tooltips ke teks dalam dokumen PDF menggunakan Aspose.PDF for .NET. File PDF yang dihasilkan kini dapat ditemukan di jalur file output yang ditentukan.

## Tanya Jawab Umum

#### T: Apa fokus dari tutorial ini?

J: Tutorial ini berfokus pada penambahan tooltip ke teks dalam file PDF menggunakan pustaka Aspose.PDF for .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan untuk mencapainya.

#### T: Namespace mana yang perlu diimpor untuk tutorial ini?

A: Pada berkas kode tempat Anda ingin menambahkan keterangan alat ke teks, impor namespace berikut di awal berkas:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

#### T: Bagaimana cara menentukan direktori dokumen?

 A: Pada kode tersebut, temukan baris`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

#### T: Bagaimana cara membuat dokumen contoh dengan teks?

 A: Pada Langkah 4, Anda akan membuat yang baru`Document` objek dan tambahkan halaman dengan fragmen teks. Kode yang diberikan menambahkan dua fragmen teks dengan teks keterangan alat masing-masing.

#### T: Bagaimana cara membuka dokumen dan menemukan fragmen teks?

 A: Pada Langkah 5, Anda akan memuat dokumen yang dibuat menggunakan`Document` konstruktor dan temukan fragmen teks yang memerlukan tooltip menggunakan`TextFragmentAbsorber`.

#### T: Bagaimana cara menambahkan keterangan alat pada fragmen teks?

 A: Pada Langkah 6, Anda akan mengulang fragmen teks yang diekstrak dan membuat tombol tak terlihat pada posisinya. Teks keterangan alat ditetapkan ke`AlternateName` milik`ButtonField`yang ditambahkan ke formulir dokumen.

#### T: Bagaimana cara mengulang proses untuk fragmen teks tambahan dengan tooltip yang panjang?

A: Untuk fragmen teks dengan tooltip yang panjang, ulangi Langkah 5 dan 6. Ubah kriteria pencarian dan teks tooltip sebagaimana mestinya.

#### T: Bagaimana cara menyimpan dokumen yang sudah dimodifikasi?

 A: Pada Langkah 8, Anda akan menyimpan dokumen PDF yang dimodifikasi menggunakan`Save` metode dari`Document` obyek.

#### T: Apa hasil utama dari tutorial ini?

J: Dengan mengikuti tutorial ini, Anda telah mempelajari cara menyempurnakan dokumen PDF dengan menambahkan tooltips ke teks menggunakan Aspose.PDF for .NET. Ini dapat memberikan informasi tambahan yang berharga bagi pembaca saat mereka berinteraksi dengan konten PDF.