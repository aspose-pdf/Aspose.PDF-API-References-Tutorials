---
title: Sesuaikan Otomatis ke Jendela
linktitle: Sesuaikan Otomatis ke Jendela
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menyesuaikan tabel secara otomatis ke jendela menggunakan Aspose.PDF untuk .NET dalam panduan terperinci langkah demi langkah ini. Sempurna untuk membuat tabel yang bagus dan pas dalam PDF.
type: docs
weight: 50
url: /id/net/programming-with-tables/auto-fit-to-window/
---
## Perkenalan

Saat bekerja dengan PDF, biasanya kita berurusan dengan tabel, dan ada kalanya Anda ingin tabel tersebut pas dengan lebar halaman. Dalam tutorial ini, kita akan mempelajari cara menyesuaikan tabel secara otomatis ke jendela menggunakan Aspose.PDF for .NET. Ini dapat membuat tabel Anda terlihat rapi dan teratur, mencegah masalah seperti kolom yang meluap atau tidak rata. Siap untuk belajar? Mari kita mulai!

## Prasyarat

Sebelum kita masuk ke panduan langkah demi langkah, ada beberapa hal yang Anda perlukan:

1. Aspose.PDF untuk .NET terpasang di proyek Anda. Jika Anda belum memilikinya, Anda dapat[unduh disini](https://releases.aspose.com/pdf/net/) atau jelajahi mereka[versi uji coba gratis](https://releases.aspose.com/).
2. Pemahaman dasar tentang pemrograman .NET.
3. Visual Studio atau IDE apa pun yang mendukung .NET terinstal di sistem Anda.

>  PS Jangan lupa Anda memerlukan lisensi untuk menggunakan Aspose.PDF tanpa batasan. Anda dapat membeli satu[Di Sini](https://purchase.aspose.com/buy) atau dapatkan[lisensi sementara](https://purchase.aspose.com/temporary-license/) untuk mencoba semua fitur.

## Paket Impor

Sebelum masuk ke kode, Anda perlu mengimpor namespace yang diperlukan:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Sekarang setelah semuanya siap, mari kita uraikan menjadi beberapa langkah sederhana dan mudah dicerna untuk memahami cara menyesuaikan tabel secara otomatis ke jendela menggunakan Aspose.PDF untuk .NET.

## Langkah 1: Inisialisasi Objek Dokumen

Pertama, Anda perlu membuat dokumen PDF. Anggap dokumen ini sebagai lembar kosong tempat Anda akan menambahkan halaman dan tabel.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat instance objek Pdf dengan memanggil konstruktor kosongnya
Document doc = new Document();
```
  
 Di sini, kita membuat dokumen baru menggunakan`Document` kelas dari Aspose.PDF.`dataDir` adalah lokasi penyimpanan PDF Anda setelah Anda selesai.

## Langkah 2: Tambahkan Halaman ke Dokumen

Dokumen PDF butuh beberapa halaman, bukan? Mari kita tambahkan satu halaman.

```csharp
// Membuat bagian (halaman) di objek Pdf
Page sec1 = doc.Pages.Add();
```
  
 Kami menambahkan halaman baru ke dokumen menggunakan`Pages.Add()` metode. Anda dapat menganggapnya sebagai penambahan lembar baru ke dokumen Anda, tempat Anda akan meletakkan tabel.

## Langkah 3: Membuat dan Mengonfigurasi Tabel

Sekarang saatnya membuat tabel dan menyesuaikannya agar pas di dalam jendela.

```csharp
// Membuat instance objek tabel
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Tambahkan tabel dalam kumpulan paragraf bagian yang diinginkan
sec1.Paragraphs.Add(tab1);
```
  
 Kami menginisialisasi yang baru`Table` objek dan menambahkannya ke koleksi paragraf halaman. Setiap halaman PDF dapat memiliki paragraf yang berbeda, dan di sini kita memperlakukan tabel sebagai paragraf.

## Langkah 4: Tentukan Lebar Kolom dan Sesuaikan Otomatis ke Jendela

Berikutnya, kita atur lebar kolom dan pastikan tabel menyesuaikan diri agar pas dengan jendela.

```csharp
// Mengatur lebar kolom untuk tabel
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
```
  
 Kami menetapkan lebar kolom tetap untuk tabel tetapi juga menambahkan`ColumnAdjustment.AutoFitToWindow`, yang memastikan bahwa tabel menyesuaikan ukurannya agar sesuai dengan jendela yang tersedia.

## Langkah 5: Mengatur Batas dan Margin untuk Tabel dan Sel

Tabel tanpa batas sering kali tidak dapat dibaca. Mari tentukan batas dan margin agar terlihat rapi.

```csharp
// Mengatur batas sel default menggunakan objek BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Tetapkan batas tabel menggunakan objek BorderInfo lain yang disesuaikan
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);

// Buat objek MarginInfo dan atur margin kiri, bawah, kanan, dan atasnya
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;

// Tetapkan bantalan sel default ke objek MarginInfo
tab1.DefaultCellPadding = margin;
```
  
 Batas ditambahkan ke tabel dan sel menggunakan`BorderInfo` kelas, tempat Anda menentukan ketebalan. Margin diatur untuk memberi sel ruang padding.

## Langkah 6: Tambahkan Baris dan Sel ke Tabel

Tabel tanpa konten? Itu tidak bagus! Mari tambahkan beberapa baris dan sel.

```csharp
//Buat baris dalam tabel dan kemudian sel dalam baris
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");

Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
```
  
Kita membuat dua baris dan menambahkan tiga sel ke setiap baris. Di sinilah Anda akan memasukkan data aktual (yang bisa berupa apa saja mulai dari string hingga elemen yang lebih kompleks).

## Langkah 7: Simpan Dokumen

Setelah semuanya diatur, Anda sebaiknya menyimpan dokumen PDF yang baru Anda buat.

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
// Simpan dokumen yang diperbarui yang berisi objek tabel
doc.Save(dataDir);
```
  
 Itu`doc.Save()` metode menyimpan PDF ke direktori yang ditentukan. Dalam hal ini, dokumen akan disimpan sebagai`AutoFitToWindow_out.pdf` di direktori yang Anda tentukan.

## Kesimpulan

Nah, itu dia! Anda baru saja membuat tabel yang secara otomatis sesuai dengan jendela menggunakan Aspose.PDF for .NET. Ini tidak hanya memastikan tabel Anda terlihat profesional dan sesuai, tetapi juga memberi Anda fleksibilitas saat bekerja dengan berbagai ukuran data. Baik Anda membuat laporan, faktur, atau dokumen apa pun yang memerlukan tabel, metode ini adalah cara yang bagus untuk mempertahankan tata letak yang bersih dan mudah dibaca.

## Pertanyaan yang Sering Diajukan

### Bisakah saya menambahkan lebih banyak baris secara dinamis?  
 Ya, Anda dapat terus menambahkan baris menggunakan`tab1.Rows.Add()` metode yang didasarkan secara dinamis pada konten.

### Bagaimana cara menyesuaikan tabel jika saya tidak menginginkannya disesuaikan secara otomatis?  
 Anda dapat mengatur secara manual`ColumnWidths` tanpa menggunakan`ColumnAdjustment.AutoFitToWindow` untuk mempertahankan lebar tabel tetap.

### Bisakah saya menambahkan gambar atau konten lain di dalam sel?  
Ya, Aspose.PDF memungkinkan Anda menambahkan gambar, teks, dan bahkan tabel lain di dalam sel!

### Bagaimana jika saya membutuhkan gaya tabel yang lebih kompleks?  
Anda dapat menyesuaikan gaya tabel dan sel lebih lanjut dengan menggunakan properti seperti warna latar belakang, perataan teks, dan pengaturan font.

### Apakah mungkin untuk mengekspor tabel ini ke format selain PDF?  
Tentu saja! Aspose.PDF mendukung ekspor ke berbagai format seperti HTML, DOCX, dan banyak lagi.