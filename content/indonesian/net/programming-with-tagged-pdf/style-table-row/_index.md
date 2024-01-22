---
title: Baris Tabel Gaya
linktitle: Baris Tabel Gaya
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara mengkustomisasi baris tabel dengan Aspose.PDF untuk .NET panduan langkah demi langkah untuk menata gaya dan memformat baris.
type: docs
weight: 180
url: /id/net/programming-with-tagged-pdf/style-table-row/
---
Dalam tutorial mendetail ini, kami akan memandu Anda melalui kode sumber C# yang disediakan langkah demi langkah untuk memformat baris tabel menggunakan Aspose.PDF untuk .NET. Ikuti instruksi di bawah ini untuk memahami cara menyesuaikan gaya dan properti baris tabel.

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
taggedContent.SetTitle("Example of Table Row Formatting");
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

## Langkah 5: Sesuaikan gaya dan properti baris tabel

Pada langkah ini, kita akan menyesuaikan gaya dan properti baris tabel.

```csharp
// Sesuaikan gaya dan properti baris tabel
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

int rowCount = 7;
int colCount = 3;
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

// Sesuaikan baris badan tabel
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);
     trElement.BackgroundColor = Color.LightGoldenrodYellow;
     trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
     trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
     trElement.MinRowHeight = 100.0;
     trElement.FixedRowHeight = 120.0;
     trElement. IsInNewPage = (rowIndex % 3 == 1);
     trElement.IsRowBroken = true;
     TextState cellTextState = new TextState();
     cellTextState.ForegroundColor = Color.Red;
     trElement. DefaultCellTextState = cellTextState;
     trElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     trElement.VerticalAlignment = VerticalAlignment.Bottom;

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// Buat garis footer tabel
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Kami telah menyesuaikan berbagai aspek baris tabel, seperti warna latar belakang, batas, tinggi baris, penomoran halaman, gaya sel default, dan banyak lagi.

## Langkah 6: Menyimpan dokumen PDF yang diberi tag

Sekarang kita telah membuat dokumen kita dengan baris tabel yang diberi gaya, kita akan menyimpannya sebagai dokumen PDF yang diberi tag.
```csharp
// Simpan dokumen PDF yang diberi tag
document.Save(dataDir + "StyleTableRow.pdf");
```

Kami menyimpan dokumen PDF yang diberi tag di direktori yang ditentukan.

## Langkah 7: Validasi kepatuhan PDF/UA

Selanjutnya, kami akan memvalidasi kesesuaian PDF/UA dokumen kami.

```csharp
// Pemeriksaan kepatuhan PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Kami mengunggah dokumen PDF yang diberi tag dan memvalidasi kepatuhan PDF/UA dengan membuat laporan XML.


### Contoh kode sumber untuk Style Table Row menggunakan Aspose.PDF untuk .NET 
```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat dokumen
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");

// Dapatkan elemen struktur akar
StructureElement rootElement = taggedContent.RootElement;

// Buat elemen struktur tabel
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 7;
int colCount = 3;
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
	trElement.BackgroundColor = Color.LightGoldenrodYellow;
	trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
	trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
	trElement.MinRowHeight = 100.0;
	trElement.FixedRowHeight = 120.0;
	trElement.IsInNewPage = (rowIndex % 3 == 1);
	trElement.IsRowBroken = true;
	TextState cellTextState = new TextState();
	cellTextState.ForegroundColor = Color.Red;
	trElement.DefaultCellTextState = cellTextState;
	trElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	trElement.VerticalAlignment = VerticalAlignment.Bottom;
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
document.Save(dataDir + "StyleTableRow.pdf");

// Memeriksa kepatuhan PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara memformat baris tabel dengan Aspose.PDF untuk .NET. Kami menyesuaikan gaya dan properti baris tabel, menambahkan header, baris isi, dan footer, menyimpan dokumen PDF yang diberi tag, dan memvalidasi kepatuhan PDF/UA-nya.

### FAQ

#### T: Apa tujuan tutorial tentang memformat baris tabel menggunakan Aspose.PDF untuk .NET?

J: Tujuan tutorial ini adalah memandu Anda melalui proses pemformatan baris tabel dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Ini memberikan petunjuk langkah demi langkah dan contoh kode sumber C# untuk membantu Anda menyesuaikan gaya dan properti baris tabel.

#### Q: Apa saja prasyarat untuk mengikuti tutorial ini?

J: Sebelum memulai, pastikan Anda telah menyiapkan lingkungan pengembangan untuk menggunakan Aspose.PDF untuk .NET. Ini melibatkan instalasi perpustakaan Aspose.PDF dan mengonfigurasi proyek Anda untuk mereferensikannya.

#### T: Bagaimana cara membuat dokumen PDF baru dan mengatur judul serta bahasanya menggunakan Aspose.PDF untuk .NET?

 J: Untuk membuat dokumen PDF baru, Anda perlu membuat a`Document` objek dari perpustakaan Aspose.PDF. Kode sumber C# yang disediakan dalam tutorial menunjukkan cara membuat dokumen dan mengatur judul dan properti bahasanya.

#### T: Apa pentingnya elemen struktur akar dalam dokumen PDF?

J: Elemen struktur akar bertindak sebagai wadah bagi elemen struktur lainnya, membantu mengatur dan mengkategorikan konten dokumen PDF. Ini memainkan peran penting dalam membangun struktur logis dokumen.

#### T: Bagaimana cara membuat dan mengkustomisasi elemen struktur tabel untuk memformat baris tabel menggunakan Aspose.PDF untuk .NET?

A: Tutorial ini menjelaskan cara membuat elemen struktur tabel dan menyesuaikan propertinya untuk memformat baris tabel. Ini mencakup aspek-aspek seperti warna latar belakang, batas, tinggi baris, penomoran halaman, gaya sel default, dan banyak lagi.

#### T: Dapatkah saya mengkustomisasi gaya dan properti sel individual dalam baris tabel?

J: Ya, Anda bisa mengkustomisasi gaya dan properti sel individual dalam baris tabel. Tutorial ini menunjukkan cara mengatur properti seperti warna latar belakang, batas, warna teks, padding, dan lainnya untuk sel tabel dalam baris tabel yang diformat.

#### T: Bagaimana cara menambahkan header, baris isi, dan footer ke baris tabel yang diformat?

A: Tutorial memberikan contoh membuat dan menambahkan header, baris isi, dan footer ke elemen struktur tabel. Elemen-elemen ini dapat dikustomisasi lebih lanjut menggunakan properti yang dijelaskan dalam tutorial.

#### T: Apa yang dimaksud dengan kepatuhan PDF/UA, dan bagaimana cara memvalidasinya untuk dokumen PDF saya yang diberi tag?

 J: Kepatuhan PDF/UA memastikan bahwa dokumen PDF mematuhi standar aksesibilitas, sehingga lebih mudah diakses oleh pengguna penyandang disabilitas. Tutorial ini menunjukkan cara memvalidasi kesesuaian PDF/UA menggunakan`Validate()` metode dan menghasilkan laporan kepatuhan XML.

#### T: Bagaimana cara memasukkan konsep ini ke dalam aplikasi .NET saya sendiri?

J: Anda dapat menggunakan contoh kode sumber C# yang disediakan sebagai panduan untuk mengimplementasikan pemformatan baris tabel di aplikasi .NET Anda sendiri. Ubah dan sesuaikan kode agar sesuai dengan kebutuhan Anda dan integrasikan ke dalam proyek Anda.

#### T: Apakah ada rekomendasi praktik terbaik untuk memformat baris tabel dalam dokumen PDF?

J: Saat memformat baris tabel, pertimbangkan keterbacaan dan aksesibilitas konten. Pastikan warna memiliki kontras yang cukup, gunakan font yang jelas dan terbaca, dan pertahankan tata letak yang konsisten. Validasi kepatuhan PDF/UA untuk memastikan standar aksesibilitas terpenuhi.

#### T: Apa saja fitur Aspose.PDF untuk .NET lainnya yang dapat saya jelajahi untuk kustomisasi dokumen PDF?

J: Aspose.PDF untuk .NET menawarkan berbagai fitur untuk penyesuaian dokumen PDF, termasuk manipulasi teks, penyisipan gambar, manajemen bidang formulir, tanda tangan digital, anotasi, dan banyak lagi. Lihat dokumentasi dan sumber daya resmi untuk menjelajahi fungsi tambahan.