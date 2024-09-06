---
title: Konversi Wilayah Halaman ke DOM
linktitle: Konversi Wilayah Halaman ke DOM
second_title: Referensi API Aspose.PDF untuk .NET
description: Konversikan dengan mudah wilayah tertentu dari halaman PDF ke Model Objek Dokumen (DOM) dengan Aspose.PDF untuk .NET.
type: docs
weight: 80
url: /id/net/programming-with-images/convert-page-region-to-dom/
---
Panduan ini akan memandu Anda langkah demi langkah cara mengonversi wilayah tertentu pada halaman ke Document Object Model (DOM) menggunakan Aspose.PDF untuk .NET. Pastikan Anda telah menyiapkan lingkungan Anda dan ikuti langkah-langkah di bawah ini:

## Langkah 1: Tentukan direktori dokumen

Sebelum memulai, pastikan Anda mengatur direktori yang benar untuk dokumen tersebut. Ganti`"YOUR DOCUMENT DIRECTORY"` dalam kode dengan jalur ke direktori tempat dokumen PDF Anda berada.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Buka dokumen

 Pada langkah ini, kita akan membuka dokumen PDF menggunakan`Document` kelas Aspose.PDF. Gunakan`Document` konstruktor dan meneruskan jalur ke dokumen PDF.

```csharp
Document document = new Document(dataDir + "AddImage.pdf");
```

## Langkah 3: Dapatkan Persegi Panjang Wilayah Halaman

 Pada langkah ini, kita akan menentukan persegi panjang yang mewakili wilayah tertentu dari halaman yang ingin kita ubah ke DOM. Gunakan`Aspose.Pdf.Rectangle` kelas untuk menentukan koordinat persegi panjang.

```csharp
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
```

## Langkah 4: Tentukan area pemotongan halaman

 Gunakan`CropBox` milik`Page` objek untuk mengatur kotak potong halaman ke persegi panjang wilayah yang diinginkan.

```csharp
document.Pages[1].CropBox = pageRect;
```

## Langkah 5: Simpan dokumen PDF yang dipotong ke aliran

 Pada langkah ini, kita akan menyimpan dokumen PDF yang dipotong ke aliran menggunakan`MemoryStream` kelas.

```csharp
MemoryStream ms = new MemoryStream();
document.Save(ms);
```

## Langkah 6: Buka dokumen PDF yang dipotong dan ubah menjadi gambar

 Buka dokumen PDF yang dipotong menggunakan`Document`kelas dan mengubahnya menjadi gambar. Kami akan menggunakan resolusi 300 dpi.

```csharp
document = newDocument(ms);
Resolution resolution = new Resolution(300);
PngDevice pngDevice = new PngDevice(resolution);
```

## Langkah 7: Ubah halaman tertentu menjadi gambar

 Ubah halaman tertentu menjadi gambar menggunakan`Process` metode dari`pngDevice` objek. Tentukan jalur keluaran gambar.

```csharp
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
pngDevice.Process(document.Pages[1], dataDir);
```

### Contoh kode sumber untuk Mengonversi Wilayah Halaman ke DOM menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document document = new Document( dataDir + "AddImage.pdf");
// Dapatkan persegi panjang dari wilayah halaman tertentu
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
// Tetapkan nilai CropBox sesuai persegi panjang wilayah halaman yang diinginkan
document.Pages[1].CropBox = pageRect;
// Simpan dokumen yang dipotong ke dalam aliran
MemoryStream ms = new MemoryStream();
document.Save(ms);
// Buka dokumen PDF yang dipotong dan ubah menjadi gambar
document = new Document(ms);
// Buat objek Resolusi
Resolution resolution = new Resolution(300);
// Buat perangkat PNG dengan atribut yang ditentukan
PngDevice pngDevice = new PngDevice(resolution);
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
// Konversi halaman tertentu dan simpan gambar ke streaming
pngDevice.Process(document.Pages[1], dataDir);
ms.Close();
Console.WriteLine("\nPage region converted to DOM successfully.\nFile saved at " + dataDir); 
```

## Kesimpulan

Selamat! Anda telah berhasil mengonversi wilayah tertentu dari suatu halaman ke Document Object Model (DOM) menggunakan Aspose.PDF untuk .NET. Gambar yang dihasilkan disimpan di direktori yang ditentukan. Anda sekarang dapat menggunakan gambar ini di proyek atau aplikasi Anda.

## Pertanyaan yang Sering Diajukan

#### T: Apa tujuan mengonversi wilayah tertentu pada suatu halaman ke Model Objek Dokumen (DOM) menggunakan Aspose.PDF untuk .NET?

A: Mengonversi wilayah tertentu pada halaman PDF ke Model Objek Dokumen (DOM) dapat membantu dalam mengekstrak dan memanipulasi bagian konten tertentu dalam dokumen PDF.

#### T: Bagaimana Aspose.PDF untuk .NET memfasilitasi konversi wilayah halaman tertentu ke DOM?

A: Aspose.PDF untuk .NET menyediakan proses langkah demi langkah untuk menentukan wilayah halaman yang diinginkan, mengatur area pemotongan, menyimpan dokumen PDF yang dipotong ke aliran, dan mengubah wilayah halaman yang ditentukan menjadi gambar.

#### T: Mengapa penting untuk menentukan direktori dokumen sebelum memulai proses konversi?

A: Menentukan direktori dokumen memastikan bahwa dokumen PDF dan gambar yang dihasilkan berlokasi dengan benar di jalur keluaran yang diinginkan.

####  T: Bagaimana caranya`Document` class in Aspose.PDF for .NET help in the conversion process?

 Sebuah:`Document` Kelas ini memungkinkan Anda untuk membuka, memanipulasi, dan menyimpan dokumen PDF. Dalam hal ini, kelas ini digunakan untuk memuat dokumen PDF dan membuat versi yang dipotong.

####  T: Apa tujuan dari`Rectangle` class in the page region conversion process?

 Sebuah:`Rectangle`class menentukan koordinat wilayah tertentu pada halaman PDF yang ingin Anda ubah ke DOM. Class ini membantu menentukan area pemotongan secara akurat.

#### T: Bagaimana area pemotongan halaman diatur ke wilayah yang diinginkan dalam proses konversi?

 Sebuah:`CropBox` milik`Page` Objek digunakan untuk mengatur area pemotongan halaman ke persegi panjang yang ditentukan yang mewakili wilayah tertentu.

#### T: Bagaimana dokumen PDF yang dipotong disimpan ke aliran selama proses konversi?

 A: Dokumen PDF yang dipotong disimpan ke`MemoryStream` objek, yang memungkinkan manipulasi konten PDF secara efisien.

####  T: Apa peran`PngDevice` class play in the page region to DOM conversion process?

 Sebuah:`PngDevice` kelas membantu mengubah dokumen PDF yang dipotong menjadi format gambar, seperti PNG, yang memungkinkan Anda memvisualisasikan wilayah halaman tertentu.

#### T: Dapatkah saya menyesuaikan resolusi atau atribut lain dari gambar yang dihasilkan selama proses konversi?

 A: Ya, Anda dapat mengubah resolusi dan atribut lain dari gambar yang dihasilkan dengan mengonfigurasi`PngDevice` objek sebelum mengonversi halaman.