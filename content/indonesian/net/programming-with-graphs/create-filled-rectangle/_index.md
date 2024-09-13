---
title: Buat Persegi Panjang Terisi
linktitle: Buat Persegi Panjang Terisi
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara membuat persegi panjang yang terisi dalam PDF menggunakan Aspose.PDF for .NET dengan tutorial langkah demi langkah ini. Sempurna untuk pengembang dari semua tingkatan.
type: docs
weight: 50
url: /id/net/programming-with-graphs/create-filled-rectangle/
---
## Perkenalan

Pernahkah Anda ingin membuat PDF yang menarik secara visual secara terprogram? Jika ya, Anda berada di tempat yang tepat! Dalam tutorial ini, kita akan menyelami dunia Aspose.PDF untuk .NET, pustaka canggih yang memungkinkan Anda memanipulasi dokumen PDF dengan mudah. Hari ini, kita akan fokus pada pembuatan persegi panjang yang terisi dalam file PDF. Apakah Anda seorang pengembang berpengalaman atau baru memulai, panduan ini akan memandu Anda melalui setiap langkah dengan cara yang ramah dan menarik. Jadi, ambil topi pengodean Anda, dan mari kita mulai!

## Prasyarat

Sebelum kita masuk ke kode, ada beberapa hal yang perlu Anda siapkan:

1. Visual Studio: Pastikan Anda telah menginstal Visual Studio di komputer Anda. Ini adalah IDE yang fantastis untuk pengembangan .NET.
2.  Aspose.PDF untuk .NET: Anda perlu mengunduh dan menginstal pustaka Aspose.PDF. Anda dapat menemukannya[Di Sini](https://releases.aspose.com/pdf/net/).
3. Pengetahuan Dasar C#: Sedikit pengetahuan dengan pemrograman C# akan membantu Anda memahami potongan kode dengan lebih baik.

## Paket Impor

Untuk memulai, Anda perlu mengimpor paket yang diperlukan ke dalam proyek C# Anda. Berikut cara melakukannya:

### Buat Proyek Baru

Buka Visual Studio dan buat proyek C# baru. Anda dapat memilih Aplikasi Konsol untuk mempermudah.

### Tambahkan Referensi Aspose.PDF

1. Klik kanan pada proyek Anda di Solution Explorer.
2. Pilih "Kelola Paket NuGet."
3. Cari "Aspose.PDF" dan instal versi terbaru.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Sekarang setelah semuanya disiapkan, mari masuk ke kodenya!

## Langkah 1: Siapkan Direktori Dokumen Anda

Pertama-tama, Anda perlu menentukan jalur penyimpanan PDF Anda. Ini penting karena jalur ini memberi tahu program tempat membuat file.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya pada komputer Anda tempat Anda ingin menyimpan PDF.

## Langkah 2: Buat Contoh Dokumen

 Selanjutnya, kita akan membuat sebuah instance dari`Document`Kelas ini mewakili dokumen PDF yang akan Anda gunakan.

```csharp
// Buat contoh Dokumen
Document doc = new Document();
```

Baris ini menginisialisasi dokumen PDF baru yang dapat kita manipulasi.

## Langkah 3: Tambahkan Halaman ke Dokumen

Sekarang, mari tambahkan satu halaman ke dokumen kita. Setiap PDF memerlukan setidaknya satu halaman, bukan?

```csharp
// Tambahkan halaman ke koleksi halaman file PDF
Page page = doc.Pages.Add();
```

Kode ini menambahkan halaman baru ke dokumen, yang memungkinkan kita menggambar bentuk di atasnya.

## Langkah 4: Buat Contoh Grafik

 Untuk menggambar bentuk, kita perlu membuat`Graph` Misalnya, bayangkan grafik sebagai kanvas tempat Anda dapat menggambar berbagai bentuk.

```csharp
// Buat contoh Grafik
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100.0, 400.0);
```

Di sini, kita membuat grafik dengan lebar 100 dan tinggi 400.

## Langkah 5: Tambahkan Grafik ke Halaman

Sekarang setelah kita memiliki grafiknya, mari tambahkan ke halaman yang kita buat sebelumnya.

```csharp
// Tambahkan objek grafik ke koleksi paragraf dari contoh halaman
page.Paragraphs.Add(graph);
```

Garis ini menempelkan grafik ke halaman, membuatnya siap untuk digambar.

## Langkah 6: Buat Instansi Persegi Panjang

Berikutnya, kita akan membuat persegi panjang yang ingin kita isi dengan warna.

```csharp
// Buat instance Persegi Panjang
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
```

Dalam kode ini, kita mendefinisikan posisi dan ukuran persegi panjang. Parameter mewakili koordinat x dan y, lebar, dan tinggi.

## Langkah 7: Tentukan Warna Isi

Sekarang, mari kita pilih warna untuk persegi panjang kita. Kita akan mengisinya dengan warna merah untuk contoh ini.

```csharp
// Tentukan warna isian untuk objek Grafik
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

Baris ini mengatur warna isian persegi panjang menjadi merah. Anda dapat memilih warna apa pun yang Anda suka!

## Langkah 8: Tambahkan Persegi Panjang ke Grafik

Setelah persegi panjang kita siap, saatnya menambahkannya ke grafik.

```csharp
// Tambahkan objek persegi panjang ke koleksi bentuk objek Grafik
graph.Shapes.Add(rect);
```

Kode ini menambahkan persegi panjang ke grafik, menjadikannya bagian dari gambar kita.

## Langkah 9: Simpan Dokumen PDF

Terakhir, kita perlu menyimpan dokumen kita ke direktori yang ditentukan.

```csharp
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// Simpan file PDF
doc.Save(dataDir);
```

 Kode ini menyimpan file PDF dengan nama`CreateFilledRectangle_out.pdf` di direktori yang Anda tentukan sebelumnya.

## Langkah 10: Pesan Konfirmasi

Untuk memberi tahu kami bahwa semuanya berjalan lancar, kami dapat mencetak pesan konfirmasi.

```csharp
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);
```

Baris ini akan menampilkan pesan pada konsol, mengonfirmasi bahwa persegi panjang yang terisi telah berhasil dibuat.

## Kesimpulan

Nah, itu dia! Anda telah berhasil membuat persegi panjang yang terisi dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Pustaka canggih ini membuka banyak kemungkinan untuk manipulasi PDF, yang memungkinkan Anda membuat dokumen yang menakjubkan secara terprogram. Baik Anda membuat laporan, faktur, atau jenis PDF lainnya, Aspose.PDF siap membantu Anda.

## Pertanyaan yang Sering Diajukan

### Apa itu Aspose.PDF untuk .NET?
Aspose.PDF untuk .NET adalah pustaka yang memungkinkan pengembang untuk membuat, memanipulasi, dan mengonversi dokumen PDF secara terprogram.

### Dapatkah saya menggunakan Aspose.PDF secara gratis?
 Ya, Aspose menawarkan versi uji coba gratis yang dapat Anda gunakan untuk menjelajahi fitur-fitur pustaka. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/).

### Apakah ada cara untuk mendapatkan dukungan untuk Aspose.PDF?
 Tentu saja! Anda bisa mendapatkan dukungan melalui forum Aspose[Di Sini](https://forum.aspose.com/c/pdf/10).

### Bagaimana saya dapat membeli Aspose.PDF?
 Anda dapat membeli Aspose.PDF dengan mengunjungi halaman pembelian[Di Sini](https://purchase.aspose.com/buy).

### Jenis bentuk apa yang dapat saya buat dengan Aspose.PDF?
Anda dapat membuat berbagai bentuk, termasuk persegi panjang, lingkaran, garis, dan banyak lagi, menggunakan pustaka Aspose.PDF.