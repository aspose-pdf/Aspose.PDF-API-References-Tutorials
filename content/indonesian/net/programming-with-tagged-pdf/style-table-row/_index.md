---
title: Baris Tabel Gaya
linktitle: Baris Tabel Gaya
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menata baris tabel dalam PDF menggunakan Aspose.PDF untuk .NET dengan panduan langkah demi langkah untuk menyempurnakan pemformatan dokumen Anda dengan mudah.
type: docs
weight: 180
url: /id/net/programming-with-tagged-pdf/style-table-row/
---
## Perkenalan

Jika ingin membuat dokumen PDF yang terstruktur dengan baik dan berformat indah, Aspose.PDF for .NET adalah solusi yang tepat. Baik Anda mengotomatiskan laporan, faktur, atau membuat tabel dinamis, memformat tabel dengan berbagai gaya adalah kunci untuk dokumen yang sempurna. Dalam tutorial ini, kita akan mendalami lebih jauh tentang cara menata baris tabel menggunakan Aspose.PDF for .NET. Dan jangan khawatir, saya akan memandu Anda langkah demi langkah, seperti mengobrol santai sambil minum kopi!

## Prasyarat

Sebelum kita mulai, mari pastikan Anda sudah mempersiapkan semuanya dengan baik. Anda memerlukan:

1. Aspose.PDF untuk Pustaka .NET  
    Jika Anda belum memilikinya, Anda dapat mengambilnya dari[Di Sini](https://releases.aspose.com/pdf/net/) Anda juga bisa mendapatkan[uji coba gratis](https://releases.aspose.com/) untuk memulai.
2. Lingkungan Pengembangan  
   Siapkan Visual Studio atau IDE C# pilihan Anda. Anda juga perlu menginstal .NET, tetapi saya rasa Anda sudah familier dengan itu.
3. Pengetahuan Dasar tentang C# dan .NET  
   Pemahaman yang baik tentang C# akan membuat tutorial ini mudah. Namun jangan khawatir, saya akan menjelaskan setiap langkah secara terperinci!

## Paket Impor

Sebelum kita dapat mulai bekerja dengan Aspose.PDF, kita perlu mengimpor namespace yang diperlukan. Dalam proyek C# Anda, pastikan Anda menyertakan yang berikut ini:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Ini penting untuk membuat dan menata tabel, dan tentu saja, untuk bekerja dengan konten yang diberi tag demi kepatuhan.

Sekarang mari kita uraikan tugas ini langkah demi langkah, sehingga Anda dapat menata baris tabel Anda seperti seorang profesional!

## Langkah 1: Buat Dokumen PDF Baru

Hal pertama yang harus dilakukan: mari kita buat dokumen PDF baru. Dokumen ini akan memuat semua baris tabel yang diberi gaya.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat dokumen
Document document = new Document();
```

 Di sini, kita hanya menginisialisasi yang baru`Document` objek yang akan mewakili berkas PDF kita. Pastikan untuk mengatur jalur direktori tempat Anda akan menyimpan berkas keluaran.

## Langkah 2: Bekerja dengan Konten yang Ditandai

Untuk menyusun PDF Anda agar mudah diakses, kami akan bekerja dengan konten yang diberi tag. Ini membantu dalam pembuatan elemen terstruktur seperti tabel, memastikannya sesuai dengan standar aksesibilitas seperti PDF/UA.

```csharp
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");
```

Di sini, kami menetapkan judul dan bahasa untuk konten PDF yang diberi tag. Ini seperti memberi nama pada PDF Anda dan menentukan bahasa yang harus digunakan!

## Langkah 3: Tentukan Struktur Tabel

Selanjutnya, mari kita definisikan struktur tabel yang akan kita buat. Setiap tabel memerlukan header, body, dan footer – seperti halnya posting blog yang terorganisasi dengan baik!

```csharp
// Dapatkan elemen struktur akar
StructureElement rootElement = taggedContent.RootElement;

// Buat elemen struktur tabel
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Apa yang kita lakukan di sini adalah membuat tabel dengan header (`THead`), tubuh (`TBody`), dan footer (`TFoot`). Elemen-elemen ini akan menahan baris-baris kita.

## Langkah 4: Tambahkan Baris Header Tabel

Tabel tanpa tajuk bagaikan buku tanpa judul. Mari buat baris tajuk terlebih dahulu untuk menyediakan konteks bagi data.

```csharp
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText(String.Format("Head {0}", colIndex));
}
```

Di sini, kita mengulang dan menambahkan tiga sel header (`TableTHElement`), yang masing-masing berisi teks deskriptif. Sederhana, bukan?

## Langkah 5: Tambahkan Baris Tubuh Bergaya

Sekarang tibalah bagian yang menyenangkan – menata baris! Mari buat tujuh baris dengan gaya khusus. Kita akan mengatur warna latar belakang, batas, padding, dan perataan teks.

```csharp
for (int rowIndex = 0; rowIndex < 7; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = String.Format("Row {0}", rowIndex);
    trElement.BackgroundColor = Color.LightGoldenrodYellow;
    trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
    trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
    trElement.MinRowHeight = 100.0;
    trElement.FixedRowHeight = 120.0;
    trElement.IsInNewPage = (rowIndex % 3 == 1);
    trElement.IsRowBroken = true;

    for (int colIndex = 0; colIndex < 3; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
    }
}
```

- Warna Latar Belakang: Kami menggunakan warna kuning keemasan muda untuk kesan profesional namun tetap hangat.
- Batas: Setiap baris mendapat batas luar abu-abu gelap dan batas sel biru untuk tampilan yang tajam.
- Tinggi dan Bantalan: Tinggi baris diatur, dan bantalan ditambahkan agar tampilan lebih rapi.
- Hentian Halaman: Untuk membuat tabel lebih mudah dibaca, setiap baris kedua dimulai pada halaman baru.

## Langkah 6: Tambahkan Baris Footer

Seperti halnya header, footer menjadi jangkar tabel. Mari kita buat satu.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText(String.Format("Foot {0}", colIndex));
}
```

Kita cukup mengulang tiga sel footer dan menambahkan sedikit teks. Teks alternatif untuk footer adalah “Foot Row” agar dapat diakses.

## Langkah 7: Simpan Dokumen PDF

Sekarang meja sudah siap, waktunya menyimpan karya agung Anda!

```csharp
document.Save(dataDir + "StyleTableRow.pdf");
```

Sama seperti itu, PDF Anda disimpan dengan semua baris tabel cantik yang baru saja kita tata gayanya.

## Langkah 8: Validasi Kepatuhan PDF/UA

Untuk memastikan PDF kami mematuhi standar aksesibilitas, kami akan memvalidasinya untuk kepatuhan PDF/UA.

```csharp
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

Ini memastikan bahwa PDF Anda memenuhi standar PDF/UA, sehingga dapat diakses oleh semua orang. Aksesibilitas adalah tujuan utama!

## Kesimpulan

Nah, itu dia! Hanya dengan beberapa baris kode, Anda telah membuat tabel bergaya lengkap dalam format PDF menggunakan Aspose.PDF for .NET. Dari header hingga footer, kami telah menata setiap baris, menambahkan elemen aksesibilitas, dan bahkan memvalidasi dokumen untuk memastikan kepatuhan. Baik Anda sedang mengerjakan laporan perusahaan, presentasi, atau sekadar bersenang-senang dengan PDF, panduan ini akan membantu Anda. Sekarang, lanjutkan dan mulailah menata tabel Anda seperti seorang profesional!

## Pertanyaan yang Sering Diajukan

### Bisakah saya mengubah gaya font tabel juga?  
 Ya! Anda dapat mengubah gaya font menggunakan`TextState` objek untuk setiap sel, memungkinkan penyesuaian penuh.

### Bagaimana cara menambahkan lebih banyak kolom ke tabel saya?  
 Sesuaikan saja`colCount`variabel dan menambahkan lebih banyak sel dalam loop untuk header, body, dan footer.

### Apa yang terjadi jika saya tidak mengatur tinggi baris?  
Jika Anda tidak mengatur tinggi baris, tabel akan otomatis menyesuaikan berdasarkan konten.

### Dapatkah saya menggunakan ini untuk jumlah baris yang dinamis?  
Tentu saja! Anda dapat mengambil data dari database atau sumber lain dan menyesuaikan jumlah baris dan kolom secara dinamis.

### Apakah Aspose.PDF untuk .NET gratis untuk digunakan?  
 Aspose.PDF untuk .NET adalah produk berlisensi, tetapi Anda dapat mencobanya dengan[uji coba gratis](https://releases.aspose.com/) atau dapatkan[lisensi sementara](https://purchase.aspose.com/temporary-license/).