---
title: Gaya Tabel Sel
linktitle: Gaya Tabel Sel
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menata sel tabel dalam PDF menggunakan Aspose.PDF untuk .NET dengan tutorial terperinci ini. Ikuti petunjuk untuk membuat dan memformat tabel PDF yang cantik.
type: docs
weight: 160
url: /id/net/programming-with-tagged-pdf/style-table-cell/
---
## Perkenalan

Membuat tabel PDF yang tampak profesional bisa jadi sulit, tetapi dengan Aspose.PDF untuk .NET, semuanya menjadi sangat mudah! Baik Anda ingin menata tajuk, catatan kaki, atau sel tabel tertentu, pustaka canggih ini menyediakan semua alat yang Anda butuhkan untuk membuat dokumen PDF berformat cantik. Dalam tutorial ini, kami akan memandu Anda tentang cara menata sel tabel dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Jangan khawatir—kami akan menguraikan semuanya menjadi langkah-langkah yang mudah diikuti.

## Prasyarat

Sebelum menyelami kode, pastikan Anda memiliki prasyarat berikut:

1. Aspose.PDF untuk .NET: Unduh dan instal versi terbaru Aspose.PDF dari[Di Sini](https://releases.aspose.com/pdf/net/).
2. IDE (seperti Visual Studio): Siapkan lingkungan pengembangan .NET.
3. Pengetahuan dasar pemrograman C#: Diperlukan sedikit pengetahuan tentang C#.
4.  Lisensi Aspose.PDF: Dapatkan lisensi sementara atau penuh untuk membuka fitur lengkap pustaka. Anda bisa mendapatkan uji coba gratis[Di Sini](https://purchase.aspose.com/temporary-license/).

## Paket Impor

Sebelum memulai, pastikan untuk mengimpor namespace yang diperlukan. Anda memerlukan hal berikut dalam proyek Anda:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Sekarang semuanya sudah disiapkan, mari masuk ke panduan langkah demi langkah!

Kita akan membuat tabel dalam dokumen PDF dan menata sel-selnya. Setiap langkah akan menjelaskan prosesnya secara terperinci.

## Langkah 1: Buat Dokumen PDF Baru

 Langkah pertama adalah membuat dokumen PDF baru. Di Aspose.PDF, Anda dapat menginisialisasi dokumen PDF baru.`Document` objek yang mewakili berkas PDF Anda.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat dokumen PDF baru
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");
```

Di sini, kami menginisialisasi dokumen PDF dan menetapkan judul serta bahasanya. Ini akan memberikan dokumen Anda struktur yang tepat, yang penting untuk kepatuhan PDF/UA.

## Langkah 2: Siapkan Struktur Tabel

Tabel dalam PDF didefinisikan dalam elemen struktur. Mari buat tabel dan tentukan baris dan kolom tabel.

```csharp
// Dapatkan elemen struktur akar
StructureElement rootElement = taggedContent.RootElement;

// Membuat elemen struktur tabel
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Sekarang kita telah mendefinisikan kepala tabel (`TableTHeadElement`), tubuh (`TableTBodyElement`), dan kaki (`TableTFootElement`) bagian. Anda dapat menganggapnya sebagai kerangka tabel Anda.

## Langkah 3: Memberi Gaya pada Sel Header

Penataan sel header akan membuatnya menonjol. Di sini, kami menerapkan warna latar belakang, batas, dan perataan teks.

```csharp
int colCount = 4;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
    thElement.BackgroundColor = Color.GreenYellow;
    thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
    thElement.IsNoBorder = true;
    thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
    thElement.Alignment = HorizontalAlignment.Right;
}
```

Pada langkah ini, kita akan mengulang setiap sel header, memberinya latar belakang hijau-kuning, batas abu-abu, dan teks rata kanan. Anda dapat menyesuaikan properti ini agar sesuai dengan desain yang Anda inginkan.

## Langkah 4: Mengisi dan Menata Badan Tabel

Isi tabel berisi data aktual. Berikut cara memberi gaya pada setiap sel dengan margin, batas, dan pengaturan teks tertentu.

```csharp
int rowCount = 4;

for (int rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = $"Row {rowIndex}";

    for (int colIndex = 0; colIndex < colCount; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
        tdElement.BackgroundColor = Color.Yellow;
        tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
        tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
        tdElement.Alignment = HorizontalAlignment.Center;
        
        TextState cellTextState = new TextState();
        cellTextState.ForegroundColor = Color.DarkBlue;
        cellTextState.FontSize = 7.5F;
        cellTextState.FontStyle = FontStyles.Bold;
        cellTextState.Font = FontRepository.FindFont("Arial");
        tdElement.DefaultCellTextState = cellTextState;
    }
}
```

 Pada langkah ini, kita mengisi badan tabel dengan empat baris dan memberi gaya pada setiap sel dengan latar belakang kuning dan teks biru tebal di tengah. Kita juga menggunakan`MarginInfo`kelas untuk menentukan bantalan di sekitar teks.

## Langkah 5: Memberi Gaya pada Footer

Untuk memberi tabel struktur yang lengkap, kita menambahkan dan memberi gaya pada sel footer, sama seperti yang kita lakukan pada header.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText($"Foot {colIndex}");
}
```

Bagian footer ditata serupa dengan header, sehingga memudahkan pembaca mengikuti struktur tabel.

## Langkah 6: Simpan dan Validasi Dokumen PDF

Terakhir, kami menyimpan dokumen PDF dan memeriksa apakah itu sesuai PDF/UA.

```csharp
// Simpan dokumen PDF yang diberi tag
document.Save(dataDir + "StyleTableCell.pdf");

// Memeriksa kepatuhan PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

 Kami menyimpan PDF dan menggunakan`Validate` metode untuk memastikannya memenuhi standar aksesibilitas (kepatuhan PDF/UA).

## Kesimpulan

Mendesain tabel dalam PDF menggunakan Aspose.PDF untuk .NET sangat canggih dan fleksibel. Dengan beberapa baris kode, Anda dapat membuat desain tabel khusus yang akan membuat dokumen PDF Anda menonjol. Mulai dari menyesuaikan batas sel dan latar belakang hingga memastikan kepatuhan aksesibilitas, Aspose.PDF memudahkan pembuatan file PDF yang bagus.

## Pertanyaan yang Sering Diajukan

### Bisakah saya menerapkan gaya yang berbeda pada sel tabel individual?  
Ya, Anda dapat menata sel individual dengan menyesuaikannya`TableTDElement` properti.

### Bagaimana cara menggabungkan sel tabel?  
 Anda dapat menggunakan`ColSpan` Dan`RowSpan` properti untuk menggabungkan sel dalam tabel.

### Apakah mungkin untuk membuat tabel yang sesuai PDF/UA?  
 Ya, seperti yang ditunjukkan dalam panduan ini, Anda dapat memastikan kepatuhan PDF/UA dengan memvalidasi dokumen Anda menggunakan`Validate` metode.

### Bisakah saya menggunakan font yang berbeda dalam sel tabel?  
 Tentu saja! Anda dapat menentukan font yang berbeda menggunakan`TextState` objek untuk setiap sel.

### Bagaimana cara mengunduh Aspose.PDF untuk .NET?  
 Anda dapat mengunduhnya dari[halaman rilis](https://releases.aspose.com/pdf/net/).