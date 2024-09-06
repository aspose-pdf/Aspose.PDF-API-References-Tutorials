---
title: Tetapkan Nama Font Default
linktitle: Tetapkan Nama Font Default
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menetapkan nama font default saat merender PDF ke gambar menggunakan Aspose.PDF untuk .NET. Panduan ini mencakup prasyarat, petunjuk langkah demi langkah, dan Tanya Jawab Umum.
type: docs
weight: 270
url: /id/net/document-conversion/set-default-font-name/
---
## Perkenalan

Pernahkah Anda mencoba merender dokumen PDF ke gambar tetapi font-nya tidak terlihat benar? Mungkin teksnya tampak terdistorsi, atau mungkin font aslinya tidak didukung. Di sinilah pengaturan font default dapat menyelamatkan hari! Dengan menggunakan Aspose.PDF untuk .NET, Anda dapat dengan mudah mengatur font default untuk rendering PDF Anda, memastikan bahwa dokumen Anda terlihat tajam dan profesional. Dalam tutorial ini, kami akan memandu Anda tentang cara mengatur nama font default saat merender PDF ke gambar. Di akhir panduan ini, Anda akan memiliki keterampilan untuk mengatasi tantangan rendering PDF apa pun yang menghadang Anda. Siap? Mari kita mulai!

## Prasyarat

Sebelum kita masuk ke kode, ada beberapa hal yang perlu Anda siapkan:

- Aspose.PDF untuk .NET: Pustaka canggih ini akan kita gunakan untuk memanipulasi dokumen PDF kita. Anda dapat mengunduhnya dari[Situs web Aspose](https://releases.aspose.com/pdf/net/).
- Visual Studio: Pastikan Anda telah menginstal Visual Studio di komputer Anda. Ini akan menjadi lingkungan pengembangan kita.
- .NET Framework: Pastikan Anda telah menginstal .NET Framework. Aspose.PDF untuk .NET mendukung berbagai versi, jadi periksa dokumentasi untuk menyesuaikan dengan kebutuhan Anda.
- Dokumen PDF: Anda memerlukan contoh dokumen PDF untuk digunakan. Jika Anda tidak memilikinya, buat PDF sederhana atau unduh contohnya secara daring.

Setelah Anda menyiapkan semuanya, kita siap untuk memulai membuat kode!

## Paket Impor

Sebelum kita mulai membuat kode, penting untuk mengimpor paket-paket yang diperlukan. Ini memastikan bahwa kita memiliki akses ke semua kelas dan metode yang kita butuhkan untuk proyek kita.

```csharp
using Aspose.Pdf.Devices;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

Impor ini penting karena menghadirkan namespace yang diperlukan untuk menangani manipulasi PDF, penyajian gambar, dan operasi aliran file.

## Langkah 1: Siapkan Jalur Proyek dan Dokumen Anda

Pertama-tama, mari kita atur jalur direktori tempat dokumen PDF Anda berada. Ini akan menjadi titik awal Anda untuk memanipulasi berkas PDF.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
 Di Sini,`dataDir` adalah direktori tempat dokumen PDF Anda berada. Pastikan untuk mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke dokumen Anda. Hal ini penting karena kode perlu mengetahui dari mana mengambil berkas PDF.

## Langkah 2: Muat Dokumen PDF

Sekarang setelah kita memiliki jalur dokumen, langkah berikutnya adalah memuat dokumen PDF ke dalam memori sehingga kita dapat mulai mengerjakannya.

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
```
 Kami menggunakan`Document` kelas dari pustaka Aspose.PDF untuk memuat berkas PDF kita. Kelas ini menyediakan berbagai metode dan properti untuk bekerja dengan dokumen PDF.`"input.pdf"` harus diganti dengan nama file PDF Anda yang sebenarnya. File ini akan digunakan sebagai input untuk rendering.

## Langkah 3: Buat Aliran Gambar untuk Output

Setelah dokumen dimuat, kita perlu menyiapkan aliran untuk menyimpan gambar yang telah dirender. Di sinilah gambar keluaran akan disimpan.

```csharp
using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
```
 Itu`FileStream`kelas digunakan untuk membuat file baru tempat gambar yang dirender akan disimpan. Dalam contoh ini, kami menyimpan gambar sebagai`"SetDefaultFontName.png"` . Itu`FileMode.Create` memastikan bahwa file baru dibuat, atau file yang sudah ada ditimpa.

## Langkah 4: Atur Resolusi Gambar

Sebelum mengubah PDF menjadi gambar, penting untuk mengatur resolusinya. Ini menentukan kualitas dan kejelasan gambar keluaran.

```csharp
Resolution resolution = new Resolution(300);
```
 Itu`Resolution` class menetapkan resolusi gambar keluaran. Di sini, kami telah memilih resolusi 300 DPI (titik per inci), yang merupakan standar untuk gambar berkualitas tinggi. Ini memastikan bahwa teks dan grafik dalam PDF Anda ditampilkan dengan jelas tanpa kehilangan detail.

## Langkah 5: Konfigurasikan Perangkat PNG

Berikutnya, kita perlu mengonfigurasi perangkat yang akan menangani pemrosesan PDF ke gambar PNG.

```csharp
PngDevice pngDevice = new PngDevice(resolution);
```
 Itu`PngDevice` kelas bertanggung jawab untuk merender dokumen PDF menjadi gambar PNG. Dengan melewati`resolution` keberatan dengan hal tersebut, kami memastikan bahwa gambar dibuat dengan DPI yang ditentukan.

## Langkah 6: Mengatur Nama Font Default

Berikut bagian yang penting – menetapkan nama font default. Ini akan menjadi font cadangan jika font asli dalam PDF tidak tersedia.

```csharp
RenderingOptions ro = new RenderingOptions();
ro.DefaultFontName = "Arial";
pngDevice.RenderingOptions = ro;
```
 Kami membuat sebuah contoh`RenderingOptions` dan mengaturnya`DefaultFontName` properti untuk`"Arial"`. Ini berarti bahwa jika font asli dalam PDF tidak dapat ditemukan, Arial akan digunakan sebagai gantinya. Langkah ini penting untuk menjaga keterbacaan dan tampilan teks dalam gambar yang ditampilkan.

## Langkah 7: Render Halaman PDF ke Gambar

Akhirnya, setelah semuanya siap, kita sekarang dapat mengubah halaman pertama dokumen PDF menjadi gambar dan menyimpannya menggunakan aliran file yang kita buat sebelumnya.

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```
 Itu`Process` metode dari`PngDevice` kelas digunakan untuk merender halaman PDF yang ditentukan (dalam kasus ini, halaman pertama) menjadi gambar. Output kemudian disimpan ke`imageStream`Langkah ini mengonversi halaman PDF menjadi gambar PNG dengan resolusi dan font default yang ditentukan.

## Langkah 8: Tutup Aliran File dan Dokumen PDF

Setelah merender gambar, penting untuk menutup aliran file dan dokumen PDF untuk mengosongkan sumber daya.

```csharp
imageStream.Close();
pdfDocument.Dispose();
```
Penutupan`imageStream` memastikan bahwa file disimpan dengan benar dan tidak ada data yang hilang. Membuang`pdfDocument` membebaskan memori dan sumber daya, mencegah potensi kebocoran memori.

## Kesimpulan

Nah, itu dia! Hanya dengan beberapa baris kode, Anda telah mempelajari cara mengatur nama fon default saat merender PDF ke gambar menggunakan Aspose.PDF for .NET. Keterampilan ini sangat berguna, terutama saat menangani PDF yang mungkin berisi fon yang tidak didukung. Dengan mengatur fon default, Anda memastikan bahwa gambar yang dirender tetap mudah dibaca dan terlihat profesional.

## Pertanyaan yang Sering Diajukan

### Apa yang terjadi jika font default yang ditentukan tidak terpasang pada sistem?
 Jika font default yang ditentukan dalam`RenderingOptions` tidak terinstal di sistem, Aspose.PDF akan menggunakan font fallback yang ditentukan sistem.

### Bisakah saya menggunakan font selain Arial sebagai font default?
Tentu saja! Anda dapat mengatur font apa pun yang terinstal di sistem Anda sebagai font default.

### Mungkinkah mengubah beberapa halaman PDF menjadi gambar sekaligus?
Ya, Anda dapat mengulang halaman-halaman PDF Anda dan merender setiap halaman secara individual menggunakan proses yang sama.

### Apakah pengaturan resolusi tinggi mempengaruhi kinerja rendering PDF?
Ya, resolusi yang lebih tinggi akan menghasilkan berkas gambar yang lebih besar dan dapat meningkatkan waktu rendering, tetapi resolusi yang lebih tinggi juga akan menghasilkan gambar yang lebih jelas.

### Bisakah saya mengubah PDF ke format gambar lain selain PNG?
Ya, Aspose.PDF mendukung rendering ke berbagai format gambar seperti JPEG, BMP, dan TIFF.