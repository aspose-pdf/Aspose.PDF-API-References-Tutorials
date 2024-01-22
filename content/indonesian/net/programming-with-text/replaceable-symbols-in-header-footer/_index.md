---
title: Simbol yang Dapat Diganti Di Header Footer
linktitle: Simbol yang Dapat Diganti Di Header Footer
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menggunakan simbol yang dapat diganti di header dan footer dokumen PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 320
url: /id/net/programming-with-text/replaceable-symbols-in-header-footer/
---
Dalam tutorial ini, kami akan menjelaskan cara menggunakan simbol yang dapat diganti di header dan footer dokumen PDF menggunakan perpustakaan Aspose.PDF untuk .NET. Kita akan melalui proses langkah demi langkah dalam membuat PDF, mengatur margin, menambahkan header dan footer dengan simbol yang dapat diganti, dan menyimpan PDF menggunakan kode sumber C# yang disediakan.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Pustaka Aspose.PDF untuk .NET diinstal.
- Pemahaman dasar tentang pemrograman C#.

## Langkah 1: Siapkan Direktori Dokumen

 Pertama, Anda perlu mengatur jalur ke direktori tempat Anda ingin menyimpan file PDF yang dihasilkan. Mengganti`"YOUR DOCUMENT DIRECTORY"` dalam`dataDir`variabel dengan jalur ke direktori yang Anda inginkan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Buat Dokumen dan Halaman PDF

 Selanjutnya, kita membuat dokumen PDF baru dan menambahkan halaman ke dalamnya menggunakan`Document` kelas dan`Page` kelas dari perpustakaan Aspose.PDF.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Langkah 3: Tetapkan Margin

 Kami mengatur margin untuk halaman menggunakan`MarginInfo`kelas. Sesuaikan nilai margin sesuai dengan kebutuhan Anda.

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## Langkah 4: Tambahkan Header dengan Simbol yang Dapat Diganti

 Kami membuat`HeaderFooter` objek untuk halaman dan tambahkan a`TextFragment` dengan simbol yang dapat diganti.

```csharp
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

TextFragment t1 = new TextFragment("report title");
// Atur properti teks jika diinginkan
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;

hfFirst.Paragraphs.Add(t1);

// Tambahkan lebih banyak TextFragment atau sesuaikan sesuai kebutuhan
```

## Langkah 5: Tambahkan Footer dengan Simbol yang Dapat Diganti

 Demikian pula, kami membuat a`HeaderFooter` objek untuk footer halaman dan tambahkan`TextFragment` objek dengan simbol yang dapat diganti.

```csharp
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");

// Tambahkan lebih banyak TextFragment atau sesuaikan sesuai kebutuhan

hfFoot.Paragraphs.Add(tab2);
```

## Langkah 6: Simpan Dokumen PDF

Terakhir, kami menyimpan dokumen PDF ke file keluaran yang ditentukan.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### Contoh kode sumber untuk Simbol yang Dapat Diganti di Header Footer menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
// Tetapkan instance marginInfo ke properti Margin sec1.PageInfo
page.PageInfo.Margin = marginInfo;
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;
// Buat instance paragraf Teks yang akan menyimpan konten untuk ditampilkan sebagai header
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;
hfFirst.Paragraphs.Add(t1);
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t2.TextState.LineSpacing = 5f;
t2.TextState.FontSize = 12;
hfFirst.Paragraphs.Add(t2);
// Buat objek HeaderFooter untuk bagian tersebut
HeaderFooter hfFoot = new HeaderFooter();
// Atur objek HeaderFooter menjadi footer ganjil & genap
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// Tambahkan paragraf teks yang berisi nomor halaman saat ini dari jumlah halaman total
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// Buat instance objek tabel
Table tab2 = new Table();
// Tambahkan tabel dalam kumpulan paragraf dari bagian yang diinginkan
hfFoot.Paragraphs.Add(tab2);
// Atur dengan lebar kolom tabel
tab2.ColumnWidths = "165 172 165";
// Buat baris dalam tabel dan kemudian sel dalam baris
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();
// Atur perataan vertikal teks menjadi rata tengah
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
//Sec1.Paragraphs.Add(New Text("Aspose.Total for Java adalah kompilasi dari setiap komponen Java yang ditawarkan oleh Aspose. Ini dikompilasi setiap hari#$NL" + "untuk memastikan komponen tersebut berisi versi paling mutakhir dari masing-masing komponen komponen Java kami. #$NL " + "Menggunakan Aspose.Total untuk Java, pengembang dapat membuat berbagai macam aplikasi. #$NL #$NL #$NP" + "Aspose.Total untuk Java adalah kompilasi dari setiap komponen Java ditawarkan oleh Aspose. Ini dikompilasi setiap hari#$NL" + "untuk memastikan berisi versi terbaru dari masing-masing komponen Java kami. #$NL " + "Menggunakan Aspose.Total untuk pengembang Java dapat membuat berbagai macam berbagai aplikasi. #$NL #$NL #$NP" + "Aspose.Total untuk Java adalah kompilasi dari setiap komponen Java yang ditawarkan oleh Aspose. Ini dikompilasi setiap hari#$NL" + "untuk memastikan komponen tersebut berisi paling banyak versi terkini dari masing-masing komponen Java kami. #$NL " + "Menggunakan Aspose.Total untuk pengembang Java dapat membuat berbagai macam aplikasi. #$NL #$NL"))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// Tambahkan tabel dalam kumpulan paragraf dari bagian yang diinginkan
page.Paragraphs.Add(table);
// Tetapkan batas sel default menggunakan objek BorderInfo
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
// Tetapkan batas tabel menggunakan objek BorderInfo khusus lainnya
table.Border = new BorderInfo(BorderSide.All, 1f);
table.RepeatingRowsCount = 1;
// Buat baris dalam tabel dan kemudian sel dalam baris
Row row1 = table.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
const string CRLF = "\r\n";
for (int i = 0; i <= 10; i++)
{
	Row row = table.Rows.Add();
	row.IsRowBroken = true;
	for (int c = 0; c <= 2; c++)
	{
		Cell c1;
		if (c == 2)
			c1 = row.Cells.Add("Aspose.Total for Java is a compilation of every Java component offered by Aspose. It is compiled on a" + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "Using Aspose.Total for Java developers can create a wide range of applications.");
		else
			c1 = row.Cells.Add("item1" + c);
		c1.Margin = new MarginInfo();
		c1.Margin.Left = 30;
		c1.Margin.Top = 10;
		c1.Margin.Bottom = 10;
	}
}
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nSymbols replaced successfully in header and footer.\nFile saved at " + dataDir);
```

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara menggunakan simbol yang dapat diganti di header dan footer dokumen PDF menggunakan pustaka Aspose.PDF untuk .NET. Dengan mengikuti panduan langkah demi langkah dan menjalankan kode C# yang disediakan, Anda dapat membuat PDF, mengatur margin, menambahkan header dan footer dengan simbol yang dapat diganti, dan menyimpan PDF.

### FAQ

#### Q: Apa tujuan dari tutorial "Simbol yang Dapat Diganti di Header Footer"?

J: Tutorial "Simbol yang Dapat Diganti di Header Footer" bertujuan untuk memandu Anda melalui proses penggunaan pustaka Aspose.PDF untuk .NET guna menambahkan simbol yang dapat diganti ke header dan footer dokumen PDF. Simbol yang dapat diganti memungkinkan Anda mengganti placeholder tertentu secara dinamis dengan nilai sebenarnya saat membuat PDF.

#### T: Simbol apa yang dapat diganti dalam konteks header dan footer PDF?

J: Simbol yang dapat diganti adalah placeholder yang dapat Anda sisipkan ke header dan footer dokumen PDF. Simbol-simbol ini bertindak sebagai tempat penampung dinamis untuk nilai-nilai yang dapat diisi pada waktu proses, seperti nomor halaman, tanggal, dan informasi khusus.

#### T: Mengapa saya ingin menggunakan simbol yang dapat diganti di header dan footer PDF?

J: Simbol yang dapat diganti di header dan footer berguna saat Anda ingin menyertakan informasi dinamis dalam dokumen PDF Anda, seperti nomor halaman, tanggal, atau data variabel lainnya yang mungkin berubah saat dokumen dibuat.

#### T: Bagaimana cara mengatur margin untuk halaman PDF?

 J: Anda dapat mengatur margin untuk halaman PDF menggunakan`MarginInfo` kelas dan menugaskannya ke`Margin` properti dari`PageInfo` dari halaman. Sesuaikan nilai margin sesuai kebutuhan.

#### T: Bagaimana cara menambahkan simbol yang dapat diganti ke header dan footer?

 A: Anda dapat menambahkan simbol yang dapat diganti dengan membuat a`HeaderFooter` objek untuk header dan footer halaman. Lalu, Anda bisa menambahkan`TextFragment`objek dengan teks yang diinginkan, termasuk simbol yang dapat diganti, ke`Paragraphs` koleksi`HeaderFooter` obyek.

#### T: Dapatkah saya menyesuaikan tampilan simbol yang dapat diganti?

 J: Ya, Anda dapat menyesuaikan tampilan simbol yang dapat diganti dengan memodifikasi propertinya`TextFragment` benda yang mengandung simbol. Anda dapat mengatur properti seperti font, ukuran font, warna, perataan, dan spasi baris.

#### T: Simbol apa yang dapat diganti apa yang dapat saya gunakan?

A: Anda dapat menggunakan berbagai simbol yang dapat diganti, seperti:

- `$p`: Nomor halaman saat ini.
- `$P`: Jumlah total halaman.
- `$d`: Tanggal sekarang.
- `$t`: Waktu saat ini.
- Placeholder khusus yang Anda tetapkan.

#### T: Dapatkah saya menyertakan teks dan format lain di sekitar simbol yang dapat diganti?

 J: Ya, Anda dapat menyertakan teks dan format lain di sekitar simbol yang dapat diganti di dalamnya`TextFragment` objek. Hal ini memungkinkan Anda membuat header dan footer yang lebih kompleks yang menggabungkan konten dinamis dan statis.

#### T: Bagaimana cara menyimpan dokumen PDF yang dihasilkan?

 A: Untuk menyimpan dokumen PDF yang dihasilkan, Anda dapat menggunakan`Save` metode`Document`kelas. Berikan jalur dan nama file keluaran yang diinginkan sebagai argumen.

#### T: Apakah Lisensi Aspose yang valid diperlukan untuk tutorial ini?

A: Ya, Lisensi Aspose yang valid diperlukan agar kode berhasil dieksekusi dalam tutorial ini. Anda bisa mendapatkan lisensi penuh atau lisensi sementara 30 hari dari situs web Aspose.