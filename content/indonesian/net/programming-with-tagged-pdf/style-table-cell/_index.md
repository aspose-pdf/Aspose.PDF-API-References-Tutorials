---
title: Gaya Tabel Sel
linktitle: Gaya Tabel Sel
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menata sel tabel dengan Aspose.PDF untuk .NET. Panduan langkah demi langkah untuk membuat dan menyesuaikan tabel.
type: docs
weight: 160
url: /id/net/programming-with-tagged-pdf/style-table-cell/
---
Selamat datang di tutorial terperinci tentang pemformatan sel tabel menggunakan Aspose.PDF untuk .NET. Dalam panduan ini, kami akan menjelaskan secara terperinci setiap langkah dari kode sumber C# yang disediakan untuk membantu Anda memahami cara memberi gaya pada sel tabel. Pastikan Anda telah menginstal Aspose.PDF untuk .NET dan menyiapkan lingkungan pengembangan Anda sebelum memulai.

## Langkah 1: Menyiapkan lingkungan

Sebelum memulai, pastikan Anda telah mengonfigurasi lingkungan pengembangan Anda untuk menggunakan Aspose.PDF untuk .NET. Ini termasuk menginstal pustaka Aspose.PDF dan mengonfigurasi proyek Anda untuk merujuknya.

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

Kami telah membuat dokumen baru dan menetapkan judul dan bahasa dokumen.

## Langkah 3: Mendapatkan elemen struktur akar

Pada langkah ini kita akan mendapatkan elemen struktur akar untuk dokumen kita.

```csharp
// Dapatkan elemen struktur akar
StructureElement rootElement = taggedContent.RootElement;
```

Kita mendapat elemen struktur akar yang akan berfungsi sebagai wadah bagi elemen-elemen array.

## Langkah 4: Membuat elemen struktur array

Sekarang mari membuat elemen struktur tabel baru untuk dokumen kita.

```csharp
// Membuat elemen struktur array
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Kami telah membuat elemen struktur array baru dan menambahkannya ke elemen struktur root. Kami juga membuat elemen header, body, dan footer tabel.

## Langkah 5: Menambahkan header tabel

Pada langkah ini kita akan menambahkan tajuk tabel ke dalam tabel kita.

```csharp
// Jumlah baris dan kolom dalam tabel
int rowCount = 4;
int colCount = 4;

int rowIndex;
int colIndex;

// Membuat baris tajuk tabel
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

Kami menambahkan baris ke badan tabel menggunakan loop untuk mengulangi setiap sel tabel. Kami menetapkan properti pemformatan untuk setiap sel, seperti warna latar belakang, batas, margin, perataan teks, dll.

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

Sekarang setelah kita membuat dokumen dengan tabel bergaya, kita akan menyimpannya sebagai dokumen PDF yang diberi tag.

```csharp
// Simpan dokumen PDF yang diberi tag
document.Save(dataDir + "StyleTableCell.pdf");
```

Kami menyimpan dokumen PDF yang diberi tag pada direktori yang ditentukan.

## Langkah 9: Validasi kepatuhan PDF/UA

Berikutnya, kami akan memvalidasi kesesuaian PDF/UA dokumen kami.

```csharp
// Pemeriksaan kepatuhan PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Kami mengunggah dokumen PDF yang diberi tag dan memvalidasi kepatuhan PDF/UA-nya dengan membuat laporan XML.

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

Dalam tutorial ini, kita mempelajari cara memberi gaya pada sel tabel menggunakan Aspose.PDF untuk .NET. Kita telah melihat cara membuat dokumen, menambahkan tabel dengan tajuk, baris isi, dan catatan kaki, serta menyesuaikan gaya sel. Terakhir, kita menyimpan dokumen PDF yang diberi tag dan memvalidasi kepatuhan PDF/UA-nya. Kini Anda dapat menggunakan Aspose.PDF untuk .NET guna membuat dan memberi gaya pada tabel di aplikasi .NET Anda.

### Pertanyaan yang Sering Diajukan

#### T: Apa tujuan tutorial memformat sel tabel menggunakan Aspose.PDF untuk .NET ini?

J: Tutorial ini bertujuan untuk memberikan panduan lengkap tentang cara menata sel tabel dalam dokumen PDF menggunakan pustaka Aspose.PDF untuk .NET. Tutorial ini mencakup petunjuk langkah demi langkah dan contoh kode sumber C# untuk membantu Anda memahami dan menerapkan pemformatan sel tabel.

#### T: Apa saja prasyarat untuk mengikuti tutorial ini?

J: Sebelum memulai, pastikan Anda telah menginstal Aspose.PDF untuk .NET dan telah menyiapkan lingkungan pengembangan Anda. Ini termasuk mengonfigurasi proyek Anda untuk merujuk ke pustaka Aspose.PDF.

#### T: Bagaimana cara membuat dokumen PDF baru menggunakan Aspose.PDF untuk .NET?

 A: Untuk membuat dokumen PDF baru, Anda perlu membuat instance`Document` objek dari pustaka Aspose.PDF. Kode sumber C# yang disediakan menunjukkan cara membuat dokumen dan mengatur judul serta bahasanya.

#### T: Apa pentingnya elemen struktur akar dalam dokumen PDF?

A: Elemen struktur akar berfungsi sebagai wadah bagi elemen struktur lainnya, membantu mengatur dan mengkategorikan konten dokumen PDF. Elemen ini berperan penting dalam membangun struktur logis dokumen.

#### T: Bagaimana cara membuat elemen struktur tabel dan menyesuaikan tampilannya menggunakan Aspose.PDF untuk .NET?

 A: Anda dapat membuat elemen struktur tabel menggunakan`CreateTableElement()` metode. Kode sumber yang diberikan menunjukkan cara menyesuaikan tampilan tabel, termasuk header, body, dan footer, dengan mengatur properti seperti warna latar belakang, border, margin, dan alignment.

#### T: Dapatkah saya menambahkan beberapa baris dan kolom ke badan tabel dan menyesuaikan formatnya?

A: Ya, tutorial ini menunjukkan cara menambahkan beberapa baris dan kolom ke badan tabel menggunakan loop. Tutorial ini juga menyediakan contoh penyesuaian format sel, seperti warna latar belakang, batas, perataan teks, gaya font, dan banyak lagi.

#### T: Apa tujuan memvalidasi kepatuhan PDF/UA, dan bagaimana saya dapat melakukan validasi ini?

 A: Memvalidasi kepatuhan PDF/UA memastikan bahwa dokumen PDF mematuhi standar aksesibilitas, sehingga lebih mudah diakses oleh pengguna penyandang disabilitas. Tutorial ini menunjukkan cara memvalidasi kesesuaian PDF/UA menggunakan`Validate()` metode dan menghasilkan laporan XML.

#### T: Bagaimana saya dapat menerapkan konsep ini ke aplikasi .NET saya sendiri?

J: Anda dapat menggunakan contoh kode sumber C# yang disediakan sebagai panduan untuk menerapkan pemformatan sel tabel di aplikasi .NET Anda sendiri. Sesuaikan kode sesuai kebutuhan agar sesuai dengan persyaratan Anda dan integrasikan ke dalam proyek Anda.

#### T: Apakah ada praktik terbaik yang direkomendasikan untuk menata gaya sel tabel dalam dokumen PDF?

J: Saat menata sel tabel, pertimbangkan kebutuhan audiens Anda, termasuk persyaratan aksesibilitas. Gunakan warna yang kontras, font yang sesuai, dan perataan sel yang jelas untuk meningkatkan keterbacaan. Selain itu, validasi kepatuhan PDF/UA untuk memastikan standar aksesibilitas terpenuhi.

#### T: Fitur Aspose.PDF for .NET apa lagi yang dapat saya jelajahi untuk manipulasi dokumen PDF?

J: Aspose.PDF untuk .NET menawarkan berbagai fitur untuk manipulasi dokumen PDF, termasuk ekstraksi teks, penyisipan gambar, manajemen bidang formulir, tanda tangan digital, dan banyak lagi. Jelajahi dokumentasi dan sumber daya resmi untuk mempelajari tentang fungsi tambahan.
