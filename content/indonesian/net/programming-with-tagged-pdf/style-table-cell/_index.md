---
title: Sel Tabel Gaya
linktitle: Sel Tabel Gaya
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menata gaya sel tabel dengan Aspose.PDF untuk .NET. Panduan langkah demi langkah untuk membuat dan menyesuaikan tabel.
type: docs
weight: 160
url: /id/net/programming-with-tagged-pdf/style-table-cell/
---
Selamat datang di tutorial mendetail tentang memformat sel tabel menggunakan Aspose.PDF untuk .NET. Dalam panduan ini, kami akan menjelaskan secara detail setiap langkah kode sumber C# yang disediakan untuk membantu Anda memahami cara menata gaya sel tabel. Pastikan Anda telah menginstal Aspose.PDF untuk .NET dan menyiapkan lingkungan pengembangan sebelum memulai.

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
taggedContent.SetTitle("Example of table cell formatting");
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
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Kami telah membuat elemen struktur array baru dan menambahkannya ke elemen struktur root. Kami juga membuat elemen header, body, dan footer tabel.

## Langkah 5: Menambahkan header tabel

Pada langkah ini kita akan menambahkan header tabel ke tabel kita.

```csharp
// Jumlah baris dan kolom dalam tabel
int rowCount = 4;
int colCount = 4;

int rowIndex;
int colIndex;

// Buat baris header tabel
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
     theElement.BackgroundColor = Color.GreenYellow;
     theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
     theElement. IsNoBorder = true;
     theElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     theElement.Alignment = HorizontalAlignment.Right;
}
```

Kami membuat baris header untuk tabel kami dan menambahkan sel header dengan properti pemformatan seperti warna latar belakang, batas, margin, dan perataan.

## Langkah 6: Menambahkan baris isi tabel

Sekarang mari tambahkan baris isi tabel ke tabel kita.
```csharp
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         int colSpan = 1;
         int rowSpan = 1;

         if (colIndex == 1 && rowIndex == 1)
         {
             colSpan = 2;
             rowSpan = 2;
         }
         else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
         {
             keep on going;
         }
         else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
         {
             keep on going;
         }

         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
         tdElement.BackgroundColor = Color.Yellow;
         tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
         tdElement.IsNoBorder = false;
         tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
         tdElement.Alignment = HorizontalAlignment.Center;

         TextState cellTextState = new TextState();
         cellTextState.ForegroundColor = Color.DarkBlue;
         cellTextState.FontSize = 7.5F;
         cellTextState.FontStyle = FontStyles.Bold;
         cellTextState.Font = FontRepository.FindFont("Arial");

         tdElement. DefaultCellTextState = cellTextState;
         tdElement.IsWordWrapped = true;
         tdElement.VerticalAlignment = VerticalAlignment.Center;
         tdElement.ColSpan = colSpan;
         tdElement. RowSpan = rowSpan;
     }
}
```

Kami menambahkan baris ke badan tabel menggunakan loop untuk mengulangi setiap sel tabel. Kami mengatur properti pemformatan untuk setiap sel, seperti warna latar belakang, batas, margin, perataan teks, dll.

## Langkah 7: Menambahkan footer

Terakhir, kita akan menambahkan footer tabel ke tabel kita.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Kami membuat footer untuk tabel kami dan menambahkan sel footer dengan teks.



## Langkah 8: Menyimpan dokumen PDF yang diberi tag

Sekarang kita telah membuat dokumen kita dengan tabel yang diberi gaya, kita akan menyimpannya sebagai dokumen PDF yang diberi tag.

```csharp
// Simpan dokumen PDF yang diberi tag
document.Save(dataDir + "StyleTableCell.pdf");
```

Kami menyimpan dokumen PDF yang diberi tag di direktori yang ditentukan.

## Langkah 9: Validasi kepatuhan PDF/UA

Selanjutnya, kami akan memvalidasi kesesuaian PDF/UA dokumen kami.

```csharp
// Pemeriksaan kepatuhan PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Kami mengunggah dokumen PDF yang diberi tag dan memvalidasi kepatuhan PDF/UA dengan membuat laporan XML.

### Contoh kode sumber untuk Style Table Cell menggunakan Aspose.PDF untuk .NET 
```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat dokumen
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

// Dapatkan elemen struktur akar
StructureElement rootElement = taggedContent.RootElement;

// Buat elemen struktur tabel
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 4;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
	thElement.BackgroundColor = Color.GreenYellow;
	thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
	thElement.IsNoBorder = true;
	thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	thElement.Alignment = HorizontalAlignment.Right;
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		int colSpan = 1;
		int rowSpan = 1;
		if (colIndex == 1 && rowIndex == 1)
		{
			colSpan = 2;
			rowSpan = 2;
		}
		else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
		{
			continue;
		}
		else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
		{
			continue;
		}
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
		tdElement.BackgroundColor = Color.Yellow;
		tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
		tdElement.IsNoBorder = false;
		tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
		tdElement.Alignment = HorizontalAlignment.Center;
		TextState cellTextState = new TextState();
		cellTextState.ForegroundColor = Color.DarkBlue;
		cellTextState.FontSize = 7.5F;
		cellTextState.FontStyle = FontStyles.Bold;
		cellTextState.Font = FontRepository.FindFont("Arial");
		tdElement.DefaultCellTextState = cellTextState;
		tdElement.IsWordWrapped = true;
		tdElement.VerticalAlignment = VerticalAlignment.Center;
		tdElement.ColSpan = colSpan;
		tdElement.RowSpan = rowSpan;
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
document.Save(dataDir + "StyleTableCell.pdf");

// Memeriksa kepatuhan PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara menata gaya sel tabel menggunakan Aspose.PDF untuk .NET. Kita telah melihat cara membuat dokumen, menambahkan tabel dengan header, baris isi, dan footer, serta menyesuaikan gaya sel. Terakhir, kami menyimpan dokumen PDF yang diberi tag dan memvalidasi kepatuhan PDF/UA-nya. Anda sekarang dapat menggunakan Aspose.PDF untuk .NET untuk membuat dan menata tabel di aplikasi .NET Anda.

### FAQ

#### T: Apa tujuan tutorial memformat sel tabel menggunakan Aspose.PDF untuk .NET?

J: Tutorial ini bertujuan untuk memberikan panduan komprehensif tentang cara menata gaya sel tabel dalam dokumen PDF menggunakan perpustakaan Aspose.PDF untuk .NET. Ini mencakup petunjuk langkah demi langkah dan contoh kode sumber C# untuk membantu Anda memahami dan menerapkan pemformatan sel tabel.

#### Q: Apa saja prasyarat untuk mengikuti tutorial ini?

J: Sebelum memulai, pastikan Anda telah menginstal Aspose.PDF untuk .NET dan telah menyiapkan lingkungan pengembangan Anda. Ini termasuk mengonfigurasi proyek Anda untuk mereferensikan pustaka Aspose.PDF.

#### T: Bagaimana cara membuat dokumen PDF baru menggunakan Aspose.PDF untuk .NET?

J: Untuk membuat dokumen PDF baru, Anda perlu membuat instance a`Document` objek dari perpustakaan Aspose.PDF. Kode sumber C# yang disediakan menunjukkan cara membuat dokumen dan mengatur judul dan bahasanya.

#### T: Apa pentingnya elemen struktur akar dalam dokumen PDF?

J: Elemen struktur akar berfungsi sebagai wadah bagi elemen struktur lainnya, membantu mengatur dan mengkategorikan konten dokumen PDF. Ini memainkan peran penting dalam membangun struktur logis dokumen.

#### T: Bagaimana cara membuat elemen struktur tabel dan mengkustomisasi tampilannya menggunakan Aspose.PDF untuk .NET?

 A: Anda dapat membuat elemen struktur tabel menggunakan`CreateTableElement()` metode. Kode sumber yang disediakan menunjukkan cara menyesuaikan tampilan tabel, termasuk header, body, dan footer, dengan mengatur properti seperti warna latar belakang, batas, margin, dan perataan.

#### T: Dapatkah saya menambahkan beberapa baris dan kolom ke badan tabel dan menyesuaikan formatnya?

J: Ya, tutorial ini menunjukkan cara menambahkan beberapa baris dan kolom ke badan tabel menggunakan loop. Ini juga memberikan contoh penyesuaian pemformatan sel, seperti warna latar belakang, batas, perataan teks, gaya font, dan banyak lagi.

#### T: Apa tujuan memvalidasi kepatuhan PDF/UA, dan bagaimana cara melakukan validasi ini?

 J: Memvalidasi kepatuhan PDF/UA memastikan bahwa dokumen PDF mematuhi standar aksesibilitas, sehingga lebih mudah diakses oleh pengguna penyandang disabilitas. Tutorial ini menunjukkan cara memvalidasi kesesuaian PDF/UA menggunakan`Validate()` metode dan menghasilkan laporan XML.

#### T: Bagaimana cara menerapkan konsep ini pada aplikasi .NET saya sendiri?

J: Anda dapat menggunakan contoh kode sumber C# yang disediakan sebagai panduan untuk mengimplementasikan pemformatan sel tabel di aplikasi .NET Anda sendiri. Sesuaikan kode seperlunya agar sesuai dengan kebutuhan Anda dan integrasikan ke dalam proyek Anda.

#### T: Apakah ada rekomendasi praktik terbaik untuk menata gaya sel tabel di dokumen PDF?

J: Saat menata gaya sel tabel, pertimbangkan kebutuhan audiens Anda, termasuk persyaratan aksesibilitas. Gunakan warna kontras, font yang sesuai, dan perataan sel yang jelas untuk meningkatkan keterbacaan. Selain itu, validasi kepatuhan PDF/UA untuk memastikan standar aksesibilitas terpenuhi.

#### T: Fitur Aspose.PDF untuk .NET apa lagi yang dapat saya jelajahi untuk manipulasi dokumen PDF?

J: Aspose.PDF untuk .NET menawarkan berbagai fitur untuk manipulasi dokumen PDF, termasuk ekstraksi teks, penyisipan gambar, manajemen bidang formulir, tanda tangan digital, dan banyak lagi. Jelajahi dokumentasi dan sumber daya resmi untuk mempelajari tentang fungsi tambahan.
