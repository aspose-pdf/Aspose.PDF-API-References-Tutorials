---
title: Penempatan Gambar
linktitle: Penempatan Gambar
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mengekstrak dan memanipulasi penempatan gambar dalam dokumen PDF menggunakan Aspose.PDF for .NET. Panduan langkah demi langkah dengan contoh dan cuplikan kode.
type: docs
weight: 170
url: /id/net/programming-with-images/image-placements/
---
## Perkenalan

Bekerja dengan gambar dalam file PDF bisa jadi sulit, tetapi dengan Aspose.PDF untuk .NET, Anda dapat dengan mudah memanipulasi dan mengekstrak properti gambar tanpa kesulitan. Baik Anda ingin mendapatkan dimensi gambar, mengekstraknya, atau mengambil properti lain seperti resolusi, Aspose.PDF memiliki alat yang Anda butuhkan. Tutorial ini akan memandu Anda melalui panduan langkah demi langkah tentang cara mengekstrak penempatan gambar dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Kami akan membahas semuanya mulai dari mengimpor paket hingga mengambil properti gambar seperti lebar, tinggi, dan resolusi.

## Prasyarat

Sebelum kita mulai tutorialnya, ada beberapa hal yang perlu Anda persiapkan. Berikut daftar periksa singkatnya:

1.  Aspose.PDF untuk .NET: Pastikan Anda telah menginstal pustaka Aspose.PDF untuk .NET. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/pdf/net/).
2. Lingkungan Pengembangan: Anda memerlukan Visual Studio atau IDE lain yang mendukung .NET yang terpasang di komputer Anda.
3. Dokumen PDF: Siapkan contoh dokumen PDF yang berisi gambar. Untuk contoh ini, kita akan menggunakan file bernama`ImagePlacement.pdf`.
4. Pengetahuan Dasar C#: Meskipun panduan ini ramah bagi pemula, pengetahuan dasar C# akan membantu Anda lebih memahami cuplikan kode.

## Paket Impor

Sebelum kita masuk ke inti kode, hal pertama yang perlu Anda lakukan adalah mengimpor namespace yang diperlukan. Paket-paket ini penting untuk bekerja dengan dokumen PDF dan manipulasi gambar di Aspose.PDF for .NET.

```csharp
using System.IO;
using Aspose.Pdf;
using System;
using System.Drawing;
```

Paket ini memungkinkan Anda bekerja dengan PDF (`Aspose.Pdf`), memanipulasi penempatan gambar (`Aspose.Pdf.ImagePlacement`), dan menangani aliran gambar dan grafik (`System.Drawing` Dan`System.IO`).

Sekarang setelah kita menyiapkan prasyarat dan paket, mari kita uraikan setiap bagian tutorial dalam panduan yang sederhana dan mudah diikuti.

## Langkah 1: Muat Dokumen PDF

Langkah pertama adalah memuat dokumen PDF ke dalam proyek Anda. Ini akan menjadi dasar untuk bekerja dengan gambar di dalam berkas PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "ImagePlacement.pdf");
```

 Pada langkah ini, kami mendefinisikan jalur file dokumen PDF menggunakan`dataDir`dan kemudian membuat instance baru dari`Aspose.Pdf.Document` kelas. Ini memungkinkan kita untuk memuat berkas PDF ke dalam program kita. Sederhana, bukan? Sama seperti membuka buku untuk mulai membaca, kita sekarang siap untuk menjelajahi konten di dalamnya.

## Langkah 2: Inisialisasi Penyerap Penempatan Gambar

Untuk mengekstrak gambar, kita memerlukan sesuatu yang disebut "Image Placement Absorber." Anggap saja seperti alat yang menyerap semua informasi gambar pada halaman tertentu.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
```

 Di sini, kita membuat sebuah instance dari`ImagePlacementAbsorber`Objek ini akan mengumpulkan dan menyimpan informasi tentang semua penempatan gambar pada halaman PDF tertentu. Bayangkan seperti memindai halaman dengan kaca pembesar dan mengidentifikasi semua gambar di dalamnya!

## Langkah 3: Terima Penyerap di Halaman Pertama

Selanjutnya, kita perlu memberi tahu absorber halaman PDF mana yang akan dipindai. Untuk contoh ini, kita akan fokus pada halaman pertama.

```csharp
doc.Pages[1].Accept(abs);
```

 Itu`Accept` metode memindai halaman pertama dokumen PDF untuk gambar apa pun dan menyimpan hasilnya di dalam`ImagePlacementAbsorber`Ini seperti memberi tahu kaca pembesar di mana harus mencari gambar.

## Langkah 4: Ulangi Setiap Penempatan Gambar

Sekarang setelah kita memindai halaman, kita perlu mengulang setiap gambar yang ditemukan pada halaman dan mengambil propertinya.

```csharp
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
    Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
    Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
    Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
    Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
    Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
    Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
}
```

Loop ini menelusuri setiap gambar yang ditemukan di halaman. Kami mencetak lebar, tinggi, x kiri bawah (LLX), y kiri bawah (LLY), dan resolusi gambar (baik horizontal maupun vertikal). Rincian ini membantu Anda memahami ukuran dan posisi setiap gambar di dalam PDF.

## Langkah 5: Ekstrak Gambar dengan Dimensi Terlihat

Setelah mengumpulkan informasi tentang gambar, Anda mungkin ingin mengekstrak gambar sebenarnya beserta dimensinya. Berikut cara melakukannya.

```csharp
Bitmap scaledImage;
using (MemoryStream imageStream = new MemoryStream())
{
    imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
    Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);
    scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
}
```

 Potongan kode ini mengambil gambar dari PDF dan menyesuaikannya dengan dimensi sebenarnya seperti yang ditentukan dalam`ImagePlacement` objek. Dengan menyimpan gambar dalam aliran memori dan menskalakannya, Anda memastikan bahwa gambar yang Anda ekstrak mempertahankan ukuran persis seperti yang ditampilkan dalam PDF.

## Kesimpulan

Mengekstrak penempatan gambar dari dokumen PDF menggunakan Aspose.PDF untuk .NET cukup mudah setelah Anda menguraikannya langkah demi langkah. Kami telah membahas semuanya mulai dari memuat PDF hingga mengambil properti gambar dan mengekstrak gambar dengan dimensi sebenarnya. Aspose.PDF membuat bekerja dengan PDF dan memanipulasi konten menjadi sangat mudah, memungkinkan Anda bekerja secara efisien dengan gambar, teks, dan banyak lagi.

## Pertanyaan yang Sering Diajukan

### Bisakah saya mengekstrak gambar dari halaman PDF tertentu?  
 Ya, dengan menentukan nomor halaman saat menggunakan`Accept` metode ini, Anda dapat fokus pada halaman tertentu mana saja.

### Format gambar apa yang didukung untuk ekstraksi?  
Aspose.PDF mendukung berbagai format, termasuk PNG, JPEG, BMP, dan banyak lagi.

### Apakah mungkin untuk memanipulasi gambar yang diekstrak?  
 Tentu saja! Setelah diekstraksi, Anda dapat menggunakan`System.Drawing` namespace untuk memanipulasi gambar.

### Bisakah saya mengekstrak gambar dari PDF yang dilindungi kata sandi?  
Ya, Anda bisa, tetapi Anda harus membuka kunci PDF menggunakan kredensial yang sesuai sebelum mengekstrak gambar.

### Apakah Aspose.PDF untuk .NET berfungsi pada semua kerangka kerja .NET?  
Ya, ini mendukung .NET Framework, .NET Core, dan .NET 5 dan di atasnya.