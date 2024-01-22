---
title: Tambahkan Tooltip Ke Teks Dalam File PDF
linktitle: Tambahkan Tooltip Ke Teks Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menambahkan tooltips ke teks dalam file PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 90
url: /id/net/programming-with-text/add-tooltip-to-text/
---
Tutorial ini akan memandu Anda melalui proses menambahkan tooltips ke teks dalam file PDF menggunakan Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan.

## Persyaratan
Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau kompiler C# lainnya yang diinstal pada mesin Anda.
- Aspose.PDF untuk perpustakaan .NET. Anda dapat mendownloadnya dari situs resmi Aspose atau menggunakan manajer paket seperti NuGet untuk menginstalnya.

## Langkah 1: Siapkan proyek
1. Buat proyek C# baru di lingkungan pengembangan pilihan Anda.
2. Tambahkan referensi ke perpustakaan Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan
Dalam file kode tempat Anda ingin menambahkan tooltips ke teks, tambahkan arahan penggunaan berikut di bagian atas file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## Langkah 3: Atur direktori dokumen
 Dalam kode, temukan baris yang bertuliskan`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur ke direktori tempat dokumen Anda disimpan.

## Langkah 4: Buat contoh dokumen dengan teks
 Buat yang baru`Document` objek dan tambahkan halaman dengan fragmen teks. Dalam kode yang disediakan, dua fragmen teks ditambahkan ke dokumen dengan teks tooltip masing-masing.

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## Langkah 5: Buka dokumen dan temukan potongan teksnya
 Muat dokumen yang dibuat menggunakan`Document` konstruktor dan temukan fragmen teks yang memerlukan penggunaan tooltip`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## Langkah 6: Tambahkan tooltips ke fragmen teks
 Ulangi fragmen teks yang diekstraksi dan buat tombol tak terlihat di posisinya. Tetapkan teks tooltip yang diinginkan ke`AlternateName` properti dari`ButtonField`. Tambahkan bidang tombol ke formulir dokumen.

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## Langkah 7: Ulangi untuk fragmen teks tambahan dengan tooltip yang panjang
Ulangi langkah 5 dan 6 untuk fragmen teks dengan tooltip yang panjang. Ubah kriteria pencarian dan teks keterangan alat yang sesuai.

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
 Simpan dokumen PDF yang dimodifikasi menggunakan`Save` metode`Document` obyek.

```csharp
document. Save(outputFile);
```

### Contoh kode sumber untuk Menambahkan Tooltip Ke Teks menggunakan Aspose.PDF untuk .NET 
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
// Ulangi fragmennya
foreach (TextFragment fragment in textFragments)
{
	// Buat tombol tak terlihat pada posisi fragmen teks
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Nilai AlternateName akan ditampilkan sebagai tooltip oleh aplikasi penampil
	field.AlternateName = "Tooltip for text.";
	// Tambahkan bidang tombol ke dokumen
	document.Form.Add(field);
}
// Berikutnya adalah contoh tooltip yang sangat panjang
absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorber);
textFragments = absorber.TextFragments;
foreach (TextFragment fragment in textFragments)
{
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Atur teks yang sangat panjang
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
Anda telah berhasil menambahkan tooltips ke teks dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. File PDF yang dihasilkan sekarang dapat ditemukan di jalur file keluaran yang ditentukan.

## FAQ

#### Q: Apa fokus dari tutorial ini?

J: Tutorial ini berfokus pada menambahkan tooltips ke teks dalam file PDF menggunakan perpustakaan Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan untuk mencapai hal ini.

#### T: Namespace mana yang perlu diimpor untuk tutorial ini?

J: Dalam file kode tempat Anda ingin menambahkan tooltips ke teks, impor namespace berikut di awal file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

#### T: Bagaimana cara menentukan direktori dokumen?

 A: Di dalam kode, temukan barisnya`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

#### T: Bagaimana cara membuat contoh dokumen dengan teks?

 J: Pada Langkah 4, Anda akan membuat yang baru`Document` objek dan tambahkan halaman dengan fragmen teks. Kode yang diberikan menambahkan dua fragmen teks dengan teks tooltip masing-masing.

#### T: Bagaimana cara membuka dokumen dan menemukan potongan teksnya?

 J: Pada Langkah 5, Anda akan memuat dokumen yang dibuat menggunakan`Document` konstruktor dan temukan fragmen teks yang memerlukan tooltips menggunakan`TextFragmentAbsorber`.

#### T: Bagaimana cara menambahkan keterangan alat ke fragmen teks?

 J: Pada Langkah 6, Anda akan menelusuri fragmen teks yang diekstraksi dan membuat tombol tak terlihat di posisinya. Teks tooltip ditugaskan ke`AlternateName` properti dari`ButtonField`yang ditambahkan ke formulir dokumen.

#### T: Bagaimana cara mengulangi proses untuk fragmen teks tambahan dengan tooltip yang panjang?

J: Untuk fragmen teks dengan tooltip yang panjang, ulangi Langkah 5 dan 6. Ubah kriteria pencarian dan teks tooltip yang sesuai.

#### T: Bagaimana cara menyimpan dokumen yang diubah?

 J: Pada Langkah 8, Anda akan menyimpan dokumen PDF yang dimodifikasi menggunakan`Save` metode`Document` obyek.

#### T: Apa manfaat utama dari tutorial ini?

J: Dengan mengikuti tutorial ini, Anda telah mempelajari cara menyempurnakan dokumen PDF Anda dengan menambahkan tooltip ke teks menggunakan Aspose.PDF untuk .NET. Hal ini dapat memberikan informasi tambahan yang berharga bagi pembaca ketika mereka berinteraksi dengan konten PDF.