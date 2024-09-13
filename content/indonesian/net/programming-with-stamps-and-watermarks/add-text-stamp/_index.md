---
title: Tambahkan Stempel Teks Dalam File PDF
linktitle: Tambahkan Stempel Teks Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menambahkan stempel teks dalam berkas PDF menggunakan Aspose.PDF untuk .NET dengan panduan langkah demi langkah kami dan tingkatkan presentasi dokumen Anda.
type: docs
weight: 50
url: /id/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
## Perkenalan

Di era digital saat ini, PDF merupakan format umum untuk berbagi dan mengirimkan dokumen. Baik Anda seorang pengembang, kreator konten, atau sekadar seseorang yang ingin menyempurnakan file PDF mereka, mengetahui cara memanipulasi PDF secara terprogram dapat menjadi pengubah permainan. Salah satu fitur praktis yang mungkin ingin Anda manfaatkan adalah kemampuan untuk menambahkan stempel teks di file PDF Anda. Menambahkan stempel teks dapat memberikan sentuhan profesional pada dokumen Anda atau menyampaikan informasi penting, seperti "Contoh", "Rahasia", atau bahkan tanda air.

## Prasyarat

Sebelum kita mulai membuat kode, ada beberapa prasyarat untuk memastikan Anda telah menyiapkan semuanya dengan benar. Berikut ini yang Anda perlukan:

1.  Aspose.PDF untuk .NET: Pastikan Anda telah memasang pustaka Aspose.PDF di proyek Anda. Jika Anda belum melakukannya, Anda dapat mengunduhnya dari[Situs web Aspose](https://releases.aspose.com/pdf/net/).
2. Visual Studio atau IDE yang Kompatibel: Anda akan memerlukan lingkungan pengembangan untuk menulis dan menjalankan kode .NET Anda. Visual Studio adalah pilihan yang paling umum di antara para pengembang.
3. Pengetahuan Dasar C#: Keakraban dengan C# dan prinsip-prinsip pemrograman berorientasi objek akan membantu Anda memahami contoh-contoh dengan lebih baik.
4. Contoh Berkas PDF: Anda harus memiliki berkas PDF yang siap digunakan. Anda dapat membuat PDF dasar atau menggunakan PDF yang sudah ada untuk menguji fungsionalitasnya.

Setelah Anda menyelesaikan prasyarat ini, kita dapat beralih ke pengkodean!

## Paket Impor

Sekarang, mari impor paket-paket yang diperlukan. Langkah ini penting karena membuat kelas-kelas dan metode-metode dari pustaka Aspose tersedia dalam proyek Anda.

### Impor Aspose.PDF Assembly

Untuk memulai, Anda perlu mengimpor namespace Aspose.PDF. Di bagian atas file C# Anda, tambahkan perintah berikut:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Ini akan memungkinkan Anda untuk mengakses kelas-kelas yang penting untuk membuat dan memanipulasi dokumen PDF.

Sekarang, mari kita masuk ke inti tutorial. Kami akan menguraikan prosesnya menjadi beberapa langkah yang jelas dan ringkas. Setiap langkah akan memandu Anda melalui kode untuk menambahkan stempel teks ke berkas PDF.

## Langkah 1: Siapkan Direktori Dokumen

Pertama, Anda perlu menentukan direktori tempat dokumen PDF Anda disimpan. Ini berarti kode Anda perlu mengetahui tempat menemukan berkas PDF yang ingin Anda edit.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Penjelasan: Ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya tempat file PDF Anda (`AddTextStamp.pdf`) disimpan. Jalur ini digunakan nanti untuk membuka dan menyimpan PDF yang dimodifikasi.

## Langkah 2: Buka Dokumen PDF

 Selanjutnya kita akan membuka dokumen PDF dengan menggunakan`Document` kelas dari namespace Aspose.PDF.

```csharp
// Buka dokumen
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

 Penjelasan: Di sini, kita membuat sebuah instance dari`Document` class dan meneruskan jalur ke berkas PDF kita. Ini akan memuat PDF sehingga kita dapat memanipulasinya.

## Langkah 3: Buat Stempel Teks

Sekarang, kita akan membuat stempel teks yang nantinya akan kita terapkan pada dokumen PDF kita.

```csharp
// Buat stempel teks
TextStamp textStamp = new TextStamp("Sample Stamp");
```

 Penjelasan:`TextStamp` objek dibuat dengan teks yang ingin Anda tampilkan. Dalam kasus ini, kami menggunakan "Contoh Prangko" sebagai teks untuk prangko kami.

## Langkah 4: Mengatur Properti Stempel

Untuk menyesuaikan prangko Anda, kita dapat mengatur berbagai properti seperti warna latar belakang, posisi, dan rotasi. Mari kita lakukan itu sekarang:

```csharp
// Atur apakah stempel adalah latar belakang
textStamp.Background = true;

// Tetapkan asal
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Putar prangko
textStamp.Rotate = Rotation.on90;
```

Penjelasan:
- Latar Belakang: Mengatur ini ke`true` berarti cap akan muncul di belakang konten PDF.
- XIndent & YIndent: Properti ini menentukan posisi prangko pada halaman. Dalam contoh ini, prangko akan ditempatkan 100 unit dari tepi kiri dan atas halaman.
- Putar: Ini akan memutar prangko hingga 90 derajat. Anda dapat memilih opsi rotasi yang berbeda berdasarkan kebutuhan desain Anda.

## Langkah 5: Sesuaikan Properti Teks

Selanjutnya, mari berkreasi dengan menyesuaikan tampilan teks dalam prangko kita:

```csharp
// Mengatur properti teks
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(Color.Aqua);
```

Penjelasan:
- Font: Kami menggunakan font Arial dan membuatnya tebal dan miring.
- FontSize: Ditetapkan pada 14 poin.
- ForegroundColor: Menggunakan RGB untuk menyetel warna teks ke Aqua. Jangan ragu untuk mengubah warna agar sesuai dengan kebutuhan merek atau desain Anda!

## Langkah 6: Tambahkan Stempel ke Halaman PDF

Sekarang saatnya menambahkan prangko ke halaman tertentu pada dokumen PDF.

```csharp
// Tambahkan prangko ke halaman tertentu
pdfDocument.Pages[1].AddStamp(textStamp);
```

Penjelasan: Dalam contoh ini, prangko ditambahkan ke halaman pertama PDF (halaman diberi indeks 1). Sesuaikan nomor halaman sesuai kebutuhan dokumen Anda.

## Langkah 7: Simpan PDF yang Dimodifikasi

Terakhir, mari simpan dokumen dengan stempel teks yang baru ditambahkan.

```csharp
dataDir = dataDir + "AddTextStamp_out.pdf";

// Simpan dokumen keluaran
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);
```

Penjelasan: Kami menentukan jalur baru untuk berkas keluaran dan kemudian menyimpan dokumen yang dimodifikasi. Setelah disimpan, jalur tersebut dicetak ke konsol, yang mengonfirmasi keberhasilan operasi.

## Kesimpulan

Selamat! Anda telah berhasil menambahkan cap teks ke berkas PDF menggunakan Aspose.PDF untuk .NET. Metode ini memungkinkan Anda untuk memberi anotasi pada dokumen secara efisien, sehingga meningkatkan profesionalisme dan kegunaannya. Baik Anda menambahkan tanda air, tanda tangan, atau catatan sederhana, pustaka Aspose menyediakan alat yang hebat untuk memanipulasi PDF Anda dengan mudah.

## Pertanyaan yang Sering Diajukan

### Apa itu stempel teks dalam PDF?
Stempel teks adalah hamparan grafis berisi teks yang dapat ditempatkan pada dokumen PDF, sering digunakan untuk anotasi atau tanda air.

### Bisakah saya menyesuaikan prangko dengan gambar?
Ya, Aspose.PDF juga mendukung penambahan stempel gambar, memberikan lebih banyak fleksibilitas desain.

### Bahasa pemrograman apa yang dapat saya gunakan dengan Aspose.PDF?
Aspose.PDF terutama difokuskan pada .NET, tetapi ada versi yang tersedia untuk bahasa lain seperti Java dan Python.

### Bagaimana cara mendapatkan lisensi sementara untuk Aspose.PDF?
 Anda dapat mengajukan permohonan lisensi sementara dengan mengunjungi[tautan pembelian](https://purchase.aspose.com/temporary-license/) di situs web mereka.

### Di mana saya dapat menemukan dukungan untuk Aspose.PDF?
 Dukungan untuk Aspose.PDF tersedia di[forum dukungan](https://forum.aspose.com/c/pdf/10).