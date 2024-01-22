---
title: Integrasikan Dengan Database Dalam File PDF
linktitle: Integrasikan Dengan Database Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Sematkan data dari database dalam file PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 120
url: /id/net/programming-with-tables/integrate-with-database/
---
Dalam tutorial ini, kita akan mempelajari cara menyematkan data dari database dalam file PDF menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber dalam C# langkah demi langkah. Di akhir tutorial ini, Anda akan mengetahui cara mengimpor data tabel dari database ke dokumen PDF. Ayo mulai!

## Langkah 1: Menyiapkan lingkungan
Pastikan Anda telah mengonfigurasi lingkungan pengembangan C# Anda dengan Aspose.PDF untuk .NET. Tambahkan referensi ke perpustakaan dan impor namespace yang diperlukan.

## Langkah 2: Membuat DataTable
Kami membuat instance DataTable untuk mewakili data yang ingin kami sematkan dalam dokumen PDF. Dalam contoh ini, kita membuat DataTable dengan tiga kolom: Employee_ID, Employee_Name, dan Gender. Kami juga menambahkan dua baris ke DataTable dengan data dummy.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));

DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);

dr = dt. NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
```

## Langkah 3: Membuat Dokumen dan Tabel PDF
Kami membuat sebuah instance dari Dokumen dan menambahkan halaman ke dokumen ini. Selanjutnya, kita membuat instance Tabel untuk mewakili tabel kita di dokumen PDF. Kami menentukan lebar kolom tabel dan gaya batas.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Langkah 4: Mengimpor data dari DataTable ke dalam tabel
Kami menggunakan metode ImportDataTable untuk mengimpor data dari DataTable ke dalam tabel di dokumen PDF.

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## Langkah 5: Menambahkan tabel ke dokumen
Kami menambahkan tabel ke kumpulan paragraf di halaman dokumen.

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## Langkah 6: Simpan dokumen
Kami menyimpan dokumen PDF dengan data dari database tertanam.

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

Selamat! Anda sekarang tahu cara menyematkan data database ke dalam dokumen PDF menggunakan Aspose.PDF untuk .NET.

### Contoh kode sumber untuk Integrasi Dengan Database menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
// Tambahkan 2 baris ke objek DataTable secara terprogram
DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
// Buat contoh Dokumen
Document doc = new Document();
doc.Pages.Add();
// Menginisialisasi instance baru dari Tabel
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Atur lebar kolom tabel
table.ColumnWidths = "40 100 100 100";
// Atur warna batas tabel menjadi LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Tetapkan batas untuk sel tabel
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.ImportDataTable(dt, true, 0, 1, 3, 3);

// Tambahkan objek tabel ke halaman pertama dokumen masukan
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "DataIntegrated_out.pdf";
// Simpan dokumen terbaru yang berisi objek tabel
doc.Save(dataDir);

Console.WriteLine("\nDatabase integrated successfully.\nFile saved at " + dataDir);
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara menyematkan data dari database ke dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Anda dapat menggunakan panduan langkah demi langkah ini untuk mengimpor data dari database Anda sendiri dan menampilkannya dalam dokumen PDF. Jelajahi dokumentasi Aspose.PDF lebih jauh untuk menemukan fitur dan kemungkinan lain yang ditawarkan oleh perpustakaan canggih ini.

### FAQ untuk mengintegrasikan dengan database dalam file PDF

#### T: Bisakah saya menggunakan Aspose.PDF untuk .NET dengan tipe database berbeda seperti MySQL, SQL Server, atau Oracle?

J: Ya, Anda dapat menggunakan Aspose.PDF untuk .NET dengan tipe database berbeda seperti MySQL, SQL Server, Oracle, dan lainnya. Aspose.PDF untuk .NET menyediakan fungsionalitas untuk membaca data dari berbagai sumber data, termasuk database, file XML, dan lainnya. Anda dapat mengambil data dari tipe database yang Anda inginkan dan mengisinya ke dalam DataTable atau struktur data lainnya yang kompatibel dengan Aspose.PDF untuk .NET.

#### T: Bagaimana cara menyesuaikan tampilan tabel di dokumen PDF?

J: Anda dapat mengkustomisasi tampilan tabel dalam dokumen PDF menggunakan berbagai properti yang disediakan oleh perpustakaan Aspose.PDF untuk .NET. Misalnya, Anda bisa mengatur gaya batas, warna latar belakang, gaya font, dan perataan yang berbeda untuk tabel dan selnya. Lihat dokumentasi Aspose.PDF untuk .NET untuk detail selengkapnya tentang menyesuaikan tampilan tabel.

#### T: Apakah mungkin menambahkan hyperlink atau elemen interaktif ke data yang diimpor dari database?

J: Ya, Anda bisa menambahkan hyperlink atau elemen interaktif lainnya ke data yang diimpor dari database. Aspose.PDF untuk .NET mendukung penambahan hyperlink, bookmark, dan elemen interaktif lainnya ke dokumen PDF. Anda dapat memanipulasi konten di DataTable sebelum mengimpornya ke dalam tabel dan menyertakan hyperlink atau fitur interaktif lainnya.

#### T: Bisakah saya memberi nomor halaman pada tabel jika melebihi jumlah baris tertentu?

 J: Ya, Anda dapat membuat halaman tabel jika melebihi jumlah baris tertentu. Untuk mencapai hal ini, Anda dapat menggunakan`IsInNewPage`properti objek Row untuk menunjukkan bahwa halaman baru harus dimulai setelah baris tertentu. Anda dapat menghitung jumlah baris yang akan ditampilkan per halaman dan mengaturnya`IsInNewPage` properti yang sesuai.

#### T: Bagaimana cara mengekspor dokumen PDF dengan data database tertanam ke format file berbeda seperti DOCX atau XLSX?

J: Aspose.PDF untuk .NET memungkinkan Anda mengonversi dokumen PDF ke berbagai format file lainnya, termasuk DOCX (Microsoft Word) dan XLSX (Microsoft Excel). Anda dapat menggunakan pustaka Aspose.PDF untuk .NET yang dikombinasikan dengan pustaka Aspose lainnya seperti Aspose.Words dan Aspose.Cells untuk mencapai hal ini. Pertama, simpan dokumen PDF dengan data database tertanam, lalu gunakan perpustakaan Aspose masing-masing untuk mengonversinya ke format file yang Anda inginkan.