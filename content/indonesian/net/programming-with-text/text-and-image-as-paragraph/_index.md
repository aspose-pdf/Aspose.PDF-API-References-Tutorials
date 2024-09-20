---
title: Teks Dan Gambar Sebagai Paragraf Dalam File PDF
linktitle: Teks Dan Gambar Sebagai Paragraf Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Buat PDF dengan teks dan gambar menggunakan Aspose.PDF untuk .NET. Pelajari cara menambahkan teks dan gambar sebaris langkah demi langkah.
type: docs
weight: 530
url: /id/net/programming-with-text/text-and-image-as-paragraph/
---
## Perkenalan

Di dunia digital saat ini, PDF merupakan format dokumen universal yang sering kita jumpai setiap hari. Baik itu laporan, e-book, atau faktur bisnis, PDF memudahkan kita untuk berbagi informasi di berbagai platform. Namun, bagaimana jika Anda ingin menyesuaikan PDF secara terprogram? Di sinilah Aspose.PDF for .NET berperan. Dalam tutorial ini, kami akan memandu Anda untuk menyisipkan teks dan gambar sebagai paragraf sebaris dalam file PDF menggunakan Aspose.PDF for .NET.

## Prasyarat

Sebelum menyelami kodenya, mari pastikan Anda memiliki semua yang dibutuhkan agar dapat mengikutinya dengan lancar:

-  Pustaka Aspose.PDF untuk .NET: Anda perlu menginstal Aspose.PDF untuk .NET. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/pdf/net/).
- Visual Studio: Versi apa pun yang mendukung .NET akan berfungsi dengan baik.
- Pemahaman Dasar tentang C#: Sedikit pengetahuan tentang C# akan membantu, tetapi jangan khawatir—saya akan memandu Anda melalui setiap langkah!
- Dokumen PDF Siap: Jika Anda ingin menambahkan gambar khusus, siapkan terlebih dahulu.

 Anda juga bisa mendapatkan uji coba perpustakaan secara gratis[Di Sini](https://releases.aspose.com/) , atau jika Anda sedang mengerjakan proyek berskala besar, pertimbangkan untuk membelinya[Di Sini](https://purchase.aspose.com/buy) . Perlu informasi lebih lanjut? Lihat dokumentasinya[Di Sini](https://reference.aspose.com/pdf/net/).

## Paket Impor

Untuk memulai Aspose.PDF untuk .NET, Anda perlu mengimpor namespace yang diperlukan. Namespace ini memungkinkan kode C# Anda berinteraksi dengan fungsionalitas Aspose.PDF.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
using System;
```

Mudah, bukan? Sekarang mari kita masuk ke bagian yang menyenangkan—membuat berkas PDF Anda sendiri.

## Panduan Langkah demi Langkah: Membuat PDF dengan Teks dan Gambar Sebaris

Mari kita uraikan ini menjadi beberapa langkah yang mudah dipahami dan diikuti. Bayangkan Anda sedang menyusun puzzle; setiap langkah seperti menemukan dan menempatkan bagian yang tepat.

## Langkah 1: Inisialisasi Dokumen PDF

Langkah pertama adalah menginisialisasi dokumen PDF baru menggunakan Aspose.PDF. Dokumen ini akan berfungsi sebagai dasar untuk menambahkan teks dan gambar.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Membuat contoh dokumen
Document doc = new Document();
```

 Apa yang terjadi di sini? Kami hanya membuat dokumen baru menggunakan`Document`class dan menentukan direktori tempat Anda ingin menyimpan PDF. Ini seperti membuka kanvas baru untuk karya agung Anda!

## Langkah 2: Tambahkan Halaman ke PDF Anda

Sebuah dokumen tidak akan berguna tanpa halaman, bukan? Mari tambahkan halaman kosong ke dokumen Anda.

```csharp
// Tambahkan halaman ke koleksi halaman dari contoh Dokumen
Page page = doc.Pages.Add();
```

Potongan kode ini menambahkan halaman baru ke koleksi halaman dokumen Anda. Bayangkan seperti membuka halaman kosong di buku catatan.

## Langkah 3: Tambahkan Teks sebagai Paragraf

Berikutnya, kita akan menambahkan paragraf teks. Di sinilah Anda dapat menyisipkan pesan atau judul.

```csharp
// Buat TextFragment
TextFragment text = new TextFragment("Hello World.. ");
// Tambahkan fragmen teks ke koleksi paragraf objek Halaman
page.Paragraphs.Add(text);
```

 Di sini, kita membuat`TextFragment` objek untuk menampung teks "Halo Dunia..", yang kemudian ditambahkan ke halaman sebagai paragraf. Ini seperti menulis kalimat pertama dalam dokumen PDF Anda.

## Langkah 4: Tambahkan Gambar sebagai Paragraf Sebaris

Setelah teksnya tersedia, mari kita bumbui dengan menambahkan gambar sebagai paragraf sebaris. Paragraf sebaris berarti gambar akan muncul tepat setelah teks, seperti halnya gambar ditampilkan dalam dokumen Word.

```csharp
// Buat contoh gambar
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Atur gambar sebagai paragraf sebaris sehingga muncul tepat setelahnya
// Objek paragraf sebelumnya (TextFragment)
image.IsInLineParagraph = true;
// Tentukan jalur file gambar
image.File = dataDir + "aspose-logo.jpg";
```

 Dalam cuplikan ini, kami membuat`Image` objek, perintahkan agar sejajar dengan teks, dan tentukan jalur ke berkas gambar. Ini sama saja dengan menempelkan gambar tepat setelah kalimat dalam dokumen. Anda dapat mengganti "aspose-logo.jpg" dengan gambar yang Anda inginkan.

## Langkah 5: Atur Ukuran Gambar (Opsional)

Ingin mengubah ukuran gambar? Tidak masalah. Aspose.PDF memberi Anda opsi untuk menyesuaikan tinggi dan lebar gambar sebelum menambahkannya ke dokumen Anda.

```csharp
// Atur Tinggi Gambar (opsional)
image.FixHeight = 30;
// Atur Lebar Gambar (opsional)
image.FixWidth = 100;
```

Bagian ini bersifat opsional, tetapi membantu Anda mengontrol seberapa besar atau kecil gambar yang muncul di PDF Anda. Ini seperti mengubah ukuran foto sebelum mencetaknya.

## Langkah 6: Tambahkan Gambar ke Koleksi Paragraf

Kita sudah menyiapkan gambarnya. Sekarang mari kita masukkan ke dalam dokumen sebagai paragraf sebaris.

```csharp
// Tambahkan gambar ke koleksi paragraf objek halaman
page.Paragraphs.Add(image);
```

Baris ini menambahkan gambar tepat setelah teks dalam kumpulan paragraf. Mirip seperti menekan tombol "Sisipkan Gambar" di editor teks.

## Langkah 7: Tambahkan Paragraf Teks Sebaris Lainnya

Bagaimana jika Anda ingin menambahkan lebih banyak teks tepat setelah gambar? Mari kita lakukan itu dengan menyisipkan fragmen teks sebaris lainnya.

```csharp
// Inisialisasi ulang objek TextFragment dengan konten yang berbeda
text = new TextFragment(" Hello Again..");
// Tetapkan TextFragment sebagai paragraf sebaris
text.IsInLineParagraph = true;
// Tambahkan TextFragment yang baru dibuat ke koleksi paragraf halaman
page.Paragraphs.Add(text);
```

 Kami menggunakan kembali`TextFragment`objek di sini dengan teks baru ("Halo Lagi..") dan masukkan sebaris, tepat setelah gambar. Ini akan memberikan tampilan yang mengalir dan kohesif pada PDF Anda.

## Langkah 8: Simpan Dokumen PDF

Kita hampir selesai! Sekarang, mari simpan dokumen ke direktori yang Anda tentukan.

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as inline paragraphs.\nFile saved at " + dataDir);
```

Langkah terakhir ini menyimpan berkas di direktori Anda dengan nama "TextAndImageAsParagraph_out.pdf". Selamat—Anda telah membuat PDF dengan teks dan gambar sebaris!

## Kesimpulan

Nah, itu dia—membuat PDF dengan teks dan gambar sebagai paragraf sebaris menggunakan Aspose.PDF untuk .NET semudah mengikuti langkah-langkah berikut. Hanya dengan beberapa baris kode, Anda dapat menambahkan konten dinamis ke berkas PDF, membuatnya lebih menarik secara visual dan profesional. Baik untuk laporan bisnis atau eBook, memiliki kendali atas tata letak PDF dapat membuat perbedaan besar.

## Pertanyaan yang Sering Diajukan

### Bisakah saya menambahkan beberapa gambar sebagai paragraf sebaris?  
 Ya, Anda dapat menambahkan beberapa gambar dengan membuat gambar terpisah`Image` objek dan menambahkannya ke koleksi paragraf.

### Dapatkah saya mengontrol posisi teks dan gambar dalam PDF?  
Ya, dengan menggunakan properti seperti margin, Anda dapat mengontrol penempatan teks dan gambar yang tepat.

### Apakah Aspose.PDF untuk .NET gratis?  
 Tidak, ini adalah produk berlisensi, tetapi Anda bisa mendapatkannya[uji coba gratis](https://releases.aspose.com/) atau beli lisensi[Di Sini](https://purchase.aspose.com/buy).

### Bisakah saya menambahkan hyperlink ke teks?  
 Ya, Aspose.PDF memungkinkan Anda menambahkan hyperlink dalam fragmen teks. Periksa[dokumentasi](https://reference.aspose.com/pdf/net/) untuk lebih jelasnya.

### Bisakah saya menyesuaikan font dan gaya teks?  
Tentu saja! Anda dapat dengan mudah menyesuaikan font, warna, dan properti gaya lainnya pada fragmen teks.