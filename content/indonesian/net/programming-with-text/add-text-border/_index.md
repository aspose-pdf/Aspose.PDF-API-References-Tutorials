---
title: Tambahkan Batas Teks Dalam File PDF
linktitle: Tambahkan Batas Teks Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menambahkan batas teks dalam file PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 70
url: /id/net/programming-with-text/add-text-border/
---
Tutorial ini akan memandu Anda melalui proses menambahkan batas teks dalam file PDF menggunakan Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan.

## Persyaratan
Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau kompiler C# lainnya yang diinstal pada mesin Anda.
- Aspose.PDF untuk perpustakaan .NET. Anda dapat mendownloadnya dari situs resmi Aspose atau menggunakan manajer paket seperti NuGet untuk menginstalnya.

## Langkah 1: Siapkan proyek
1. Buat proyek C# baru di lingkungan pengembangan pilihan Anda.
2. Tambahkan referensi ke perpustakaan Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan
Dalam file kode di mana Anda ingin menambahkan batas teks, tambahkan arahan penggunaan berikut di bagian atas file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Langkah 3: Atur direktori dokumen
 Dalam kode, temukan baris yang bertuliskan`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur ke direktori tempat dokumen Anda disimpan.

## Langkah 4: Buat objek Dokumen baru
 Buat instance yang baru`Document` objek dengan menambahkan baris kode berikut:

```csharp
Document pdfDocument = new Document();
```

## Langkah 5: Tambahkan halaman ke dokumen
 Tambahkan halaman baru ke dokumen dengan menggunakan`Add` metode`Pages`koleksi. Dalam kode yang disediakan, halaman baru ditugaskan ke variabel`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Langkah 6: Buat TextFragment
 Membuat`TextFragment` objek dan memberikan teks yang diinginkan. Atur posisi fragmen teks menggunakan`Position` Properti. Dalam kode yang disediakan, teks disetel ke "teks utama" dan diposisikan pada (100, 600) pada halaman.

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## Langkah 7: Atur properti teks
Sesuaikan properti teks seperti ukuran font, jenis font, warna latar belakang, warna latar depan, dll. Dalam kode yang disediakan, properti seperti ukuran font, font, warna latar belakang, warna latar depan, dan warna guratan diatur untuk fragmen teks.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## Langkah 8: Aktifkan batas teks
 Untuk mengaktifkan batas teks, atur`DrawTextRectangleBorder`milik fragmen teks`TextState` ke`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## Langkah 9: Tambahkan TextFragment ke halaman
 Menggunakan`TextBuilder` kelas untuk menambahkan`TextFragment` keberatan dengan halaman tersebut.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## Langkah 10: Simpan dokumen PDF
 Simpan dokumen PDF menggunakan`Save` metode`Document` obyek. Tentukan jalur file keluaran yang Anda atur di Langkah 3.

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
// Atur properti teks
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Atur properti StrokingColor untuk menggambar batas (guratan) di sekitar persegi panjang teks
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// Tetapkan nilai properti DrawTextRectangleBorder ke true
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// Simpan dokumennya
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## Kesimpulan
Anda telah berhasil menambahkan batas teks ke dokumen PDF Anda menggunakan Aspose.PDF untuk .NET. File PDF yang dihasilkan sekarang dapat ditemukan di jalur file keluaran yang ditentukan.

### FAQ

#### Q: Apa fokus utama tutorial ini?

J: Tutorial ini memandu Anda melalui proses menambahkan batas teks ke file PDF menggunakan pustaka Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan untuk mencapai hal ini.

#### T: Namespace manakah yang perlu saya impor untuk tutorial ini?

J: Dalam file kode tempat Anda ingin menambahkan batas teks, impor namespace berikut di awal file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### T: Bagaimana cara menentukan direktori dokumen?

 A: Di dalam kode, temukan barisnya`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

#### T: Bagaimana cara membuat objek Dokumen?

 J: Pada Langkah 4, Anda akan membuat instance yang baru`Document` objek menggunakan baris kode berikut:

```csharp
Document pdfDocument = new Document();
```

#### T: Bagaimana cara menambahkan halaman ke dokumen?

 J: Pada Langkah 5, Anda akan menambahkan halaman baru ke dokumen menggunakan`Add` metode`Pages` koleksi:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### T: Bagaimana cara membuat TextFragment dan mengatur posisinya?

 J: Pada Langkah 6, Anda akan membuat a`TextFragment`objek dan atur posisinya pada halaman menggunakan`Position` Properti:

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### T: Bagaimana cara menyesuaikan properti teks, termasuk batas teks?

J: Pada Langkah 7, Anda akan menyesuaikan berbagai properti teks seperti ukuran font, jenis font, warna latar belakang, warna latar depan, dan batas teks:

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### T: Bagaimana cara menambahkan TextFragment ke dokumen PDF?

 J: Pada Langkah 9, Anda akan menggunakan`TextBuilder` kelas untuk menambahkan`TextFragment` keberatan dengan halaman:

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### Q: Bagaimana cara menyimpan dokumen PDF yang dihasilkan?

 A: Setelah menambahkan teks dengan pembatas, gunakan`Save` metode`Document` keberatan untuk menyimpan dokumen PDF:

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### T: Apa manfaat utama dari tutorial ini?

J: Dengan mengikuti tutorial ini, Anda telah berhasil mempelajari cara menyempurnakan dokumen PDF Anda dengan menambahkan batas teks menggunakan Aspose.PDF untuk .NET. Ini bisa sangat berguna untuk menekankan konten teks tertentu dalam file PDF Anda.