---
title: Panjang Dasbor
linktitle: Panjang Dasbor
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara mengatur panjang tanda hubung dengan Aspose.PDF untuk .NET. Panduan langkah demi langkah untuk menyesuaikan pola dasbor.
type: docs
weight: 70
url: /id/net/programming-with-graphs/dash-length/
---
Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# berikut langkah demi langkah untuk mengatur panjang tanda hubung menggunakan Aspose.PDF untuk .NET.

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
Page page = doc.Pages.Add();
```

## Langkah 3: Membuat Objek Grafik dan menambahkannya ke halaman

Kami membuat objek Grafik dengan dimensi tertentu dan menambahkannya ke koleksi paragraf halaman.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(canvas);
```

## Langkah 4: Membuat Objek Garis dan Konfigurasi

Kami membuat objek Garis dengan koordinat yang ditentukan dan mengkonfigurasi warna dan panjang garis putus-putus.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Langkah 5: Menambahkan Garis ke Objek Grafik

Kita menambahkan garis pada kumpulan bentuk objek Graph.

```csharp
canvas.Shapes.Add(line);
```

## Langkah 6: Menyimpan File PDF yang Dihasilkan

Terakhir, kami menyimpan file PDF yang dihasilkan dengan nama "DashLength_out.pdf" di direktori yang ditentukan.

```csharp
doc.Save(dataDir + "DashLength_out.pdf");
```

### Contoh kode sumber untuk Panjang Dash menggunakan Aspose.PDF untuk .NET 

```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buat instance Dokumen
Document doc = new Document();
// Tambahkan halaman ke halaman koleksi objek Dokumen
Page page = doc.Pages.Add();
// Membuat objek Gambar dengan dimensi tertentu
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Tambahkan objek gambar ke kumpulan paragraf contoh halaman
page.Paragraphs.Add(canvas);
// Buat objek Garis
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Atur warna untuk objek Garis
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
// Tentukan larik tanda hubung untuk objek garis
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
// Atur fase tanda hubung untuk instance Line
line.GraphInfo.DashPhase = 1;
// Tambahkan garis ke kumpulan bentuk objek gambar
canvas.Shapes.Add(line);
dataDir = dataDir + "DashLength_out.pdf";
// Simpan dokumen PDF
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);            

```

## Kesimpulan

Dalam tutorial ini, kami menjelaskan cara mengatur panjang tanda hubung menggunakan Aspose.PDF untuk .NET. Sekarang Anda dapat menggunakan pengetahuan ini untuk membuat garis dengan pola garis khusus di file PDF Anda.

## FAQ

#### T: Apa tujuan dari tutorial ini?

J: Tujuan tutorial ini adalah memandu Anda melalui proses pengaturan panjang tanda hubung untuk garis menggunakan Aspose.PDF untuk .NET. Anda akan mempelajari cara membuat garis dengan pola garis putus-putus khusus di file PDF Anda.

#### Q: Prasyarat apa saja yang diperlukan sebelum memulai?

J: Sebelum memulai, pastikan Anda telah menginstal pustaka Aspose.PDF dan menyiapkan lingkungan pengembangan Anda. Pemahaman dasar tentang pemrograman C# juga disarankan.

#### Q: Bagaimana cara menentukan direktori untuk menyimpan file PDF?

J: Ubah variabel "dataDir" dalam kode sumber yang disediakan untuk menunjukkan direktori tempat Anda ingin menyimpan file PDF yang dihasilkan.

#### T: Bagaimana cara membuat garis dengan pola garis putus-putus khusus?

 J: Tutorial ini mendemonstrasikan pembuatan objek Garis dan mengonfigurasi warna, larik garis putus-putus, dan fase garis putus-putus menggunakan`GraphInfo` obyek. Ubah pengaturan ini untuk mencapai pola garis putus-putus yang diinginkan.

#### T: Dapatkah saya menyesuaikan warna garis?

 A: Ya, Anda dapat menyesuaikan warna garis dengan mengatur`Color` properti dari`GraphInfo` objek yang terkait dengan Garis.

#### T: Bagaimana cara menyimpan dokumen PDF setelah mengatur panjang tanda hubung?

 A: Setelah mengkonfigurasi objek Garis dengan pola garis yang diinginkan, Anda dapat menyimpan dokumen PDF yang dihasilkan menggunakan`doc.Save(dataDir + "DashLength_out.pdf");` baris dalam kode sumber yang disediakan.