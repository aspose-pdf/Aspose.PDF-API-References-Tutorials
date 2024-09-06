---
title: Lebar Garis Anotasi lnk
linktitle: Lebar Garis Anotasi lnk
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mengatur lebar garis anotasi tinta dalam PDF menggunakan Aspose.PDF untuk .NET. Tutorial terperinci ini memandu Anda melalui setiap langkah, memastikan hasil berkualitas tinggi.
type: docs
weight: 110
url: /id/net/annotations/lnkannotationlinewidth/
---
## Perkenalan

Saat bekerja dengan dokumen PDF, menambahkan anotasi dapat menjadi cara yang ampuh untuk menyorot informasi atau menambahkan elemen interaktif ke berkas Anda. Salah satu anotasi tersebut adalah Anotasi Tinta, yang memungkinkan Anda menggambar garis bentuk bebas pada PDF Anda. Namun, bagaimana jika Anda perlu menyesuaikan tampilan garis-garis ini, khususnya lebar garis? Dalam tutorial ini, kami akan memandu Anda melalui proses pengaturan lebar garis anotasi tinta menggunakan Aspose.PDF untuk .NET.

## Prasyarat

Sebelum masuk ke kode, mari pastikan Anda telah menyiapkan semuanya untuk mengikuti tutorial ini dengan lancar:

1.  Aspose.PDF untuk .NET: Pastikan Anda telah menginstal pustaka Aspose.PDF untuk .NET. Anda dapat mengunduhnya dari[halaman unduhan](https://releases.aspose.com/pdf/net/) atau menginstalnya melalui NuGet Package Manager di Visual Studio.
2. Lingkungan Pengembangan: Tutorial ini mengasumsikan Anda bekerja di lingkungan pengembangan .NET seperti Visual Studio.
3. Pengetahuan Dasar C#: Pemahaman mendasar tentang C# akan membantu Anda mengikuti langkah-langkah pengkodean.
4. Dokumen PDF: Gunakan dokumen PDF yang ada atau buat yang baru untuk tutorial ini.

## Mengimpor Ruang Nama yang Diperlukan

Sebelum Anda memulai pengkodean, pastikan untuk mengimpor namespace yang diperlukan dalam proyek Anda:

```csharp
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using System;
using System.Collections;
using System.Collections.Generic;
```

Ruang nama ini menyediakan kelas dan metode yang dibutuhkan untuk memanipulasi dokumen PDF, bekerja dengan anotasi, dan menangani elemen grafis.

Sekarang setelah prasyarat kita terpenuhi, mari kita uraikan proses pengaturan lebar garis anotasi tinta ke dalam langkah-langkah yang jelas dan mudah dikelola.

## Langkah 1: Inisialisasi Dokumen PDF

Pertama, kita perlu membuat atau membuka dokumen PDF. Untuk tutorial ini, kita akan membuat dokumen PDF baru dari awal.

```csharp
// Inisialisasi Dokumen PDF
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Tentukan direktori dokumen Anda
Document doc = new Document();
doc.Pages.Add(); // Tambahkan halaman kosong ke dokumen
```

 Di sini, kita sedang menginisialisasi yang baru`Document` objek, yang mewakili berkas PDF kita. Kemudian kita tambahkan halaman kosong ke dokumen ini untuk digunakan.

## Langkah 2: Buat Anotasi Tinta

Selanjutnya, kita akan membuat anotasi tinta itu sendiri. Ini melibatkan penentuan titik-titik yang membentuk goresan tinta.

```csharp
// Buat Anotasi Tinta
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = Color.Red;
lineInfo.LineWidth = 2;
```

 Pada langkah ini, kami mendefinisikan`LineInfo` objek, yang menyimpan koordinat goresan tinta, visibilitasnya, warna, dan lebar garis awal.`VerticeCoordinate` array berisi koordinat X dan Y setiap titik dalam goresan.

## Langkah 3: Ubah Koordinat menjadi Titik

Sekarang, kita perlu mengubah koordinat ini menjadi titik-titik yang dapat digunakan oleh Anotasi Tinta.

```csharp
// Konversi Koordinat ke Titik
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
```

 Loop ini memproses array koordinat, mengubah setiap pasangan koordinat menjadi`Point` objek, yang kemudian ditambahkan ke kami`inkList`.

## Langkah 4: Tambahkan Anotasi Tinta ke Halaman PDF

Setelah titik-titiknya siap, sekarang kita dapat membuat anotasi tinta dan menambahkannya ke halaman PDF.

```csharp
// Tambahkan Anotasi Tinta ke Halaman PDF
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(Color.Green);
```

 Pada langkah ini, kami menginisialisasi`InkAnnotation`objek, yang menentukan halaman, persegi panjang pembatas, dan daftar poin. Kami juga menetapkan subjek, judul, dan warna anotasi.

## Langkah 5: Sesuaikan Batas Anotasi

Untuk menyesuaikan tampilan anotasi kita lebih lanjut, kita akan memodifikasi properti batasnya.

```csharp
// Sesuaikan Batas Anotasi
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);
```

 Di sini, kita membuat`Border` objek untuk anotasi kita, mengatur lebarnya, efeknya, pola garis putus-putusnya, dan gayanya. Langkah ini memastikan bahwa anotasi tersebut menonjol secara visual pada halaman PDF.

## Langkah 6: Simpan Dokumen PDF

Akhirnya, setelah membuat semua perubahan yang diperlukan, saatnya menyimpan dokumen.

```csharp
// Simpan Dokumen PDF
dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nInk annotation line width setup successfully.\nFile saved at " + dataDir);
```

 Kode ini menyimpan dokumen PDF yang dimodifikasi dengan anotasi tinta di direktori yang ditentukan.`Console.WriteLine` pernyataan mengonfirmasi keberhasilan eksekusi kode.

## Kesimpulan

Selamat! Anda telah berhasil membuat dan menyesuaikan anotasi tinta dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Tutorial ini mencakup seluruh proses, mulai dari menginisialisasi dokumen hingga menyimpan file akhir. Dengan pengetahuan ini, Anda dapat lebih jauh mengeksplorasi berbagai kemampuan Aspose.PDF untuk .NET dan menerapkan teknik serupa ke jenis anotasi atau manipulasi PDF lainnya.

## Pertanyaan yang Sering Diajukan

### Dapatkah saya menggunakan warna yang berbeda untuk bagian yang berbeda pada anotasi tinta?  
 Ya, Anda dapat membuat beberapa`InkAnnotation` objek dengan warna berbeda dan menambahkannya ke halaman yang sama atau berbeda di PDF Anda.

### Bagaimana cara mengubah lebar garis secara dinamis?  
 Anda dapat menyesuaikan`LineWidth` milik`LineInfo` objek sebelum mengubah koordinat menjadi titik.

### Apakah mungkin untuk membuat anotasi tinta menjadi transparan?  
 Ya, Anda dapat memodifikasi`Opacity` milik`InkAnnotation` objek untuk membuatnya transparan.

### Bisakah saya menambahkan beberapa anotasi tinta pada halaman yang sama?  
Tentu saja! Anda dapat menambahkan anotasi tinta sebanyak yang Anda suka ke satu halaman dengan mengulangi prosesnya.

### Bagaimana cara menghapus anotasi tinta dari PDF?  
 Anda dapat menghapus anotasi menggunakan`doc.Pages[1].Annotations.Delete(a1)` metode, dimana`a1` adalah objek anotasi Anda.