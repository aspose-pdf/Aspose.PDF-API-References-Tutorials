---
title: Atur Ukuran Gambar Dalam File PDF
linktitle: Atur Ukuran Gambar Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Panduan langkah demi langkah untuk mengatur ukuran gambar dalam file PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 270
url: /id/net/programming-with-images/set-image-size/
---
Dalam tutorial ini, kami akan memandu Anda tentang cara mengatur ukuran gambar dalam file PDF menggunakan Aspose.PDF untuk .NET. Ikuti langkah-langkah berikut untuk melakukan operasi ini dengan mudah.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau lingkungan pengembangan lainnya diinstal dan dikonfigurasi.
- Pengetahuan dasar tentang bahasa pemrograman C#.
- Pustaka Aspose.PDF untuk .NET diinstal. Anda dapat mendownloadnya dari situs resmi Aspose.

## Langkah 1: Pembuatan dokumen PDF

Untuk memulai, gunakan kode berikut untuk membuat dokumen PDF baru:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Buat instance objek Dokumen
Document doc = new Document();

// Tambahkan halaman ke kumpulan halaman file PDF
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

// Setel jenis gambar ke tidak diketahui (Tidak Diketahui)
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

//Jalur ke file sumber gambar
img.File = dataDir + "aspose-logo.jpg";

// Tambahkan gambar ke koleksi paragraf halaman
page.Paragraphs.Add(img);
```

Pastikan untuk memberikan jalur yang benar ke file sumber gambar.

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
// Buat instance objek Dokumen
Document doc = new Document();
// tambahkan halaman ke halaman koleksi file PDF
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

Selamat! Anda telah berhasil mengatur ukuran gambar dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Anda sekarang dapat menerapkan metode ini pada proyek Anda sendiri untuk menyesuaikan ukuran gambar dalam file PDF.

### FAQ untuk mengatur ukuran gambar dalam file PDF

#### Q: Apa tujuan mengatur ukuran gambar dalam dokumen PDF menggunakan Aspose.PDF for .NET?

A: Tujuan pengaturan ukuran gambar pada dokumen PDF adalah untuk mengontrol dimensi gambar saat ditambahkan ke PDF. Ini memungkinkan Anda untuk menyesuaikan tampilan dan tata letak gambar dalam file PDF Anda.

#### Q: Bagaimana cara kerja proses pengaturan ukuran gambar di dokumen PDF?

 J: Prosesnya melibatkan pembuatan`Aspose.Pdf.Image` misalnya, menentukan lebar dan tingginya menggunakan`FixWidth` Dan`FixHeight` properti, lalu menambahkan gambar ke dokumen PDF. Selain itu, Anda dapat mengatur dimensi halaman itu sendiri untuk mengakomodasi gambar.

#### T: Dapatkah saya mengatur ukuran gambar ke persentase tertentu dari dimensi halaman?

J: Kode yang diberikan menetapkan lebar dan tinggi absolut gambar dalam poin. Jika Anda ingin mengatur ukuran gambar berdasarkan persentase dimensi halaman, Anda perlu menghitung dimensinya dan menyesuaikan kodenya.

####  T: Apa pentingnya`FileType` property when adding an image to the PDF document?

 J: Itu`FileType`properti menentukan jenis gambar yang ditambahkan ke dokumen PDF. Dalam kode yang diberikan, nilainya`Unknown` menunjukkan bahwa jenis gambar tidak diketahui, dan Aspose.PDF akan mencoba menentukan jenis gambar berdasarkan ekstensi file.

#### T: Bisakah saya menambahkan banyak gambar ke satu halaman menggunakan metode ini?

 J: Ya, Anda dapat menambahkan banyak gambar ke satu halaman dengan membuat beberapa halaman`Aspose.Pdf.Image` contoh dan menambahkannya ke koleksi paragraf halaman. Pastikan untuk menyesuaikan posisi dan tata letak gambar sesuai kebutuhan.

#### T: Bagaimana cara mengontrol penempatan dan perataan gambar yang ditambahkan pada halaman?

 J: Penempatan dan perataan gambar yang ditambahkan dapat dikontrol dengan mengatur koordinat dan tata letak gambar menggunakan properti seperti`img.Left`, `img.Top`, dan properti pemformatan paragraf.

####  Q: Apa tujuan pengaturan properti halaman menggunakan`page.PageInfo.Width` and `page.PageInfo.Height`?

J: Mengatur properti halaman memungkinkan Anda menentukan dimensi halaman itu sendiri. Hal ini memastikan bahwa dimensi halaman mengakomodasi gambar yang ditambahkan dan konten lain yang mungkin Anda miliki di halaman.

#### T: Bisakah saya mengatur ukuran berbeda untuk gambar berbeda dalam dokumen PDF yang sama?

 J: Ya, Anda dapat mengatur ukuran berbeda untuk gambar berbeda dengan membuat gambar terpisah`Aspose.Pdf.Image` contoh dan menyesuaikan`FixWidth`, `FixHeight`, dan properti penempatan untuk setiap gambar.

#### T: Bagaimana cara mengintegrasikan metode ini ke dalam proyek saya sendiri untuk mengatur ukuran gambar dalam file PDF?

J: Untuk mengintegrasikan metode ini ke dalam proyek Anda, ikuti langkah-langkah yang diuraikan dan ubah kode sesuai kebutuhan. Anda dapat menggunakan metode ini untuk menambahkan gambar dengan ukuran tertentu ke dokumen PDF Anda berdasarkan kebutuhan aplikasi Anda.