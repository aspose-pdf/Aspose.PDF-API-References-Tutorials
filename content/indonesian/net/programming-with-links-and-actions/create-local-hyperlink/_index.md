---
title: Buat Hyperlink Lokal Dalam File PDF
linktitle: Buat Hyperlink Lokal Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara membuat hyperlink lokal dalam berkas PDF menggunakan Aspose.PDF for .NET dengan mudah dengan panduan langkah demi langkah kami.
type: docs
weight: 40
url: /id/net/programming-with-links-and-actions/create-local-hyperlink/
---
## Perkenalan

Dalam panduan ini, kami akan memandu Anda melalui proses pembuatan hyperlink lokal dalam file PDF menggunakan Aspose.PDF untuk .NET. Kami akan menguraikan setiap langkah dengan jelas, memastikan bahwa meskipun Anda baru dalam dunia manipulasi PDF, Anda akan dapat mengikutinya dengan mudah.

## Prasyarat

Sebelum menyelami kodenya, mari pastikan Anda memiliki semua yang dibutuhkan:

1.  Visual Studio: Anda akan memerlukan ini untuk mengembangkan aplikasi .NET Anda. Unduh dari[situs web](https://visualstudio.microsoft.com/).
2.  Aspose.PDF untuk .NET: Anda dapat mengunduh pustaka ini melalui[tautan unduhan di sini](https://releases.aspose.com/pdf/net/)Dilengkapi dengan serangkaian fitur lengkap untuk manipulasi PDF.
3. Pengetahuan Dasar C#: Sedikit pengetahuan tentang pemrograman C# akan membantu, tetapi jangan khawatir; kita akan membahas kode tersebut baris demi baris.
4.  .NET Framework: Pastikan Anda telah menginstal .NET Framework di komputer Anda. Anda dapat memeriksa persyaratannya di Aspose.PDF[dokumentasi](https://reference.aspose.com/pdf/net/).

Dengan prasyarat ini yang disiapkan, Anda siap mempelajari cara membuat hyperlink lokal dalam dokumen PDF Anda!

## Paket Impor

Setelah semuanya siap, saatnya mengimpor paket yang diperlukan ke dalam proyek C# Anda. Pustaka Aspose.PDF berisi semua kelas yang kita butuhkan. Berikut cara melakukannya:

### Buka Proyek Anda

Buka proyek .NET yang sudah ada atau buat yang baru di Visual Studio. Jika Anda memulai dari awal, pilih “Buat proyek baru” dari layar awal.

### Tambahkan Referensi ke Aspose.PDF

 Klik kanan pada "Dependencies" di folder proyek Anda di Solution Explorer. Pilih "Manage NuGet Packages," lalu cari`Aspose.PDF`. Instal versi terbaru yang tersedia. Ini akan menyediakan semua alat yang Anda perlukan untuk membuat dan memanipulasi PDF.

### Mengimpor Ruang Nama

Di bagian atas file .cs Anda, tambahkan arahan penggunaan untuk pustaka Aspose.PDF seperti ini:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Dengan cara ini, Anda akan dapat mengakses fitur-fitur perpustakaan.

Mari kita uraikan proses pembuatan hyperlink lokal ke dalam beberapa langkah sederhana. Setiap langkah akan dijelaskan secara komprehensif untuk membantu Anda memahami logika di baliknya.

## Langkah 1: Siapkan Instansi Dokumen

Pada langkah ini, Anda akan membuat contoh baru kelas Dokumen, yang mewakili berkas PDF yang akan Anda kerjakan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Atur direktori dokumen Anda
Document doc = new Document(); // Buat contoh Dokumen
```
 Itu`dataDir` variabel adalah tempat PDF yang baru Anda buat akan berada. Anda perlu mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya pada sistem Anda.`Document` Kelas membuat dokumen PDF baru tempat kita dapat menambahkan halaman dan tautan.

## Langkah 2: Tambahkan Halaman ke Dokumen

Berikutnya, Anda akan menambahkan halaman ke dokumen PDF Anda. 

```csharp
Page page = doc.Pages.Add(); // Tambahkan halaman ke koleksi halaman
```
 Itu`Pages.Add()` metode menambahkan halaman baru ke dokumen. Di sinilah semua konten Anda akan berada.

## Langkah 3: Buat Fragmen Teks

Sekarang, mari kita membuat sepotong teks yang akan berfungsi sebagai tautan yang dapat diklik.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
```
 Itu`TextFragment` mewakili segmen teks dalam PDF. Di sini, kami membuat tautan yang memberi tahu pengguna bahwa tautan tersebut akan membawa mereka ke halaman 7.

## Langkah 4: Buat Hyperlink Lokal

Di sinilah keajaiban terjadi! Anda perlu membuat hyperlink lokal yang akan memberi tahu fragmen teks ke mana harus diarahkan.

```csharp
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink(); // Buat hyperlink lokal
link.TargetPageNumber = 7; //Tetapkan halaman target untuk contoh tautan
text.Hyperlink = link; // Tetapkan hyperlink TextFragment
```
 Itu`LocalHyperlink` kelas adalah apa yang memungkinkan kita untuk menunjuk ke halaman lain dalam dokumen yang sama. Dengan mengatur`TargetPageNumber` ke 7, Anda memberi tahu hyperlink untuk melompat ke halaman tertentu saat diklik.

## Langkah 5: Tambahkan Fragmen Teks ke Halaman

Setelah menyiapkan hyperlink, saatnya menambahkan fragmen teks ke halaman yang kita buat.

```csharp
page.Paragraphs.Add(text); // Tambahkan teks ke koleksi paragraf Halaman
```
Baris ini menambahkan teks yang dapat diklik ke kumpulan paragraf halaman.

## Langkah 6: Buat Fragmen Teks Lain (Opsional)

Mari tambahkan hyperlink lain untuk menavigasi kembali ke halaman 1.

```csharp
text = new TextFragment("link page number test to page 1"); // Buat TextFragment baru
text.IsInNewPage = true; // Tambahkan ke halaman baru
```
 Membuat yang baru`TextFragment` untuk link kedua kita atur`IsInNewPage` menjadi benar, yang menunjukkan teks ini akan berpindah ke halaman baru.

## Langkah 7: Siapkan Hyperlink Lokal Kedua

Sama seperti sebelumnya, Anda akan membuat hyperlink lokal lain untuk halaman 1.

```csharp
link = new LocalHyperlink(); // Buat instance hyperlink lokal lainnya
link.TargetPageNumber = 1; //Tetapkan halaman Target untuk hyperlink kedua
text.Hyperlink = link; // Tetapkan tautan untuk TextFragment kedua
```
Hyperlink ini menargetkan halaman 1, yang memungkinkan pengguna untuk melompat kembali saat mereka mencapai halaman kedua.

## Langkah 8: Tambahkan Fragmen Teks Kedua ke Halaman Baru

Sekarang, mari tambahkan teks ini ke halamannya.

```csharp
page.Paragraphs.Add(text); // Tambahkan teks ke kumpulan paragraf objek halaman
```
Mirip dengan langkah 5, baris ini menambahkan teks hyperlink baru ke halaman yang baru dibuat.

## Langkah 9: Simpan Dokumen

Akhirnya, tibalah waktunya untuk menyimpan kerja keras Anda! 

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf"; // Tentukan nama file keluaran
doc.Save(dataDir); // Simpan dokumen yang diperbarui
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);
```
 Ini menggabungkan jalur direktori Anda dengan nama file.`Save()` metode ini menyimpan dokumen Anda dan pesan konfirmasi memberi tahu Anda bahwa semuanya berjalan lancar!

## Kesimpulan

Membuat hyperlink lokal dalam file PDF menggunakan Aspose.PDF untuk .NET bukan sekadar trik keren; ini adalah fitur praktis yang meningkatkan navigasi dan pengalaman pengguna. Kini Anda dibekali dengan pengetahuan untuk mengarahkan pembaca langsung ke informasi yang mereka butuhkan. Coba ingat kembali analogi awal kita—tidak ada lagi jiwa yang tersesat yang berkeliaran di halaman yang tak berujung.

## Pertanyaan yang Sering Diajukan

### Apa itu Aspose.PDF untuk .NET?
Aspose.PDF untuk .NET adalah pustaka yang memungkinkan pengembang untuk membuat, memanipulasi, dan mengonversi dokumen PDF secara terprogram menggunakan kerangka kerja .NET.

### Bisakah saya membuat hyperlink ke halaman web eksternal?
Ya, Aspose.PDF juga mendukung pembuatan hyperlink ke URL eksternal selain hyperlink lokal dalam PDF.

### Apakah ada uji coba gratis untuk Aspose.PDF?
 Tentu saja! Anda dapat mengakses uji coba gratis dari[lokasi](https://releases.aspose.com/).

### Bahasa pemrograman apa yang didukung Aspose?
Aspose menawarkan pustaka untuk berbagai bahasa pemrograman, termasuk Java, CBahasa Indonesia: ++, dan Python, antara lain.

### Bagaimana cara mendapatkan dukungan untuk produk Aspose?
 Anda dapat mencari dukungan melalui[Forum Aspose](https://forum.aspose.com/c/pdf/10).