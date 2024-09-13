---
title: Nomor Halaman Di Header Footer Menggunakan Floating Box
linktitle: Nomor Halaman Di Header Footer Menggunakan Floating Box
second_title: Referensi API Aspose.PDF untuk .NET
description: Tambahkan nomor halaman dengan mudah di header dan footer PDF Anda menggunakan Kotak Mengambang dengan Aspose.PDF untuk .NET dalam tutorial langkah demi langkah ini.
type: docs
weight: 150
url: /id/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
## Perkenalan

Jika berbicara tentang pengelolaan dokumen PDF secara terprogram, Aspose.PDF untuk .NET menonjol sebagai alat yang luar biasa. Alat ini menyederhanakan cara kita membuat, mengedit, dan memanipulasi file PDF dalam aplikasi .NET. Baik Anda membuat faktur, laporan, atau jenis dokumen apa pun, menambahkan nomor halaman secara elegan dapat meningkatkan profesionalisme dan pengaturan PDF Anda. Dalam tutorial ini, kita akan membahas cara menambahkan nomor halaman di header dan footer PDF Anda menggunakan Floating Box. Siap untuk memulai? Ayo!

## Prasyarat

Sebelum kita memulai perjalanan menarik ini ke dalam dunia manipulasi PDF, ada beberapa hal yang perlu Anda miliki:

### Pengaturan Lingkungan .NET
Pastikan Anda memiliki lingkungan pengembangan .NET. Anda dapat menggunakan Visual Studio, yang merupakan pilihan populer di kalangan pengembang untuk aplikasi .NET.

### Pustaka Aspose.PDF
Instal pustaka Aspose.PDF. Anda dapat mengunduhnya dengan mudah dari situs web:

- [Unduh Aspose.PDF untuk .NET](https://releases.aspose.com/pdf/net/)

### Pengetahuan Dasar Pemrograman C#
Pemahaman dasar tentang C# akan membantu Anda memahami konsep dan potongan kode yang disajikan dalam tutorial ini.

### Akses ke Dokumentasi
 Selalu bermanfaat untuk memiliki[Dokumentasi Aspose.PDF](https://reference.aspose.com/pdf/net/) berguna untuk referensi dan eksplorasi lebih dalam terhadap fungsi tambahan apa pun.

## Paket Impor

Untuk memulai, Anda perlu mengimpor paket yang diperlukan ke dalam proyek Anda. Ini memastikan bahwa assembly Aspose.PDF dapat diakses untuk digunakan dalam kode Anda. Berikut cara melakukannya:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Sekarang, mari kita uraikan proses penambahan nomor halaman menggunakan Floating Box menjadi beberapa langkah yang mudah dikelola. Ikuti langkah-langkahnya.

## Langkah 1: Siapkan Lingkungan Dokumen Anda

Mari kita mulai dengan menentukan direktori tempat dokumen PDF Anda akan disimpan. Ini penting karena menentukan di mana file output Anda akan disimpan.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`YOUR DOCUMENT DIRECTORY` dengan jalur pilihan Anda di mana Anda ingin menyimpan berkas PDF keluaran.

## Langkah 2: Buat Instansiasi Dokumen

 Membuat dokumen PDF baru adalah langkah selanjutnya. Ini melibatkan penggunaan`Document` kelas dari pustaka Aspose.PDF.

```csharp
// Membuat contoh dokumen
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
```
 Di sini, kita membuat contoh baru dari`Document` kelas, yang berfungsi sebagai kanvas untuk manipulasi.

## Langkah 3: Tambahkan Halaman Baru

Sekarang, mari tambahkan satu halaman ke dokumen PDF kita. Setiap PDF memerlukan setidaknya satu halaman, bukan?

```csharp
// Tambahkan Halaman ke dalam dokumen PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
```
Potongan kode ini menambahkan halaman baru ke dokumen kita, membuatnya siap menerima konten, termasuk kotak mengambang dengan nomor halaman.

## Langkah 4: Buat Kotak Mengambang

 Selanjutnya, saatnya membuat Kotak Mengambang yang akan menampung nomor halaman.`FloatingBox`kelas memungkinkan kita untuk memposisikan konten secara bebas di halaman.

```csharp
// Menginisialisasi instance baru dari kelas FloatingBox
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);
```
 Di sini, parameternya`(140, 80)` Tentukan lebar dan tinggi Kotak Terapung. Anda dapat menyesuaikan nilai ini berdasarkan preferensi tata letak Anda.

## Langkah 5: Memposisikan Kotak Mengambang

 Penempatan adalah kuncinya! Anda ingin menentukan di mana nomor halaman akan muncul di halaman. Anda akan bekerja dengan`Left` Dan`Top` properti untuk menentukan posisi.

```csharp
// Nilai float yang menunjukkan posisi kiri paragraf
box1.Left = 2;
// Nilai float yang menunjukkan posisi teratas paragraf
box1.Top = 10;
```
Nilai-nilai ini menentukan penempatan Floating Box pada halaman. Jangan ragu untuk bereksperimen dengan nilai-nilai ini untuk melihat apa yang paling cocok untuk dokumen Anda.

## Langkah 6: Tambahkan Teks dengan Makro Nomor Halaman

Sekarang, kita akan menambahkan string yang secara dinamis menampilkan nomor halaman. Di sinilah keajaiban terjadi!

```csharp
// Tambahkan makro ke koleksi paragraf FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));
```
 Dalam kasus ini,`($p/ $P)`adalah makro yang akan menampilkan nomor halaman saat ini (`$p`) dan jumlah halaman total (`$P`). Akibatnya, teks diformat menjadi seperti "Halaman: 1/5".

## Langkah 7: Tambahkan Kotak Mengambang ke Halaman

Sekarang saatnya menambahkan Kotak Mengambang, beserta teks nomor halaman, ke halaman yang baru kita buat.

```csharp
// Tambahkan floatingBox ke halaman
page.Paragraphs.Add(box1);
```
Baris ini pada dasarnya menanamkan Kotak Mengambang Anda ke dalam halaman, menjadikannya bagian dari tata letak dokumen. 

## Langkah 8: Simpan Dokumen Anda

Terakhir, jangan lupa untuk menyimpan pekerjaan Anda! Langkah terakhir adalah menyimpan dokumen PDF Anda dengan nama file yang tepat.

```csharp
// Simpan dokumen
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```
Pastikan jalur yang ditentukan menyertakan nama berkas yang Anda inginkan. Sekarang, PDF Anda yang menakjubkan dengan nomor halaman telah dibuat! 

## Kesimpulan

Nah, itu dia! Menambahkan nomor halaman ke header dan footer PDF Anda menggunakan Aspose.PDF for .NET semudah itu. Hanya dengan beberapa baris kode, Anda telah memulai perjalanan untuk menguasai pemrosesan dokumen dalam aplikasi Anda. Jangan ragu untuk bereksperimen dengan tata letak dan format yang berbeda—bagaimanapun juga, kreativitas tidak mengenal batas! Siap untuk membuat dokumen profesional? Ambil topi coding Anda dan mulailah bereksperimen.

## Pertanyaan yang Sering Diajukan

### Bisakah saya menyesuaikan tampilan teks nomor halaman?  
 Ya, Anda dapat menyesuaikan properti teks, seperti ukuran font, warna, dan gaya dengan menyesuaikan`TextFragment` properti.

### Apakah Aspose.PDF gratis untuk digunakan?  
 Meskipun Aspose.PDF menawarkan uji coba gratis, ini adalah produk berbayar untuk penggunaan produksi. Anda dapat[beli disini](https://purchase.aspose.com/buy).

### Di mana saya dapat menemukan dokumentasi yang lebih rinci?  
 Anda dapat menemukan dokumentasi lengkap di[Situs Dokumentasi Aspose.PDF](https://reference.aspose.com/pdf/net/).

### Bagaimana cara menerapkan header dan footer ke beberapa halaman?  
Anda dapat mengulang semua halaman di dokumen Anda dan menerapkan Kotak Mengambang ke setiap halaman dengan cara yang sama.

### Bagaimana jika saya memerlukan dukungan untuk fitur tambahan?  
Untuk pertanyaan atau dukungan tambahan, Anda dapat mengunjungi[Forum Aspose](https://forum.aspose.com/c/pdf/10).