---
title: Ekstrak Teks Dari Wilayah Halaman Dalam File PDF
linktitle: Ekstrak Teks Dari Wilayah Halaman Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mengekstrak teks dari wilayah tertentu dalam PDF menggunakan Aspose.PDF untuk .NET dengan panduan langkah demi langkah ini. Kumpulkan dan simpan teks dari dokumen Anda secara efisien.
type: docs
weight: 190
url: /id/net/programming-with-text/extract-text-from-page-region/
---
## Perkenalan

Bekerja dengan PDF sering kali memerlukan ekstraksi konten tertentu, baik itu penarikan data dari formulir, tabel, atau bagian tertentu dari suatu dokumen. Dalam tutorial ini, kami akan memandu Anda untuk mengekstrak teks dari bagian tertentu PDF menggunakan Aspose.PDF for .NET. Daripada memilah-milah seluruh dokumen, kami akan menentukan dengan tepat di mana teks berada dan mengekstraknya secara efisien.

## Prasyarat

Sebelum kita masuk ke kode, pastikan Anda telah menyiapkan hal-hal berikut:

1.  Aspose.PDF untuk .NET: Jika Anda belum melakukannya, unduh dan instal pustaka Aspose.PDF untuk .NET.[Unduh Aspose.PDF untuk .NET](https://releases.aspose.com/pdf/net/).
2. IDE: Lingkungan pengembangan .NET apa pun seperti Visual Studio.
3. .NET Framework: Pastikan proyek Anda disiapkan dengan kerangka kerja .NET yang sesuai.
4. Dokumen PDF: Contoh PDF yang teksnya akan kita ekstrak.

 Jangan lupa bahwa Anda bisa[dapatkan uji coba gratis](https://releases.aspose.com/) dari Aspose.PDF atau gunakan[lisensi sementara](https://purchase.aspose.com/temporary-license/) untuk fungsionalitas penuh.

## Mengimpor Paket yang Diperlukan

Untuk mulai bekerja dengan Aspose.PDF untuk .NET, Anda perlu mengimpor namespace yang diperlukan ke dalam proyek Anda. Paket-paket ini menyediakan kelas dan metode yang diperlukan untuk menangani dokumen PDF.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

## Langkah 1: Menyiapkan Direktori Dokumen dan Memuat PDF

Langkah pertama adalah menentukan lokasi berkas PDF Anda dan memuatnya ke dalam proyek Anda. Anda dapat menggunakan jalur direktori lokal ke berkas PDF yang ingin Anda gunakan.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buka dokumen PDF
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

 Langkah ini memastikan bahwa file PDF dimuat dengan benar dan siap untuk dikerjakan.`Document` kelas dari pustaka Aspose.PDF memungkinkan Anda memanipulasi berkas PDF.

## Langkah 2: Inisialisasi Text Absorber untuk Ekstraksi

 Pada langkah ini, kita membuat`TextAbsorber` objek, yang dirancang untuk mengekstrak teks dari dokumen PDF.`TextAbsorber` fleksibel dan dapat disesuaikan untuk fokus pada wilayah atau halaman tertentu.

```csharp
// Buat objek TextAbsorber untuk mengekstrak teks
TextAbsorber absorber = new TextAbsorber();
```

 Itu`TextAbsorber`kelas adalah alat yang hebat yang menangkap semua teks dalam batasan yang Anda tentukan.

## Langkah 3: Tentukan Wilayah untuk Mengekstrak Teks

Di sinilah keajaiban terjadi. Alih-alih menarik teks dari seluruh halaman, kita dapat membatasi ekstraksi ke area persegi panjang tertentu di halaman. Ini sempurna jika Anda tahu persis di mana konten Anda berada.

```csharp
// Batasi ekstraksi teks ke wilayah tertentu
absorber.TextSearchOptions.LimitToPageBounds = true;
absorber.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
```

 Itu`Rectangle` objek memungkinkan Anda menentukan koordinat (dalam poin) area tempat teks akan diekstraksi.`TextSearchOptions.LimitToPageBounds` memastikan bahwa hanya teks dalam persegi panjang tertentu yang diekstraksi.

## Langkah 4: Terima Penyerap pada Halaman yang Diinginkan

 Setelah menyiapkan wilayah, langkah selanjutnya adalah menerima`TextAbsorber` untuk halaman tertentu yang teksnya ingin Anda ekstrak. Di sini, kita akan fokus pada halaman pertama PDF.

```csharp
// Terima penyerap untuk halaman pertama
pdfDocument.Pages[1].Accept(absorber);
```

 Dengan menelepon`Accept` metode di halaman, kami memerintahkan Aspose.PDF untuk menjalankan penyerap dan mengumpulkan teks dari wilayah yang ditentukan.

## Langkah 5: Ambil dan Simpan Teks yang Diekstrak

 Setelah penyerap telah melakukan tugasnya, saatnya untuk mengumpulkan teks yang diekstraksi dan menyimpannya. Langkah ini melibatkan pengambilan teks dan menuliskannya ke`.txt` mengajukan.

```csharp
// Dapatkan teks yang diekstraksi
string extractedText = absorber.Text;

// Buat penulis untuk menyimpan teks yang diekstraksi
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");

// Tuliskan teks ke dalam file
tw.WriteLine(extractedText);

// Tutup alirannya
tw.Close();
```

 Di sini,`TextWriter` Kelas ini digunakan untuk menulis teks yang diekstrak ke dalam berkas teks. Ini memastikan bahwa konten yang diekstrak tersimpan dengan aman untuk penggunaan selanjutnya.

## Kesimpulan

 Mengekstrak teks dari wilayah tertentu dalam dokumen PDF bisa sangat berguna, terutama saat menangani konten terstruktur seperti formulir atau tabel. Dengan menggunakan Aspose.PDF untuk .NET, Anda dapat mencapai tugas ini hanya dengan beberapa baris kode. Dengan mendefinisikan wilayah, menginisialisasi`TextAbsorber`, dan menyimpan teks yang diekstrak, Anda memiliki kontrol penuh atas apa yang diambil dari PDF Anda.

Baik Anda sedang mengerjakan proyek kecil atau mengelola dokumen besar, metode ini menyediakan cara yang efisien untuk mengekstrak data relevan dari PDF Anda tanpa harus menyisir seluruh dokumen.

## Pertanyaan yang Sering Diajukan

### Bisakah saya mengekstrak teks dari beberapa halaman sekaligus?
 Ya, dengan mengulangi melalui`Pages` koleksi dari`pdfDocument` Anda dapat menerapkan`TextAbsorber` ke beberapa halaman.

### Bagaimana jika teks berada di wilayah lain PDF?
 Anda dapat dengan mudah menyesuaikan`Rectangle` koordinat yang cocok dengan wilayah tempat teks Anda berada.

### Apakah ini berfungsi dengan PDF yang dipindai?
Tidak, PDF yang dipindai memerlukan OCR (Optical Character Recognition) untuk mengubah gambar menjadi teks. Aspose.PDF juga menawarkan fitur OCR.

### Apakah ada cara untuk mengekstrak teks berdasarkan kata kunci tertentu?
 Ya, Anda bisa menggunakannya`TextFragmentAbsorber` untuk ekstraksi teks berbasis kata kunci.

### Bagaimana cara mengekstrak teks dari PDF yang dienkripsi?
Anda harus mendekripsi PDF terlebih dahulu dengan memberikan kata sandi yang benar, lalu melanjutkan dengan ekstraksi teks.