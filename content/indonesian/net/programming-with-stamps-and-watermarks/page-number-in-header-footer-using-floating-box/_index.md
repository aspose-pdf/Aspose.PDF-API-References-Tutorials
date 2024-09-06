---
title: Nomor Halaman Di Header Footer Menggunakan Floating Box
linktitle: Nomor Halaman Di Header Footer Menggunakan Floating Box
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menambahkan nomor halaman di header dan footer dokumen PDF dengan Aspose.PDF untuk .NET.
type: docs
weight: 150
url: /id/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
Dalam tutorial ini, kami akan memandu Anda langkah demi langkah tentang cara menambahkan nomor halaman di header dan footer dokumen PDF menggunakan FloatingBox dengan Aspose.PDF untuk .NET. Kami akan menggunakan kode sumber C# yang disediakan untuk membuat dokumen PDF, menambahkan halaman, membuat FloatingBox, mengatur posisinya dan menambahkan nomor halaman ke dalamnya, lalu menyimpan dokumen PDF yang dimodifikasi.

## Langkah 1: Menyiapkan lingkungan

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Lingkungan pengembangan .NET yang terinstal.
- Pustaka Aspose.PDF untuk .NET diunduh dan dirujuk dalam proyek Anda.

## Langkah 2: Membuat dokumen PDF dan menambahkan halaman

Langkah pertama adalah membuat contoh dokumen PDF dan menambahkan halaman ke dalamnya. Berikut caranya:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Membuat instance dokumen PDF
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Tambahkan halaman ke dokumen PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori tempat Anda ingin menyimpan dokumen PDF.

## Langkah 3: Membuat FloatingBox dan menambahkan nomor halaman

Sekarang halaman tersebut telah ditambahkan ke dokumen PDF, kita dapat membuat FloatingBox, mengatur posisinya, dan menambahkan nomor halaman ke dalamnya. Berikut caranya:

```csharp
// Buat FloatingBox dengan lebar 140 dan tinggi 80
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Mengatur posisi kiri paragraf
box1. Left = 2;

// Mengatur posisi atas paragraf
box1. Top = 10;

// Tambahkan nomor halaman ke FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Tambahkan FloatingBox ke halaman
page.Paragraphs.Add(box1);
```

Kode di atas membuat FloatingBox dengan lebar 140 dan tinggi 80. Selanjutnya, kita atur posisinya dengan menentukan nilai kiri dan atas. Terakhir, kita tambahkan nomor halaman ke FloatingBox menggunakan TextFragment yang berisi sintaks "($p/ $P )" yang akan diganti dengan nomor halaman saat ini dan jumlah total halaman.

## Langkah 4: Menyimpan dokumen PDF yang dimodifikasi

Setelah nomor halaman ditambahkan ke header atau footer menggunakan FloatingBox, kita dapat menyimpan dokumen PDF yang dimodifikasi. Berikut caranya:

```csharp
// Simpan dokumen PDF yang dimodifikasi
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

Kode di atas menyimpan dokumen PDF yang telah diedit ke direktori yang ditentukan.

### Contoh kode sumber untuk Nomor Halaman di Header dan Footer Menggunakan Kotak Mengambang menggunakan Aspose.PDF untuk .NET 
```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Membuat contoh dokumen
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Tambahkan Halaman ke dalam dokumen pdf
Aspose.Pdf.Page page = pdf.Pages.Add();

// Menginisialisasi instance baru dari kelas FloatingBox
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Nilai float yang menunjukkan posisi kiri paragraf
box1.Left = 2;

// Nilai float yang menunjukkan posisi teratas paragraf
box1.Top = 10;

// Tambahkan makro ke koleksi paragraf FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Tambahkan floatingBox ke halaman
page.Paragraphs.Add(box1);

// Simpan dokumen
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## Kesimpulan

Selamat! Anda telah mempelajari cara menambahkan nomor halaman di header dan footer dokumen PDF menggunakan FloatingBox dengan Aspose.PDF untuk .NET. Kini Anda dapat menyesuaikan header dan footer dengan menambahkan informasi dinamis seperti nomor halaman.

### Pertanyaan yang Sering Diajukan

#### T: Apa itu FloatingBox, dan bagaimana cara menggunakannya untuk menambahkan nomor halaman di header atau footer dokumen PDF?

A: FloatingBox adalah elemen tata letak serbaguna di Aspose.PDF yang dapat menampung berbagai konten, termasuk teks dan gambar. Dalam tutorial ini, elemen ini digunakan untuk membuat wadah bagi nomor halaman, yang memungkinkan Anda memasukkan nomor halaman saat ini dan jumlah halaman total secara dinamis ke dalam header atau footer.

#### T: Bagaimana kode sumber C# yang disediakan mencapai penambahan nomor halaman menggunakan FloatingBox?

A: Potongan kode menunjukkan cara membuat dokumen PDF, menambahkan halaman, membuat FloatingBox, mengatur posisinya di dalam halaman, dan memasukkan nomor halaman menggunakan TextFragment. Sintaks "($p/ $P )" di TextFragment diganti dengan nomor halaman saat ini dan jumlah halaman total.

#### T: Dapatkah saya menyesuaikan tampilan dan format nomor halaman yang ditambahkan menggunakan FloatingBox?

A: Ya, Anda dapat menyesuaikan tampilan nomor halaman dengan mengubah properti TextFragment di dalam FloatingBox. Anda dapat mengubah ukuran font, warna, gaya, perataan, dan opsi pemformatan lainnya.

#### T: Apakah mungkin untuk menambahkan elemen dinamis yang berbeda, seperti tanggal dan waktu, ke header atau footer menggunakan pendekatan yang serupa?

J: Tentu saja, Anda dapat menambahkan berbagai elemen dinamis seperti tanggal, waktu, metadata dokumen, atau teks kustom dengan memodifikasi konten TextFragment di dalam FloatingBox. Anda dapat menggunakan makro seperti "($p/ $P )" untuk nomor halaman atau "($date)" untuk tanggal saat ini.

#### T: Bagaimana cara menentukan posisi FloatingBox dalam bagian header atau footer?
 A: Kode yang diberikan mengatur posisi FloatingBox menggunakan`Left` Dan`Top` properti. Anda dapat menyesuaikan nilai-nilai ini untuk memposisikan FloatingBox sesuai keinginan di bagian header atau footer.

#### T: Dapatkah saya menggunakan font atau gaya yang berbeda untuk nomor halaman di header atau footer?

A: Ya, Anda dapat menyesuaikan font, gaya, dan properti pemformatan lainnya dari teks nomor halaman dengan memodifikasi properti TextFragment dalam FloatingBox.

#### T: Apa yang terjadi jika konten dalam FloatingBox melebihi dimensinya?

J: Jika konten dalam FloatingBox melebihi dimensinya, konten tersebut dapat terpotong atau timbul masalah tata letak. Pastikan dimensi FloatingBox sesuai untuk menampung konten, dan pertimbangkan untuk menyesuaikan tata letak halaman jika diperlukan.

#### T: Apakah mungkin untuk menambahkan beberapa FloatingBox dengan konten berbeda pada header atau footer di halaman yang sama?

A: Ya, Anda dapat menambahkan beberapa FloatingBox dengan konten berbeda ke header atau footer halaman yang sama dengan membuat contoh FloatingBox terpisah dan menambahkannya ke koleksi Paragraf halaman.

#### T: Dapatkah saya menggunakan pendekatan FloatingBox untuk menambahkan konten ke bagian lain dokumen PDF, seperti badan atau margin?

A: Meskipun FloatingBox umumnya digunakan untuk header dan footer, Anda juga dapat menggunakannya untuk menambahkan konten ke bagian lain dokumen PDF, seperti badan atau margin, dengan memposisikannya sesuai kebutuhan di dalam halaman.