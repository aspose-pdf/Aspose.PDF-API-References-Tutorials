---
title: Ekspor Data Lembar Kerja Excel Ke Tabel
linktitle: Ekspor Data Lembar Kerja Excel Ke Tabel
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mengekspor data lembar kerja Excel ke tabel PDF menggunakan Aspose.PDF untuk .NET. Tutorial langkah demi langkah dengan contoh kode, prasyarat, dan kiat bermanfaat.
type: docs
weight: 70
url: /id/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
## Perkenalan

Pernahkah Anda perlu mengekspor data dari lembar kerja Excel ke dalam file PDF, yang disusun rapi dalam format tabel? Bayangkan memiliki banyak data di Excel, tetapi perlu membagikannya sebagai PDF yang tampak profesional. Kedengarannya rumit, bukan? Namun dengan Aspose.PDF untuk .NET, Anda dapat mengubah tugas ini menjadi mudah. Dalam tutorial ini, kami akan memandu Anda melalui proses mengekspor data lembar kerja Excel ke dalam tabel di dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Kami akan memandu Anda langkah demi langkah, menguraikan semuanya sehingga meskipun Anda baru dalam hal ini, Anda akan merasa seperti seorang profesional pada akhirnya.

## Prasyarat

Sebelum kita masuk ke pengkodean, mari kita siapkan beberapa hal:

1.  Aspose.PDF untuk Pustaka .NET – Pastikan Anda telah menginstal versi terbaru. Anda dapat[unduh disini](https://releases.aspose.com/pdf/net/).
2.  Pustaka Aspose.Cells untuk .NET – Anda memerlukan ini untuk menangani operasi Excel. Unduh dari[Di Sini](https://releases.aspose.com/cells/net/).
3. Lingkungan Pengembangan .NET – Alat seperti Visual Studio akan bekerja dengan sempurna untuk pengkodean.
4. Berkas Excel – Siapkan berkas Excel berisi data yang ingin diekspor.

 Jika Anda tidak memiliki pustaka Aspose.PDF dan Aspose.Cells, Anda dapat memulai dengan[uji coba gratis](https://releases.aspose.com/).

## Paket Impor

Untuk memulainya, pastikan Anda telah memasang pustaka Aspose.PDF dan Aspose.Cells di proyek Anda. Anda dapat memasangnya menggunakan NuGet Package Manager di Visual Studio.

Berikut cara mengimpor paket yang diperlukan dalam kode C# Anda:

```csharp
using System.Data;
using System.IO;
using System.Linq;
```

Sekarang setelah prasyarat ditetapkan, mari kita jalani proses mengekspor data dari lembar Excel ke tabel dalam dokumen PDF.

## Langkah 1: Muat Buku Kerja Excel

Untuk memulai, Anda perlu memuat buku kerja Excel ke dalam program. Pada langkah ini, kita akan menggunakan Aspose.Cells untuk membuka berkas Excel.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Memuat buku kerja Excel
Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

 Penjelasan: Di sini, kita tentukan jalur direktori tempat file Excel kita berada dan memuat buku kerja menggunakan`Aspose.Cells.Workbook` Pastikan untuk menyesuaikan`"YOUR DOCUMENT DIRECTORY"` untuk menunjuk ke lokasi berkas Anda.

## Langkah 2: Akses Lembar Kerja Pertama

Setelah memuat buku kerja, kita perlu mengakses lembar kerja pertama tempat data kita disimpan.

```csharp
// Mengakses lembar kerja pertama dalam file Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

Penjelasan: Langkah ini mudah—kita ambil lembar kerja pertama dari buku kerja, yang berisi data yang akan diekspor.

## Langkah 3: Ekspor Data ke DataTable

Sekarang, mari ekspor data dari lembar Excel ke objek DataTable, yang akan bertindak sebagai perantara untuk mentransfer data ke PDF.

```csharp
// Mengekspor konten 7 baris dan 2 kolom mulai dari sel ke-1 ke DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

 Penjelasan:`ExportDataTable` metode mengekstrak data mulai dari sel pertama lembar kerja dan mencakup semua baris dan kolom. Data ini kemudian disimpan dalam`DataTable` untuk penggunaan lebih lanjut.

## Langkah 4: Buat Dokumen PDF Baru

Berikutnya, kita perlu membuat dokumen PDF baru menggunakan Aspose.PDF.

```csharp
// Membuat instance Dokumen
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Buat halaman dalam contoh dokumen
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

 Penjelasan: Di sini kita menginisialisasi sebuah`Aspose.Pdf.Document`dan tambahkan halaman ke dalamnya. Halaman ini nantinya akan berisi tabel yang kita buat dari data Excel.

## Langkah 5: Buat Objek Tabel dalam PDF

Mari kita lanjutkan ke pembuatan tabel di dalam dokumen PDF.

```csharp
// Membuat objek Tabel
Aspose.Pdf.Table table = new Aspose.Pdf.Table();

// Tambahkan objek Tabel ke koleksi paragraf halaman
page.Paragraphs.Add(table);
```

 Penjelasan: Kami membuat sebuah`Aspose.Pdf.Table` objek dan menambahkannya ke koleksi paragraf halaman, yang memastikan bahwa tabel ditampilkan di halaman.

## Langkah 6: Mengatur Lebar dan Batas Kolom

Tabel dalam format PDF memerlukan lebar kolom yang ditentukan. Kami juga akan menambahkan batas agar tabel lebih mudah dibaca.

```csharp
// Mengatur lebar kolom tabel
table.ColumnWidths = "40 100 100";

// Tetapkan batas sel default
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

 Penjelasan: Kami mengatur lebar tiga kolom dan memberikan semua sel batas default dengan ketebalan`0.1F`.

## Langkah 7: Impor Data dari DataTable ke Tabel PDF

Sekarang, saatnya mengimpor data dari DataTable ke tabel PDF kita.

```csharp
// Mengimpor data ke objek Tabel dari DataTable
table.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Penjelasan:`ImportDataTable`metode mentransfer semua data dari`DataTable` ke tabel PDF. Ini akan mengisi tabel dengan data dari lembar Excel Anda.

## Langkah 8: Memberi Gaya pada Baris Header

Mari beri gaya pada baris tajuk tabel dengan mengubah warna latar belakang, font, dan perataan.

```csharp
// Dapatkan baris pertama dari tabel
Aspose.Pdf.Row headerRow = table.Rows[0];

// Mengatur gaya untuk baris tajuk
foreach (Aspose.Pdf.Cell cell in headerRow.Cells)
{
    cell.BackgroundColor = Color.Blue;
    cell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    cell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    cell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}
```

Penjelasan: Kita mengulang semua sel pada baris pertama (header) dan mengatur warna latar belakang menjadi biru, warna teks menjadi kuning, lalu meratakan teks ke tengah.

## Langkah 9: Tata Baris yang Tersisa

Untuk membedakan antara tajuk dan baris lainnya, mari tambahkan gaya berbeda untuk baris lainnya.

```csharp
for (int i = 1; i <= dataTable.Rows.Count; i++)
{
    foreach (Aspose.Pdf.Cell cell in table.Rows[i].Cells)
    {
        cell.BackgroundColor = Color.Gray;
        cell.DefaultCellTextState.ForegroundColor = Color.White;
    }
}
```

Penjelasan: Untuk semua baris kecuali header, kami menetapkan latar belakang abu-abu dan warna teks putih.

## Langkah 10: Simpan Dokumen PDF

Terakhir, simpan dokumen PDF dengan tabel.

```csharp
// Simpan PDFnya
pdfDocument.Save(dataDir + "Exceldata_toPdf_table.pdf");
```

Penjelasan: Kami menyimpan PDF ke direktori yang ditentukan. Voilà! Data Excel Anda sekarang ada di dalam tabel PDF yang diformat dengan indah.

## Kesimpulan

Nah, itu dia! Hanya dalam beberapa langkah, Anda telah mengekspor data dari lembar kerja Excel ke dalam tabel di dalam PDF menggunakan Aspose.PDF for .NET. Dengan memecah proses dan menatanya di sepanjang proses, Anda dapat menyesuaikan hasil dan memastikan data Anda terlihat bersih dan profesional. Jadi, lain kali seseorang memberi Anda file Excel dan meminta laporan PDF, Anda tahu persis apa yang harus dilakukan.

## Pertanyaan yang Sering Diajukan

### Bisakah saya menyesuaikan tabel lebih lanjut?
Tentu saja! Anda dapat mengubah warna, font, perataan, dan bahkan menambahkan batas pada sel tertentu.

### Apakah Aspose.PDF untuk .NET gratis?
 Ini menawarkan uji coba gratis, tetapi untuk penggunaan yang lebih lama, Anda memerlukan lisensi. Anda dapat[beli disini](https://purchase.aspose.com/buy).

### Bisakah saya mengekspor hanya baris dan kolom tertentu?
 Ya, Anda dapat mengubah parameter di`ExportDataTable` metode untuk mengekspor rentang tertentu.

### Apakah ini berfungsi dengan file Excel berukuran besar?
Ya, Aspose.Cells dirancang untuk menangani file Excel berukuran besar secara efisien.

### Bagaimana cara menambahkan lebih banyak halaman ke PDF?
 Anda dapat menggunakan`pdfDocument.Pages.Add()` untuk menambahkan halaman sebanyak yang Anda perlukan.