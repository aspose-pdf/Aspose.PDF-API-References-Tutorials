---
title: Isi Teks Goresan Dalam File PDF
linktitle: Isi Teks Goresan Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mengisi teks guratan dalam file PDF dengan mudah menggunakan Aspose.PDF untuk .NET dengan panduan langkah demi langkah yang dilengkapi dengan contoh-contoh praktis.
type: docs
weight: 90
url: /id/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
## Perkenalan

Pernahkah Anda ingin memodifikasi berkas PDF agar menonjol? Mungkin Anda perlu menambahkan tanda air yang mencolok atau stempel tebal yang membuat dokumen penting tampak seperti milik Anda. Dengan Aspose.PDF untuk .NET, Anda dapat dengan mudah mengisi teks guratan pada berkas PDF, menambahkan gaya artistik yang menarik perhatian. Dalam tutorial hari ini, kita akan membahas proses untuk melakukan hal tersebut—mengisi teks guratan pada PDF menggunakan C#. Pada akhirnya, Anda akan memiliki pemahaman yang kuat tentang cara memanipulasi berkas PDF seperti seorang profesional.

## Prasyarat

Sebelum kita masuk ke pengkodean, ada beberapa hal yang perlu Anda siapkan agar tutorial ini berjalan lancar:

1. Visual Studio: Pastikan Anda telah menginstal Visual Studio di komputer Anda karena kita akan menulis kode C#.
2.  Pustaka Aspose.PDF: Pastikan Anda telah mengunduh pustaka Aspose.PDF untuk .NET. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/pdf/net/).
3. Pengetahuan Dasar C#: Keakraban dengan pemrograman C# akan membantu Anda memahami tutorial dengan lebih mudah.
4. Contoh File PDF: Anda memerlukan contoh file PDF (`input.pdf`untuk tujuan pengujian. Anda dapat membuat yang sederhana atau menggunakan PDF apa pun yang sudah Anda miliki.

Setelah semua siap, mari kita masuk ke inti pengisian teks goresan pada berkas PDF Anda.

## Paket Impor

Untuk memulai, kita perlu mengimpor paket-paket yang diperlukan. Berikut ini ikhtisar singkat tentang impor penting untuk proyek kita:

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Paket-paket ini akan memungkinkan kita untuk menggunakan fungsionalitas yang kuat dari pustaka Aspose.PDF.

Mari kita uraikan tugas utama ke dalam langkah-langkah yang jelas. Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah mengisi teks guratan ke dalam berkas PDF Anda. 

## Langkah 1: Siapkan Lingkungan Anda

Pertama, pastikan Anda telah menyiapkan semuanya dengan benar di proyek Visual Studio Anda. Buat proyek baru atau pilih proyek yang sudah ada. Jika Anda memerlukan bantuan, berikut caranya:

1. Buka Visual Studio.
2. Buat proyek C# baru (misalnya, Aplikasi Konsol).
3. Klik kanan pada proyek di Solution Explorer, pilih “Kelola Paket NuGet.”
4.  Pencarian untuk`Aspose.PDF` dan menginstalnya.

## Langkah 2: Tentukan Direktori Dokumen Anda

Setiap perjalanan memerlukan titik awal, dan dalam kasus kami, itu adalah direktori dokumen tempat file masukan dan keluaran akan berada. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya tempat berkas PDF masukan Anda berada. 

## Langkah 3: Buat Objek TextState

Langkah ini adalah tempat Anda mulai menentukan properti teks yang ingin Anda tambahkan. 

```csharp
TextState ts = new TextState();
```

 Itu`TextState` Objek tersebut akan menampung pilihan gaya untuk teks guratan Anda.

## Langkah 4: Mengatur Warna untuk Stroke

Berikutnya, Anda ingin menentukan warna goresan untuk teks Anda. 

```csharp
ts.StrokingColor = Color.Gray;
```

Dalam kode ini, kami menggunakan warna abu-abu untuk goresannya. Jangan ragu untuk mengubah warna sesuai kebutuhan Anda!

## Langkah 5: Konfigurasikan Mode Rendering

Untuk memastikan teks Anda ditampilkan sebagaimana mestinya, atur mode rendering:

```csharp
ts.RenderingMode = TextRenderingMode.StrokeText;
```

Ini memberi instruksi pada pustaka Aspose bahwa kita sedang bekerja dengan teks goresan.

## Langkah 6: Muat Dokumen PDF Input Anda

Sekarang saatnya memuat berkas PDF yang akan Anda modifikasi. 

```csharp
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

Pastikan input PDF Anda (`input.pdf`terletak di direktori dokumen yang didefinisikan pada langkah sebelumnya.

## Langkah 7: Buat Objek Prangko

Berikutnya, buatlah prangko yang akan menampung teks goresan Anda. 

```csharp
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
```

Stempel ini akan digunakan untuk melapisi teks Anda pada PDF.

## Langkah 8: Tentukan Teks yang Akan Dicap

Anda perlu menentukan teks apa yang ingin Anda tambahkan ke PDF:

```csharp
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));
```

Di sini, “PAID IN FULL” adalah teks yang kami tambahkan, beserta atribut gayanya. Sesuaikan sesuai kebutuhan Anda!

## Langkah 9: Ikat Status Teks

 Sekarang, ikat`TextState` Anda definisikan sebelumnya pada prangko. 

```csharp
stamp.BindTextState(ts);
```

Langkah ini menerapkan semua gaya seperti warna dan mode rendering ke teks Anda.

## Langkah 10: Mengatur Posisi Stempel

Tentukan di mana prangko Anda akan muncul di PDF:

```csharp
stamp.SetOrigin(100, 100);
```

 Argumen`(100, 100)` menunjukkan koordinat X dan Y (dalam poin) untuk asal teks. Sesuaikan nilai-nilai ini untuk memposisikan teks Anda dengan sempurna!

## Langkah 11: Konfigurasikan Opacity dan Rotasi

Di sinilah Anda dapat bermain-main dengan tampilan teks Anda:

```csharp
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
```

Dalam kasus ini, nilai opasitas dan sudut rotasi 45 derajat akan menambahkan kesan unik pada teks Anda. Jangan ragu untuk mengubah pengaturan ini untuk mendapatkan efek yang berbeda.

## Langkah 12: Tambahkan Stempel ke PDF

Ini adalah langkah krusial di mana kita akhirnya menambahkan stempel yang menyertakan teks goresan ke PDF:

```csharp
fileStamp.AddStamp(stamp);
```

Dan begitu saja, teks Anda siap untuk membuat pernyataan!

## Langkah 13: Simpan dan Tutup Dokumen

Terakhir, simpan perubahan Anda dan pastikan semuanya dibersihkan dengan benar. 

```csharp
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

 File PDF Anda yang baru dimodifikasi yang berisi teks goresan akan disimpan sebagai`output_out.pdf` di direktori dokumen Anda. 

## Kesimpulan

Nah, itu dia! Dengan mengikuti langkah-langkah sederhana ini, Anda dapat dengan mudah mengisi teks guratan pada berkas PDF menggunakan Aspose.PDF for .NET. Baik untuk dokumen bisnis maupun proyek pribadi, teknik ini memungkinkan Anda menambahkan sentuhan unik pada PDF Anda, membuatnya menonjol di tumpukan kertas mana pun.

## Pertanyaan yang Sering Diajukan

### Apa itu Aspose.PDF untuk .NET?
Aspose.PDF untuk .NET adalah pustaka yang memungkinkan pengembang untuk membuat, memanipulasi, dan mengonversi file PDF secara terprogram.

### Dapatkah saya menggunakan Aspose.PDF secara gratis?
Ya, Aspose menawarkan uji coba gratis. Anda bisa mendapatkannya[Di Sini](https://releases.aspose.com/).

### Apakah saya perlu membayar lisensi?
 Meskipun perpustakaan memiliki uji coba gratis, lisensi sementara juga dapat dibeli di[tautan ini](https://purchase.aspose.com/temporary-license/).

### Di mana saya dapat menemukan dokumentasinya?
 Anda dapat mengakses dokumentasi lengkap[Di Sini](https://reference.aspose.com/pdf/net/).

### Apakah ada dukungan yang tersedia jika saya mengalami masalah?
 Tentu saja! Anda bisa mendapatkan dukungan di forum Aspose[Di Sini](https://forum.aspose.com/c/pdf/10).