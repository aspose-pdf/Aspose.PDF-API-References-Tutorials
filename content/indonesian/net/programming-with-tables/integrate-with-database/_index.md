---
title: Integrasikan Dengan Basis Data Dalam File PDF
linktitle: Integrasikan Dengan Basis Data Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Sematkan data dari database dalam berkas PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 120
url: /id/net/programming-with-tables/integrate-with-database/
---
Dalam tutorial ini, kita akan mempelajari cara menyematkan data dari database ke dalam file PDF menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber dalam C# langkah demi langkah. Di akhir tutorial ini, Anda akan mengetahui cara mengimpor data tabel dari database ke dalam dokumen PDF. Mari kita mulai!

## Langkah 1: Menyiapkan lingkungan
Pastikan Anda telah mengonfigurasi lingkungan pengembangan C# dengan Aspose.PDF untuk .NET. Tambahkan referensi ke pustaka dan impor namespace yang diperlukan.

## Langkah 2: Membuat DataTable
Kami membuat contoh DataTable untuk mewakili data yang ingin kami sisipkan dalam dokumen PDF. Dalam contoh ini, kami membuat DataTable dengan tiga kolom: Employee_ID, Employee_Name, dan Gender. Kami juga menambahkan dua baris ke DataTable dengan data dummy.

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

## Langkah 3: Membuat Dokumen PDF dan Tabel
Kita buat contoh Dokumen dan tambahkan halaman ke dokumen ini. Selanjutnya, kita buat contoh Tabel untuk mewakili tabel kita dalam dokumen PDF. Kita tentukan lebar kolom tabel dan gaya batas.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Langkah 4: Mengimpor data dari DataTable ke tabel
Kami menggunakan metode ImportDataTable untuk mengimpor data dari DataTable ke dalam tabel dalam dokumen PDF.

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## Langkah 5: Menambahkan tabel ke dokumen
Kami menambahkan tabel ke koleksi paragraf di halaman dokumen.

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## Langkah 6: Simpan dokumen
Kami menyimpan dokumen PDF dengan data dari basis data yang tertanam.

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

Selamat! Kini Anda tahu cara menyematkan data basis data ke dalam dokumen PDF menggunakan Aspose.PDF for .NET.

### Contoh kode sumber untuk Integrasi dengan Basis Data menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
//Tambahkan 2 baris ke objek DataTable secara terprogram
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
// Menginisialisasi contoh baru Tabel
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Mengatur lebar kolom tabel
table.ColumnWidths = "40 100 100 100";
// Atur warna batas tabel menjadi LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Mengatur batas untuk sel tabel
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.ImportDataTable(dt, true, 0, 1, 3, 3);

// Tambahkan objek tabel ke halaman pertama dokumen input
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "DataIntegrated_out.pdf";
// Simpan dokumen yang diperbarui yang berisi objek tabel
doc.Save(dataDir);

Console.WriteLine("\nDatabase integrated successfully.\nFile saved at " + dataDir);
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara menanamkan data dari basis data ke dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Anda dapat menggunakan panduan langkah demi langkah ini untuk mengimpor data dari basis data Anda sendiri dan menampilkannya dalam dokumen PDF. Jelajahi dokumentasi Aspose.PDF lebih lanjut untuk menemukan fitur dan kemungkinan lain yang ditawarkan oleh pustaka hebat ini.

### FAQ untuk integrasi dengan database dalam file PDF

#### T: Dapatkah saya menggunakan Aspose.PDF untuk .NET dengan tipe database yang berbeda seperti MySQL, SQL Server, atau Oracle?

J: Ya, Anda dapat menggunakan Aspose.PDF untuk .NET dengan berbagai jenis basis data seperti MySQL, SQL Server, Oracle, dan lainnya. Aspose.PDF untuk .NET menyediakan fungsionalitas untuk membaca data dari berbagai sumber data, termasuk basis data, file XML, dan lainnya. Anda dapat mengambil data dari jenis basis data yang diinginkan dan mengisinya ke dalam DataTable atau struktur data lain yang kompatibel dengan Aspose.PDF untuk .NET.

#### T: Bagaimana saya dapat menyesuaikan tampilan tabel dalam dokumen PDF?

J: Anda dapat menyesuaikan tampilan tabel dalam dokumen PDF menggunakan berbagai properti yang disediakan oleh pustaka Aspose.PDF for .NET. Misalnya, Anda dapat mengatur berbagai gaya batas, warna latar belakang, gaya fon, dan perataan untuk tabel dan sel-selnya. Lihat dokumentasi Aspose.PDF for .NET untuk detail lebih lanjut tentang penyesuaian tampilan tabel.

#### T: Apakah mungkin untuk menambahkan hyperlink atau elemen interaktif ke data yang diimpor dari basis data?

J: Ya, Anda dapat menambahkan hyperlink atau elemen interaktif lainnya ke data yang diimpor dari database. Aspose.PDF untuk .NET mendukung penambahan hyperlink, bookmark, dan elemen interaktif lainnya ke dokumen PDF. Anda dapat memanipulasi konten dalam DataTable sebelum mengimpornya ke dalam tabel dan menyertakan hyperlink atau fitur interaktif lainnya.

#### T: Dapatkah saya membuat halaman pada tabel jika jumlah barisnya melebihi jumlah tertentu?

A: Ya, Anda dapat membagi tabel menjadi beberapa halaman jika jumlahnya melebihi jumlah baris tertentu. Untuk mencapainya, Anda dapat menggunakan`IsInNewPage` properti objek Baris untuk menunjukkan bahwa halaman baru harus dimulai setelah baris tertentu. Anda dapat menghitung jumlah baris yang akan ditampilkan per halaman dan mengatur`IsInNewPage` properti sebagaimana mestinya.

#### T: Bagaimana cara mengekspor dokumen PDF dengan data basis data tertanam ke format file lain seperti DOCX atau XLSX?

J: Aspose.PDF untuk .NET memungkinkan Anda mengonversi dokumen PDF ke berbagai format file lain, termasuk DOCX (Microsoft Word) dan XLSX (Microsoft Excel). Anda dapat menggunakan pustaka Aspose.PDF untuk .NET bersama dengan pustaka Aspose lain seperti Aspose.Words dan Aspose.Cells untuk mencapainya. Pertama, simpan dokumen PDF dengan data basis data tertanam, lalu gunakan pustaka Aspose terkait untuk mengonversinya ke format file yang Anda inginkan.