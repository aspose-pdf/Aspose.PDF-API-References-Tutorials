---
title: Tambahkan Batas Teks Dalam File PDF
linktitle: Tambahkan Batas Teks Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menambahkan bingkai teks dalam file PDF menggunakan Aspose.PDF for .NET dengan panduan langkah demi langkah ini. Sempurnakan dokumen PDF Anda.
type: docs
weight: 70
url: /id/net/programming-with-text/add-text-border/
---
## Perkenalan

Membuat dan memanipulasi dokumen PDF telah menjadi keterampilan penting di dunia digital saat ini. Baik Anda membuat laporan, faktur, atau jenis dokumentasi lainnya, memiliki kendali atas tampilan teks dapat membuat perbedaan yang signifikan. Salah satu peningkatan yang mungkin ingin Anda terapkan adalah menambahkan bingkai di sekeliling teks dalam file PDF. Dalam panduan ini, kami akan memandu Anda melalui langkah-langkah untuk menambahkan bingkai teks dalam file PDF menggunakan pustaka Aspose.PDF untuk .NET. Jadi, mari kita langsung mulai!

## Prasyarat

Sebelum kita mulai, ada beberapa hal yang perlu Anda persiapkan. Jangan khawatir, ini cukup mudah!

1. Visual Studio: Pastikan Anda telah menginstal Visual Studio di komputer Anda. Ini akan menjadi lingkungan pengembangan tempat Anda menulis dan menjalankan kode.
2.  Aspose.PDF untuk .NET: Anda perlu mengunduh dan memasang pustaka Aspose.PDF. Anda bisa mendapatkannya dari[Halaman unduhan Aspose PDF untuk .NET](https://releases.aspose.com/pdf/net/) Jika Anda ingin mencobanya terlebih dahulu, Anda juga bisa mendapatkan[uji coba gratis di sini](https://releases.aspose.com/).
3. Pengetahuan Dasar C#: Pemahaman mendasar tentang bahasa pemrograman C# akan membantu Anda mengikuti contoh-contoh dengan mudah.
4. .NET Framework: Pastikan Anda telah menginstal dan menyiapkan .NET Framework di proyek Anda.

Setelah Anda memiliki prasyarat ini, Anda siap untuk mulai membuat kode!

## Paket Impor

Setelah semuanya siap, mari impor paket yang diperlukan untuk menggunakan Aspose.PDF dalam proyek kita. Anda dapat melakukannya dengan menambahkan perintah berikut di bagian atas file C# Anda:

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

```

Ruang nama ini akan memungkinkan Anda bekerja dengan dokumen PDF dan fragmen teks secara efektif. 

Sekarang, mari kita uraikan proses penambahan bingkai teks ke dalam beberapa langkah terperinci. Kita akan membahas setiap langkahnya sehingga Anda dapat memahami dengan tepat apa yang terjadi di balik layar.

## Langkah 1: Siapkan Dokumen

Pertama-tama, kita perlu membuat dokumen PDF baru. Di sinilah semua keajaiban kita akan terjadi.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buat objek dokumen baru
Document pdfDocument = new Document();
```

 Pada langkah ini, kita tentukan direktori tempat kita ingin menyimpan file PDF kita. Kemudian kita buat instance baru dari`Document` kelas, yang mewakili dokumen PDF kita.

## Langkah 2: Tambahkan Halaman Baru

Selanjutnya, kita perlu menambahkan halaman ke dokumen kita. Anggap saja ini seperti menambahkan kanvas kosong tempat kita akan meletakkan teks.

```csharp
// Dapatkan halaman tertentu
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

 Di sini, kami menyebutnya`Add()` metode pada`Pages` koleksi kami`pdfDocument` objek. Ini menambahkan halaman baru ke dokumen, dan kami menyimpan referensi ke sana di`pdfPage` variabel.

## Langkah 3: Buat Fragmen Teks

Sekarang, mari kita buat teks yang ingin kita tampilkan dalam PDF kita. Di sinilah kita mendefinisikan konten fragmen teks kita.

```csharp
// Buat fragmen teks
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

 Dalam kode ini, kita membuat yang baru`TextFragment` objek dengan teks "teks utama". Kami juga mengatur posisinya di halaman menggunakan`Position` kelas. Koordinat (100, 600) menentukan di mana teks akan ditempatkan pada halaman.

## Langkah 4: Mengatur Properti Teks

Selanjutnya, kita akan menyesuaikan fragmen teks kita agar menarik secara visual. Ini termasuk pengaturan ukuran font, jenis font, warna latar belakang, dan warna latar depan.

```csharp
// Mengatur properti teks
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

Di sini, kami menetapkan ukuran font menjadi 12, menggunakan "Times New Roman" sebagai font, dan menerapkan warna latar belakang abu-abu muda dengan teks merah. Properti ini membantu meningkatkan visibilitas teks.

## Langkah 5: Mengatur Warna Goresan untuk Perbatasan

Sekarang, kita sampai pada bagian yang menarik—menambahkan bingkai pada teks kita!

```csharp
// Atur properti StrokingColor untuk menggambar batas (stroking) di sekitar persegi panjang teks
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

Pada langkah ini, kita tentukan warna batas yang ingin kita buat di sekeliling teks. Di sini, kita pilih warna merah tua.

## Langkah 6: Aktifkan Batas Persegi Panjang Teks

 Untuk benar-benar menggambar batas di sekitar teks kita, kita perlu mengaktifkan`DrawTextRectangleBorder` milik.

```csharp
// Tetapkan nilai properti DrawTextRectangleBorder ke true
textFragment.TextState.DrawTextRectangleBorder = true;
```

 Dengan mengatur properti ini ke`true`, kami memberi tahu Aspose.PDF untuk menggambar batas di sekitar persegi panjang teks berdasarkan warna goresan yang ditentukan.

## Langkah 7: Tambahkan Fragmen Teks ke Halaman

Sekarang setelah fragmen teks kita siap dengan semua properti yang ditetapkan, saatnya untuk menambahkannya ke halaman.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

 Di sini, kita membuat`TextBuilder` objek yang terkait dengan kita`pdfPage` Kemudian kami menggunakan`AppendText` metode untuk menambahkan kita`textFragment` ke halaman. 

## Langkah 8: Simpan Dokumen

Terakhir, kita perlu menyimpan dokumen PDF kita ke direktori yang ditentukan. Inilah saatnya untuk menentukan kebenaran!

```csharp
// Simpan dokumen
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

Pada langkah ini, kita memanggil`Save` metode pada kami`pdfDocument` objek, yang menyediakan jalur tempat kita ingin menyimpan file. Setelah menjalankan kode, Anda akan menemukan PDF yang baru Anda buat dengan bingkai teks di direktori yang ditentukan!

## Kesimpulan

Nah, itu dia! Anda telah berhasil menambahkan bingkai teks ke berkas PDF menggunakan Aspose.PDF for .NET. Fitur sederhana namun hebat ini dapat meningkatkan keterbacaan dan estetika dokumen PDF Anda secara signifikan. Baik Anda membuat laporan, brosur, atau jenis dokumentasi lainnya, mengetahui cara memanipulasi format teks dapat berguna.

## Pertanyaan yang Sering Diajukan

### Apa itu Aspose.PDF untuk .NET?
Aspose.PDF untuk .NET adalah pustaka hebat yang memungkinkan pengembang untuk membuat, memanipulasi, dan memproses dokumen PDF secara terprogram menggunakan kerangka kerja .NET.

### Dapatkah saya mencoba Aspose.PDF secara gratis?
 Ya! Aspose menawarkan[uji coba gratis](https://releases.aspose.com/) perpustakaan PDF mereka, yang memungkinkan Anda menguji fitur-fiturnya sebelum melakukan pembelian.

### Bagaimana cara membeli Aspose.PDF untuk .NET?
 Anda dapat membeli Aspose.PDF untuk .NET langsung dari mereka[halaman pembelian](https://purchase.aspose.com/buy).

### Apakah ada dukungan yang tersedia untuk Aspose.PDF?
 Tentu saja! Anda bisa mendapatkan dukungan dengan mengunjungi[Forum dukungan Aspose](https://forum.aspose.com/c/pdf/10).

### Bagaimana jika saya memerlukan lisensi sementara?
 Aspose menyediakan[lisensi sementara](https://purchase.aspose.com/temporary-license/) pilihan bagi pengembang yang perlu mengevaluasi pustaka untuk waktu terbatas.