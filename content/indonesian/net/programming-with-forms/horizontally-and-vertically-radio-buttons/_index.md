---
title: Tombol Radio Horizontal dan Vertikal
linktitle: Tombol Radio Horizontal dan Vertikal
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara membuat tombol radio yang selaras secara horizontal dan vertikal dalam PDF menggunakan Aspose.PDF untuk .NET dengan tutorial langkah demi langkah ini.
type: docs
weight: 180
url: /id/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
## Perkenalan

Membuat formulir PDF interaktif dapat meningkatkan pengalaman pengguna secara signifikan, terutama dalam hal pengumpulan informasi. Salah satu elemen formulir yang paling umum adalah tombol radio, yang memungkinkan pengguna untuk memilih satu opsi dari sekumpulan opsi. Dalam tutorial ini, kita akan menjelajahi cara membuat tombol radio yang sejajar secara horizontal dan vertikal menggunakan Aspose.PDF untuk .NET. Apakah Anda seorang pengembang berpengalaman atau baru memulai, panduan ini akan memandu Anda melalui proses tersebut langkah demi langkah, memastikan Anda memiliki pemahaman yang jelas tentang setiap bagian.

## Prasyarat

Sebelum menyelami kodenya, ada beberapa prasyarat yang harus Anda penuhi:

1.  Aspose.PDF untuk .NET: Pastikan Anda telah menginstal pustaka Aspose.PDF. Anda dapat mengunduhnya dari[lokasi](https://releases.aspose.com/pdf/net/).
2. Visual Studio: Lingkungan pengembangan tempat Anda dapat menulis dan menguji kode Anda.
3. Pengetahuan Dasar C#: Keakraban dengan pemrograman C# akan membantu Anda memahami potongan kode dengan lebih baik.

## Paket Impor

Untuk memulai, Anda perlu mengimpor paket yang diperlukan ke dalam proyek C# Anda. Berikut cara melakukannya:

### Buat Proyek Baru

Buka Visual Studio dan buat proyek C# baru. Anda dapat memilih Aplikasi Konsol untuk mempermudah.

### Tambahkan Referensi Aspose.PDF

1. Klik kanan pada proyek Anda di Solution Explorer.
2. Pilih "Kelola Paket NuGet."
3. Cari "Aspose.PDF" dan instal versi terbaru.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Facades;
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

Sekarang setelah Anda menyiapkan semuanya, mari kita uraikan kode untuk membuat tombol radio yang selaras secara horizontal dan vertikal.

## Langkah 1: Siapkan Direktori Dokumen

Pada langkah ini, kita akan menentukan jalur ke direktori tempat dokumen PDF Anda akan disimpan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya tempat Anda ingin menyimpan berkas PDF. Hal ini penting karena memberi tahu program tempat mencari berkas masukan dan tempat menyimpan berkas keluaran.

## Langkah 2: Muat Dokumen PDF yang Ada

 Selanjutnya, kita perlu memuat dokumen PDF yang akan kita kerjakan. Ini dilakukan dengan menggunakan`FormEditor` kelas.

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

Di sini, kita membuat sebuah instance dari`FormEditor` dan mengikatnya ke file PDF yang ada bernama`input.pdf`Pastikan berkas ini ada di direktori yang Anda tentukan.

## Langkah 3: Konfigurasikan Properti Tombol Radio

Sekarang, mari kita tetapkan beberapa properti untuk tombol radio kita. Ini termasuk jarak antar tombol, orientasinya, dan ukurannya.

```csharp
formEditor.RadioGap = 4; // Jarak antara opsi tombol radio
formEditor.RadioHoriz = true; // Atur ke benar untuk perataan horizontal
formEditor.RadioButtonItemSize = 20; // Ukuran tombol radio
formEditor.Facade.BorderWidth = 1; // Lebar perbatasan
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Warna batas
```

 Properti ini akan membantu menentukan bagaimana tombol radio akan muncul di PDF.`RadioGap` properti mengontrol ruang antara tombol, sementara`RadioHoriz` menentukan tata letaknya.

## Langkah 4: Tambahkan Tombol Radio Horizontal

Sekarang, mari tambahkan tombol radio horizontal ke PDF.

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

 Dalam kode ini, kami mendefinisikan item untuk tombol radio dan menambahkannya ke PDF.`AddField`Metode ini mengambil beberapa parameter, termasuk jenis bidang, nama bidang, dan koordinat penempatan.

## Langkah 5: Tambahkan Tombol Radio Vertikal

Selanjutnya, kita akan menambahkan tombol radio vertikal. Untuk melakukannya, kita perlu mengubah orientasi kembali ke vertikal.

```csharp
formEditor.RadioHoriz = false; // Atur ke false untuk perataan vertikal
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

Sama seperti sebelumnya, kami mendefinisikan item dan menambahkannya ke PDF, tetapi kali ini akan disejajarkan secara vertikal.

## Langkah 6: Simpan Dokumen PDF

Terakhir, kita perlu menyimpan dokumen PDF yang sudah dimodifikasi.

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
```

Kode ini menyimpan PDF dengan tombol radio yang baru ditambahkan. Pastikan untuk memeriksa direktori yang ditentukan untuk file output.

## Kesimpulan

Membuat tombol radio dalam PDF menggunakan Aspose.PDF untuk .NET adalah proses yang mudah. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat dengan mudah menambahkan tombol radio yang sejajar secara horizontal dan vertikal ke formulir PDF Anda. Ini tidak hanya meningkatkan interaktivitas dokumen Anda tetapi juga meningkatkan pengalaman pengguna secara keseluruhan. Jadi, silakan dan cobalah!

## Pertanyaan yang Sering Diajukan

### Apa itu Aspose.PDF untuk .NET?
Aspose.PDF untuk .NET adalah pustaka hebat yang memungkinkan pengembang untuk membuat, memanipulasi, dan mengonversi dokumen PDF secara terprogram.

### Dapatkah saya menggunakan Aspose.PDF secara gratis?
 Ya, Aspose menawarkan versi uji coba gratis yang dapat Anda gunakan untuk mengevaluasi pustaka. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/).

### Bagaimana cara mendapatkan dukungan untuk Aspose.PDF?
 Anda bisa mendapatkan dukungan dengan mengunjungi[Forum Aspose](https://forum.aspose.com/c/pdf/10).

### Apakah mungkin untuk membuat elemen formulir lain dengan Aspose.PDF?
Tentu saja! Aspose.PDF mendukung berbagai elemen formulir, termasuk kolom teks, kotak centang, dan dropdown.

### Di mana saya dapat membeli Aspose.PDF untuk .NET?
 Anda dapat membeli Aspose.PDF untuk .NET dari[halaman pembelian](https://purchase.aspose.com/buy).