---
title: Buat PDF Multi Kolom
linktitle: Buat PDF Multi Kolom
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara membuat PDF multikolom menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 110
url: /id/net/programming-with-text/create-multi-column-pdf/
---
Tutorial ini akan memandu Anda melalui proses pembuatan PDF multikolom menggunakan Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan.

## Persyaratan
Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau kompiler C# lainnya terinstal di komputer Anda.
- Aspose.PDF untuk pustaka .NET. Anda dapat mengunduhnya dari situs web resmi Aspose atau menggunakan pengelola paket seperti NuGet untuk menginstalnya.

## Langkah 1: Siapkan proyek
1. Buat proyek C# baru di lingkungan pengembangan pilihan Anda.
2. Tambahkan referensi ke pustaka Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan
Pada berkas kode tempat Anda ingin membuat PDF multikolom, tambahkan perintah penggunaan berikut di bagian atas berkas:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## Langkah 3: Mengatur direktori dokumen
 Dalam kode, temukan baris yang bertuliskan`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur ke direktori tempat dokumen Anda disimpan.

## Langkah 4: Buat contoh Dokumen baru
 Membuat instance baru`Document` objek dengan menambahkan baris kode berikut:

```csharp
Document doc = new Document();
```

## Langkah 5: Mengatur margin halaman
 Tentukan informasi margin kiri dan kanan untuk file PDF menggunakan`PageInfo.Margin` milik`Document`.

```csharp
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;
```

## Langkah 6: Tambahkan halaman ke dokumen
 Tambahkan halaman baru ke dokumen menggunakan`Add` metode dari`Pages`koleksi. Dalam kode yang diberikan, halaman baru ditetapkan ke variabel`page`.

```csharp
Page page = doc.Pages.Add();
```

## Langkah 7: Buat objek Grafik dan tambahkan garis
 Buat yang baru`Graph` objek dengan dimensi tertentu dan tambahkan garis padanya. Kemudian, tambahkan`Graph` keberatan terhadap`Paragraphs` koleksi halaman.

```csharp
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
float[] backPos = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
page.Paragraphs.Add(graph1);
```

## Langkah 8: Tambahkan teks judul dengan format HTML
 Membuat sebuah`HtmlFragment` objek dan atur kontennya ke teks HTML yang diinginkan. Kemudian, tambahkan fragmen ke`Paragraphs` koleksi halaman.

```csharp
string s = "<font face=\"Times New Roman\" size=4>" +
     "<strong>How to Steer Clear of money scams</<strong>" +
     "</font>";
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
```

## Langkah 9: Buat FloatingBox dengan beberapa kolom
 Membuat sebuah`FloatingBox` objek dan atur jumlah kolom dan spasi kolom. Kemudian, tambahkan fragmen teks dan baris ke`Paragraphs` koleksi dari`FloatingBox`.

```csharp
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
box. ColumnInfo. ColumnCount = 2;
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";

TextFragment text1 = new TextFragment("By A Googling (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);

TextFragment text2 = new TextFragment("Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam...");
box.Paragraphs.Add(text2);

Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
box.Paragraphs.Add(graph2);

page.Paragraphs.Add(box);
```

## Langkah 10: Simpan dokumen PDF
 Simpan dokumen PDF menggunakan`Save` metode dari`Document` obyek.

```csharp
doc.Save(dataDir);
```

### Contoh kode sumber untuk Membuat PDF Multi Kolom menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
//Tentukan info margin kiri untuk file PDF
doc.PageInfo.Margin.Left = 40;
// Tentukan info margin kanan untuk file PDF
doc.PageInfo.Margin.Right = 40;
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
// Tambahkan baris ke koleksi parafrase objek bagian
page.Paragraphs.Add(graph1);
// Tentukan koordinat untuk garis
float[] posArr = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
// Buat variabel string dengan teks yang berisi tag html
string s = "<font face=\"Times New Roman\" size=4>" +
"<strong> How to Steer Clear of money scams</<strong> "
+ "</font>";
// Membuat paragraf teks yang berisi teks HTML
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
// Tambahkan empat kolom di bagian tersebut
box.ColumnInfo.ColumnCount = 2;
// Mengatur jarak antar kolom
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);
text1.TextState.FontSize = 10;
text1.TextState.FontStyle = FontStyles.Italic;
// Buat objek grafik untuk menggambar garis
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
// Tentukan koordinat untuk garis
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
// Tambahkan baris ke kumpulan paragraf objek bagian
box.Paragraphs.Add(graph2);
TextFragment text2 = new TextFragment(@"Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam. Pellentesque sit amet elit. Vestibulum interdum pellentesque augue. Cras mollis arcu sit amet purus. Donec augue. Nam mollis tortor a elit. Nulla viverra nisl vel mauris. Vivamus sapien. nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et,nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.");
box.Paragraphs.Add(text2);
page.Paragraphs.Add(box);
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";
// Simpan file PDF
doc.Save(dataDir);
Console.WriteLine("\nMulti column pdf file created successfully.\nFile saved at " + dataDir);
```

## Kesimpulan
Anda telah berhasil membuat PDF multikolom menggunakan Aspose.PDF untuk .NET. File PDF yang dihasilkan kini dapat ditemukan di jalur file keluaran yang ditentukan.

### Pertanyaan yang Sering Diajukan

#### T: Apa fokus dari tutorial ini?

Tutorial ini difokuskan untuk memandu Anda melalui proses pembuatan PDF multi-kolom menggunakan pustaka Aspose.PDF for .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan untuk mencapainya.

#### T: Namespace mana yang harus saya impor untuk tutorial ini?

A: Pada berkas kode tempat Anda ingin membuat PDF multi-kolom, impor namespace berikut di awal berkas:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### T: Bagaimana cara menentukan direktori dokumen?

 A: Pada kode tersebut, temukan baris`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

#### T: Bagaimana cara membuat contoh Dokumen baru?

 A: Pada Langkah 4, Anda akan membuat instance baru`Document` objek menggunakan kode yang disediakan.

#### T: Bagaimana cara mengatur margin halaman?

 A: Pada Langkah 5, Anda akan menggunakan`PageInfo.Margin` milik`Document` untuk menentukan informasi margin kiri dan kanan untuk berkas PDF.

#### T: Bagaimana cara menambahkan halaman ke dokumen?

 A: Pada Langkah 6, Anda akan menambahkan halaman baru ke dokumen menggunakan`Add` metode dari`Pages` koleksi.

#### T: Bagaimana cara membuat objek Grafik dan menambahkan garis?

 A: Pada Langkah 7, Anda akan membuat yang baru`Graph` objek, tambahkan garis ke dalamnya, lalu tambahkan`Graph` keberatan terhadap`Paragraphs` koleksi halaman.

#### T: Bagaimana cara menambahkan teks judul dengan format HTML?

 A: Pada Langkah 8, Anda akan membuat`HtmlFragment` objek dan mengatur kontennya ke teks HTML yang diinginkan, lalu menambahkan fragmen ke`Paragraphs` koleksi halaman.

#### T: Bagaimana cara membuat FloatingBox dengan beberapa kolom?

 A: Pada Langkah 9, Anda akan membuat`FloatingBox` objek dengan beberapa kolom dan spasi kolom, lalu tambahkan fragmen teks dan baris ke`Paragraphs` koleksi dari`FloatingBox`.

#### T: Bagaimana cara menyimpan dokumen PDF?

 A: Pada Langkah 10, Anda akan menyimpan dokumen PDF menggunakan`Save` metode dari`Document` obyek.

#### T: Apa hasil utama dari tutorial ini?

A: Dengan mengikuti tutorial ini, Anda telah mempelajari cara membuat dokumen PDF multi-kolom menggunakan Aspose.PDF untuk .NET. Ini dapat berguna untuk menampilkan konten dalam tata letak yang terstruktur dan terorganisasi.