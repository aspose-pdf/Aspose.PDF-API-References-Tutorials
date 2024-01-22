---
title: Stempel Nomor Halaman Dalam File PDF
linktitle: Stempel Nomor Halaman Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menambahkan stempel nomor halaman dalam file PDF dengan Aspose.PDF untuk .NET.
type: docs
weight: 160
url: /id/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
Dalam tutorial ini, kami akan memandu Anda langkah demi langkah tentang cara menambahkan stempel nomor halaman di file PDF menggunakan Aspose.PDF untuk .NET. Kami akan menggunakan kode sumber C# yang disediakan untuk membuka dokumen PDF yang ada, membuat stempel nomor halaman, mengatur propertinya, dan menambahkannya ke halaman tertentu di file PDF.

## Langkah 1: Menyiapkan lingkungan

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Lingkungan pengembangan .NET yang terinstal.
- Pustaka Aspose.PDF untuk .NET diunduh dan direferensikan dalam proyek Anda.

## Langkah 2: Memuat dokumen PDF yang ada

Langkah pertama adalah memuat dokumen PDF yang ada ke dalam proyek Anda. Begini caranya:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Buka dokumen PDF yang ada
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori tempat dokumen PDF Anda berada.

## Langkah 3: Membuat dan Mengonfigurasi Stempel Penomoran Halaman

Sekarang dokumen PDF telah dimuat, kita dapat membuat buffer penomoran halaman dan mengkonfigurasinya sesuai kebutuhan kita. Begini caranya:

```csharp
// Buat buffer nomor halaman
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Tentukan apakah buffer ada di latar belakang atau tidak
pageNumberStamp.Background = false;

// Format buffer penomoran halaman
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

// Margin bawah buffer penomoran halaman
pageNumberStamp.BottomMargin = 10;

// Penjajaran horizontal buffer penomoran halaman
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

// Mulai nomor penomoran halaman
pageNumberStamp.StartingNumber = 1;

// Setel properti teks buffer nomor halaman
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

Kode di atas membuat stempel nomor halaman dengan properti seperti format nomor halaman, margin bawah, perataan horizontal, nomor awal, dan properti teks.

## Langkah 4: Menambahkan stempel nomor halaman ke halaman tertentu

Setelah cap nomor halaman dikonfigurasi, kita dapat menambahkannya ke halaman tertentu dari dokumen PDF. Begini caranya:

```csharp
// Tambahkan buffer nomor halaman ke halaman tertentu
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

Kode di atas menambahkan cap nomor halaman ke halaman pertama dokumen PDF. Anda dapat mengubah nomor halaman sesuai kebutuhan.

## Langkah 5: Menyimpan dokumen PDF yang dimodifikasi

Setelah cap nomor halaman ditambahkan ke dokumen PDF, kita dapat menyimpan dokumen PDF yang dimodifikasi. Begini caranya:

```csharp
// Simpan dokumen PDF yang dimodifikasi
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori tempat Anda ingin menyimpan dokumen PDF yang telah diedit.

### Contoh kode sumber untuk Stempel Nomor Halaman menggunakan Aspose.PDF untuk .NET 
```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buka dokumen
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

// Buat stempel nomor halaman
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Apakah stempel tersebut merupakan latar belakang
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;

// Atur properti teks
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;

// Tambahkan stempel ke halaman tertentu
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
dataDir = dataDir + "PageNumberStamp_out.pdf";

// Simpan dokumen keluaran
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## Kesimpulan

Selamat! Anda telah mempelajari cara menambahkan stempel nomor halaman ke dokumen PDF menggunakan Aspose.PDF untuk .NET. Anda sekarang dapat mempersonalisasi dokumen PDF Anda dengan menambahkan nomor halaman yang jelas dan informatif.

### FAQ untuk stempel nomor halaman dalam file PDF

#### T: Apa itu Stempel Nomor Halaman, dan bagaimana cara menggunakannya untuk menambahkan nomor halaman ke file PDF?

J: Stempel Nomor Halaman adalah fitur di Aspose.PDF yang memungkinkan Anda menambahkan nomor halaman dinamis ke halaman tertentu dalam dokumen PDF. Dalam tutorial ini, hal ini dicapai dengan membuat objek PageNumberStamp, mengonfigurasi propertinya, dan menambahkannya ke halaman yang ditentukan.

#### T: Bagaimana kode sumber C# yang disediakan dapat menambahkan stempel nomor halaman ke file PDF?

J: Kode ini menunjukkan cara memuat dokumen PDF yang ada, membuat PageNumberStamp, mengatur berbagai properti (seperti format, font, perataan, dll.), lalu menambahkan stempel ke halaman tertentu. Stempel secara otomatis menghitung jumlah halaman total dan memasukkan nomor halaman yang benar.

#### T: Dapatkah saya menyesuaikan tampilan nomor halaman, seperti gaya font, warna, dan ukuran?

J: Tentu saja, Anda dapat menyesuaikan tampilan cap nomor halaman dengan menyesuaikan properti seperti font, ukuran font, gaya font (tebal, miring, dll.), dan warna teks.

#### T: Apakah mungkin menambahkan stempel nomor halaman ke beberapa halaman dalam dokumen PDF?

J: Ya, Anda dapat menambahkan stempel nomor halaman ke beberapa halaman dengan membuat beberapa objek PageNumberStamp dan menambahkan masing-masing objek ke halaman yang diinginkan.

#### T: Dapatkah saya memilih apakah stempel nomor halaman muncul sebagai bagian dari konten halaman atau sebagai elemen latar belakang?

 J: Ya, Anda dapat mengontrol apakah cap nomor halaman muncul sebagai bagian dari konten halaman atau sebagai elemen latar belakang dengan mengatur`Background` milik PageNumberStamp.

#### T: Bagaimana cara menentukan format nomor halaman, termasuk jumlah halaman total?

 A: Kode menggunakan`Format`properti PageNumberStamp untuk menentukan format nomor halaman. Makro "# of" digunakan untuk mewakili jumlah halaman total.

#### Q: Apa yang terjadi jika saya menambahkan stempel nomor halaman yang sama ke beberapa halaman?

J: Menambahkan instance PageNumberStamp yang sama ke beberapa halaman akan menampilkan nomor halaman yang benar untuk setiap halaman. Stempel secara otomatis menyesuaikan nomor halaman dan jumlah halaman total.

#### T: Dapatkah saya menambahkan stempel nomor halaman ke bagian header atau footer dokumen PDF?

J: Meskipun PageNumberStamps biasanya ditambahkan langsung ke konten halaman, Anda dapat menggunakan FloatingBox atau teknik lain untuk memposisikannya di bagian header atau footer.

#### Q: Bagaimana cara menentukan posisi cap nomor halaman pada halaman?

 J: Itu`BottomMargin` Dan`HorizontalAlignment` properti PageNumberStamp memungkinkan Anda mengontrol posisi stempel di dalam halaman.

#### T: Bagaimana jika saya ingin memulai penomoran halaman dari nomor yang berbeda, bukan 1?

 J: Anda dapat mengaturnya`StartingNumber`properti PageNumberStamp untuk menentukan nomor halaman awal.