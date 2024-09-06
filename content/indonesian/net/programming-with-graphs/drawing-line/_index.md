---
title: Menggambar Garis
linktitle: Menggambar Garis
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menggambar garis di halaman menggunakan Aspose.PDF untuk .NET. Panduan langkah demi langkah untuk membuat garis khusus.
type: docs
weight: 80
url: /id/net/programming-with-graphs/drawing-line/
---
Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# berikut langkah demi langkah untuk menggambar garis menggunakan Aspose.PDF untuk .NET.

Pastikan Anda telah menginstal pustaka Aspose.PDF dan menyiapkan lingkungan pengembangan sebelum memulai. Anda juga harus memiliki pengetahuan dasar tentang pemrograman C#.

## Langkah 1: Pengaturan Direktori Dokumen

Dalam kode sumber yang diberikan, Anda perlu menentukan direktori tempat Anda ingin menyimpan file PDF yang dihasilkan. Ubah variabel "dataDir" ke direktori yang diinginkan.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Membuat Instansi Dokumen dan Menambahkan Halaman

Kami membuat contoh kelas Dokumen dan menambahkan halaman ke dokumen ini.

```csharp
Document pDoc = new Document();
Page pg = pDoc.Pages.Add();
```

## Langkah 3: Mengatur Margin Halaman

Kami mengatur margin halaman menjadi 0 di semua sisi.

```csharp
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

## Langkah 4: Membuat Objek Grafik dan Garis Pertama

Kita membuat objek Grafik dengan dimensi yang sama dengan dimensi halaman dan menggambar garis pertama dari sudut kiri bawah ke sudut kanan atas halaman.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width, (float)pg.PageInfo.Height);
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect. URY });
graph.Shapes.Add(line);
```

## Langkah 5: Menggambar garis kedua

Kita menggambar garis kedua dari sudut kiri atas ke sudut kanan bawah halaman.

```csharp
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect. LLX });
graph.Shapes.Add(line2);
```

## Langkah 6: Menambahkan Objek Grafik ke Halaman

Kami menambahkan objek Grafik ke koleksi paragraf halaman.

```csharp
pg.Paragraphs.Add(graph);
```

## Langkah 7: Menyimpan File PDF yang Dihasilkan

Terakhir, kami menyimpan file PDF yang dihasilkan dengan nama "DrawingLine_out.pdf" di direktori yang ditentukan.

```csharp
pDoc.Save(dataDir + "DrawingLine_out.pdf");
```

### Contoh kode sumber untuk Menggambar Garis menggunakan Aspose.PDF untuk .NET 

```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buat contoh Dokumen
Document pDoc = new Document();
// Tambahkan halaman ke koleksi halaman dokumen PDF
Page pg = pDoc.Pages.Add();
// Atur margin halaman di semua sisi menjadi 0
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
// Buat objek Grafik dengan Lebar dan Tinggi sama dengan dimensi halaman
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width , (float)pg.PageInfo.Height);
// Buat objek baris pertama mulai dari sudut Kiri Bawah hingga sudut Kanan Atas halaman
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });
// Tambahkan garis ke koleksi bentuk objek Grafik
graph.Shapes.Add(line);
// Gambar garis dari sudut kiri atas halaman ke sudut kanan bawah halaman
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });
// Tambahkan garis ke koleksi bentuk objek Grafik
graph.Shapes.Add(line2);
// Tambahkan objek Grafik ke koleksi paragraf halaman
pg.Paragraphs.Add(graph);
dataDir = dataDir + "DrawingLine_out.pdf";
// Simpan file PDF
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);            

```

## Kesimpulan

Dalam tutorial ini, kami menjelaskan cara menggambar garis menggunakan Aspose.PDF untuk .NET. Kini Anda dapat menggunakan pengetahuan ini untuk membuat bentuk geometris dengan garis khusus dalam berkas PDF Anda.

### Pertanyaan yang Sering Diajukan

#### T: Apa tujuan dari tutorial ini?

J: Tujuan tutorial ini adalah untuk memandu Anda melalui proses menggambar garis menggunakan Aspose.PDF untuk .NET. Anda akan mempelajari cara membuat garis pada halaman PDF dan menyesuaikan tampilannya.

#### T: Prasyarat apa yang diperlukan sebelum memulai?

J: Sebelum memulai, pastikan Anda telah menginstal pustaka Aspose.PDF dan menyiapkan lingkungan pengembangan Anda. Pengetahuan dasar tentang pemrograman C# juga direkomendasikan.

#### T: Bagaimana cara menentukan direktori untuk menyimpan berkas PDF?

A: Ubah variabel "dataDir" dalam kode sumber yang disediakan untuk menunjukkan direktori tempat Anda ingin menyimpan file PDF yang dihasilkan.

#### T: Bagaimana cara membuat garis pada halaman PDF?

A: Tutorial ini menunjukkan cara membuat objek Graph dengan dimensi halaman, lalu menambahkan objek Line ke dalamnya. Ubah koordinat dan properti objek Line untuk membuat garis yang diinginkan.

#### T: Bisakah saya menyesuaikan tampilan garis?

A: Ya, Anda dapat menyesuaikan tampilan garis dengan mengubah properti objek Garis. Ini termasuk mengubah koordinat, warna, ketebalan, dan atribut grafis lainnya.

#### T: Bagaimana cara menyimpan dokumen PDF setelah menggambar garis?

 A: Setelah menambahkan objek Grafik dengan objek Garis ke halaman, Anda dapat menyimpan dokumen PDF yang dihasilkan menggunakan`pDoc.Save(dataDir + "DrawingLine_out.pdf");` baris dalam kode sumber yang disediakan.

#### T: Dapatkah saya menggambar garis dengan sudut dan orientasi yang berbeda?

A: Ya, Anda dapat menggambar garis dengan sudut dan orientasi berbeda dengan menyesuaikan koordinat dan properti objek Garis dalam Grafik.