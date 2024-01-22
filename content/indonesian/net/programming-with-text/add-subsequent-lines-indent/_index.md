---
title: Tambahkan Indentasi Baris Berikutnya Dalam File PDF
linktitle: Tambahkan Indentasi Baris Berikutnya Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menambahkan indentasi baris berikutnya ke teks dalam file PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 60
url: /id/net/programming-with-text/add-subsequent-lines-indent/
---
Tutorial ini akan memandu Anda melalui proses menambahkan indentasi baris berikutnya ke teks dalam file PDF menggunakan Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan.

## Persyaratan
Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau kompiler C# lainnya yang diinstal pada mesin Anda.
- Aspose.PDF untuk perpustakaan .NET. Anda dapat mendownloadnya dari situs resmi Aspose atau menggunakan manajer paket seperti NuGet untuk menginstalnya.

## Langkah 1: Siapkan proyek
1. Buat proyek C# baru di lingkungan pengembangan pilihan Anda.
2. Tambahkan referensi ke perpustakaan Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan
Dalam file kode di mana Anda ingin menambahkan indentasi baris berikutnya, tambahkan arahan penggunaan berikut di bagian atas file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Langkah 3: Atur direktori dokumen
 Dalam kode, temukan baris yang bertuliskan`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur ke direktori tempat dokumen Anda disimpan.

## Langkah 4: Buat objek Dokumen baru
 Buat instance yang baru`Document` objek dengan menambahkan baris kode berikut:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## Langkah 5: Tambahkan halaman ke dokumen
 Tambahkan halaman baru ke dokumen dengan menggunakan`Add` metode`Pages`koleksi. Dalam kode yang disediakan, halaman baru ditugaskan ke variabel`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## Langkah 6: Buat TextFragment dengan indentasi baris berikutnya
 Buat contoh a`TextFragment` objek dan memberikan teks yang diinginkan. Dalam kode yang disediakan, teks ditugaskan ke variabel`text` . Kemudian, inisialisasi`TextFormattingOptions` Untuk`TextFragment`dan tentukan`SubsequentLinesIndent` nilai.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## Langkah 7: Tambahkan TextFragment ke halaman
 Tambahkan`TextFragment` keberatan dengan kumpulan paragraf halaman.

```csharp
page.Paragraphs.Add(text);
```

## Langkah 8: Ulangi langkah 6 dan 7 untuk baris tambahan
Untuk menambahkan baris berikutnya dengan indentasi yang sama, ulangi langkah 6 dan 7 untuk setiap baris. Perbarui konten teks sesuai kebutuhan.

```csharp
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
```

## Langkah 9: Simpan dokumen PDF
 Simpan dokumen PDF menggunakan`Save` metode`Document` obyek. Tentukan jalur file keluaran.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Contoh kode sumber untuk Tambahkan Indentasi Baris Berikutnya menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buat objek dokumen baru
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
// Inisialisasi TextFormattingOptions untuk fragmen teks dan tentukan nilai SubsequentLinesIndent
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
	SubsequentLinesIndent = 20
};
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Kesimpulan
Anda telah berhasil menambahkan indentasi baris berikutnya ke teks menggunakan Aspose.PDF untuk .NET. File PDF yang dihasilkan sekarang dapat ditemukan di jalur file keluaran yang ditentukan.

### FAQ

#### Q: Apa fokus dari tutorial ini?

J: Tutorial ini memberikan panduan komprehensif tentang cara menambahkan indentasi baris berikutnya ke teks dalam file PDF menggunakan perpustakaan Aspose.PDF untuk .NET. Ini mencakup contoh kode sumber C# untuk mengilustrasikan langkah-langkah yang diperlukan untuk mencapai hal ini.

#### T: Namespace manakah yang perlu saya impor untuk tutorial ini?

J: Dalam file kode tempat Anda ingin menambahkan indentasi baris berikutnya, impor namespace berikut di awal file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### T: Bagaimana cara menentukan direktori dokumen?

 A: Di dalam kode, temukan barisnya`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

#### T: Bagaimana cara membuat objek Dokumen?

 J: Pada Langkah 4, Anda akan membuat instance yang baru`Document` objek menggunakan baris kode berikut:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### T: Bagaimana cara menambahkan halaman ke dokumen?

 J: Pada Langkah 5, Anda akan menambahkan halaman baru ke dokumen menggunakan`Add` metode`Pages` koleksi:

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### T: Bagaimana cara menambahkan indentasi baris berikutnya ke teks?

 J: Pada Langkah 6, Anda akan membuat a`TextFragment` objek dan tetapkan teks yang diinginkan padanya. Kemudian, Anda akan melakukan inisialisasi`TextFormattingOptions` Untuk`TextFragment`dan tentukan`SubsequentLinesIndent` nilai:

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### T: Bagaimana cara menambahkan TextFragment ke dokumen PDF?

 J: Pada Langkah 7, Anda akan menambahkan`TextFragment` objek (`text`) ke kumpulan paragraf halaman:

```csharp
page.Paragraphs.Add(text);
```

#### T: Dapatkah saya mengulangi proses untuk jalur tambahan?

 A: Ya, pada Langkah 8, Anda dapat mengulangi proses untuk baris tambahan dengan indentasi yang sama dengan membuat yang baru`TextFragment` objek dan menambahkannya ke kumpulan paragraf halaman.

#### Q: Bagaimana cara menyimpan dokumen PDF yang dihasilkan?

 A: Setelah menambahkan teks dengan indentasi baris berikutnya, gunakan`Save` metode`Document` keberatan untuk menyimpan dokumen PDF:

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### T: Apa inti dari tutorial ini?

J: Dengan mengikuti tutorial ini, Anda telah berhasil mempelajari cara meningkatkan keterbacaan teks dalam dokumen PDF dengan menambahkan indentasi baris berikutnya menggunakan Aspose.PDF untuk .NET. Teknik ini dapat berguna untuk berbagai jenis dokumen dan laporan.