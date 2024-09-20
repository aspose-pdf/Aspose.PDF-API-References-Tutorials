---
title: Ekstrak Batas Dalam File PDF
linktitle: Ekstrak Batas Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mengekstrak batas dari file PDF dan menyimpannya sebagai gambar menggunakan Aspose.PDF untuk .NET. Panduan langkah demi langkah dengan contoh kode dan kiat untuk meraih keberhasilan.
type: docs
weight: 80
url: /id/net/programming-with-tables/extract-border/
---
## Perkenalan

Saat bekerja dengan PDF, mengekstrak elemen tertentu seperti border atau jalur grafis mungkin tampak seperti tugas yang sulit. Namun dengan Aspose.PDF untuk .NET, Anda dapat dengan mudah mengekstrak border atau bentuk dari file PDF dan menyimpannya sebagai gambar. Dalam tutorial ini, kita akan menyelami proses mengekstrak border dari PDF dan menyimpannya sebagai gambar PNG. Bersiaplah untuk mengendalikan konten grafis PDF Anda!

## Prasyarat

Sebelum kita masuk ke kode, pastikan Anda telah menyiapkan semuanya:

1.  Aspose.PDF untuk .NET: Jika Anda belum menginstal pustaka Aspose.PDF, Anda dapat[unduh disini](https://releases.aspose.com/pdf/net/)Anda juga perlu menerapkan lisensi, baik melalui uji coba gratis atau lisensi yang dibeli.
2. Penyiapan IDE: Siapkan proyek C# di Visual Studio atau IDE .NET lainnya. Pastikan Anda telah menambahkan referensi yang diperlukan ke pustaka Aspose.PDF.
3. Masukkan File PDF: Siapkan file PDF yang akan Anda gunakan untuk mengekstrak batas. Tutorial ini akan merujuk ke file bernama`input.pdf`.

## Mengimpor Paket yang Diperlukan

Mari kita mulai dengan mengimpor namespace yang diperlukan. Paket-paket ini menyediakan alat yang dibutuhkan untuk memanipulasi konten PDF.

```csharp
using System.IO;
using System;
using System.Drawing.Drawing2D;
using System.Drawing.Imaging;
using System.Collections;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

Sekarang setelah kita membahas dasar-dasarnya, mari beralih ke panduan langkah demi langkah di mana kita akan menguraikan setiap bagian kode untuk menjelaskannya secara terperinci.


## Langkah 1: Memuat Dokumen PDF

Langkah pertama adalah memuat dokumen PDF yang berisi border yang ingin Anda ekstrak. Anggap saja seperti membuka buku sebelum mulai membaca — Anda perlu mengakses isinya!

 Kita akan mulai dengan menentukan direktori tempat file PDF Anda disimpan dan memuat dokumen menggunakan`Aspose.Pdf.Document` kelas.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

 Kode ini memuat`input.pdf` file dari direktori yang Anda tentukan. Pastikan jalur file sudah benar, atau Anda mungkin mendapatkan kesalahan file tidak ditemukan.

## Langkah 2: Menyiapkan Grafik dan Bitmap

Sebelum kita mulai mengekstrak, kita perlu membuat kanvas untuk menggambar. Dalam dunia .NET, ini berarti menyiapkan objek Bitmap dan Graphics. Bitmap mewakili gambar, dan objek Graphics akan memungkinkan kita menggambar bentuk, seperti batas, yang diekstrak dari PDF.

```csharp
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);
```

Berikut rinciannya:
- Kami membuat gambar bitmap seukuran halaman pertama PDF.
- GraphicsPath digunakan untuk menentukan bentuk (dalam kasus ini, batas).
- Matriks mendefinisikan bagaimana grafik akan diubah; kita memerlukan matriks inversi karena PDF dan .NET memiliki sistem koordinat yang berbeda.

## Langkah 3: Memproses Konten PDF


Berkas PDF adalah serangkaian perintah gambar, dan kita perlu memproses setiap perintah ini untuk mengidentifikasi dan mengekstrak informasi batas.

```csharp
foreach (Operator op in doc.Pages[1].Contents)
{
    // Memproses perintah seperti menyimpan/mengembalikan status, menggambar garis, mengisi bentuk, dan lain-lain.
}
```

Kode tersebut mengulang setiap operator gambar dalam aliran konten PDF. Setiap operator dapat mewakili garis, persegi panjang, atau instruksi grafis lainnya.

## Langkah 4: Menangani Operator PDF

Setiap operator dalam berkas PDF mengendalikan suatu tindakan. Untuk mengekstrak batas, kita perlu mengidentifikasi perintah seperti "pindah ke", "garis ke", dan "gambar persegi panjang". Operator berikut menangani tindakan ini:

- MoveTo: Memindahkan kursor ke titik awal.
- LineTo: Menggambar garis dari titik saat ini ke titik baru.
- Re: Menggambar persegi panjang (ini bisa menjadi bagian dari perbatasan).

```csharp
Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;

if (opMoveTo != null)
{
    lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
    System.Drawing.PointF linePoint = new System.Drawing.PointF((float)opLineTo.X, (float)opLineTo.Y);
    graphicsPath.AddLine(lastPoint, linePoint);
    lastPoint = linePoint;
}
else if (opRe != null)
{
    System.Drawing.RectangleF re = new System.Drawing.RectangleF((float)opRe.X, (float)opRe.Y, (float)opRe.Width, (float)opRe.Height);
    graphicsPath.AddRectangle(re);
}
```

Pada langkah ini:
- Kami menangkap titik untuk setiap garis atau bentuk yang digambar.
- Untuk persegi panjang (`opRe` ), kami menambahkannya langsung ke`graphicsPath`, yang akan kita gunakan nanti untuk menggambar batas.

## Langkah 5: Menggambar Batas

Setelah kita mengidentifikasi garis dan persegi panjang yang membentuk batas, kita perlu menggambarnya pada objek Bitmap. Di sinilah objek Graphics berperan.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
    gr.SmoothingMode = SmoothingMode.HighQuality;
    gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
}
```

- Kami membuat objek Grafik berdasarkan bitmap.
- SmoothingMode.HighQuality memastikan kita mendapatkan gambar yang halus dan bagus.
- Terakhir, kita menggunakan DrawPath untuk menggambar batas.

## Langkah 6: Menyimpan Border yang Diekstrak

Setelah kita mengekstrak border, sekarang saatnya menyimpannya sebagai file gambar. Ini akan menyimpan border sebagai PNG.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

- Bitmap disimpan sebagai gambar PNG.
- Anda sekarang dapat membuka gambar ini untuk melihat batas yang diekstrak.

## Kesimpulan

Mengekstrak batas dari berkas PDF menggunakan Aspose.PDF untuk .NET mungkin tampak rumit pada awalnya, tetapi setelah Anda menguraikannya, semuanya menjadi mudah. Dengan memahami operator gambar dalam PDF dan memanfaatkan pustaka .NET yang canggih, Anda dapat memanipulasi dan mengekstrak konten grafis secara efisien. Panduan ini memberi Anda dasar yang kuat untuk memulai manipulasi PDF!

## Pertanyaan yang Sering Diajukan

### Bagaimana cara menangani banyak halaman dalam PDF?  
 Anda dapat mengulang setiap halaman dalam dokumen dengan mengulanginya`doc.Pages` alih-alih hardcoding`doc.Pages[1]`.

### Bisakah saya mengekstrak elemen lain, seperti teks, menggunakan pendekatan yang sama?  
Ya, Aspose.PDF menyediakan API yang kaya untuk mengekstrak teks, gambar, dan konten lainnya dari file PDF.

### Bagaimana cara mengajukan lisensi untuk menghindari batasan?  
 Kamu bisa[menerapkan lisensi](https://purchase.aspose.com/temporary-license/) dengan memuatnya melalui`License` kelas yang disediakan oleh Aspose.

### Bagaimana jika PDF saya tidak memiliki batas?  
Jika PDF Anda tidak memiliki batas yang terlihat, proses ekstraksi grafik mungkin tidak akan memberikan hasil apa pun. Pastikan konten PDF menyertakan batas yang dapat digambar.

### Bisakah saya menyimpan output dalam format selain PNG?  
 Ya, cukup ubah`ImageFormat.Png` ke format lain yang didukung seperti`ImageFormat.Jpeg`.