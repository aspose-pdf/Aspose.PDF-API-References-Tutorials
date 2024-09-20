---
title: Elemen Tabel Gaya
linktitle: Elemen Tabel Gaya
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara membuat dan menata elemen tabel di Aspose.PDF untuk .NET dengan petunjuk langkah demi langkah, gaya khusus, dan kepatuhan PDF/UA.
type: docs
weight: 170
url: /id/net/programming-with-tagged-pdf/style-table-element/
---
## Perkenalan

Dalam artikel ini, kita akan membahas cara membuat dan menata elemen tabel menggunakan Aspose.PDF untuk .NET. Anda akan mempelajari cara menyusun tabel, menerapkan gaya khusus, dan memvalidasi kepatuhan PDF/UA dokumen Anda. Di akhir tutorial ini, Anda akan dapat membuat tabel yang tampak profesional dalam PDF Anda dengan mudah!

## Prasyarat

Sebelum memulai tutorial, Anda harus memastikan Anda memiliki hal berikut:

1. Visual Studio atau IDE serupa terinstal di komputer Anda.
2. .NET Framework atau .NET Core SDK untuk menjalankan aplikasi.
3.  Pustaka Aspose.PDF untuk .NET diunduh dan dirujuk dalam proyek Anda. Anda dapat mengambil versi terbaru dari[Di Sini](https://releases.aspose.com/pdf/net/).
4.  Lisensi Aspose yang valid atau[lisensi sementara](https://purchase.aspose.com/temporary-license/) untuk membuka fungsionalitas penuh perpustakaan.

## Paket Impor

Untuk memulai, impor namespace yang diperlukan ke dalam proyek Anda:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Ruang nama ini mencakup operasi inti PDF, konten yang diberi tag, tabel, dan pemformatan teks.

Sekarang mari kita bahas proses pembuatan dan penataan tabel di Aspose.PDF. Kami akan membahas setiap bagian secara terperinci sehingga Anda dapat mengikutinya.

## Langkah 1: Buat Dokumen PDF Baru dan Siapkan Konten yang Ditandai

Pada langkah pertama ini, kita akan membuat dokumen PDF kosong dan menyiapkan konten yang diberi tag.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat dokumen PDF baru
Document document = new Document();

// Siapkan konten yang diberi tag
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");
```

 Kita mulai dengan membuat yang baru`Document` objek, yang mewakili PDF kita.`TaggedContent`Objek digunakan untuk mengelola struktur dokumen, memastikan kepatuhan terhadap standar aksesibilitas. Kami menetapkan judul dan bahasa dokumen untuk penandaan yang tepat.

## Langkah 2: Tentukan Elemen Root

Berikutnya, kita akan membuat elemen struktur root, yang berfungsi sebagai wadah untuk semua konten dalam PDF kita.

```csharp
// Dapatkan elemen struktur akar
StructureElement rootElement = taggedContent.RootElement;
```

 Itu`RootElement` berfungsi sebagai wadah dasar untuk semua elemen terstruktur, termasuk tabel kita. Wadah ini membantu menjaga hierarki struktural dokumen, yang penting untuk pengorganisasian dan aksesibilitas.

## Langkah 3: Membuat dan Menata Elemen Tabel

 Sekarang setelah elemen root telah disiapkan, kita akan membuat`TableElement` dan menerapkan gaya seperti warna latar belakang, batas, dan perataan.

```csharp
// Buat elemen struktur tabel
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);

// Menata tabel
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
```

 Kami menciptakan sebuah`TableElement` , yang mendefinisikan struktur tabel kita.`BackgroundColor`, `Border` , Dan`Alignment` properti memungkinkan kita untuk menyesuaikan tampilan tabel.`Broken` Properti memastikan bahwa jika tabel terbagi beberapa halaman, tabel tersebut akan terbagi secara vertikal.

## Langkah 4: Mengatur Dimensi Tabel dan Gaya Sel

Pada langkah ini, kita akan menentukan jumlah kolom, pengisi sel, dan properti tabel penting lainnya.

```csharp
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
```

 Kami menentukan lebar kolom untuk memastikan setiap kolom dalam tabel memiliki jarak yang sama.`DefaultCellBorder`, `DefaultCellPadding` , Dan`DefaultCellTextState` menentukan gaya default untuk sel, termasuk batas, bantalan, warna teks, dan ukuran font.

## Langkah 5: Tambahkan Baris Berulang dan Gaya Kustom

Kita juga dapat menentukan gaya untuk mengulang baris dan elemen tabel spesifik lainnya seperti header dan footer.

```csharp
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

 Itu`RepeatingRowsCount` memastikan bahwa tiga baris pertama diulang jika tabel mencakup beberapa halaman. Kami mengatur`RepeatingRowsStyle` untuk menerapkan warna latar belakang khusus pada baris-baris ini.

## Langkah 6: Tambahkan Elemen Kepala, Badan, dan Kaki Tabel

Sekarang, mari buat bagian header, body, dan footer tabel dan isi dengan konten.

```csharp
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// Buat baris tajuk
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 5; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
}

// Mengisi badan tabel
for (int rowIndex = 0; rowIndex < 10; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    for (int colIndex = 0; colIndex < 5; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
    }
}
```

 Tabel dibagi menjadi tiga bagian: kepala, badan, dan kaki. Pertama-tama kita membuat baris tajuk menggunakan`TableTHElement`dan menambahkan judul kolom. Kemudian, kita mengisi badan tabel dengan`TableTDElement`, mengisi setiap sel dengan label yang menyertakan posisinya.

## Langkah 7: Simpan Dokumen

Terakhir, kami menyimpan dokumen PDF ke direktori yang ditentukan.

```csharp
// Simpan dokumen PDF yang diberi tag
document.Save(dataDir + "StyleTableElement.pdf");
```

Langkah ini menyelesaikan proses pembuatan dokumen dengan menyimpan berkas PDF dengan tabel bergaya.

## Langkah 8: Validasi Kepatuhan PDF/UA

Setelah menyimpan dokumen, penting untuk memastikan bahwa dokumen tersebut mematuhi standar PDF/UA (Aksesibilitas Universal).

```csharp
// Periksa kepatuhan PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

Di sini, kami memuat ulang dokumen dan memvalidasinya berdasarkan standar PDF/UA. Kepatuhan memastikan bahwa PDF Anda memenuhi persyaratan aksesibilitas, sehingga cocok untuk berbagai macam pengguna.

## Kesimpulan

Dengan Aspose.PDF untuk .NET, membuat dan menata tabel dalam dokumen PDF Anda menjadi mudah dan intuitif. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat membuat tabel dengan gaya yang disesuaikan dan memastikan PDF Anda memenuhi standar aksesibilitas. Baik Anda membuat laporan atau membuat dokumen terstruktur, tabel merupakan alat yang ampuh untuk menyajikan data dengan jelas.

## Pertanyaan yang Sering Diajukan

### Bisakah saya menambahkan gambar di dalam sel tabel?
 Ya, Anda dapat memasukkan gambar ke dalam sel tabel menggunakan`Image` elemen.

### Bagaimana cara menyesuaikan lebar kolom secara dinamis?
 Anda dapat mengatur`ColumnAdjustment` properti untuk`AutoFitToWindow` untuk menyesuaikan lebar kolom secara otomatis berdasarkan konten.

### Apakah kepatuhan PDF/UA wajib untuk semua dokumen?
Meskipun tidak wajib, namun direkomendasikan untuk dokumen yang memerlukan standar aksesibilitas tinggi.

### Bisakah saya menerapkan gaya yang berbeda pada baris tertentu?
 Ya, Anda dapat menyesuaikan baris atau sel individual dengan menyesuaikannya`TextState` atau`BackgroundColor`.

### Apa manfaat menggunakan konten yang diberi tag?
Konten yang diberi tag meningkatkan aksesibilitas dokumen dan membantu memastikan kepatuhan terhadap standar seperti PDF/UA.