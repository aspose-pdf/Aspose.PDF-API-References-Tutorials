---
title: Buat Elemen Tabel
linktitle: Buat Elemen Tabel
second_title: Referensi API Aspose.PDF untuk .NET
description: Panduan langkah demi langkah untuk membuat elemen array dengan Aspose.PDF untuk .NET. Hasilkan PDF dinamis dengan tabel dengan mudah.
type: docs
weight: 80
url: /id/net/programming-with-tagged-pdf/create-table-element/
---
Dalam panduan langkah demi langkah ini, kami akan memandu Anda melalui proses pembuatan elemen array menggunakan Aspose.PDF untuk .NET. Aspose.PDF adalah pustaka canggih yang memungkinkan Anda memanipulasi dokumen PDF secara terprogram. Pembuatan elemen array merupakan persyaratan umum saat membuat PDF dinamis, dan Aspose.PDF menawarkan cara mudah dan efisien untuk mencapainya.

Mari selami kode dan pelajari cara membuat elemen array menggunakan Aspose.PDF untuk .NET.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

1. Pustaka Aspose.PDF untuk .NET terpasang.
2. Pengetahuan dasar tentang bahasa pemrograman C#.

## Langkah 1: Menyiapkan lingkungan

Untuk memulai, buka lingkungan pengembangan C# Anda dan buat proyek baru. Pastikan Anda telah menambahkan referensi ke pustaka Aspose.PDF untuk .NET dalam proyek Anda.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Membuat dokumen

 Langkah pertama adalah membuat dokumen PDF baru menggunakan`Document` kelas.

```csharp
// Buat dokumen
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Array");
taggedContent.SetLanguage("fr-FR");
```

Di sini kami juga mengatur judul dan bahasa untuk konten yang diberi tag.

## Langkah 3: Membuat elemen array

Selanjutnya, kita perlu membuat elemen array dan menambahkannya ke dokumen. Kita mulai dengan mendapatkan elemen struktur root, lalu kita membuat elemen tabel baru menggunakan`CreateTableElement` metode.

```csharp
// Dapatkan elemen struktur akar
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";
headTrElement.BackgroundColor = Color.LightGray;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTHElement theElement = headTrElement.CreateTH();
thElement.SetText(String.Format("Header {0}", colIndex));
theElement.BackgroundColor = Color.GreenYellow;
theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
theElement. IsNoBorder = true;
theElement.Margin = new MarginInfo(16.0, 2

.0, 8.0, 2.0);
theElement.Alignment = HorizontalAlignment.Right;
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
keep on going;
}
else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
{
keep on going;
}
TableTDElement tdelement = trElement.CreateTD();
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
tdElement. DefaultCellTextState = cellTextState;
tdElement.IsWordWrapped = true;
tdElement.VerticalAlignment = VerticalAlignment.Center;
tdElement.ColSpan = colSpan;
tdElement. RowSpan = rowSpan;
}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTDElement tdElement = footTrElement.CreateTD();
tdElement.SetText(String.Format("Foot {0}", colIndex));
tdElement.Alignment = HorizontalAlignment.Center;
tdElement.StructureTextState.FontSize = 7F;
tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for the table");
tableAttributes.SetAttribute(summaryAttribute);

// Simpan dokumen PDF yang diberi tag
document.Save(dataDir + "CreateTableElement.pdf");

// Pemeriksaan kepatuhan PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

### Contoh kode sumber untuk Membuat Elemen Tabel menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat dokumen
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table");
taggedContent.SetLanguage("en-US");

// Dapatkan elemen struktur akar
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
headTrElement.BackgroundColor = Color.LightGray;
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
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
	tdElement.Alignment = HorizontalAlignment.Center;
	tdElement.StructureTextState.FontSize = 7F;
	tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for table");
tableAttributes.SetAttribute(summaryAttribute);

// Simpan Dokumen Pdf yang Ditandai
document.Save(dataDir + "CreateTableElement.pdf");

// Memeriksa kepatuhan PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Kesimpulan

Anda telah mempelajari cara membuat elemen array menggunakan Aspose.PDF untuk .NET. Kini Anda dapat membuat dokumen PDF dengan tabel dinamis menggunakan metode ini. Jangan ragu untuk menjelajahi lebih banyak fitur Aspose.PDF untuk menemukan potensinya secara penuh.

### Pertanyaan yang Sering Diajukan

#### T: Apa itu elemen array dalam dokumen PDF, dan mengapa saya perlu membuatnya menggunakan Aspose.PDF untuk .NET?

A: Elemen array dalam dokumen PDF merupakan kumpulan data terstruktur, yang sering digunakan untuk membuat tabel atau kisi. Anda mungkin perlu membuat elemen array menggunakan Aspose.PDF for .NET saat membuat PDF dinamis yang memerlukan presentasi data terstruktur, seperti informasi tabular atau kisi.

#### T: Bagaimana Aspose.PDF untuk .NET menyederhanakan proses pembuatan elemen array?

J: Aspose.PDF untuk .NET menyediakan serangkaian kelas dan metode komprehensif yang memungkinkan Anda membuat, menyesuaikan, dan mengelola elemen array (tabel) dalam dokumen PDF secara terprogram. Ini menghilangkan kebutuhan untuk manipulasi PDF secara manual dan menyederhanakan pembuatan representasi data terstruktur.

#### T: Apa saja langkah utama yang terlibat dalam pembuatan elemen array menggunakan Aspose.PDF untuk .NET?

A: Langkah-langkah utamanya meliputi menyiapkan lingkungan, membuat dokumen, memperoleh elemen struktur akar, membuat elemen tabel, menentukan baris dan sel dalam tabel, serta menentukan format dan properti untuk elemen-elemen tersebut. Contoh kode yang diberikan menunjukkan langkah-langkah ini.

####  T: Apa peran`taggedContent` object play in creating an array element?

 Sebuah:`taggedContent` objek, diperoleh dari dokumen`TaggedContent`properti, memungkinkan Anda menentukan struktur konten yang diberi tag dalam dokumen PDF. Ini termasuk membuat dan mengatur elemen array dan elemen turunannya secara hierarkis.

#### T: Bagaimana kode memastikan aksesibilitas dan semantik elemen array yang dibuat?

 A: Kode tersebut menetapkan atribut seperti`AlternativeText`, `BackgroundColor`, `Border`, `Margin`, `Alignment` , Dan`ColSpan` untuk meningkatkan aksesibilitas dan semantik elemen array. Atribut ini berkontribusi pada representasi data yang terstruktur dengan baik, informatif, dan menarik secara visual.

#### T: Apa pentingnya kepatuhan PDF/UA dalam konteks pembuatan elemen array?

 A: Kepatuhan PDF/UA (Aksesibilitas Universal) memastikan bahwa dokumen PDF yang dihasilkan dapat diakses oleh pengguna penyandang disabilitas dan memenuhi standar aksesibilitas tertentu. Contoh kode memeriksa kepatuhan PDF/UA menggunakan`Validate` metode yang membantu Anda membuat dokumen yang inklusif dan mudah diakses.

#### T: Dapatkah saya menyesuaikan format dan tampilan elemen array lebih lanjut?

A: Ya, Anda dapat menyesuaikan format dan tampilan elemen array dengan menyesuaikan atribut seperti warna latar belakang, gaya border, ukuran font, dan perataan. Aspose.PDF untuk .NET menyediakan berbagai properti untuk menyesuaikan tampilan visual dengan kebutuhan Anda.

#### T: Bagaimana saya dapat memperluas pengetahuan ini untuk membuat struktur tabel yang lebih kompleks atau menggabungkan elemen array ke dalam dokumen PDF yang lebih besar?

J: Anda dapat memperluas pengetahuan ini dengan menjelajahi fitur-fitur tambahan Aspose.PDF untuk .NET, seperti menggabungkan beberapa elemen array, membuat tabel bertingkat, menambahkan header dan footer, dan mengintegrasikan elemen-elemen array ke dalam tata letak PDF yang lebih besar. Dokumentasi dan contoh pustaka menyediakan panduan untuk skenario-skenario lanjutan ini.

#### T: Apakah mungkin untuk mengimpor data dari sumber eksternal, seperti basis data atau lembar kerja, untuk mengisi elemen array?

A: Ya, Anda dapat mengimpor data dari sumber eksternal untuk mengisi elemen array. Anda dapat menggunakan teknik pengambilan dan transformasi data dalam C# untuk mengambil data dari basis data, spreadsheet, atau sumber lain, lalu mengisi elemen array sebagaimana mestinya.

#### T: Bagaimana saya dapat menggunakan pengetahuan yang diperoleh dari tutorial ini untuk meningkatkan kualitas dan kegunaan dokumen PDF yang saya buat secara terprogram?

A: Pengetahuan yang diperoleh dari tutorial ini memungkinkan Anda membuat elemen array (tabel) yang terstruktur dan menarik secara visual dalam dokumen PDF. Dengan menggabungkan teknik-teknik ini, Anda dapat meningkatkan keterbacaan, aksesibilitas, dan pengalaman pengguna PDF yang dibuat secara dinamis, sehingga menjadi lebih informatif dan mudah digunakan.