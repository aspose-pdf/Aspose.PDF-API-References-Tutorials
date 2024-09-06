---
title: Sesuaikan Nomor Halaman Sambil Menambahkan Daftar Isi
linktitle: Sesuaikan Nomor Halaman Sambil Menambahkan Daftar Isi
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menyesuaikan nomor halaman sambil menambahkan Daftar Isi ke dokumen PDF Anda menggunakan Aspose.PDF untuk .NET dalam tutorial komprehensif ini.
type: docs
weight: 100
url: /id/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---
## Perkenalan

Dalam dunia manajemen dokumen, PDF adalah yang paling unggul. PDF adalah format yang paling tepat untuk berbagi dan menyimpan dokumen di berbagai platform. Namun, apa yang terjadi jika Anda ingin menyempurnakan dokumen PDF dengan fitur seperti Daftar Isi (TOC)? Di sinilah Aspose.PDF for .NET berperan! Pustaka canggih ini memungkinkan pengembang untuk memanipulasi file PDF dengan mudah, sehingga mereka dapat menambahkan, memodifikasi, dan menyesuaikan konten dengan mudah. Dalam tutorial ini, kita akan membahas cara menyesuaikan nomor halaman sambil menambahkan TOC ke dokumen PDF menggunakan Aspose.PDF for .NET. Jadi, ambil topi koding Anda, dan mari kita mulai!

## Prasyarat

Sebelum kita masuk ke kode, ada beberapa hal yang perlu Anda siapkan:

1. Visual Studio: Pastikan Anda telah menginstal Visual Studio di komputer Anda. Ini akan menjadi lingkungan pengembangan kita.
2. Aspose.PDF untuk .NET: Anda perlu mengunduh dan menginstal pustaka Aspose.PDF. Anda dapat menemukannya[Di Sini](https://releases.aspose.com/pdf/net/).
3. Pengetahuan Dasar C#: Keakraban dengan pemrograman C# akan membantu Anda memahami potongan kode dengan lebih baik.
4. Contoh Berkas PDF: Siapkan contoh berkas PDF yang dapat kami gunakan. Anda dapat membuat berkas PDF sederhana atau mengunduh berkas PDF yang sudah ada.

## Paket Impor

Untuk memulai, kita perlu mengimpor paket yang diperlukan. Buka proyek Visual Studio Anda dan tambahkan referensi ke pustaka Aspose.PDF. Anda dapat melakukannya dengan menggunakan NuGet Package Manager:

1. Klik kanan pada proyek Anda di Solution Explorer.
2. Pilih "Kelola Paket NuGet."
3. Cari "Aspose.PDF" dan instal.

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Setelah pustaka terinstal, Anda dapat mulai membuat kode!

## Langkah 1: Siapkan Direktori Dokumen Anda

Pertama-tama, kita perlu menyiapkan direktori dokumen. Di sinilah kita akan menyimpan berkas PDF masukan dan keluaran. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
```

Dalam cuplikan ini, ganti`YOUR DOCUMENT DIRECTORY` dengan jalur sebenarnya tempat file PDF Anda berada. Ini akan membantu kami memuat PDF yang ada dan menyimpan versi yang dimodifikasi.

## Langkah 2: Muat File PDF yang Ada

Sekarang setelah direktori dokumen kita disiapkan, mari muat berkas PDF yang ada. 

```csharp
Document doc = new Document(inFile);
```

 Di sini, kita membuat yang baru`Document` objek dengan meneruskan jalur berkas input. Hal ini memungkinkan kita untuk memanipulasi konten PDF secara terprogram.

## Langkah 3: Masukkan Halaman Baru untuk Daftar Isi

Berikutnya, kita perlu membuat halaman baru di PDF kita tempat Daftar Isi akan berada.

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

Baris ini menyisipkan halaman baru di awal dokumen. Daftar isi akan ditampilkan di halaman ini.

## Langkah 4: Buat Informasi Daftar Isi

Sekarang, mari membuat objek untuk mewakili informasi TOC.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

 Pada langkah ini, kita membuat`TocInfo` objek dan atur judulnya menjadi "Daftar Isi." Kami juga menyesuaikan ukuran dan gaya font.`PageNumbersPrefix` diatur ke "P," yang akan menjadi awalan nomor halaman di TOC.

## Langkah 5: Tambahkan Judul ke Daftar Isi

Sekarang tibalah bagian yang menyenangkan! Kita akan mengulang halaman-halaman dokumen dan menambahkan judul ke TOC kita.

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    heading2.DestinationPage = doc.Pages[i + 1];
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    segment2.Text = "Page " + i.ToString();
    tocPage.Paragraphs.Add(heading2);
}
```

 Dalam loop ini, kita membuat yang baru`Heading` objek untuk setiap halaman. Kami menetapkan halaman tujuan untuk setiap judul dan menentukan teks yang akan ditampilkan, yaitu "Halaman X" di mana X adalah nomor halaman. Terakhir, kami menambahkan judul ke halaman TOC.

## Langkah 6: Simpan Dokumen yang Diperbarui

Setelah menambahkan semua judul yang diperlukan, saatnya menyimpan dokumen kita yang telah diperbarui.

```csharp
doc.Save(outFile);
```

Baris ini menyimpan PDF yang dimodifikasi dengan TOC yang disertakan. Sekarang Anda dapat membuka file output dan melihat Daftar Isi yang telah Anda sesuaikan!

## Kesimpulan

Nah, itu dia! Anda telah berhasil menyesuaikan nomor halaman sambil menambahkan Daftar Isi ke dokumen PDF Anda menggunakan Aspose.PDF untuk .NET. Pustaka canggih ini memudahkan Anda memanipulasi file PDF, dan hanya dengan beberapa baris kode, Anda dapat menyempurnakan dokumen Anda secara signifikan. Baik Anda membuat laporan, eBook, atau jenis PDF lainnya, memiliki Daftar Isi dapat sangat meningkatkan navigasi bagi pembaca Anda. Jadi, tunggu apa lagi? Pelajari Aspose.PDF dan mulailah membuat PDF yang menakjubkan hari ini!

## Pertanyaan yang Sering Diajukan

### Apa itu Aspose.PDF untuk .NET?
Aspose.PDF untuk .NET adalah pustaka yang memungkinkan pengembang untuk membuat, memanipulasi, dan mengonversi dokumen PDF secara terprogram.

### Dapatkah saya menggunakan Aspose.PDF secara gratis?
 Ya, Aspose menawarkan versi uji coba gratis yang dapat Anda gunakan untuk menjelajahi fitur-fitur pustaka. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/).

### Bagaimana cara mendapatkan dukungan untuk Aspose.PDF?
 Anda bisa mendapatkan dukungan dengan mengunjungi forum Aspose[Di Sini](https://forum.aspose.com/c/pdf/10).

### Apakah ada lisensi sementara yang tersedia?
 Ya, Anda dapat meminta lisensi sementara untuk Aspose.PDF[Di Sini](https://purchase.aspose.com/temporary-license/).

### Di mana saya dapat membeli Aspose.PDF untuk .NET?
 Anda dapat membeli Aspose.PDF untuk .NET[Di Sini](https://purchase.aspose.com/buy).