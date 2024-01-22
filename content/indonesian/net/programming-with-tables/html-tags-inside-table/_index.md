---
title: Tag HTML Di Dalam Tabel Dalam File PDF
linktitle: Tag HTML Di Dalam Tabel Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menggunakan tag HTML di dalam tabel dalam file PDF dengan Aspose.PDF untuk .NET.
type: docs
weight: 100
url: /id/net/programming-with-tables/html-tags-inside-table/
---
Dalam tutorial ini, kita akan mempelajari cara menggunakan tag HTML di dalam tabel dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber dalam C# langkah demi langkah. Di akhir tutorial ini, Anda akan mengetahui cara menyisipkan konten HTML ke dalam tabel di dokumen PDF. Ayo mulai!

## Langkah 1: Menyiapkan lingkungan
Pastikan Anda telah mengonfigurasi lingkungan pengembangan C# Anda dengan Aspose.PDF untuk .NET. Tambahkan referensi ke perpustakaan dan impor namespace yang diperlukan.

## Langkah 2: Membuat data tabel
Kami membuat DataTable yang berisi kolom "data" bertipe String. Kami kemudian menambahkan baris ke DataTable ini menggunakan konten HTML.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);
```

## Langkah 3: Membuat Dokumen dan Tabel
Kami membuat dokumen PDF baru dan menambahkan halaman di dokumen ini. Selanjutnya, kita menginisialisasi sebuah instance dari kelas Tabel dan mengatur properti tabel.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
tableProvider. ColumnWidths = "400 50";
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 2.5F;
margin. Left = 2.5F;
margin. Bottom = 1.0F;
tableProvider. DefaultCellPadding = margin;
```

## Langkah 4: Mengimpor data ke dalam tabel
Kami mengimpor data dari DataTable ke dalam tabel menggunakan metode "ImportDataTable". Kami menentukan parameter metode untuk menunjukkan rentang baris dan kolom DataTable mana yang harus diimpor.

```csharp
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

## Langkah 5: Menambahkan tabel ke dokumen
Kami menambahkan tabel ke halaman dokumen.

```csharp
doc.Pages[1].Paragraphs.Add(tableProvider);
```

## Tahap 6: Menyimpan dokumen
Kami menyimpan dokumen PDF dengan tabel yang berisi konten HTML.

```csharp
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

### Contoh kode sumber untuk Tag HTML Di Dalam Tabel menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);

Document doc = new Document();
doc.Pages.Add();
// Menginisialisasi instance baru dari Tabel
Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
//Atur lebar kolom tabel
tableProvider.ColumnWidths = "400 50 ";
// Atur warna batas tabel menjadi LightGray
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Tetapkan batas untuk sel tabel
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 2.5F;
margin.Left = 2.5F;
margin.Bottom = 1.0F;
tableProvider.DefaultCellPadding = margin;

tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);

doc.Pages[1].Paragraphs.Add(tableProvider);
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara menggunakan tag HTML di dalam tabel dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Anda dapat menggunakan panduan langkah demi langkah ini untuk memasukkan konten HTML ke dalam sel tabel dalam dokumen PDF menggunakan C#.

### FAQ untuk tag HTML di dalam tabel dalam file PDF

#### T: Bisakah saya menggunakan tag dan atribut HTML lain di dalam sel tabel?

 A: Ya, Anda dapat menggunakan berbagai tag dan atribut HTML di dalam sel tabel, seperti`<b>`, `<i>`, `<a>`dan masih banyak lagi. Aspose.PDF untuk .NET mendukung berbagai elemen dan gaya HTML yang dapat Anda gunakan untuk memformat konten dalam sel tabel.

#### T: Bisakah saya menerapkan gaya CSS ke konten HTML di dalam sel tabel?

J: Ya, Anda bisa menerapkan gaya CSS ke konten HTML di dalam sel tabel. Aspose.PDF untuk .NET menyediakan dukungan untuk gaya CSS dasar yang dapat diterapkan pada elemen HTML.

#### T: Apakah mungkin menambahkan gambar beserta konten HTML di dalam sel tabel?

 A: Ya, Anda dapat menambahkan gambar beserta konten HTML di dalam sel tabel. Anda dapat menggunakan HTML`<img>` tag untuk menyertakan gambar dari berbagai sumber, seperti file atau URL lokal.

#### T: Bagaimana cara menentukan lebar kolom yang berbeda untuk tabel?

 J: Anda dapat menentukan lebar kolom berbeda untuk tabel menggunakan`ColumnWidths` properti tabel. Properti ini mengambil string yang berisi nilai yang dipisahkan spasi, di mana setiap nilai mewakili lebar kolom dalam poin.

#### T: Dapatkah saya menggunakan tabel bertumpuk di dalam sel dengan konten HTML?

J: Ya, Anda bisa menggunakan tabel bersarang di dalam sel dengan konten HTML. Anda dapat membuat instance tabel terpisah dan menambahkannya sebagai bagian dari konten HTML di dalam sel untuk mencapai efek bersarang.