---
title: Urutan Persegi Panjang Kontrol Z Dalam File PDF
linktitle: Urutan Persegi Panjang Kontrol Z Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mengontrol urutan Z persegi panjang dalam berkas PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 40
url: /id/net/programming-with-graphs/control-rectangle-z-order/
---
Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# berikut langkah demi langkah untuk mengontrol urutan Z persegi panjang menggunakan Aspose.PDF untuk .NET.

Pastikan Anda telah menginstal pustaka Aspose.PDF dan menyiapkan lingkungan pengembangan sebelum memulai. Anda juga harus memiliki pengetahuan dasar tentang pemrograman C#.

## Langkah 1: Pengaturan Direktori Dokumen

Dalam kode sumber yang diberikan, Anda perlu menentukan direktori tempat Anda ingin menyimpan file PDF yang dihasilkan. Ubah variabel "dataDir" ke direktori yang diinginkan.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Membuat Instansi Objek Dokumen dan Menambahkan Halaman

Kami membuat contoh kelas Dokumen dan menambahkan halaman ke dokumen ini.

```csharp
Document doc1 = new Document();
Aspose.Pdf.Page page1 = doc1.Pages.Add();
```

## Langkah 3: Mengatur ukuran halaman

Kami mengatur ukuran halaman PDF menggunakan metode SetPageSize.

```csharp
page1.SetPageSize(375, 300);
```

## Langkah 4: Mengatur Margin Halaman

Kita dapat mengonfigurasi margin halaman menggunakan properti objek PageInfo.

```csharp
page1.PageInfo.Margin.Left = 0;
page1.PageInfo.Margin.Top = 0;
```

## Langkah 5: Tambahkan Persegi Panjang dengan Urutan Z yang Ditentukan

Kami membuat dan menambahkan persegi panjang ke halaman dengan warna berbeda dan urutan Z yang ditentukan.

```csharp
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
```

## Langkah 6: Menyimpan File PDF yang Dihasilkan

Terakhir, kami menyimpan file PDF yang dihasilkan dengan nama "ControlRectangleZOrder_out.pdf" di direktori yang ditentukan.

```csharp
doc1.Save(dataDir);
```
### Contoh kode sumber untuk Control Rectangle Z Order menggunakan Aspose.PDF untuk .NET 

```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Membuat instance objek kelas Dokumen
Document doc1 = new Document();
/// Tambahkan halaman ke koleksi halaman file PDF
Aspose.Pdf.Page page1 = doc1.Pages.Add();
// Atur ukuran halaman PDF
page1.SetPageSize(375, 300);
// Tetapkan margin kiri untuk objek halaman sebagai 0
page1.PageInfo.Margin.Left = 0;
// Tetapkan margin atas objek halaman sebagai 0
page1.PageInfo.Margin.Top = 0;
//Buat persegi panjang baru dengan Warna sebagai Merah, Urutan Z sebagai 0 dan dimensi tertentu
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
// Buat persegi panjang baru dengan Warna sebagai Biru, Urutan Z sebagai 0 dan dimensi tertentu
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
// Buat persegi panjang baru dengan Warna sebagai Hijau, Urutan Z sebagai 0 dan dimensi tertentu
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
dataDir = dataDir + "ControlRectangleZOrder_out.pdf";
// Simpan file PDF yang dihasilkan
doc1.Save(dataDir);

```

## Kesimpulan

Dalam tutorial ini, kami menjelaskan cara mengontrol urutan Z persegi panjang menggunakan Aspose.PDF untuk .NET. Kini Anda dapat menggunakan pengetahuan ini untuk mengatur dan melapisi persegi panjang dalam file PDF Anda dengan presisi.

### FAQ tentang persegi panjang kontrol urutan z dalam file PDF

#### T: Apa tujuan dari tutorial ini?

A: Tutorial ini bertujuan untuk memandu Anda melalui proses pengendalian urutan Z persegi panjang menggunakan Aspose.PDF untuk .NET, yang memungkinkan Anda untuk mengatur dan melapisi persegi panjang dalam file PDF Anda.

#### T: Prasyarat apa yang diperlukan sebelum memulai?

J: Sebelum memulai, pastikan Anda telah menginstal pustaka Aspose.PDF dan menyiapkan lingkungan pengembangan Anda. Selain itu, Anda disarankan untuk memiliki pemahaman dasar tentang pemrograman C#.

#### T: Bagaimana cara menentukan direktori untuk menyimpan berkas PDF?

A: Dalam kode sumber yang disediakan, Anda dapat mengubah variabel "dataDir" untuk menunjukkan direktori tempat Anda ingin menyimpan file PDF yang dihasilkan.

#### T: Apa tujuan pengaturan ukuran halaman dan margin?

A: Mengatur ukuran halaman dan margin membantu mengonfigurasi tata letak halaman PDF dan menyediakan kanvas tempat Anda dapat mengatur persegi panjang.

#### T: Bagaimana cara menambahkan persegi panjang dengan urutan Z yang ditentukan?

A: Anda dapat membuat dan menambahkan persegi panjang ke halaman menggunakan`AddRectangle` metode, yang menentukan posisi, dimensi, warna, dan urutan Z untuk setiap persegi panjang.

#### T: Apa itu Z-order, dan mengapa itu penting?

A: Urutan Z menentukan susunan objek pada halaman. Objek dengan nilai urutan Z yang lebih tinggi diposisikan di atas objek dengan nilai urutan Z yang lebih rendah, yang memengaruhi visibilitas dan pelapisannya.

#### T: Dapatkah saya menyesuaikan warna dan dimensi persegi panjang?

 A: Ya, Anda dapat menyesuaikan warna, posisi, dan dimensi persegi panjang dengan memodifikasi parameter yang diteruskan ke`AddRectangle` metode.

#### T: Bagaimana cara menyimpan berkas PDF yang dihasilkan setelah menyusun persegi panjang?

 A: Setelah mengatur persegi panjang, Anda dapat menyimpan file PDF yang dihasilkan menggunakan`doc1.Save(dataDir);` baris dalam kode sumber yang disediakan.