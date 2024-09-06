---
title: Ekspor Data Lembar Kerja Excel Ke Tabel
linktitle: Ekspor Data Lembar Kerja Excel Ke Tabel
second_title: Referensi API Aspose.PDF untuk .NET
description: Ekspor data dari lembar Excel ke tabel PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 70
url: /id/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
Dalam tutorial ini, kita akan mempelajari cara mengekspor data dari lembar kerja Excel dan membuat tabel dalam dokumen PDF menggunakan pustaka Aspose.PDF for .NET. Kita akan membahas kode sumber langkah demi langkah dan menjelaskan setiap bagian secara terperinci. Di akhir tutorial ini, Anda akan dapat membuat file PDF dengan tabel yang berisi data dari lembar kerja Excel. Mari kita mulai!

## Persyaratan
Sebelum kita mulai, pastikan Anda memiliki hal berikut:

- Pengetahuan dasar bahasa pemrograman C#
- Visual Studio terinstal di komputer Anda
- Pustaka Aspose.PDF untuk .NET ditambahkan ke proyek Anda

## Langkah 1: Menyiapkan Lingkungan
Untuk memulai, buat proyek C# baru di Visual Studio. Tambahkan referensi ke pustaka Aspose.PDF for .NET dengan mengklik kanan proyek Anda di Solution Explorer, pilih "Manage NuGet Packages," dan cari "Aspose.PDF." Instal paket dan Anda siap memulai.

## Langkah 2: Memuat Lembar Kerja Excel
Pada langkah pertama kode kita, kita tentukan jalur ke direktori yang berisi dokumen Excel. Ganti "DIREKTORI DOKUMEN ANDA" dengan jalur direktori sebenarnya tempat file Excel Anda berada.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

Di sini, kami menggunakan pustaka Aspose.Cells untuk memuat buku kerja Excel. Pastikan untuk mengganti "newBook1.xlsx" dengan nama file Excel Anda.

## Langkah 3: Mengakses Lembar Kerja
 Selanjutnya, kita perlu mengakses lembar kerja pertama dalam file Excel. Kita melakukan ini dengan menggunakan`Worksheets` koleksi dari`Workbook` obyek.

```csharp
// Mengakses lembar kerja pertama dalam file Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

 Jika file Excel Anda berisi beberapa lembar kerja, Anda dapat mengubah nilai indeks`[0]` untuk mengakses lembar kerja yang berbeda.

## Langkah 4: Mengekspor Data ke DataTable
 Sekarang, kita akan mengekspor isi lembar kerja Excel ke`DataTable` objek. Kami menentukan rentang sel yang akan diekspor menggunakan`ExportDataTable` metode.

```csharp
// Mengekspor konten 7 baris dan 2 kolom mulai dari sel ke-1 ke DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

Dalam contoh ini, kami mengekspor semua baris dan kolom mulai dari sel pertama (0, 0) hingga sel terakhir di lembar kerja. Tetapkan rentang yang sesuai berdasarkan kebutuhan Anda.

## Langkah 5: Membuat Dokumen PDF
Sekarang, kita akan membuat dokumen PDF baru menggunakan pustaka Aspose.PDF.

```csharp
// Membuat instance Dokumen
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Ini menciptakan dokumen PDF kosong tempat kita dapat menambahkan konten.

## Langkah 6: Menambahkan Halaman dan Tabel
Untuk menampilkan data dalam format tabel, kita perlu menambahkan halaman dan tabel ke dokumen PDF.

```csharp
// Buat halaman dalam contoh dokumen
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Membuat objek Tabel
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Tambahkan objek Tabel dalam koleksi paragraf bagian
sec1.Paragraphs.Add(tab1);
```

Di sini, kita membuat halaman baru dan objek tabel. Kemudian, kita menambahkan tabel ke koleksi paragraf halaman tersebut.

## Langkah 7: Mengatur Properti Tabel
Sebelum mengimpor data, kita perlu mengatur beberapa properti tabel, seperti lebar kolom dan batas sel default.

```csharp
// Mengatur lebar kolom tabel
tab1.ColumnWidths = "40 100 100";

// Mengatur batas sel default tabel menggunakan objek BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

Dalam contoh ini, kami menetapkan lebar kolom menjadi 40, 100, dan 100 unit. Sesuaikan nilai berdasarkan data Anda. Kami juga menetapkan batas sel default untuk menampilkan batas di semua sisi setiap sel.

## Langkah 8: Mengimpor Data ke Tabel
 Sekarang, kita akan mengimpor data dari`DataTable` objek ke dalam tabel menggunakan`ImportDataTable` metode.

```csharp
// Impor data ke objek Tabel dari DataTable yang dibuat di atas
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Di sini, kami menentukan rentang baris dan kolom yang akan diimpor. Dalam contoh ini, kami mengimpor semua baris dan kolom dari`dataTable` obyek.

## Langkah 9: Memformat Tabel
Untuk menyempurnakan tampilan tabel, kita dapat menerapkan pemformatan pada sel atau baris tertentu. Pada langkah ini, kita akan memformat baris pertama dan baris berikutnya pada tabel.

```csharp
// Dapatkan baris pertama dari tabel
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Format baris pertama
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     // Mengatur warna latar belakang sel di baris pertama
     curCell.BackgroundColor = Color.Blue;// Mengatur wajah untuk sel di baris pertama
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     // Mengatur warna font sel di baris pertama
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     // Mengatur perataan teks untuk sel di baris pertama
     curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

// Format baris alternatif
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         // Mengatur warna latar belakang sel dalam baris bergantian
         curCell.BackgroundColor = Color.Gray;
        
         // Mengatur warna teks sel dalam baris bergantian
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

Di sini, kita mengulang sel-sel di baris pertama dan mengatur warna latar belakang, jenis huruf, warna huruf, dan perataan teks. Kemudian, kita mengulang semua sel di baris berikutnya dan mengatur warna latar belakang dan teks.

## Langkah 10: Menyimpan Dokumen PDF
Terakhir, kami menyimpan dokumen PDF ke lokasi yang ditentukan.

```csharp
// Simpan PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur direktori dan nama file yang diinginkan untuk file PDF keluaran.

### Contoh kode sumber untuk Mengekspor Data Lembar Kerja Excel ke Tabel menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// Mengakses lembar kerja pertama dalam file Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// Mengekspor konten 7 baris dan 2 kolom mulai dari sel ke-1 ke DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

// Membuat Instansi Dokumen
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Buat halaman dalam contoh dokumen
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Membuat objek Tabel
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Tambahkan objek Tabel dalam koleksi paragraf bagian
sec1.Paragraphs.Add(tab1);

// Mengatur lebar kolom tabel. Kita perlu menentukan ColumnCount secara manual.
// Karena lembar kerja excel saat ini memiliki tiga kolom, maka kami menentukan jumlah yang sama
tab1.ColumnWidths = "40 100 100";

// Mengatur batas sel default tabel menggunakan objek BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Impor data ke objek Tabel dari DataTable yang dibuat di atas
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// Dapatkan baris pertama dari tabel
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Ulangi semua sel di baris pertama dan atur warna latar belakangnya menjadi biru
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// Mengatur latar belakang semua sel pada baris pertama tabel.
	curCell.BackgroundColor = Color.Blue;
	// Mengatur jenis huruf untuk sel baris ke-1 dalam tabel.
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	// Atur warna font semua sel di baris ke-1 tabel.
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// Atur perataan teks untuk sel baris ke-1 sebagai Tengah.
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// Ulangi semua sel di baris pertama dan atur warna latar belakangnya menjadi biru
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// Mengatur warna latar belakang semua sel kecuali baris ke-1.
		curCell.BackgroundColor = Color.Gray;
		// Tetapkan warna Teks semua sel kecuali baris ke-1.
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

// Simpan PDFnya
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara mengekspor data dari lembar kerja Excel ke tabel PDF menggunakan pustaka Aspose.PDF for .NET. Kita membahas proses langkah demi langkah untuk memuat lembar kerja Excel, membuat dokumen PDF, menambahkan tabel, mengimpor data, dan memformat tabel. Kini Anda dapat membuat file PDF dengan tabel yang berisi data Excel secara terprogram.

### Pertanyaan yang Sering Diajukan

#### T: Apa tujuan mengekspor data lembar kerja Excel ke tabel PDF?

A: Mengekspor data lembar kerja Excel ke tabel PDF memungkinkan Anda menyajikan data dalam format terstruktur dan terorganisasi. Ini memungkinkan Anda membuat file PDF dengan tabel yang berisi data dari lembar kerja Excel, sehingga memudahkan untuk berbagi dan menyimpan informasi dalam format dokumen portabel.

#### T: Dapatkah saya menyesuaikan tampilan tabel PDF?

A: Ya, Anda dapat menyesuaikan tampilan tabel PDF menggunakan berbagai properti yang disediakan oleh Aspose.PDF untuk .NET. Dalam kode sumber C# yang disediakan, Anda dapat mengubah lebar kolom, batas sel, perataan teks, gaya font, dan lainnya sesuai dengan kebutuhan spesifik Anda.

#### T: Bagaimana cara menangani file Excel dengan beberapa lembar kerja?

 A: Dalam kode C# yang diberikan, kami mengakses lembar kerja pertama dalam file Excel menggunakan indeks`[0]` Jika file Excel Anda berisi beberapa lembar kerja, Anda dapat mengaksesnya dengan mengubah nilai indeks yang sesuai, seperti`[1]` untuk lembar kerja kedua atau`[2]` untuk lembar kerja ketiga.

#### T: Dapatkah saya menerapkan format berbeda pada baris atau sel tertentu dalam tabel PDF?

J: Ya, Anda dapat menerapkan format yang berbeda pada baris atau sel tertentu dalam tabel PDF. Dalam kode sumber C# yang diberikan, kami menunjukkan cara memformat baris pertama dan baris berikutnya secara berbeda dengan mengubah warna latar belakang, gaya fon, dan warna fon. Anda dapat menerapkan teknik pemformatan serupa pada baris atau sel tertentu sesuai kebutuhan.

#### T: Apakah Aspose.PDF untuk .NET satu-satunya pustaka yang memungkinkan pengeksporan data Excel ke tabel PDF?

J: Aspose.PDF untuk .NET adalah pustaka yang hebat untuk bekerja dengan dokumen PDF dalam aplikasi .NET. Meskipun mungkin ada pustaka lain yang tersedia, Aspose.PDF untuk .NET menawarkan berbagai fitur dan kemampuan untuk membuat, memanipulasi, dan mengekspor file PDF dengan tabel dari data Excel, menjadikannya pilihan populer untuk tugas-tugas tersebut.