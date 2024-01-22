---
title: Kontrol Urutan Rectangle Z Dalam File PDF
linktitle: Kontrol Urutan Rectangle Z Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara mengontrol urutan Z persegi panjang dalam file PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 40
url: /id/net/programming-with-graphs/control-rectangle-z-order/
---
Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# berikut langkah demi langkah untuk mengontrol persegi panjang orde Z menggunakan Aspose.PDF untuk .NET.

Pastikan Anda telah menginstal perpustakaan Aspose.PDF dan mengatur lingkungan pengembangan Anda sebelum memulai. Juga memiliki pengetahuan dasar tentang pemrograman C#.

## Langkah 1: Pengaturan Direktori Dokumen

Dalam kode sumber yang disediakan, Anda perlu menentukan direktori tempat Anda ingin menyimpan file PDF yang dihasilkan. Ubah variabel "dataDir" ke direktori yang diinginkan.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Membuat Instansi Objek Dokumen dan Menambahkan Halaman

Kami membuat instance kelas Dokumen dan menambahkan halaman ke dokumen ini.

```csharp
Document doc1 = new Document();
Aspose.Pdf.Page page1 = doc1.Pages.Add();
```

## Langkah 3: Menyiapkan ukuran halaman

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

## Langkah 5: Tambahkan Persegi Panjang dengan Urutan Z Tertentu

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
// Buat instance objek kelas Dokumen
Document doc1 = new Document();
/// Tambahkan halaman ke halaman koleksi file PDF
Aspose.Pdf.Page page1 = doc1.Pages.Add();
// Atur ukuran halaman PDF
page1.SetPageSize(375, 300);
// Tetapkan margin kiri untuk objek halaman sebagai 0
page1.PageInfo.Margin.Left = 0;
// Tetapkan margin atas objek halaman sebagai 0
page1.PageInfo.Margin.Top = 0;
// Buat persegi panjang baru dengan Warna sebagai Merah, Z-Order sebagai 0 dan dimensi tertentu
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
// Buat persegi panjang baru dengan Warna sebagai Biru, Z-Order sebagai 0 dan dimensi tertentu
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
//Buat persegi panjang baru dengan Warna sebagai Hijau, Z-Order sebagai 0 dan dimensi tertentu
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
dataDir = dataDir + "ControlRectangleZOrder_out.pdf";
// Simpan file PDF yang dihasilkan
doc1.Save(dataDir);

```

## Kesimpulan

Dalam tutorial ini, kami menjelaskan cara mengontrol urutan Z persegi panjang menggunakan Aspose.PDF untuk .NET. Anda sekarang dapat menggunakan pengetahuan ini untuk menyusun dan melapisi persegi panjang dalam file PDF Anda dengan presisi.

### Urutan z persegi panjang kontrol FAQ dalam file PDF

#### T: Apa tujuan dari tutorial ini?

J: Tutorial ini bertujuan untuk memandu Anda melalui proses mengontrol persegi panjang orde Z menggunakan Aspose.PDF untuk .NET, memungkinkan Anda menyusun dan melapisi persegi panjang dalam file PDF Anda.

#### Q: Prasyarat apa saja yang diperlukan sebelum memulai?

J: Sebelum memulai, pastikan Anda telah menginstal pustaka Aspose.PDF dan menyiapkan lingkungan pengembangan Anda. Selain itu, disarankan untuk memiliki pemahaman dasar tentang pemrograman C#.

#### Q: Bagaimana cara menentukan direktori untuk menyimpan file PDF?

J: Dalam kode sumber yang disediakan, Anda dapat memodifikasi variabel "dataDir" untuk menunjukkan direktori tempat Anda ingin menyimpan file PDF yang dihasilkan.

#### Q: Apa tujuan pengaturan ukuran dan margin halaman?

J: Mengatur ukuran halaman dan margin membantu mengonfigurasi tata letak halaman PDF dan menyediakan kanvas tempat Anda dapat mengatur persegi panjang.

#### Q: Bagaimana cara menambahkan persegi panjang dengan urutan Z yang ditentukan?

 J: Anda dapat membuat dan menambahkan persegi panjang ke halaman menggunakan`AddRectangle` metode, menentukan posisi, dimensi, warna, dan urutan Z untuk setiap persegi panjang.

#### T: Apa itu Z-order dan mengapa ini penting?

A: Z-order menentukan urutan penumpukan objek pada suatu halaman. Objek dengan nilai orde Z lebih tinggi diposisikan di atas objek dengan nilai orde Z lebih rendah, sehingga memengaruhi visibilitas dan pelapisannya.

#### T: Dapatkah saya menyesuaikan warna dan dimensi persegi panjang?

 J: Ya, Anda dapat menyesuaikan warna, posisi, dan dimensi persegi panjang dengan memodifikasi parameter yang diteruskan ke`AddRectangle` metode.

#### Q: Bagaimana cara menyimpan file PDF yang dihasilkan setelah menyusun persegi panjang?

 A: Setelah menyusun persegi panjang, Anda dapat menyimpan file PDF yang dihasilkan menggunakan`doc1.Save(dataDir);` baris dalam kode sumber yang disediakan.