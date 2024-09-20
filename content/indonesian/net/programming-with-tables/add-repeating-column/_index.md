---
title: Tambahkan Kolom Berulang Dalam Dokumen PDF
linktitle: Tambahkan Kolom Berulang Dalam Dokumen PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menambahkan kolom berulang ke dokumen PDF menggunakan Aspose.PDF untuk .NET. Panduan langkah demi langkah dengan contoh dan kode. Sempurna untuk pengembang.
type: docs
weight: 20
url: /id/net/programming-with-tables/add-repeating-column/
---
## Perkenalan

Jika Anda bekerja dengan dokumen PDF dan perlu menambahkan kolom berulang, Anda berada di tempat yang tepat! Dengan menggunakan Aspose.PDF untuk .NET, Anda dapat mengelola tabel dan konten dalam PDF dengan mudah. Baik Anda membuat laporan dinamis, faktur, atau dokumen terstruktur lainnya, kolom berulang dapat menjadi pengubah permainan dalam mengatur data. Mari selami panduan langkah demi langkah tentang cara menambahkan kolom berulang ke dokumen PDF.

## Prasyarat

Sebelum kita masuk ke kode, mari pastikan Anda sudah menyiapkan semuanya:

- Aspose.PDF untuk .NET: Anda perlu menginstal pustaka Aspose.PDF untuk .NET di proyek Anda.
- [Unduh Aspose.PDF untuk .NET](https://releases.aspose.com/pdf/net/)
- [Uji Coba Gratis](https://releases.aspose.com/)
- Lingkungan Pengembangan: Pastikan Anda memiliki IDE yang kompatibel dengan .NET seperti Visual Studio yang terpasang.
- Pemahaman Dasar C#: Meskipun kami akan menguraikan semuanya, pemahaman dasar C# akan membantu Anda mengikutinya dengan lancar.
  
 Jika Anda belum memiliki Aspose.PDF untuk .NET, Anda bisa mendapatkannya[lisensi sementara](https://purchase.aspose.com/temporary-license/) untuk mulai menjelajahi fitur-fiturnya.

## Paket Impor

Untuk memulai, Anda perlu mengimpor namespace yang diperlukan dari Aspose.PDF untuk .NET. Berikut cara melakukannya:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Paket-paket ini menyediakan kelas-kelas dan metode-metode penting yang dibutuhkan untuk bekerja dengan dokumen PDF dan memanipulasi tabel.

Sekarang, mari kita bagi prosesnya menjadi beberapa langkah untuk menambahkan kolom berulang ke dokumen PDF. Ikuti langkah-langkahnya!

## Langkah 1: Tetapkan Jalur ke Direktori Dokumen Anda

Sebelum kita membuat atau memanipulasi berkas apa pun, kita perlu menentukan jalur tempat PDF yang dihasilkan akan disimpan. Dalam proyek C# Anda, tetapkan jalur direktori tempat berkas Anda akan ditempatkan:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
```

 Jalur ini menunjuk ke direktori tempat PDF keluaran akan disimpan. Ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya di mesin Anda.

## Langkah 2: Buat Dokumen PDF Baru

 Untuk memulai, buat instance baru`Document` objek. Ini akan berfungsi sebagai wadah untuk semua halaman dan konten dalam PDF.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

 Di sini, kami telah membuat dokumen PDF baru dan menambahkan halaman kosong ke dalamnya.`doc.Pages.Add()` metode menyisipkan halaman baru ke dalam dokumen.

## Langkah 3: Buat Instansiasi Tabel Luar

Selanjutnya, kita buat tabel luar. Tabel ini akan membentang sepanjang lebar halaman dan berfungsi sebagai wadah bagi tabel-tabel lain, termasuk tabel yang akan memuat kolom-kolom yang berulang.

```csharp
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;
```

 Kami telah mengatur`ColumnWidths` properti menjadi "100%", yang berarti tabel akan membentang di seluruh lebar halaman.

## Langkah 4: Buat Tabel Dalam

 Sekarang, mari kita buat tabel bagian dalam, yang akan memiliki kolom berulang. Properti kunci di sini adalah`Broken` , yang memungkinkan tabel untuk terus berlanjut di halaman yang sama, dan`ColumnAdjustment`, yang secara otomatis menyesuaikan lebar kolom agar sesuai dengan konten.

```csharp
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

Tabel bagian dalam ini akan disarangkan di dalam tabel bagian luar.

## Langkah 5: Tambahkan Tabel ke Halaman

Sekarang setelah tabel luar dan dalam siap, mari tambahkan keduanya ke halaman. Langkah ini memastikan bahwa tabel disertakan dalam struktur dokumen.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
```

 Di sini, kami menambahkan`outerTable` ke halaman, dan kemudian di dalam tabel luar, kami menumpuk`mytable` Selain itu, kami juga menetapkan`RepeatingColumnsCount`hingga 5, yang menentukan berapa banyak kolom yang harus diulang saat data ditambahkan.

## Langkah 6: Tambahkan Baris Header

Sekarang saatnya menambahkan tajuk ke tabel. Baris tajuk memberikan konteks pada data dan membantu menyusun kolom. 

```csharp
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");
```

Potongan kode ini menambahkan baris pertama (yang akan kita gunakan sebagai header), dan mengisinya dengan sel yang berisi teks seperti “header 1”, “header 2”, dan seterusnya.

## Langkah 7: Tambahkan Baris Data

Terakhir, kita dapat menambahkan beberapa data ke dalam tabel. Perulangan ini secara dinamis membuat baris dan mengisi sel dengan konten:

```csharp
for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
    Aspose.Pdf.Row row1 = mytable.Rows.Add();
    row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
```

Perulangan ini diulang enam kali, menambahkan baris dan mengisi setiap sel dengan data kolom yang sesuai (misalnya, “kolom 1, 1”, “kolom 2, 2”, dst.).

## Langkah 8: Simpan Dokumen

Setelah semua baris dan kolom ditambahkan, langkah terakhir adalah menyimpan dokumen ke jalur file yang ditentukan.

```csharp
doc.Save(outFile);
```

Dokumen Anda sekarang disimpan dengan kolom yang berulang!

## Kesimpulan

Nah, itu dia! Dengan langkah-langkah sederhana ini, Anda dapat membuat dokumen PDF dengan kolom berulang menggunakan Aspose.PDF untuk .NET. Dengan memanfaatkan fleksibilitas tabel bersarang, Anda dapat memperoleh tata letak kompleks yang membuat PDF Anda tampak profesional dan teratur. Cobalah ini untuk proyek Anda berikutnya dan jelajahi potensi penuh Aspose.PDF untuk menangani kebutuhan pembuatan PDF Anda.

## Pertanyaan yang Sering Diajukan

### Apa itu Aspose.PDF untuk .NET?
Aspose.PDF untuk .NET adalah pustaka hebat yang memungkinkan pengembang untuk membuat, mengedit, dan mengelola dokumen PDF secara terprogram.

### Dapatkah saya menyesuaikan jumlah kolom berulang secara dinamis?
 Ya, Anda dapat mengubah jumlah kolom berulang dengan memodifikasi`RepeatingColumnsCount` milik.

### Bagaimana cara mengajukan lisensi ke Aspose.PDF untuk .NET?
 Anda dapat menerapkan lisensi dari file atau aliran dengan mengikuti[dokumentasi](https://reference.aspose.com/pdf/net/).

### Apakah mungkin untuk menambahkan gambar ke sel tabel?
Ya, Aspose.PDF untuk .NET mendukung penambahan berbagai jenis konten, termasuk gambar, ke sel tabel.

### Bisakah saya menyesuaikan tata letak tabel lebih lanjut?
Tentu saja! Aspose.PDF menyediakan fitur-fitur lengkap untuk menyesuaikan gaya tabel, termasuk border, padding, alignment, dan banyak lagi.