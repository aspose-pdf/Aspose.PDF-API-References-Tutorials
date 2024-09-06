---
title: Cari dan Dapatkan Gambar dalam File PDF
linktitle: Cari dan Dapatkan Gambar dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Panduan langkah demi langkah untuk mencari dan mendapatkan gambar dalam berkas PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 260
url: /id/net/programming-with-images/search-and-get-images/
---
Dalam tutorial ini, kami akan memandu Anda untuk mencari dan mendapatkan gambar dalam file PDF menggunakan Aspose.PDF for .NET. Ikuti langkah-langkah berikut untuk melakukan operasi ini dengan mudah.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau lingkungan pengembangan lainnya terinstal dan dikonfigurasi.
- Pengetahuan dasar tentang bahasa pemrograman C#.
- Pustaka Aspose.PDF untuk .NET telah terinstal. Anda dapat mengunduhnya dari situs web resmi Aspose.

## Langkah 1: Memuat dokumen PDF

Untuk memulai, gunakan kode berikut untuk memuat dokumen PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Buka dokumennya
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SearchAndGetImages.pdf");
```

Pastikan untuk memberikan jalur yang benar ke dokumen PDF Anda.

## Langkah 2: Mencari Lokasi Gambar

Untuk mencari lokasi gambar dalam dokumen PDF, gunakan kode berikut:

```csharp
// Buat objek ImagePlacementAbsorber untuk mencari lokasi gambar
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();

// Terima penyerap untuk semua halaman dokumen
doc.Pages.Accept(abs);
```

Ini akan mengumpulkan lokasi gambar dalam penyerap.

## Langkah 3: Telusuri lokasi gambar dan dapatkan gambar dan propertinya

Selanjutnya, kita akan menelusuri lokasi gambar yang dikumpulkan dan mendapatkan gambar beserta propertinya. Gunakan kode berikut:

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     // Dapatkan gambar menggunakan objek ImagePlacement
     XImage image = imagePlacement.Image;

     // Menampilkan properti lokasi gambar
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal image resolution: " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);
}
```

Ini akan menelusuri semua lokasi gambar, mendapatkan gambar yang cocok dan menampilkan propertinya.

### Contoh kode sumber untuk Pencarian dan Dapatkan Gambar menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "SearchAndGetImages.pdf");
// Buat objek ImagePlacementAbsorber untuk melakukan pencarian penempatan gambar
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Terima penyerap untuk semua halaman
doc.Pages.Accept(abs);
// Ulangi semua ImagePlacements, dapatkan gambar dan Properti ImagePlacement
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// Dapatkan gambar menggunakan objek ImagePlacement
	XImage image = imagePlacement.Image;
	// Menampilkan properti penempatan gambar untuk semua penempatan
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
}
```

## Kesimpulan

Selamat! Anda telah berhasil mencari dan memperoleh gambar dalam dokumen PDF menggunakan Aspose.PDF for .NET. Sekarang Anda dapat menerapkan metode ini ke proyek Anda sendiri untuk mengekstrak gambar dan mendapatkan propertinya dari file PDF.

### FAQ untuk mencari dan mendapatkan gambar dalam file PDF

#### T: Apa tujuan mencari dan memperoleh gambar dalam dokumen PDF menggunakan Aspose.PDF for .NET?

A: Pencarian dan perolehan gambar dalam dokumen PDF memungkinkan Anda menemukan dan mengekstrak gambar dalam berkas PDF. Hal ini dapat berguna untuk berbagai keperluan seperti menganalisis konten, memverifikasi properti gambar, atau memproses gambar lebih lanjut.

#### T: Bagaimana cara kerja proses pencarian gambar dalam dokumen PDF?

 A: Proses ini melibatkan penggunaan`ImagePlacementAbsorber` objek untuk melakukan pencarian penempatan gambar pada semua halaman dokumen PDF. Penyerap mengumpulkan informasi tentang lokasi, ukuran, dan resolusi setiap gambar dalam dokumen.

####  T: Apa tujuan dari`ImagePlacement` object in the code?

 Sebuah:`ImagePlacement`Objek mewakili penempatan gambar dalam dokumen PDF. Objek ini menyediakan properti yang memungkinkan Anda mengakses detail seperti dimensi, koordinat, dan resolusi gambar.

#### T: Dapatkah saya memfilter gambar yang dicari dan diperoleh berdasarkan kriteria tertentu?

A: Kode yang diberikan mengumpulkan informasi tentang semua gambar dalam dokumen PDF. Jika Anda ingin memfilter gambar berdasarkan kriteria tertentu (misalnya, jenis gambar, dimensi, resolusi), Anda mungkin perlu mengubah kode untuk menyertakan kondisi pemfilteran yang sesuai.

#### T: Bagaimana saya dapat mengakses konten gambar sebenarnya setelah memperoleh informasi penempatannya?

 Sebuah:`XImage` objek yang diperoleh dari`ImagePlacement` objek mewakili konten gambar sebenarnya. Anda dapat memproses ini lebih lanjut`XImage` objek, seperti menyimpannya ke file atau menampilkannya di aplikasi Anda.

#### T: Apa yang dapat saya lakukan dengan properti gambar yang diperoleh?

A: Properti gambar yang diperoleh, seperti lebar, tinggi, koordinat, dan resolusi, dapat digunakan untuk berbagai keperluan. Anda dapat menganalisis properti tersebut, menampilkannya kepada pengguna, atau menggunakannya sebagai input untuk pemrosesan lebih lanjut.

#### T: Dapatkah saya mengubah atau mengedit gambar dalam dokumen PDF menggunakan metode ini?

A: Kode yang diberikan berfokus pada pencarian dan perolehan informasi penempatan gambar. Untuk mengubah atau mengedit gambar, Anda mungkin perlu mengintegrasikan fungsi tambahan, seperti manipulasi gambar, menggunakan pustaka Aspose.PDF.

#### T: Bagaimana saya dapat mengintegrasikan metode ini ke dalam proyek saya sendiri?

J: Untuk mengintegrasikan metode ini ke dalam proyek Anda, ikuti langkah-langkah yang diuraikan dan ubah kode sesuai kebutuhan. Anda dapat menggunakan informasi dan properti penempatan gambar yang diperoleh sesuai dengan persyaratan aplikasi Anda.

#### T: Apakah Aspose.PDF untuk .NET menawarkan fitur lain yang terkait dengan manipulasi gambar dalam dokumen PDF?

A: Ya, Aspose.PDF untuk .NET menyediakan berbagai fitur untuk bekerja dengan gambar dalam dokumen PDF, termasuk penyisipan gambar, pengubahan ukuran, rotasi, ekstraksi, dan banyak lagi. Anda dapat menjelajahi dokumentasi dan contoh pustaka untuk menemukan kemampuan lengkapnya.