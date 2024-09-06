---
title: Simbol yang Dapat Diganti di Header Footer
linktitle: Simbol yang Dapat Diganti di Header Footer
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menggunakan simbol yang dapat diganti di header dan footer dokumen PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 320
url: /id/net/programming-with-text/replaceable-symbols-in-header-footer/
---
Dalam tutorial ini, kami akan menjelaskan cara menggunakan simbol yang dapat diganti di header dan footer dokumen PDF menggunakan pustaka Aspose.PDF untuk .NET. Kami akan membahas proses langkah demi langkah untuk membuat PDF, mengatur margin, menambahkan header dan footer dengan simbol yang dapat diganti, dan menyimpan PDF menggunakan kode sumber C# yang disediakan.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Pustaka Aspose.PDF untuk .NET terinstal.
- Pemahaman dasar tentang pemrograman C#.

## Langkah 1: Siapkan Direktori Dokumen

 Pertama, Anda perlu mengatur jalur ke direktori tempat Anda ingin menyimpan file PDF yang dihasilkan. Ganti`"YOUR DOCUMENT DIRECTORY"` di dalam`dataDir` variabel dengan jalur ke direktori yang Anda inginkan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Buat Dokumen dan Halaman PDF

 Selanjutnya, kita membuat dokumen PDF baru dan menambahkan halaman ke dalamnya menggunakan`Document` kelas dan`Page` kelas dari pustaka Aspose.PDF.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Langkah 3: Tetapkan Margin

Kami mengatur margin untuk halaman menggunakan`MarginInfo` kelas. Sesuaikan nilai margin sesuai dengan kebutuhan Anda.

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## Langkah 4: Tambahkan Header dengan Simbol yang Dapat Diganti

 Kami menciptakan sebuah`HeaderFooter` objek untuk halaman dan tambahkan`TextFragment` dengan simbol-simbol yang dapat diganti.

```csharp
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

TextFragment t1 = new TextFragment("report title");
// Tetapkan properti teks jika diinginkan
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;

hfFirst.Paragraphs.Add(t1);

// Tambahkan lebih banyak TextFragments atau sesuaikan sesuai kebutuhan
```

## Langkah 5: Tambahkan Footer dengan Simbol yang Dapat Diganti

 Demikian pula, kita membuat`HeaderFooter` objek untuk footer halaman dan tambahkan`TextFragment` objek dengan simbol yang dapat diganti.

```csharp
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");

// Tambahkan lebih banyak TextFragments atau sesuaikan sesuai kebutuhan

hfFoot.Paragraphs.Add(tab2);
```

## Langkah 6: Simpan Dokumen PDF

Terakhir, kami menyimpan dokumen PDF ke berkas keluaran yang ditentukan.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### Contoh kode sumber untuk Simbol yang Dapat Diganti di Header dan Footer menggunakan Aspose.PDF untuk .NET 
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
// Tetapkan instance marginInfo ke properti Margin dari sec1.PageInfo
page.PageInfo.Margin = marginInfo;
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;
// Buat paragraf Teks yang akan menyimpan konten untuk ditampilkan sebagai header
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
// Mengatur objek HeaderFooter ke footer ganjil & genap
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// Tambahkan paragraf teks yang berisi nomor halaman saat ini dari total jumlah halaman
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// Membuat instance objek tabel
Table tab2 = new Table();
// Tambahkan tabel dalam kumpulan paragraf bagian yang diinginkan
hfFoot.Paragraphs.Add(tab2);
// Diatur dengan lebar kolom tabel
tab2.ColumnWidths = "165 172 165";
// Buat baris dalam tabel dan kemudian sel dalam baris
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();
// Mengatur perataan vertikal teks menjadi rata tengah
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
//Sec1.Paragraphs.Add(New Text("Aspose.Total untuk Java adalah kompilasi dari setiap komponen Java yang ditawarkan oleh Aspose. Dikompilasi setiap hari untuk memastikannya berisi versi terbaru dari setiap komponen Java kami. #$NL " + "Dengan menggunakan Aspose.Total untuk pengembang Java, Anda dapat membuat berbagai aplikasi. #$NL #$NL #$NP" + "Aspose.Total untuk Java adalah kompilasi dari setiap komponen Java yang ditawarkan oleh Aspose. Dikompilasi setiap hari untuk memastikannya berisi versi terbaru dari setiap komponen Java kami. #$NL " + "Dengan menggunakan Aspose.Total untuk pengembang Java, Anda dapat membuat berbagai aplikasi. #$NL #$NL #$NP" + "Aspose.Total untuk Java adalah kompilasi dari setiap komponen Java yang ditawarkan oleh Aspose. Dikompilasi setiap hari untuk memastikannya berisi versi terbaru dari setiap komponen Java kami. #$NL " + "Penggunaan Aspose.Total bagi pengembang Java dapat membuat berbagai macam aplikasi. #$NL #$NL"))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// Tambahkan tabel dalam kumpulan paragraf bagian yang diinginkan
page.Paragraphs.Add(table);
// Mengatur batas sel default menggunakan objek BorderInfo
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
// Tetapkan batas tabel menggunakan objek BorderInfo lain yang disesuaikan
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

### Pertanyaan yang Sering Diajukan

#### T: Apa tujuan dari tutorial "Simbol yang Dapat Diganti di Header Footer"?

A: Tutorial "Simbol yang Dapat Diganti di Header dan Footer" bertujuan untuk memandu Anda melalui proses penggunaan pustaka Aspose.PDF untuk .NET guna menambahkan simbol yang dapat diganti ke header dan footer dokumen PDF. Simbol yang dapat diganti memungkinkan Anda mengganti placeholder tertentu secara dinamis dengan nilai aktual saat membuat PDF.

#### T: Apa saja simbol yang dapat diganti dalam konteks header dan footer PDF?

A: Simbol yang dapat diganti adalah tempat penampung yang dapat Anda sisipkan ke dalam header dan footer dokumen PDF. Simbol ini berfungsi sebagai tempat penampung dinamis untuk nilai yang dapat diisi saat runtime, seperti nomor halaman, tanggal, dan informasi khusus.

#### T: Mengapa saya ingin menggunakan simbol yang dapat diganti dalam header dan footer PDF?

A: Simbol yang dapat diganti di header dan footer berguna saat Anda ingin menyertakan informasi dinamis dalam dokumen PDF Anda, seperti nomor halaman, tanggal, atau data variabel lainnya yang dapat berubah saat dokumen dibuat.

#### T: Bagaimana cara mengatur margin untuk halaman PDF?

 A: Anda dapat mengatur margin untuk halaman PDF menggunakan`MarginInfo` kelas dan menugaskannya ke`Margin` milik`PageInfo` halaman. Sesuaikan nilai margin sesuai kebutuhan.

#### T: Bagaimana cara menambahkan simbol yang dapat diganti ke header dan footer?

 A: Anda dapat menambahkan simbol yang dapat diganti dengan membuat`HeaderFooter` objek untuk header dan footer halaman. Kemudian, Anda dapat menambahkan`TextFragment`objek dengan teks yang diinginkan, termasuk simbol yang dapat diganti, ke`Paragraphs` koleksi dari`HeaderFooter` obyek.

#### T: Dapatkah saya menyesuaikan tampilan simbol yang dapat diganti?

 A: Ya, Anda dapat menyesuaikan tampilan simbol yang dapat diganti dengan memodifikasi properti`TextFragment` objek yang berisi simbol. Anda dapat mengatur properti seperti font, ukuran font, warna, perataan, dan spasi baris.

#### T: Simbol pengganti apa saja yang bisa saya gunakan?

A: Anda dapat menggunakan berbagai simbol yang dapat diganti, seperti:

- `$p`: Nomor halaman saat ini.
- `$P`: Jumlah total halaman.
- `$d`Tanggal saat ini.
- `$t`: Waktu saat ini.
- Tempat penampung khusus yang Anda tentukan.

#### T: Dapatkah saya menyertakan teks dan format lain di sekitar simbol yang dapat diganti?

 A: Ya, Anda dapat menyertakan teks dan format lain di sekitar simbol yang dapat diganti dalam`TextFragment` objek. Hal ini memungkinkan Anda membuat header dan footer yang lebih kompleks yang menggabungkan konten dinamis dan statis.

#### T: Bagaimana cara menyimpan dokumen PDF yang dihasilkan?

 A: Untuk menyimpan dokumen PDF yang dihasilkan, Anda dapat menggunakan`Save` metode dari`Document`class. Berikan jalur dan nama file output yang diinginkan sebagai argumen.

#### T: Apakah Lisensi Aspose yang valid diperlukan untuk tutorial ini?

A: Ya, Lisensi Aspose yang valid diperlukan untuk menjalankan kode dengan sukses dalam tutorial ini. Anda dapat memperoleh lisensi penuh atau lisensi sementara 30 hari dari situs web Aspose.