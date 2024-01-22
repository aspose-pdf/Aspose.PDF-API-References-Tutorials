---
title: Elemen Tabel Gaya
linktitle: Elemen Tabel Gaya
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara memformat elemen tabel dengan Aspose.PDF untuk .NET. Panduan langkah demi langkah untuk menyesuaikan gaya dan properti.
type: docs
weight: 170
url: /id/net/programming-with-tagged-pdf/style-table-element/
---
Dalam tutorial mendetail ini, kami akan memandu Anda melalui kode sumber C# yang disediakan selangkah demi selangkah untuk memformat elemen array menggunakan Aspose.PDF untuk .NET. Ikuti instruksi di bawah ini untuk memahami cara menyesuaikan gaya dan properti elemen array.

## Langkah 1: Menyiapkan lingkungan

Sebelum memulai, pastikan Anda telah mengonfigurasi lingkungan pengembangan untuk menggunakan Aspose.PDF untuk .NET. Ini termasuk menginstal perpustakaan Aspose.PDF dan mengonfigurasi proyek Anda untuk mereferensikannya.

## Langkah 2: Membuat dokumen

Pada langkah ini, kita akan membuat objek dokumen baru Aspose.PDF.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Pembuatan dokumen
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of table formatting");
taggedContent.SetLanguage("fr-FR");
```

Kami telah membuat dokumen baru dan mengatur judul dan bahasa dokumen.

## Langkah 3: Mendapatkan elemen struktur root

Pada langkah ini kita akan mendapatkan elemen struktur root untuk dokumen kita.

```csharp
//Dapatkan elemen struktur akar
StructureElement rootElement = taggedContent.RootElement;
```

Kami mendapat elemen struktur root yang akan berfungsi sebagai wadah untuk elemen array.

## Langkah 4: Membuat elemen struktur array

Sekarang mari buat elemen struktur tabel baru untuk dokumen kita.

```csharp
// Buat elemen struktur array
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

Kami telah membuat elemen struktur array baru dan menambahkannya ke elemen struktur root.

## Langkah 5: Menyesuaikan Gaya dan Properti Elemen Array

Pada langkah ini, kita akan menyesuaikan gaya dan properti elemen array.

```csharp
// Sesuaikan gaya dan properti elemen array
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement. Alignment = HorizontalAlignment. Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement. ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement. DefaultColumnWidth = "70";
tableElement. IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement. Left = 0F;
tableElement. Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;

// Sesuaikan gaya garis berulang
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

Kami menggunakan berbagai properti untuk menyesuaikan elemen tabel, seperti warna latar belakang, batas, perataan, gaya sel default, margin, lebar kolom, dll.

## Langkah 6: Tambahkan header, body, dan footer tabel

Sekarang mari tambahkan header tabel, isi dan footer ke elemen tabel.
```csharp
// Tambahkan header tabel
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// Jumlah baris dan kolom dalam tabel
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;

// Buat baris header tabel
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
}

//Tambahkan baris badan tabel
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// Tambahkan garis pijakan tabel
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Kami menambahkan baris header, baris isi, dan footer ke tabel menggunakan elemen yang sesuai.

## Langkah 7: Menyimpan dokumen PDF yang diberi tag

Sekarang kita telah membuat dokumen kita dengan elemen tabel bergaya, kita akan menyimpannya sebagai dokumen PDF yang diberi tag.

```csharp
// Simpan dokumen PDF yang diberi tag
document.Save(dataDir + "StyleTableElement.pdf");
```

Kami menyimpan dokumen PDF yang diberi tag di direktori yang ditentukan.

## Langkah 8: Validasi kepatuhan PDF/UA

Selanjutnya, kami akan memvalidasi kesesuaian PDF/UA dokumen kami.

```csharp
// Pemeriksaan kepatuhan PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Kami mengunggah dokumen PDF yang diberi tag dan memvalidasi kepatuhan PDF/UA dengan membuat laporan XML.

### Contoh kode sumber untuk Elemen Tabel Gaya menggunakan Aspose.PDF untuk .NET 

```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat dokumen
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");

// Dapatkan elemen struktur akar
StructureElement rootElement = taggedContent.RootElement;

// Buat elemen struktur tabel
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement.DefaultColumnWidth = "70";
tableElement.IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement.Left = 0F;
tableElement.Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
}

// Simpan Dokumen Pdf yang Ditandai
document.Save(dataDir + "StyleTableElement.pdf");

// Memeriksa kepatuhan PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara memformat elemen array dengan Aspose.PDF untuk .NET. Kami menyesuaikan gaya dan properti elemen tabel, menambahkan header, baris isi, dan footer, menyimpan dokumen PDF yang diberi tag, dan memvalidasi kepatuhan PDF/UA-nya.

### FAQ

#### T: Apa tujuan tutorial tentang memformat elemen array menggunakan Aspose.PDF untuk .NET?

J: Tujuan tutorial ini adalah memandu Anda melalui proses pemformatan elemen array dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Ini memberikan petunjuk langkah demi langkah dan contoh kode sumber C# untuk membantu Anda menyesuaikan gaya dan properti elemen array.

#### Q: Apa saja prasyarat untuk mengikuti tutorial ini?

J: Sebelum memulai, pastikan Anda telah menyiapkan lingkungan pengembangan untuk menggunakan Aspose.PDF untuk .NET. Ini melibatkan instalasi perpustakaan Aspose.PDF dan mengonfigurasi proyek Anda untuk mereferensikannya.

#### T: Bagaimana cara membuat dokumen PDF baru dan mengatur judul serta bahasanya menggunakan Aspose.PDF untuk .NET?

 J: Untuk membuat dokumen PDF baru, Anda perlu membuat a`Document` objek dari perpustakaan Aspose.PDF. Kode sumber C# yang disediakan dalam tutorial menunjukkan cara membuat dokumen dan mengatur judul dan properti bahasanya.

#### T: Apa pentingnya elemen struktur akar dalam dokumen PDF?

J: Elemen struktur akar bertindak sebagai wadah bagi elemen struktur lainnya, membantu mengatur dan mengkategorikan konten dokumen PDF. Ini memainkan peran penting dalam membangun struktur logis dokumen.

#### T: Bagaimana cara membuat dan mengkustomisasi elemen struktur array menggunakan Aspose.PDF untuk .NET?

 A: Anda dapat membuat elemen struktur array menggunakan`CreateTableElement()` metode. Kode sumber tutorial memberikan contoh penyesuaian berbagai properti elemen tabel, seperti warna latar belakang, batas, perataan, lebar kolom, dan banyak lagi.

#### T: Bisakah saya mengkustomisasi gaya dan properti sel tabel dalam elemen array?

J: Ya, tutorial ini mencakup cara menyesuaikan gaya dan properti seluruh elemen tabel, termasuk header, baris isi, dan footer. Namun, ini tidak secara khusus membahas penyesuaian sel tabel individual.

#### T: Bagaimana cara menambahkan header, baris isi, dan footer ke elemen tabel?

J: Tutorial ini menjelaskan cara membuat dan menambahkan header, baris isi, dan footer ke elemen tabel menggunakan metode yang sesuai yang disediakan oleh Aspose.PDF untuk .NET.

#### T: Apa yang dimaksud dengan kepatuhan PDF/UA, dan bagaimana cara memvalidasinya untuk dokumen PDF saya yang diberi tag?

 J: Kepatuhan PDF/UA memastikan bahwa dokumen PDF mematuhi standar aksesibilitas, sehingga lebih mudah diakses oleh pengguna penyandang disabilitas. Tutorial ini menunjukkan cara memvalidasi kesesuaian PDF/UA menggunakan`Validate()` metode dan menghasilkan laporan kepatuhan XML.

#### T: Bagaimana cara memasukkan konsep ini ke dalam aplikasi .NET saya sendiri?

J: Anda dapat menggunakan contoh kode sumber C# yang disediakan sebagai panduan untuk mengimplementasikan pemformatan elemen array di aplikasi .NET Anda sendiri. Ubah dan sesuaikan kode agar sesuai dengan kebutuhan Anda dan integrasikan ke dalam proyek Anda.

#### T: Apakah ada praktik terbaik yang direkomendasikan untuk memformat elemen array dalam dokumen PDF?

J: Saat memformat elemen array (tabel), pertimbangkan keterbacaan dan aksesibilitas konten. Gunakan font yang jelas dan mudah dibaca, warna yang sesuai, dan pertahankan tata letak yang konsisten. Validasi kepatuhan PDF/UA untuk memastikan standar aksesibilitas terpenuhi.

#### T: Apa saja fitur Aspose.PDF untuk .NET lainnya yang dapat saya jelajahi untuk kustomisasi dokumen PDF?

J: Aspose.PDF untuk .NET menawarkan serangkaian fitur untuk penyesuaian dokumen PDF, termasuk manipulasi teks, penyisipan gambar, manajemen bidang formulir, tanda tangan digital, anotasi, dan banyak lagi. Lihat dokumentasi dan sumber daya resmi untuk menjelajahi fungsi tambahan.