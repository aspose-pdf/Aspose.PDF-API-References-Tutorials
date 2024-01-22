---
title: Garis Gambar
linktitle: Garis Gambar
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menggambar garis melintasi halaman menggunakan Aspose.PDF untuk .NET. Panduan langkah demi langkah untuk membuat garis khusus.
type: docs
weight: 80
url: /id/net/programming-with-graphs/drawing-line/
---
Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# berikut langkah demi langkah untuk menggambar garis menggunakan Aspose.PDF untuk .NET.

Pastikan Anda telah menginstal perpustakaan Aspose.PDF dan mengatur lingkungan pengembangan Anda sebelum memulai. Juga memiliki pengetahuan dasar tentang pemrograman C#.

## Langkah 1: Pengaturan Direktori Dokumen

Dalam kode sumber yang disediakan, Anda perlu menentukan direktori tempat Anda ingin menyimpan file PDF yang dihasilkan. Ubah variabel "dataDir" ke direktori yang diinginkan.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Membuat Instans Dokumen dan Menambahkan Halaman

Kami membuat instance kelas Dokumen dan menambahkan halaman ke dokumen ini.

```csharp
Document pDoc = new Document();
Page pg = pDoc.Pages.Add();
```

## Langkah 3: Mengatur Margin Halaman

Kami mengatur margin halaman ke 0 di semua sisi.

```csharp
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

## Langkah 4: Membuat Objek Grafik dan Baris Pertama

Kita membuat objek Grafik dengan dimensi yang sama dengan halaman dan menggambar garis pertama dari sudut kiri bawah ke sudut kanan atas halaman.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width, (float)pg.PageInfo.Height);
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect. URY });
graph.Shapes.Add(line);
```

## Langkah 5: Menggambar garis kedua

Kami menggambar garis kedua dari sudut kiri atas ke sudut kanan bawah halaman.

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
// Tambahkan halaman ke halaman koleksi dokumen PDF
Page pg = pDoc.Pages.Add();
// Tetapkan margin halaman di semua sisi sebagai 0
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
// Buat objek Grafik dengan Lebar dan Tinggi sama dengan dimensi halaman
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width , (float)pg.PageInfo.Height);
// Buat objek baris pertama mulai dari pojok kiri bawah hingga pojok kanan atas halaman
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });
// Tambahkan garis ke kumpulan bentuk objek Grafik
graph.Shapes.Add(line);
// Tarik garis dari pojok kiri atas halaman ke pojok kanan bawah halaman
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });
// Tambahkan garis ke kumpulan bentuk objek Grafik
graph.Shapes.Add(line2);
// Tambahkan objek Grafik ke kumpulan halaman paragraf
pg.Paragraphs.Add(graph);
dataDir = dataDir + "DrawingLine_out.pdf";
// Simpan berkas PDF
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);            

```

## Kesimpulan

Dalam tutorial ini, kami menjelaskan cara menggambar garis menggunakan Aspose.PDF untuk .NET. Anda sekarang dapat menggunakan pengetahuan ini untuk membuat bentuk geometris dengan garis khusus di file PDF Anda.

### FAQ

#### T: Apa tujuan dari tutorial ini?

J: Tujuan tutorial ini adalah memandu Anda melalui proses menggambar garis menggunakan Aspose.PDF untuk .NET. Anda akan mempelajari cara membuat garis pada halaman PDF dan menyesuaikan tampilannya.

#### Q: Prasyarat apa saja yang diperlukan sebelum memulai?

J: Sebelum memulai, pastikan Anda telah menginstal pustaka Aspose.PDF dan menyiapkan lingkungan pengembangan Anda. Pengetahuan dasar tentang pemrograman C# juga dianjurkan.

#### Q: Bagaimana cara menentukan direktori untuk menyimpan file PDF?

J: Ubah variabel "dataDir" dalam kode sumber yang disediakan untuk menunjukkan direktori tempat Anda ingin menyimpan file PDF yang dihasilkan.

#### Q: Bagaimana cara membuat garis pada halaman PDF?

A: Tutorial ini mendemonstrasikan pembuatan objek Grafik dengan dimensi halaman dan kemudian menambahkan objek Garis ke dalamnya. Ubah koordinat dan properti objek Garis untuk membuat garis yang diinginkan.

#### T: Dapatkah saya menyesuaikan tampilan garis?

A: Ya, Anda dapat menyesuaikan tampilan garis dengan memodifikasi properti objek Garis. Ini termasuk mengubah koordinat, warna, ketebalan, dan atribut grafis lainnya.

#### Q: Bagaimana cara menyimpan dokumen PDF setelah menggambar garis?

A: Setelah menambahkan objek Grafik dengan objek Garis ke halaman, Anda dapat menyimpan dokumen PDF yang dihasilkan menggunakan`pDoc.Save(dataDir + "DrawingLine_out.pdf");` baris dalam kode sumber yang disediakan.

#### T: Dapatkah saya menggambar garis dengan sudut dan orientasi berbeda?

A: Ya, Anda dapat menggambar garis dengan sudut dan orientasi berbeda dengan menyesuaikan koordinat dan properti objek Garis di dalam Grafik.