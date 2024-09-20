---
title: Render Tabel Dalam Dokumen PDF
linktitle: Render Tabel Dalam Dokumen PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Buat PDF profesional dengan mudah dengan membuat tabel menggunakan Aspose.PDF untuk .NET. Ikuti panduan langkah demi langkah kami untuk menguasai pembuatan dokumen.
type: docs
weight: 170
url: /id/net/programming-with-tables/render-table/
---
## Perkenalan

Membuat PDF yang tampak profesional secara terprogram mungkin tampak seperti tugas yang berat, tetapi dengan Aspose.PDF untuk .NET, hal itu menjadi mudah. Baik Anda membuat laporan, faktur, atau jenis dokumen lain yang memerlukan data tabular, Aspose.PDF menawarkan alat yang Anda butuhkan. Dalam tutorial ini, kita akan mempelajari cara merender tabel dalam dokumen PDF langkah demi langkah. Pada akhirnya, Anda akan memiliki pemahaman yang kuat tentang cara memanipulasi tabel, mengelola properti halaman, dan menyimpan file PDF dengan mudah.

## Prasyarat

Sebelum kita masuk ke kodenya, berikut ini yang Anda perlukan:

-  Visual Studio: Pastikan Anda telah menginstal Visual Studio di komputer Anda. Anda dapat mengunduhnya[Di Sini](https://visualstudio.microsoft.com/downloads/).
-  Aspose.PDF untuk .NET: Anda dapat dengan mudah mengunduh pustaka Aspose.PDF dari[Halaman rilis Aspose](https://releases.aspose.com/pdf/net/).
- Pengetahuan Dasar C#: Memahami dasar-dasar C# akan membantu Anda mengikutinya dengan lebih baik.
- .NET Framework: Idealnya, pastikan Anda bekerja di lingkungan .NET yang kompatibel.

Setelah Anda menetapkan prasyarat ini, Anda siap untuk mulai membuat dokumen PDF Anda!

## Paket Impor

Di awal berkas C#, Anda perlu mengimpor namespace Aspose.PDF yang diperlukan. Ini memungkinkan Anda untuk memanfaatkan fungsionalitas pustaka dalam proyek kita.

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

 Pastikan Anda telah menambahkan referensi yang diperlukan ke pustaka Aspose.PDF di proyek Anda. Jika Anda menggunakan NuGet, Anda dapat dengan mudah menambahkannya dengan mencari`Aspose.PDF`.

Setelah semuanya siap, mari kita bagi prosesnya menjadi beberapa langkah yang mudah untuk membuat tabel dalam dokumen PDF. Jangan khawatir; saya akan memandu Anda melalui setiap langkah dengan instruksi yang jelas!

## Langkah 1: Siapkan Info Dokumen dan Halaman

Pertama-tama, kita perlu membuat dokumen baru dan mengonfigurasi pengaturan halamannya. Berikut cara melakukannya:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo.Left = 37;
marginInfo.Right = 37;
marginInfo.Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

Penjelasan: 
- Kita mulai dengan menentukan di mana dokumen kita akan disimpan (`dataDir`). 
-  Kemudian, kita membuat instance baru dari`Document` kelas. 
- Kami mengonfigurasi margin halaman untuk menciptakan ruang bernapas di sekitar tabel kami.
- Terakhir, kami mengatur dokumen ke orientasi lanskap, yang membantu saat menampilkan tabel yang lebih lebar.

## Langkah 2: Buat Tabel Pertama

Selanjutnya, mari buat tabel pertama kita dan isi dengan beberapa contoh data:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "50 100"; // Tentukan lebar kolom
```

 Penjelasan: Di sini, kita membuat instance`Table` kelas dan atur lebar kolom. Kolom pertama akan memiliki lebar 50 unit, dan kolom kedua akan memiliki lebar 100 unit.

## Langkah 3: Isi Tabel dengan Baris

Sekarang, mari kita tambahkan baris ke tabel kita dalam satu loop:

```csharp
Page curPage = doc.Pages.Add(); // Menambahkan halaman baru
for (int i = 1; i <= 120; i++)
{
    Aspose.Pdf.Row row = table.Rows.Add();
    row.FixedRowHeight = 15; // Tetapkan tinggi tetap untuk baris
    
    Aspose.Pdf.Cell cell1 = row.Cells.Add();
    cell1.Paragraphs.Add(new TextFragment("Content 1"));
    
    Aspose.Pdf.Cell cell2 = row.Cells.Add();
    cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
```

Penjelasan: 
- Di sini kita membuat halaman baru untuk menambahkan tabel kita.
-  Kami menggunakan`for` loop untuk menambahkan 120 baris ke tabel kita. Setiap baris memiliki tinggi tetap 15 unit.
- Di dalam setiap baris, kita menambahkan dua sel dan mengisinya dengan teks.

## Langkah 4: Tambahkan Tabel Pertama ke Halaman

Setelah kita mengisi tabel, kita akan menambahkannya ke halaman saat ini:

```csharp
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs.Add(table);
```

Penjelasan: Langkah ini hanya menambahkan tabel yang kita buat ke paragraf halaman saat ini, sehingga tabel tersebut terlihat dalam dokumen PDF.

## Langkah 5: Buat Tabel Kedua

Sekarang, mari buat tabel kedua dengan konten berbeda dan tambahkan ke halaman baru:

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
    Aspose.Pdf.Row row = table1.Rows.Add();
    Aspose.Pdf.Cell cell1 = row.Cells.Add();
    cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
    
    Aspose.Pdf.Cell cell2 = row.Cells.Add();
    cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true; // Mengatur tabel kedua agar muncul di halaman baru
paragraphs.Add(table1);
```

Penjelasan: 
- Potongan kode ini membuat tabel baru dengan dua kolom, keduanya lebarnya 100 unit.
-  A`for` loop menambahkan 10 baris dengan konten sampel.
-  Dengan pengaturan`table1.IsInNewPage` untuk benar, kami memastikan tabel ini muncul di halaman baru, menjaga semuanya tetap teratur dan rapi.

## Langkah 6: Simpan Dokumen

Sekarang tabel kita sudah siap, mari simpan dokumen kita:

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);
```

 Penjelasan: Kami menentukan nama file dan menyimpan dokumen di direktori yang ditentukan. Saat Anda menjalankan kode ini, file PDF berjudul`IsNewPageProperty_Test_out.pdf` akan dibuat di lokasi yang Anda tentukan.

## Langkah 7: Pesan Konfirmasi

Terakhir, untuk memberi tahu pengguna bahwa semuanya berjalan lancar, kita dapat menambahkan pesan konsol yang ramah:

```csharp
Console.WriteLine("\nTable rendered successfully on a page.\nFile saved at " + dataDir);
```

Penjelasan: Ini adalah cara sederhana untuk mengonfirmasi bahwa operasi berhasil dan di mana pengguna dapat menemukan berkas PDF baru mereka.

## Kesimpulan

Nah, itu dia! Anda telah berhasil membuat tabel dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Hanya dengan beberapa baris kode, Anda dapat menangani dan menyajikan sejumlah besar data dalam format yang terorganisasi, sehingga dokumen Anda informatif sekaligus menarik secara visual. Baik Anda mengerjakan daftar inventaris, laporan keuangan, atau dokumen pendidikan, tabel merupakan cara yang sangat baik untuk menyampaikan informasi yang rumit secara sekilas.

## Pertanyaan yang Sering Diajukan

### Bisakah saya menyesuaikan tampilan tabel di Aspose.PDF?  
Tentu saja! Anda dapat menyesuaikan warna, batas, gaya font, dan properti lainnya untuk menyempurnakan tampilan tabel Anda.

### Apakah Aspose.PDF gratis untuk digunakan?  
 Aspose.PDF menawarkan versi uji coba gratis, tetapi untuk penggunaan komersial, diperlukan pembelian. Anda dapat memeriksa harganya[Di Sini](https://purchase.aspose.com/buy).

### Bagaimana saya bisa mendapatkan dukungan untuk masalah Aspose.PDF?  
 Anda dapat mencari bantuan dari forum dukungan Aspose[Di Sini](https://forum.aspose.com/c/pdf/10).

### Apakah ada batasan untuk versi uji coba gratis?  
 Ya, versi uji coba mungkin memiliki batasan tertentu, seperti pemberian tanda air pada dokumen yang dihasilkan. Untuk fungsionalitas penuh, pertimbangkan untuk mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).

### Di mana saya dapat menemukan informasi lebih lanjut tentang fitur Aspose.PDF?  
 Anda dapat menjelajahi dokumentasi lengkap yang tersedia[Di Sini](https://reference.aspose.com/pdf/net/).