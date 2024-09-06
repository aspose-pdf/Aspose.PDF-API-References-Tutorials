---
title: Tambahkan Baris Berikutnya Indentasi Dalam File PDF
linktitle: Tambahkan Baris Berikutnya Indentasi Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menambahkan indentasi baris berikutnya ke teks dalam berkas PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 60
url: /id/net/programming-with-text/add-subsequent-lines-indent/
---
Tutorial ini akan memandu Anda melalui proses penambahan baris berikutnya yang menjorok ke teks dalam file PDF menggunakan Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan.

## Persyaratan
Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau kompiler C# lainnya terinstal di komputer Anda.
- Aspose.PDF untuk pustaka .NET. Anda dapat mengunduhnya dari situs web resmi Aspose atau menggunakan pengelola paket seperti NuGet untuk menginstalnya.

## Langkah 1: Siapkan proyek
1. Buat proyek C# baru di lingkungan pengembangan pilihan Anda.
2. Tambahkan referensi ke pustaka Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan
Pada berkas kode tempat Anda ingin menambahkan indentasi baris berikutnya, tambahkan perintah using berikut di bagian atas berkas:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Langkah 3: Mengatur direktori dokumen
 Dalam kode, temukan baris yang bertuliskan`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur ke direktori tempat dokumen Anda disimpan.

## Langkah 4: Buat objek Dokumen baru
 Membuat instance baru`Document` objek dengan menambahkan baris kode berikut:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## Langkah 5: Tambahkan halaman ke dokumen
 Tambahkan halaman baru ke dokumen dengan menggunakan`Add` metode dari`Pages`koleksi. Dalam kode yang diberikan, halaman baru ditetapkan ke variabel`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## Langkah 6: Buat TextFragment dengan baris berikutnya yang diindentasi
 Membuat contoh sebuah`TextFragment` objek dan memberikan teks yang diinginkan. Dalam kode yang diberikan, teks ditetapkan ke variabel`text` Kemudian, inisialisasi`TextFormattingOptions` Untuk`TextFragment`dan tentukan`SubsequentLinesIndent` nilai.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## Langkah 7: Tambahkan TextFragment ke halaman
 Tambahkan`TextFragment` keberatan terhadap kumpulan paragraf pada halaman tersebut.

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
 Simpan dokumen PDF menggunakan`Save` metode dari`Document` objek. Tentukan jalur file keluaran.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Contoh kode sumber untuk Menambahkan Indentasi Baris Berikutnya menggunakan Aspose.PDF untuk .NET 
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
Anda telah berhasil menambahkan baris-baris berikutnya yang menjorok ke dalam teks menggunakan Aspose.PDF untuk .NET. File PDF yang dihasilkan sekarang dapat ditemukan di jalur file keluaran yang ditentukan.

### Pertanyaan yang Sering Diajukan

#### T: Apa fokus dari tutorial ini?

J: Tutorial ini menyediakan panduan lengkap tentang cara menambahkan baris berikutnya yang menjorok ke teks dalam file PDF menggunakan pustaka Aspose.PDF for .NET. Tutorial ini menyertakan contoh kode sumber C# untuk mengilustrasikan langkah-langkah yang diperlukan untuk mencapainya.

#### T: Namespace mana yang perlu saya impor untuk tutorial ini?

A: Pada berkas kode tempat Anda bermaksud menambahkan indentasi baris berikutnya, impor namespace berikut di awal berkas:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### T: Bagaimana cara menentukan direktori dokumen?

 A: Pada kode tersebut, temukan baris`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

#### T: Bagaimana cara membuat objek Dokumen?

 A: Pada Langkah 4, Anda akan membuat instance baru`Document` objek menggunakan baris kode berikut:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### T: Bagaimana cara menambahkan halaman ke dokumen?

 A: Pada Langkah 5, Anda akan menambahkan halaman baru ke dokumen menggunakan`Add` metode dari`Pages` koleksi:

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### T: Bagaimana cara menambahkan indentasi baris berikutnya pada teks?

 A: Pada Langkah 6, Anda akan membuat`TextFragment` objek dan tetapkan teks yang diinginkan padanya. Kemudian, Anda akan menginisialisasi`TextFormattingOptions` Untuk`TextFragment`dan tentukan`SubsequentLinesIndent` nilai:

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### T: Bagaimana cara menambahkan TextFragment ke dokumen PDF?

 A: Pada Langkah 7, Anda akan menambahkan`TextFragment` objek (`text`) ke kumpulan paragraf halaman:

```csharp
page.Paragraphs.Add(text);
```

#### T: Dapatkah saya mengulang proses untuk baris tambahan?

 A: Ya, pada Langkah 8, Anda dapat mengulangi proses untuk baris tambahan dengan indentasi yang sama dengan membuat baris baru`TextFragment` objek dan menambahkannya ke koleksi paragraf halaman.

#### T: Bagaimana cara menyimpan dokumen PDF yang dihasilkan?

 A: Setelah menambahkan teks dengan baris berikutnya indent, gunakan`Save` metode dari`Document` objek untuk menyimpan dokumen PDF:

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### T: Apa inti sari dari tutorial ini?

A: Dengan mengikuti tutorial ini, Anda telah berhasil mempelajari cara meningkatkan keterbacaan teks dalam dokumen PDF dengan menambahkan indentasi baris berikutnya menggunakan Aspose.PDF untuk .NET. Teknik ini dapat berguna untuk berbagai jenis dokumen dan laporan.