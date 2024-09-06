---
title: Mengatur Ukuran Gambar Dalam File PDF
linktitle: Mengatur Ukuran Gambar Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Panduan langkah demi langkah untuk mengatur ukuran gambar dalam berkas PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 270
url: /id/net/programming-with-images/set-image-size/
---
Dalam tutorial ini, kami akan memandu Anda untuk mengatur ukuran gambar dalam file PDF menggunakan Aspose.PDF untuk .NET. Ikuti langkah-langkah berikut untuk melakukan operasi ini dengan mudah.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau lingkungan pengembangan lainnya terinstal dan dikonfigurasi.
- Pengetahuan dasar tentang bahasa pemrograman C#.
- Pustaka Aspose.PDF untuk .NET telah terinstal. Anda dapat mengunduhnya dari situs web resmi Aspose.

## Langkah 1: Pembuatan dokumen PDF

Untuk memulai, gunakan kode berikut untuk membuat dokumen PDF baru:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Membuat instance objek Dokumen
Document doc = new Document();

// Tambahkan halaman ke koleksi halaman file PDF
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Langkah 2: Menambahkan gambar

Selanjutnya, kita akan menambahkan gambar ke halaman dokumen PDF. Gunakan kode berikut:

```csharp
// Buat contoh gambar
Aspose.Pdf.Image img = new Aspose.Pdf.Image();

// Atur lebar dan tinggi gambar dalam poin
img. FixWidth = 100;
img. FixHeight = 100;

//Tetapkan jenis gambar ke tidak diketahui (Tidak Diketahui)
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

// Jalur ke file sumber gambar
img.File = dataDir + "aspose-logo.jpg";

// Tambahkan gambar ke koleksi paragraf halaman
page.Paragraphs.Add(img);
```

Pastikan untuk memberikan jalur yang benar ke berkas sumber gambar.

## Langkah 3: Mengatur properti halaman

Terakhir, kita akan mengatur properti halaman, termasuk lebar dan tingginya. Gunakan kode berikut:

```csharp
// Tetapkan properti halaman
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```

### Contoh kode sumber untuk Mengatur Ukuran Gambar menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Membuat instance objek Dokumen
Document doc = new Document();
// tambahkan halaman ke kumpulan halaman file PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Buat contoh gambar
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Atur Lebar dan Tinggi Gambar dalam Poin
img.FixWidth = 100;
img.FixHeight = 100;
// Tetapkan jenis gambar sebagai SVG
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
// Jalur untuk file sumber
img.File = dataDir + "aspose-logo.jpg";
page.Paragraphs.Add(img);
//Tetapkan properti halaman
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
dataDir = dataDir + "SetImageSize_out.pdf";
// simpan file PDF yang dihasilkan
doc.Save(dataDir);
Console.WriteLine("\nImage size added successfully.\nFile saved at " + dataDir);
```

## Kesimpulan

Selamat! Anda telah berhasil mengatur ukuran gambar dalam dokumen PDF menggunakan Aspose.PDF for .NET. Kini Anda dapat menerapkan metode ini ke proyek Anda sendiri untuk menyesuaikan ukuran gambar dalam file PDF.

### FAQ untuk mengatur ukuran gambar dalam file PDF

#### T: Apa tujuan pengaturan ukuran gambar dalam dokumen PDF menggunakan Aspose.PDF for .NET?

A: Tujuan pengaturan ukuran gambar dalam dokumen PDF adalah untuk mengontrol dimensi gambar saat ditambahkan ke PDF. Ini memungkinkan Anda untuk menyesuaikan tampilan dan tata letak gambar dalam file PDF Anda.

#### T: Bagaimana cara kerja proses pengaturan ukuran gambar dalam dokumen PDF?

 A: Prosesnya melibatkan pembuatan`Aspose.Pdf.Image` misalnya, menentukan lebar dan tingginya menggunakan`FixWidth` Dan`FixHeight` properti, lalu menambahkan gambar ke dokumen PDF. Selain itu, Anda dapat mengatur dimensi halaman itu sendiri untuk mengakomodasi gambar.

#### T: Dapatkah saya mengatur ukuran gambar ke persentase tertentu dari dimensi halaman?

A: Kode yang diberikan menetapkan lebar dan tinggi absolut gambar dalam poin. Jika Anda ingin menetapkan ukuran gambar berdasarkan persentase dimensi halaman, Anda perlu menghitung dimensi yang sesuai dan menyesuaikan kode yang sesuai.

####  T: Apa pentingnya`FileType` property when adding an image to the PDF document?

 Sebuah:`FileType`properti menentukan jenis gambar yang akan ditambahkan ke dokumen PDF. Dalam kode yang diberikan, nilainya`Unknown` menunjukkan bahwa jenis gambar tidak diketahui, dan Aspose.PDF akan mencoba menentukan jenis gambar berdasarkan ekstensi file.

#### T: Dapatkah saya menambahkan beberapa gambar ke satu halaman menggunakan metode ini?

 A: Ya, Anda dapat menambahkan beberapa gambar ke satu halaman dengan membuat beberapa`Aspose.Pdf.Image` contoh dan menambahkannya ke kumpulan paragraf halaman. Pastikan untuk menyesuaikan posisi dan tata letak gambar sesuai kebutuhan.

#### T: Bagaimana saya dapat mengontrol penempatan dan perataan gambar yang ditambahkan pada halaman?

 A: Penempatan dan penyelarasan gambar yang ditambahkan dapat dikontrol dengan menyesuaikan koordinat dan tata letak gambar menggunakan properti seperti`img.Left`, `img.Top`, dan properti pemformatan paragraf.

####  T: Apa tujuan pengaturan properti halaman menggunakan`page.PageInfo.Width` and `page.PageInfo.Height`?

A: Menetapkan properti halaman memungkinkan Anda menentukan dimensi halaman itu sendiri. Ini memastikan bahwa dimensi halaman mengakomodasi gambar yang ditambahkan dan konten lain yang mungkin Anda miliki di halaman.

#### T: Dapatkah saya mengatur ukuran yang berbeda untuk gambar yang berbeda dalam dokumen PDF yang sama?

 A: Ya, Anda dapat mengatur ukuran yang berbeda untuk gambar yang berbeda dengan membuat gambar terpisah`Aspose.Pdf.Image` contoh dan penyesuaian`FixWidth`, `FixHeight`, dan properti penempatan untuk setiap gambar.

#### T: Bagaimana saya dapat mengintegrasikan metode ini ke dalam proyek saya sendiri untuk mengatur ukuran gambar dalam berkas PDF?

J: Untuk mengintegrasikan metode ini ke dalam proyek Anda, ikuti langkah-langkah yang dijelaskan dan ubah kode sesuai kebutuhan. Anda dapat menggunakan metode ini untuk menambahkan gambar dengan ukuran tertentu ke dokumen PDF Anda berdasarkan persyaratan aplikasi Anda.