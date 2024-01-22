---
title: Buat Persegi Panjang Dengan Warna Alpha
linktitle: Buat Persegi Panjang Dengan Warna Alpha
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara membuat persegi panjang dengan warna transparan menggunakan Aspose.PDF untuk .NET. Panduan langkah demi langkah untuk menyesuaikan transparansi.
type: docs
weight: 60
url: /id/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# berikut langkah demi langkah untuk membuat persegi panjang dengan warna alfa menggunakan Aspose.PDF untuk .NET.

Pastikan Anda telah menginstal perpustakaan Aspose.PDF dan mengatur lingkungan pengembangan Anda sebelum memulai. Juga memiliki pengetahuan dasar tentang pemrograman C#.

## Langkah 1: Pengaturan Direktori Dokumen

Dalam kode sumber yang disediakan, Anda perlu menentukan direktori tempat Anda ingin menyimpan file PDF yang dihasilkan. Ubah variabel "dataDir" ke direktori yang diinginkan.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Membuat Instansi Objek Dokumen dan Menambahkan Halaman

Kami membuat instance kelas Dokumen dan menambahkan halaman ke dokumen ini.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Langkah 3: Membuat Objek Grafik dan Persegi Panjang

Kita membuat objek Graph dengan dimensi tertentu dan persegi panjang dengan dimensi tertentu.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## Langkah 4: Menyiapkan warna alfa untuk persegi panjang

Kita dapat menentukan warna alfa untuk persegi panjang menggunakan metode FromArgb dari kelas System.Drawing.Color.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## Langkah 5: Menambahkan Persegi Panjang ke Objek Grafik

Kita menambahkan persegi panjang ke kumpulan bentuk objek Graph.

```csharp
canvas.Shapes.Add(rect);
```

## Langkah 6: Membuat persegi panjang kedua dengan warna alpha berbeda

Kami membuat persegi panjang kedua dengan dimensi tertentu dan warna alfa lainnya.

```csharp
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
```

## Langkah 7: Menambahkan Objek Grafik ke Halaman

Kita menambahkan objek Graph ke koleksi Paragraph objek Halaman.

```csharp
page.Paragraphs.Add(canvas);
```

## Langkah 8: Menyimpan File PDF yang Dihasilkan

Terakhir, kami menyimpan file PDF yang dihasilkan dengan nama "CreateRectangleWithAlphaColor_out.pdf" di direktori yang ditentukan.

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### Contoh kode sumber untuk Membuat Persegi Panjang Dengan Warna Alfa menggunakan Aspose.PDF untuk .NET 

```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buat instance Dokumen
Document doc = new Document();
// Tambahkan halaman ke halaman koleksi file PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Buat instance Grafik
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Buat objek persegi panjang dengan dimensi tertentu
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
//Atur warna isian grafik dari struktur System.Drawing.Color dari nilai ARGB 32-bit
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Tambahkan objek persegi panjang ke kumpulan bentuk instance Grafik
canvas.Shapes.Add(rect);
// Buat objek persegi panjang kedua
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
// Tambahkan contoh grafik ke kumpulan paragraf objek halaman
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
// Simpan berkas PDF
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## Kesimpulan

Dalam tutorial ini, kami menjelaskan cara membuat persegi panjang dengan warna alfa menggunakan Aspose.PDF untuk .NET. Anda sekarang dapat menggunakan pengetahuan ini untuk membuat bentuk geometris dengan warna transparan di file PDF Anda.

## FAQ

#### T: Apa tujuan dari tutorial ini?

J: Tutorial ini bertujuan untuk memandu Anda melalui proses membuat persegi panjang dengan warna alfa menggunakan Aspose.PDF untuk .NET. Anda akan belajar cara menambahkan bentuk geometris dengan warna transparan ke file PDF Anda.

#### Q: Prasyarat apa saja yang diperlukan sebelum memulai?

J: Sebelum memulai, pastikan Anda telah menginstal pustaka Aspose.PDF dan menyiapkan lingkungan pengembangan Anda. Selain itu, disarankan untuk memiliki pemahaman dasar tentang pemrograman C#.

#### Q: Bagaimana cara menentukan direktori untuk menyimpan file PDF?

J: Dalam kode sumber yang disediakan, Anda dapat memodifikasi variabel "dataDir" untuk menunjukkan direktori tempat Anda ingin menyimpan file PDF yang dihasilkan.

#### Q: Apa kegunaan dari objek Graph dan Rectangle?

A: Objek Graph bertindak sebagai wadah untuk elemen menggambar, sedangkan Rectangle mewakili bentuk geometris yang akan Anda tambahkan ke PDF.

#### T: Bagaimana cara mengatur warna alfa untuk persegi panjang?

J: Anda dapat menentukan warna alfa untuk persegi panjang menggunakan`FillColor` properti dari`GraphInfo` objek dan itu`Color.FromRgb` metode dengan nilai ARGB.

#### T: Bisakah saya membuat beberapa persegi panjang dengan warna alfa berbeda?

J: Ya, Anda dapat membuat beberapa persegi panjang dengan warna alfa berbeda dengan mengikuti langkah serupa seperti yang ditunjukkan dalam tutorial.

#### T: Bagaimana cara menyimpan file PDF yang dihasilkan setelah membuat persegi panjang dengan warna alfa?

 A: Setelah membuat persegi panjang dengan warna alpha, Anda dapat menyimpan file PDF yang dihasilkan menggunakan`doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");` baris dalam kode sumber yang disediakan.