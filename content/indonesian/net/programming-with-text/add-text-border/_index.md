---
title: Tambahkan Batas Teks Dalam File PDF
linktitle: Tambahkan Batas Teks Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menambahkan batas teks dalam berkas PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 70
url: /id/net/programming-with-text/add-text-border/
---
Tutorial ini akan memandu Anda melalui proses penambahan batas teks dalam file PDF menggunakan Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan.

## Persyaratan
Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau kompiler C# lainnya terinstal di komputer Anda.
- Aspose.PDF untuk pustaka .NET. Anda dapat mengunduhnya dari situs web resmi Aspose atau menggunakan pengelola paket seperti NuGet untuk menginstalnya.

## Langkah 1: Siapkan proyek
1. Buat proyek C# baru di lingkungan pengembangan pilihan Anda.
2. Tambahkan referensi ke pustaka Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan
Pada berkas kode tempat Anda ingin menambahkan batas teks, tambahkan perintah using berikut di bagian atas berkas:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Langkah 3: Mengatur direktori dokumen
 Dalam kode, temukan baris yang bertuliskan`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur ke direktori tempat dokumen Anda disimpan.

## Langkah 4: Buat objek Dokumen baru
 Membuat instance baru`Document` objek dengan menambahkan baris kode berikut:

```csharp
Document pdfDocument = new Document();
```

## Langkah 5: Tambahkan halaman ke dokumen
 Tambahkan halaman baru ke dokumen dengan menggunakan`Add` metode dari`Pages`koleksi. Dalam kode yang diberikan, halaman baru ditetapkan ke variabel`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Langkah 6: Buat TextFragment
 Membuat sebuah`TextFragment` objek dan berikan teks yang diinginkan. Atur posisi fragmen teks menggunakan`Position` properti. Dalam kode yang diberikan, teks diatur ke "teks utama" dan diposisikan pada (100, 600) di halaman.

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## Langkah 7: Mengatur properti teks
Sesuaikan properti teks seperti ukuran font, jenis font, warna latar belakang, warna latar depan, dll. Dalam kode yang diberikan, properti seperti ukuran font, font, warna latar belakang, warna latar depan, dan warna goresan ditetapkan untuk fragmen teks.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## Langkah 8: Aktifkan batas teks
 Untuk mengaktifkan batas teks, atur`DrawTextRectangleBorder`properti dari fragmen teks`TextState` ke`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## Langkah 9: Tambahkan TextFragment ke halaman
 Gunakan`TextBuilder` kelas untuk menambahkan`TextFragment` keberatan terhadap halaman tersebut.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## Langkah 10: Simpan dokumen PDF
 Simpan dokumen PDF menggunakan`Save` metode dari`Document` objek. Tentukan jalur file keluaran yang Anda tetapkan pada Langkah 3.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### Contoh kode sumber untuk Menambahkan Batas Teks menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buat objek dokumen baru
Document pdfDocument = new Document();
// Dapatkan halaman tertentu
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Buat fragmen teks
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// Mengatur properti teks
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Atur properti StrokingColor untuk menggambar batas (stroking) di sekitar persegi panjang teks
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// Tetapkan nilai properti DrawTextRectangleBorder ke true
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// Simpan dokumen
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## Kesimpulan
Anda telah berhasil menambahkan bingkai teks ke dokumen PDF Anda menggunakan Aspose.PDF untuk .NET. File PDF yang dihasilkan kini dapat ditemukan di jalur file keluaran yang ditentukan.

### Pertanyaan yang Sering Diajukan

#### T: Apa fokus utama tutorial ini?

J: Tutorial ini memandu Anda melalui proses penambahan batas teks ke berkas PDF menggunakan pustaka Aspose.PDF for .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan untuk mencapainya.

#### T: Namespace mana yang perlu saya impor untuk tutorial ini?

A: Pada berkas kode tempat Anda ingin menambahkan batas teks, impor namespace berikut di awal berkas:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### T: Bagaimana cara menentukan direktori dokumen?

 A: Pada kode tersebut, temukan baris`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

#### T: Bagaimana cara membuat objek Dokumen?

 A: Pada Langkah 4, Anda akan membuat instance baru`Document` objek menggunakan baris kode berikut:

```csharp
Document pdfDocument = new Document();
```

#### T: Bagaimana cara menambahkan halaman ke dokumen?

 A: Pada Langkah 5, Anda akan menambahkan halaman baru ke dokumen menggunakan`Add` metode dari`Pages` koleksi:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### T: Bagaimana cara membuat TextFragment dan mengatur posisinya?

 A: Pada Langkah 6, Anda akan membuat`TextFragment`objek dan mengatur posisinya di halaman menggunakan`Position` milik:

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### T: Bagaimana cara menyesuaikan properti teks, termasuk batas teks?

A: Pada Langkah 7, Anda akan menyesuaikan berbagai properti teks seperti ukuran font, jenis font, warna latar belakang, warna latar depan, dan batas teks:

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### T: Bagaimana cara menambahkan TextFragment ke dokumen PDF?

 A: Pada Langkah 9, Anda akan menggunakan`TextBuilder` kelas untuk menambahkan`TextFragment` keberatan terhadap halaman:

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### T: Bagaimana cara menyimpan dokumen PDF yang dihasilkan?

 A: Setelah menambahkan teks dengan batas, gunakan`Save` metode dari`Document` objek untuk menyimpan dokumen PDF:

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### T: Apa hasil utama dari tutorial ini?

J: Dengan mengikuti tutorial ini, Anda telah berhasil mempelajari cara menyempurnakan dokumen PDF Anda dengan menambahkan bingkai teks menggunakan Aspose.PDF untuk .NET. Ini dapat sangat berguna untuk menekankan konten teks tertentu dalam file PDF Anda.