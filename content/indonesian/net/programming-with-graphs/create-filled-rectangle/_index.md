---
title: Buat Persegi Panjang Terisi
linktitle: Buat Persegi Panjang Terisi
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara membuat persegi panjang terisi dengan Aspose.PDF untuk .NET. Panduan langkah demi langkah untuk menyesuaikan warna isian.
type: docs
weight: 50
url: /id/net/programming-with-graphs/create-filled-rectangle/
---
Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# berikut langkah demi langkah untuk membuat persegi panjang terisi menggunakan Aspose.PDF untuk .NET.

Pastikan Anda telah menginstal perpustakaan Aspose.PDF dan mengatur lingkungan pengembangan Anda sebelum memulai. Juga memiliki pengetahuan dasar tentang pemrograman C#.

## Langkah 1: Pengaturan Direktori Dokumen

Dalam kode sumber yang disediakan, Anda perlu menentukan direktori tempat Anda ingin menyimpan file PDF yang dihasilkan. Ubah variabel "dataDir" ke direktori yang diinginkan.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Membuat Instans Dokumen dan Menambahkan Halaman

Kami membuat instance kelas Dokumen dan menambahkan halaman ke dokumen ini.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Langkah 3: Membuat Objek Grafik dan Menambahkannya ke Halaman

Kami membuat objek Grafik dengan dimensi tertentu dan menambahkannya ke koleksi paragraf halaman.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## Langkah 4: Buat Objek Persegi Panjang dan Tambahkan ke Bagan

Kita membuat objek Rectangle dengan dimensi yang ditentukan dan menambahkannya ke koleksi bentuk grafik.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
graph.Shapes.Add(rect);
```

## Langkah 5: Mengatur warna isian

Kita dapat menentukan warna isian untuk persegi panjang menggunakan properti FillColor pada objek GraphInfo.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## Langkah 6: Menyimpan File PDF yang Dihasilkan

Terakhir, kami menyimpan file PDF yang dihasilkan dengan nama "CreateFilledRectangle_out.pdf" di direktori yang ditentukan.

```csharp
doc.Save(dataDir + "CreateFilledRectangle_out.pdf");
```

### Contoh kode sumber untuk Membuat Persegi Panjang Terisi menggunakan Aspose.PDF untuk .NET 

```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buat contoh Dokumen
Document doc = new Document();
// Tambahkan halaman ke halaman koleksi file PDF
Page page = doc.Pages.Add();
// Buat instance Grafik
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// Tambahkan objek grafik ke kumpulan paragraf contoh halaman
page.Paragraphs.Add(graph);
// Buat instance Persegi Panjang
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
// Tentukan warna isian untuk objek Grafik
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
// Tambahkan objek persegi panjang ke kumpulan bentuk objek Grafik
graph.Shapes.Add(rect);
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// Simpan berkas PDF
doc.Save(dataDir);
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);            

```

## Kesimpulan

Dalam tutorial ini, kami menjelaskan cara membuat persegi panjang terisi menggunakan Aspose.PDF untuk .NET. Anda sekarang dapat menggunakan pengetahuan ini untuk membuat bentuk geometris dengan warna isian khusus di file PDF Anda.

## FAQ

#### T: Apa tujuan dari tutorial ini?

J: Tujuan tutorial ini adalah memandu Anda melalui proses pembuatan persegi panjang terisi menggunakan Aspose.PDF untuk .NET, memungkinkan Anda menambahkan bentuk geometris khusus dengan warna isian ke file PDF Anda.

#### Q: Prasyarat apa saja yang diperlukan sebelum memulai?

J: Sebelum memulai, pastikan Anda telah menginstal pustaka Aspose.PDF dan menyiapkan lingkungan pengembangan Anda. Selain itu, disarankan untuk memiliki pemahaman dasar tentang pemrograman C#.

#### Q: Bagaimana cara menentukan direktori untuk menyimpan file PDF?

J: Dalam kode sumber yang disediakan, Anda dapat memodifikasi variabel "dataDir" untuk menunjukkan direktori tempat Anda ingin menyimpan file PDF yang dihasilkan.

#### Q: Apa tujuan dari objek Graph?

A: Objek Graph bertindak sebagai wadah untuk elemen gambar. Itu dibuat dengan dimensi tertentu dan ditambahkan ke koleksi paragraf halaman.

#### T: Bagaimana cara menambahkan persegi panjang penuh ke dokumen PDF?

J: Untuk menambahkan persegi panjang terisi, buat instance kelas Rectangle dengan dimensi dan warna isian tertentu, lalu tambahkan ke kumpulan bentuk grafik.

#### T: Dapatkah saya menyesuaikan dimensi dan mengisi warna persegi panjang?

 J: Ya, Anda dapat menyesuaikan dimensi dan mengisi warna persegi panjang dengan memodifikasi parameter yang diteruskan ke`Aspose.Pdf.Drawing.Rectangle` konstruktor dan mengatur properti FillColor.

#### T: Bagaimana cara menyimpan file PDF yang dihasilkan setelah membuat persegi panjang terisi?

 A: Setelah membuat persegi panjang yang terisi, Anda dapat menyimpan file PDF yang dihasilkan menggunakan`doc.Save(dataDir + "CreateFilledRectangle_out.pdf");` baris dalam kode sumber yang disediakan.