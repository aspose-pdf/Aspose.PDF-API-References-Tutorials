---
title: Panjang Garis
linktitle: Panjang Garis
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mengatur panjang tanda hubung dengan Aspose.PDF untuk .NET. Panduan langkah demi langkah untuk menyesuaikan pola tanda hubung.
type: docs
weight: 70
url: /id/net/programming-with-graphs/dash-length/
---
Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# berikut langkah demi langkah untuk mengatur panjang tanda hubung menggunakan Aspose.PDF untuk .NET.

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
Page page = doc.Pages.Add();
```

## Langkah 3: Membuat Objek Grafik dan menambahkannya ke halaman

Kami membuat objek Grafik dengan dimensi tertentu dan menambahkannya ke koleksi paragraf halaman.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(canvas);
```

## Langkah 4: Membuat Objek Garis dan Mengonfigurasinya

Kami membuat objek Garis dengan koordinat yang ditentukan dan mengonfigurasi warna dan panjang garis putus-putus.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Langkah 5: Menambahkan Garis ke Objek Grafik

Kita menambahkan garis ke koleksi bentuk objek Grafik.

```csharp
canvas.Shapes.Add(line);
```

## Langkah 6: Menyimpan File PDF yang Dihasilkan

Terakhir, kami menyimpan file PDF yang dihasilkan dengan nama "DashLength_out.pdf" di direktori yang ditentukan.

```csharp
doc.Save(dataDir + "DashLength_out.pdf");
```

### Contoh kode sumber untuk Dash Length menggunakan Aspose.PDF untuk .NET 

```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Membuat contoh dokumen
Document doc = new Document();
// Tambahkan halaman ke koleksi halaman objek Dokumen
Page page = doc.Pages.Add();
// Membuat objek Gambar dengan dimensi tertentu
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Tambahkan objek gambar ke koleksi paragraf dari contoh halaman
page.Paragraphs.Add(canvas);
// Buat objek Garis
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Mengatur warna untuk objek Garis
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
// Tentukan larik tanda hubung untuk objek garis
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
// Mengatur fase tanda hubung untuk instance Garis
line.GraphInfo.DashPhase = 1;
// Tambahkan garis ke koleksi bentuk objek gambar
canvas.Shapes.Add(line);
dataDir = dataDir + "DashLength_out.pdf";
// Simpan dokumen PDF
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);            

```

## Kesimpulan

Dalam tutorial ini, kami menjelaskan cara mengatur panjang garis putus-putus menggunakan Aspose.PDF untuk .NET. Sekarang Anda dapat menggunakan pengetahuan ini untuk membuat garis dengan pola garis putus-putus khusus dalam file PDF Anda.

## Tanya Jawab Umum

#### T: Apa tujuan dari tutorial ini?

J: Tujuan tutorial ini adalah untuk memandu Anda melalui proses pengaturan panjang garis putus-putus menggunakan Aspose.PDF untuk .NET. Anda akan mempelajari cara membuat garis dengan pola garis putus-putus khusus dalam file PDF Anda.

#### T: Prasyarat apa yang diperlukan sebelum memulai?

J: Sebelum memulai, pastikan Anda telah menginstal pustaka Aspose.PDF dan menyiapkan lingkungan pengembangan Anda. Pemahaman dasar tentang pemrograman C# juga direkomendasikan.

#### T: Bagaimana cara menentukan direktori untuk menyimpan berkas PDF?

A: Ubah variabel "dataDir" dalam kode sumber yang disediakan untuk menunjukkan direktori tempat Anda ingin menyimpan file PDF yang dihasilkan.

#### T: Bagaimana cara membuat garis dengan pola garis putus-putus khusus?

 A: Tutorial ini menunjukkan cara membuat objek Garis dan mengonfigurasi warna, susunan garis putus-putus, dan fase garis putus-putusnya menggunakan`GraphInfo` objek. Ubah pengaturan ini untuk mendapatkan pola garis putus-putus yang diinginkan.

#### T: Bisakah saya menyesuaikan warna garis?

 A: Ya, Anda dapat menyesuaikan warna garis dengan mengatur`Color` milik`GraphInfo` objek yang terkait dengan Garis.

#### T: Bagaimana cara menyimpan dokumen PDF setelah mengatur panjang tanda hubung?

 A: Setelah mengonfigurasi objek Garis dengan pola garis putus-putus yang diinginkan, Anda dapat menyimpan dokumen PDF yang dihasilkan menggunakan`doc.Save(dataDir + "DashLength_out.pdf");` baris dalam kode sumber yang disediakan.