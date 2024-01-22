---
title: Tambahkan Objek Garis Dalam File PDF
linktitle: Tambahkan Objek Garis Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menambahkan objek garis kustom dalam file PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 30
url: /id/net/programming-with-graphs/add-line-object/
---
Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# berikut langkah demi langkah untuk menambahkan objek garis menggunakan Aspose.PDF untuk .NET.

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

## Langkah 3: Membuat Objek Grafik dan menambahkannya ke halaman

Kami membuat objek Grafik dengan dimensi tertentu dan menambahkannya ke koleksi paragraf halaman.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## Langkah 4: Buat Objek Garis dan Tambahkan ke Bagan

Kita membuat objek Garis dengan koordinat yang ditentukan dan menambahkannya ke koleksi bentuk bagan.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## Langkah 5: Pengaturan Jalur

Kita dapat menentukan properti untuk garis, seperti tipe garis putus-putus dan fase garis putus-putus.

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Langkah 6: Menyimpan File PDF

Terakhir, kami menyimpan file PDF yang dihasilkan dengan nama "AddLineObject_out.pdf" di direktori yang ditentukan.

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### Contoh kode sumber untuk Tambahkan Objek Garis menggunakan Aspose.PDF untuk .NET 

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
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Tentukan warna isian untuk objek Grafik
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
// Tambahkan objek persegi panjang ke kumpulan bentuk objek Grafik
graph.Shapes.Add(line);
dataDir = dataDir + "AddLineObject_out.pdf";
// Simpan berkas PDF
doc.Save(dataDir);
Console.WriteLine("\nLine object added successfully to pdf.\nFile saved at " + dataDir);            

```

## Kesimpulan

Dalam tutorial ini, kami telah menjelaskan langkah demi langkah cara menambahkan objek garis menggunakan Aspose.PDF untuk .NET. Anda sekarang dapat menggunakan pengetahuan ini untuk membuat dokumen PDF dengan garis khusus di aplikasi Anda.

### FAQ untuk menambahkan objek garis dalam file PDF

#### T: Apa tujuan dari tutorial ini?

J: Tutorial ini bertujuan untuk memandu Anda melalui proses penambahan objek garis menggunakan Aspose.PDF untuk .NET guna menyempurnakan dokumen PDF Anda.

#### Q: Prasyarat apa saja yang diperlukan sebelum memulai?

J: Sebelum memulai, pastikan Anda telah menginstal pustaka Aspose.PDF dan menyiapkan lingkungan pengembangan Anda. Selain itu, disarankan untuk memiliki pemahaman dasar tentang pemrograman C#.

#### Q: Bagaimana cara menentukan direktori untuk menyimpan file PDF?

J: Dalam kode sumber yang disediakan, Anda dapat memodifikasi variabel "dataDir" untuk menunjukkan direktori tempat Anda ingin menyimpan file PDF yang dihasilkan.

#### Q: Apa tujuan dari objek Graph?

A: Objek Graph berfungsi sebagai wadah elemen gambar. Itu dibuat dengan dimensi tertentu dan ditambahkan ke koleksi paragraf halaman.

#### T: Bagaimana cara menambahkan objek garis ke dokumen PDF?

A: Untuk menambahkan objek garis, buatlah instance kelas Garis dengan koordinat tertentu dan tambahkan ke kumpulan bentuk grafik.

#### T: Dapatkah saya menyesuaikan tampilan garis?

A: Ya, Anda dapat menyesuaikan tampilan garis dengan mengatur properti seperti jenis tanda hubung dan fase tanda hubung menggunakan properti GraphInfo pada objek Garis.

#### T: Apa tujuan menentukan larik tanda hubung dan fase tanda hubung?

J: Properti larik dasbor dan fase dasbor memungkinkan Anda membuat garis putus-putus atau putus-putus dengan pola tertentu.

#### T: Bagaimana cara menyimpan file PDF setelah menambahkan objek garis?

 A: Setelah menambahkan objek garis, Anda dapat menyimpan file PDF yang dihasilkan menggunakan`doc.Save(dataDir + "AddLineObject_out.pdf");` baris dalam kode sumber yang disediakan.

#### T: Apakah ada contoh kode sumber yang tersedia?

J: Ya, tutorial menyertakan contoh kode sumber yang dapat Anda rujuk untuk menerapkan langkah-langkah yang dijelaskan.