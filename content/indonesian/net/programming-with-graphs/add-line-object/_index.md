---
title: Tambahkan Objek Garis Dalam File PDF
linktitle: Tambahkan Objek Garis Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menambahkan objek garis kustom dalam berkas PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 30
url: /id/net/programming-with-graphs/add-line-object/
---
Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# berikut langkah demi langkah untuk menambahkan objek garis menggunakan Aspose.PDF untuk .NET.

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

## Langkah 3: Membuat Objek Grafik dan menambahkannya ke halaman

Kami membuat objek Grafik dengan dimensi tertentu dan menambahkannya ke koleksi paragraf halaman.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## Langkah 4: Buat Objek Garis dan Tambahkan ke Bagan

Kami membuat objek Garis dengan koordinat yang ditentukan dan menambahkannya ke koleksi bentuk bagan.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## Langkah 5: Pengaturan Garis

Kita dapat menentukan properti untuk garis, seperti jenis garis putus-putus dan fase garis putus-putus.

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Langkah 6: Menyimpan File PDF

Terakhir, kami menyimpan file PDF yang dihasilkan dengan nama "AddLineObject_out.pdf" di direktori yang ditentukan.

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### Contoh kode sumber untuk Menambahkan Objek Garis menggunakan Aspose.PDF untuk .NET 

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
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Tentukan warna isian untuk objek Grafik
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
// Tambahkan objek persegi panjang ke koleksi bentuk objek Grafik
graph.Shapes.Add(line);
dataDir = dataDir + "AddLineObject_out.pdf";
// Simpan file PDF
doc.Save(dataDir);
Console.WriteLine("\nLine object added successfully to pdf.\nFile saved at " + dataDir);            

```

## Kesimpulan

Dalam tutorial ini, kami telah menjelaskan langkah demi langkah cara menambahkan objek garis menggunakan Aspose.PDF untuk .NET. Kini Anda dapat menggunakan pengetahuan ini untuk membuat dokumen PDF dengan garis khusus di aplikasi Anda.

### FAQ untuk menambahkan objek baris dalam file PDF

#### T: Apa tujuan dari tutorial ini?

A: Tutorial ini bertujuan untuk memandu Anda melalui proses penambahan objek garis menggunakan Aspose.PDF for .NET untuk menyempurnakan dokumen PDF Anda.

#### T: Prasyarat apa yang diperlukan sebelum memulai?

J: Sebelum memulai, pastikan Anda telah menginstal pustaka Aspose.PDF dan menyiapkan lingkungan pengembangan Anda. Selain itu, sebaiknya Anda memiliki pemahaman dasar tentang pemrograman C#.

#### T: Bagaimana cara menentukan direktori untuk menyimpan berkas PDF?

A: Dalam kode sumber yang disediakan, Anda dapat mengubah variabel "dataDir" untuk menunjukkan direktori tempat Anda ingin menyimpan file PDF yang dihasilkan.

#### T: Apa tujuan dari objek Grafik?

A: Objek Graph berfungsi sebagai wadah untuk elemen gambar. Objek ini dibuat dengan dimensi tertentu dan ditambahkan ke kumpulan paragraf halaman.

#### T: Bagaimana cara menambahkan objek garis ke dokumen PDF?

A: Untuk menambahkan objek garis, buat contoh kelas Garis dengan koordinat yang ditentukan dan tambahkan ke koleksi bentuk grafik.

#### T: Bisakah saya menyesuaikan tampilan garis?

A: Ya, Anda dapat menyesuaikan tampilan garis dengan mengatur properti seperti jenis garis putus-putus dan fase garis putus-putus menggunakan properti GraphInfo dari objek Garis.

#### T: Apa tujuan menentukan susunan tanda hubung dan fase tanda hubung?

A: Properti susunan garis putus-putus dan fase garis putus-putus memungkinkan Anda membuat garis putus-putus atau putus-putus dengan pola tertentu.

#### T: Bagaimana cara menyimpan berkas PDF setelah menambahkan objek garis?

 A: Setelah menambahkan objek garis, Anda dapat menyimpan file PDF yang dihasilkan menggunakan`doc.Save(dataDir + "AddLineObject_out.pdf");` baris dalam kode sumber yang disediakan.

#### T: Apakah ada contoh kode sumber yang tersedia?

A: Ya, tutorial menyertakan contoh kode sumber yang dapat Anda rujuk untuk menerapkan langkah-langkah yang dijelaskan.