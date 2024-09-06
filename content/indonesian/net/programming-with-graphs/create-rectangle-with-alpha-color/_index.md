---
title: Membuat Persegi Panjang Dengan Warna Alfa
linktitle: Membuat Persegi Panjang Dengan Warna Alfa
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara membuat persegi panjang dengan warna transparan menggunakan Aspose.PDF untuk .NET. Panduan langkah demi langkah untuk menyesuaikan transparansi.
type: docs
weight: 60
url: /id/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# berikut langkah demi langkah untuk membuat persegi panjang dengan warna alfa menggunakan Aspose.PDF untuk .NET.

Pastikan Anda telah menginstal pustaka Aspose.PDF dan menyiapkan lingkungan pengembangan sebelum memulai. Anda juga harus memiliki pengetahuan dasar tentang pemrograman C#.

## Langkah 1: Pengaturan Direktori Dokumen

Dalam kode sumber yang diberikan, Anda perlu menentukan direktori tempat Anda ingin menyimpan file PDF yang dihasilkan. Ubah variabel "dataDir" ke direktori yang diinginkan.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Membuat Instansi Objek Dokumen dan Menambahkan Halaman

Kami membuat contoh kelas Dokumen dan menambahkan halaman ke dokumen ini.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Langkah 3: Membuat Objek Grafik dan Persegi Panjang

Kita membuat objek Grafik dengan dimensi tertentu, dan persegi panjang dengan dimensi tertentu.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## Langkah 4: Mengatur warna alfa untuk persegi panjang

Kita dapat menentukan warna alfa untuk persegi panjang menggunakan metode FromArgb dari kelas System.Drawing.Color.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## Langkah 5: Menambahkan Persegi Panjang ke Objek Grafik

Kita menambahkan persegi panjang ke koleksi bentuk objek Grafik.

```csharp
canvas.Shapes.Add(rect);
```

## Langkah 6: Membuat persegi panjang kedua dengan warna alfa yang berbeda

Kita membuat persegi panjang kedua dengan dimensi tertentu dan warna alfa lain.

```csharp
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
```

## Langkah 7: Menambahkan Objek Grafik ke Halaman

Kita menambahkan objek Grafik ke dalam koleksi Paragraf objek Halaman.

```csharp
page.Paragraphs.Add(canvas);
```

## Langkah 8: Menyimpan File PDF yang Dihasilkan

Terakhir, kami menyimpan file PDF yang dihasilkan dengan nama "CreateRectangleWithAlphaColor_out.pdf" di direktori yang ditentukan.

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### Contoh kode sumber untuk Membuat Persegi Panjang dengan Warna Alfa menggunakan Aspose.PDF untuk .NET 

```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Membuat contoh dokumen
Document doc = new Document();
// Tambahkan halaman ke koleksi halaman file PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Buat contoh Grafik
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Membuat objek persegi panjang dengan dimensi tertentu
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
// Tetapkan warna isian grafik dari struktur System.Drawing.Color dari nilai ARGB 32-bit
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Tambahkan objek persegi panjang ke koleksi bentuk instance Grafik
canvas.Shapes.Add(rect);
// Buat objek persegi panjang kedua
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
// Tambahkan contoh grafik ke kumpulan paragraf objek halaman
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
// Simpan file PDF
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## Kesimpulan

Dalam tutorial ini, kami menjelaskan cara membuat persegi panjang dengan warna alfa menggunakan Aspose.PDF untuk .NET. Kini Anda dapat menggunakan pengetahuan ini untuk membuat bentuk geometris dengan warna transparan dalam berkas PDF Anda.

## Pertanyaan yang Sering Diajukan

#### T: Apa tujuan dari tutorial ini?

J: Tutorial ini bertujuan untuk memandu Anda melalui proses pembuatan persegi panjang dengan warna alfa menggunakan Aspose.PDF untuk .NET. Anda akan mempelajari cara menambahkan bentuk geometris dengan warna transparan ke berkas PDF Anda.

#### T: Prasyarat apa yang diperlukan sebelum memulai?

J: Sebelum memulai, pastikan Anda telah menginstal pustaka Aspose.PDF dan menyiapkan lingkungan pengembangan Anda. Selain itu, Anda disarankan untuk memiliki pemahaman dasar tentang pemrograman C#.

#### T: Bagaimana cara menentukan direktori untuk menyimpan berkas PDF?

A: Dalam kode sumber yang disediakan, Anda dapat mengubah variabel "dataDir" untuk menunjukkan direktori tempat Anda ingin menyimpan file PDF yang dihasilkan.

#### T: Apa tujuan dari objek Grafik dan Persegi Panjang?

A: Objek Grafik berfungsi sebagai wadah untuk elemen gambar, sedangkan Persegi Panjang mewakili bentuk geometris yang akan Anda tambahkan ke PDF.

#### T: Bagaimana cara mengatur warna alfa untuk persegi panjang?

 A: Anda dapat menentukan warna alfa untuk persegi panjang menggunakan`FillColor` milik`GraphInfo` objek dan`Color.FromRgb` metode dengan nilai ARGB.

#### T: Dapatkah saya membuat beberapa persegi panjang dengan warna alfa yang berbeda?

A: Ya, Anda dapat membuat beberapa persegi panjang dengan warna alfa yang berbeda dengan mengikuti langkah-langkah serupa seperti yang ditunjukkan dalam tutorial.

#### T: Bagaimana cara menyimpan berkas PDF yang dihasilkan setelah membuat persegi panjang dengan warna alfa?

 A: Setelah membuat persegi panjang dengan warna alfa, Anda dapat menyimpan file PDF yang dihasilkan menggunakan`doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");` baris dalam kode sumber yang disediakan.