---
title: Buat Persegi Panjang Terisi
linktitle: Buat Persegi Panjang Terisi
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara membuat persegi panjang yang terisi dengan Aspose.PDF untuk .NET. Panduan langkah demi langkah untuk menyesuaikan warna isian.
type: docs
weight: 50
url: /id/net/programming-with-graphs/create-filled-rectangle/
---
Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# berikut langkah demi langkah untuk membuat persegi panjang yang terisi menggunakan Aspose.PDF untuk .NET.

Pastikan Anda telah menginstal pustaka Aspose.PDF dan menyiapkan lingkungan pengembangan sebelum memulai. Anda juga harus memiliki pengetahuan dasar tentang pemrograman C#.

## Langkah 1: Pengaturan Direktori Dokumen

Dalam kode sumber yang diberikan, Anda perlu menentukan direktori tempat Anda ingin menyimpan file PDF yang dihasilkan. Ubah variabel "dataDir" ke direktori yang diinginkan.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Membuat Instansi Dokumen dan Menambahkan Halaman

Kami membuat contoh kelas Dokumen dan menambahkan halaman ke dokumen ini.

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

Kami membuat objek Persegi Panjang dengan dimensi yang ditentukan dan menambahkannya ke koleksi bentuk bagan.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
graph.Shapes.Add(rect);
```

## Langkah 5: Mengatur warna isian

Kita dapat menentukan warna isian untuk persegi panjang menggunakan properti FillColor dari objek GraphInfo.

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
// Tambahkan halaman ke koleksi halaman file PDF
Page page = doc.Pages.Add();
// Buat contoh Grafik
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// Tambahkan objek grafik ke koleksi paragraf dari contoh halaman
page.Paragraphs.Add(graph);
// Buat instance Persegi Panjang
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
// Tentukan warna isian untuk objek Grafik
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
// Tambahkan objek persegi panjang ke koleksi bentuk objek Grafik
graph.Shapes.Add(rect);
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// Simpan file PDF
doc.Save(dataDir);
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);            

```

## Kesimpulan

Dalam tutorial ini, kami menjelaskan cara membuat persegi panjang yang terisi menggunakan Aspose.PDF untuk .NET. Kini Anda dapat menggunakan pengetahuan ini untuk membuat bentuk geometris dengan warna isian khusus dalam berkas PDF Anda.

## Pertanyaan yang Sering Diajukan

#### T: Apa tujuan dari tutorial ini?

A: Tujuan dari tutorial ini adalah untuk memandu Anda melalui proses pembuatan persegi panjang terisi menggunakan Aspose.PDF untuk .NET, memungkinkan Anda untuk menambahkan bentuk geometris khusus dengan warna isian ke file PDF Anda.

#### T: Prasyarat apa yang diperlukan sebelum memulai?

J: Sebelum memulai, pastikan Anda telah menginstal pustaka Aspose.PDF dan menyiapkan lingkungan pengembangan Anda. Selain itu, Anda disarankan untuk memiliki pemahaman dasar tentang pemrograman C#.

#### T: Bagaimana cara menentukan direktori untuk menyimpan berkas PDF?

A: Dalam kode sumber yang disediakan, Anda dapat mengubah variabel "dataDir" untuk menunjukkan direktori tempat Anda ingin menyimpan file PDF yang dihasilkan.

#### T: Apa tujuan dari objek Grafik?

A: Objek Graph berfungsi sebagai wadah untuk elemen gambar. Objek ini dibuat dengan dimensi tertentu dan ditambahkan ke kumpulan paragraf halaman.

#### T: Bagaimana cara menambahkan persegi panjang terisi ke dokumen PDF?

A: Untuk menambahkan persegi panjang terisi, buatlah contoh kelas Persegi Panjang dengan dimensi dan warna isi yang ditentukan, lalu tambahkan ke koleksi bentuk grafik.

#### T: Dapatkah saya menyesuaikan dimensi dan warna isi persegi panjang?

 A: Ya, Anda dapat menyesuaikan dimensi dan mengisi warna persegi panjang dengan memodifikasi parameter yang diteruskan ke`Aspose.Pdf.Drawing.Rectangle` konstruktor dan pengaturan properti FillColor.

#### T: Bagaimana cara menyimpan berkas PDF yang dihasilkan setelah membuat persegi panjang yang terisi?

 A: Setelah membuat persegi panjang yang terisi, Anda dapat menyimpan file PDF yang dihasilkan menggunakan`doc.Save(dataDir + "CreateFilledRectangle_out.pdf");` baris dalam kode sumber yang disediakan.