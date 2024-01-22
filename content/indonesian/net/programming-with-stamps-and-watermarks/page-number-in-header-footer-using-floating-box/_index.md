---
title: Nomor Halaman Pada Header Footer Menggunakan Floating Box
linktitle: Nomor Halaman Pada Header Footer Menggunakan Floating Box
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menambahkan nomor halaman di header dan footer dokumen PDF dengan Aspose.PDF untuk .NET.
type: docs
weight: 150
url: /id/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
Dalam tutorial ini, kami akan memandu Anda langkah demi langkah tentang cara menambahkan nomor halaman di header dan footer dokumen PDF menggunakan FloatingBox dengan Aspose.PDF untuk .NET. Kami akan menggunakan kode sumber C# yang disediakan untuk membuat dokumen PDF, menambahkan halaman, membuat FloatingBox, mengatur posisinya dan menambahkan nomor halaman ke dalamnya, lalu menyimpan dokumen PDF yang dimodifikasi.

## Langkah 1: Menyiapkan lingkungan

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Lingkungan pengembangan .NET yang terinstal.
- Pustaka Aspose.PDF untuk .NET diunduh dan direferensikan dalam proyek Anda.

## Langkah 2: Membuat dokumen PDF dan menambahkan halaman

Langkah pertama adalah membuat instance dokumen PDF dan menambahkan halaman ke dalamnya. Begini caranya:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Buat instance dokumen PDF
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Tambahkan halaman ke dokumen PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori tempat Anda ingin menyimpan dokumen PDF.

## Langkah 3: Membuat FloatingBox dan menambahkan nomor halaman

Sekarang halaman tersebut telah ditambahkan ke dokumen PDF, kita dapat membuat FloatingBox, mengatur posisinya, dan menambahkan nomor halaman ke dalamnya. Begini caranya:

```csharp
// Buat FloatingBox dengan lebar 140 dan tinggi 80
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Atur posisi kiri paragraf
box1. Left = 2;

// Mengatur posisi teratas paragraf
box1. Top = 10;

// Tambahkan nomor halaman ke FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Tambahkan FloatingBox ke halaman
page.Paragraphs.Add(box1);
```

Kode di atas membuat FloatingBox dengan lebar 140 dan tinggi 80. Selanjutnya kita atur posisinya dengan menentukan nilai kiri dan atas. Terakhir, kita menambahkan nomor halaman ke FloatingBox menggunakan TextFragment yang berisi sintaks "($p/ $P )" yang akan diganti dengan nomor halaman saat ini dan jumlah total halaman.

## Langkah 4: Menyimpan dokumen PDF yang dimodifikasi

Setelah nomor halaman ditambahkan ke header atau footer menggunakan FloatingBox, kita dapat menyimpan dokumen PDF yang dimodifikasi. Begini caranya:

```csharp
// Simpan dokumen PDF yang dimodifikasi
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

Kode di atas menyimpan dokumen PDF yang diedit ke direktori yang ditentukan.

### Contoh kode sumber untuk Nomor Halaman di Header Footer Menggunakan Floating Box menggunakan Aspose.PDF untuk .NET 
```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat instance Dokumen
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Tambahkan Halaman ke dalam dokumen pdf
Aspose.Pdf.Page page = pdf.Pages.Add();

//Menginisialisasi instance baru dari kelas FloatingBox
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Nilai mengambang yang menunjukkan posisi kiri paragraf
box1.Left = 2;

// Nilai mengambang yang menunjukkan posisi teratas paragraf
box1.Top = 10;

// Tambahkan makro ke kumpulan paragraf di FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Tambahkan floatingBox ke halaman
page.Paragraphs.Add(box1);

// Simpan dokumennya
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## Kesimpulan

Selamat! Anda telah mempelajari cara menambahkan nomor halaman di header dan footer dokumen PDF menggunakan FloatingBox dengan Aspose.PDF untuk .NET. Anda sekarang dapat menyesuaikan header dan footer dengan menambahkan informasi dinamis seperti nomor halaman.

### FAQ

#### T: Apa itu FloatingBox, dan bagaimana cara menggunakannya untuk menambahkan nomor halaman di header atau footer dokumen PDF?

J: FloatingBox adalah elemen tata letak serbaguna di Aspose.PDF yang dapat menampung berbagai konten, termasuk teks dan gambar. Dalam tutorial ini, ini digunakan untuk membuat wadah untuk nomor halaman, memungkinkan Anda memasukkan secara dinamis nomor halaman saat ini dan jumlah halaman total ke dalam header atau footer.

#### T: Bagaimana kode sumber C# yang disediakan dapat menambahkan nomor halaman menggunakan FloatingBox?

J: Cuplikan kode menunjukkan cara membuat dokumen PDF, menambahkan halaman, membuat FloatingBox, mengatur posisinya di dalam halaman, dan memasukkan nomor halaman menggunakan TextFragment. Sintaks "($p/ $P )" di TextFragment diganti dengan nomor halaman saat ini dan jumlah total halaman.

#### T: Dapatkah saya menyesuaikan tampilan dan format nomor halaman yang ditambahkan menggunakan FloatingBox?

J: Ya, Anda dapat menyesuaikan tampilan nomor halaman dengan memodifikasi properti TextFragment di dalam FloatingBox. Anda dapat mengubah ukuran font, warna, gaya, perataan, dan opsi pemformatan lainnya.

#### T: Apakah mungkin menambahkan elemen dinamis yang berbeda, seperti tanggal dan waktu, ke header atau footer menggunakan pendekatan serupa?

J: Tentu saja, Anda dapat menambahkan elemen dinamis yang berbeda seperti tanggal, waktu, metadata dokumen, atau teks khusus dengan memodifikasi konten TextFragment dalam FloatingBox. Anda dapat menggunakan makro seperti "($p/ $P )" untuk nomor halaman atau "($tanggal)" untuk tanggal sekarang.

#### T: Bagaimana cara menentukan posisi FloatingBox di bagian header atau footer?
 A: Kode yang diberikan mengatur posisi FloatingBox menggunakan`Left` Dan`Top` properti. Anda dapat menyesuaikan nilai-nilai ini untuk memposisikan FloatingBox sesuai keinginan di bagian header atau footer.

#### T: Dapatkah saya menggunakan font atau gaya berbeda untuk nomor halaman di header atau footer?

J: Ya, Anda dapat menyesuaikan font, gaya, dan properti pemformatan lainnya dari teks nomor halaman dengan memodifikasi properti TextFragment di dalam FloatingBox.

#### T: Apa yang terjadi jika konten di FloatingBox melebihi dimensinya?

J: Jika konten dalam FloatingBox melebihi dimensinya, konten tersebut mungkin terpotong atau masalah tata letak dapat muncul. Pastikan dimensi FloatingBox sesuai untuk menampung konten, dan pertimbangkan untuk menyesuaikan tata letak halaman jika diperlukan.

#### T: Apakah mungkin untuk menambahkan beberapa FloatingBox dengan konten berbeda ke header atau footer pada halaman yang sama?

J: Ya, Anda dapat menambahkan beberapa FloatingBox dengan konten berbeda ke header atau footer halaman yang sama dengan membuat instance FloatingBox terpisah dan menambahkannya ke koleksi Paragraphs halaman.

#### T: Bisakah saya menggunakan pendekatan FloatingBox untuk menambahkan konten ke bagian lain dokumen PDF, seperti badan atau margin?

J: Meskipun FloatingBox biasanya digunakan untuk header dan footer, Anda juga dapat menggunakannya untuk menambahkan konten ke bagian lain dokumen PDF, seperti badan atau margin, dengan memposisikannya sesuai di dalam halaman.