---
title: Dapatkan Jendela Dokumen
linktitle: Dapatkan Jendela Dokumen
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menggunakan fitur GetDocumentWindow dari Aspose.PDF untuk .NET untuk mengambil informasi tentang properti jendela dokumen PDF.
type: docs
weight: 170
url: /id/net/programming-with-document/getdocumentwindow/
---
 Aspose.PDF untuk .NET adalah pustaka manipulasi PDF canggih yang memungkinkan pengembang membuat, mengedit, dan mengonversi file PDF di aplikasi .NET mereka. Salah satu fitur yang ditawarkan oleh perpustakaan ini adalah kemampuan untuk mengambil informasi tentang properti jendela dokumen. Tutorial ini akan memandu Anda melalui langkah-langkah menggunakan`GetDocumentWindow` fitur Aspose.PDF untuk .NET untuk mengambil informasi tentang properti jendela dokumen PDF.

## Langkah 1: Instal Aspose.PDF untuk .NET

 Untuk menggunakan Aspose.PDF untuk .NET di aplikasi .NET Anda, Anda harus menginstal perpustakaan terlebih dahulu. Anda dapat mengunduh perpustakaan versi terbaru dari[Aspose.PDF untuk halaman unduhan .NET](https://releases.aspose.com/pdf/net).

Setelah Anda mengunduh perpustakaan, ekstrak isi file ZIP ke folder di komputer Anda. Anda kemudian perlu menambahkan referensi ke Aspose.PDF untuk .NET DLL di proyek .NET Anda.

## Langkah 2: Muat Dokumen PDF

Setelah Anda menginstal Aspose.PDF untuk .NET dan menambahkan referensi ke DLL di proyek .NET Anda, Anda dapat mulai menggunakan`GetDocumentWindow` fitur untuk mengambil informasi tentang properti jendela dokumen PDF.

Langkah pertama dalam menggunakan fitur ini adalah memuat dokumen PDF yang ingin Anda ambil informasinya. Untuk melakukannya, Anda dapat menggunakan kode berikut:

```csharp
// Jalur ke dokumen PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Buka dokumen PDF
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

 Pada kode di atas, ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur ke direktori tempat dokumen PDF Anda berada. Kode ini akan memuat dokumen PDF ke dalam a`Document` objek, yang kemudian dapat Anda gunakan untuk mengambil informasi tentang properti jendela dokumen.

## Langkah 3: Ambil Properti Jendela Dokumen

Untuk mengambil informasi tentang properti jendela dokumen PDF, Anda dapat menggunakan kode berikut:

```csharp
// Ambil properti jendela dokumen
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

Dalam kode di atas, setiap baris mengambil properti window berbeda dari dokumen PDF dan menampilkannya ke konsol. Anda dapat menyesuaikan kode ini untuk mengambil hanya properti yang Anda minati.

### Contoh kode sumber untuk mendapatkan jendela dokumen file PDF menggunakan Aspose.PDF untuk .NET 

 Berikut adalah kode sumber lengkap untuk mengambil properti jendela dokumen PDF menggunakan`GetDocumentWindow` fitur Aspose.PDF untuk .NET:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buka dokumen
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// Dapatkan properti dokumen yang berbeda
// Posisi jendela dokumen - Default: false
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// Urutan bacaan yang dominan; menentukan posisi halaman
// Saat ditampilkan berdampingan - Default: L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// Apakah bilah judul jendela harus menampilkan judul dokumen
// Jika salah, bilah judul menampilkan nama file PDF - Default: salah
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// Apakah akan mengubah ukuran jendela dokumen agar sesuai dengan ukurannya
// Halaman pertama yang ditampilkan - Default: false
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// Apakah akan menyembunyikan bilah menu aplikasi penampil - Default: false
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

//Apakah akan menyembunyikan bilah alat aplikasi penampil - Default: false
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// Apakah akan menyembunyikan elemen UI seperti bilah gulir
// Dan hanya menyisakan konten halaman yang ditampilkan - Default: false
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

// Mode halaman dokumen. Cara menampilkan dokumen saat keluar dari mode layar penuh.
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// Tata letak halaman yaitu satu halaman, satu kolom
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// Bagaimana dokumen akan ditampilkan saat dibuka
// Yaitu menampilkan thumbnail, layar penuh, menampilkan panel lampiran
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## Kesimpulan

Dalam tutorial ini, kita telah mempelajari cara menggunakan Aspose.PDF untuk .NET untuk mengambil informasi tentang properti jendela dokumen PDF. Dengan memuat dokumen PDF dan mengakses properti jendelanya, Anda dapat mengumpulkan informasi tentang bagaimana dokumen tersebut harus ditampilkan ketika dibuka di aplikasi penampil. Aspose.PDF untuk .NET menyediakan serangkaian fitur canggih untuk bekerja dengan file PDF secara terprogram, menjadikannya alat yang berharga untuk manipulasi PDF dalam aplikasi .NET.

### FAQ

#### T: Apa tujuan mengambil properti jendela dokumen PDF?

J: Mengambil properti jendela dokumen PDF memungkinkan Anda mengumpulkan informasi tentang bagaimana dokumen PDF harus ditampilkan ketika dibuka di aplikasi penampil. Properti ini mengontrol berbagai aspek seperti posisi jendela, mode tampilan, dan visibilitas elemen UI.

#### T: Bagaimana cara menginstal Aspose.PDF untuk .NET di proyek .NET saya?

 J: Untuk menginstal Aspose.PDF untuk .NET, Anda perlu mengunduh perpustakaan dari[Aspose.PDF untuk halaman unduhan .NET](https://releases.aspose.com/pdf/net). Setelah mengunduh, ekstrak konten file ZIP dan tambahkan referensi ke Aspose.PDF untuk .NET DLL di proyek .NET Anda.

#### T: Dapatkah saya menyesuaikan kode untuk mengambil properti jendela tertentu saja?

J: Ya, Anda dapat menyesuaikan kode untuk mengambil properti jendela tertentu dengan mengomentari baris yang tidak Anda perlukan. Setiap baris dalam kode berhubungan dengan properti jendela tertentu, sehingga Anda dapat menyertakan atau mengecualikan properti berdasarkan kebutuhan Anda.

#### T: Jenis properti jendela apa yang dapat saya ambil menggunakan Aspose.PDF untuk .NET?

J: Menggunakan Aspose.PDF untuk .NET, Anda dapat mengambil berbagai properti jendela dokumen PDF, termasuk memusatkan jendela, mengatur tata letak halaman, mengontrol tampilan toolbar dan bilah menu, dan banyak lagi.