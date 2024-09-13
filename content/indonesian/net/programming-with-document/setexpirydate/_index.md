---
title: Tetapkan Tanggal Kedaluwarsa Dalam File PDF
linktitle: Tetapkan Tanggal Kedaluwarsa Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menetapkan tanggal kedaluwarsa dalam file PDF menggunakan Aspose.PDF untuk .NET. Tingkatkan keamanan dokumen dengan panduan langkah demi langkah ini.
type: docs
weight: 300
url: /id/net/programming-with-document/setexpirydate/
---
## Perkenalan

Di era digital saat ini, mengelola dan mengamankan dokumen menjadi lebih penting dari sebelumnya. Bayangkan mengirimkan PDF yang secara otomatis tidak dapat diakses setelah tanggal tertentu. Kedengarannya seperti sulap, bukan? Nah, dengan Aspose.PDF untuk .NET, Anda dapat dengan mudah mengatur tanggal kedaluwarsa untuk file PDF Anda. Fitur ini sangat berguna untuk dokumen sensitif yang perlu dibatasi setelah jangka waktu tertentu. Dalam tutorial ini, kami akan memandu Anda melalui proses pengaturan tanggal kedaluwarsa dalam file PDF langkah demi langkah. Jadi, ambil topi koding Anda, dan mari kita mulai!

## Prasyarat

Sebelum kita memulai, ada beberapa hal yang perlu Anda siapkan:

1. Lingkungan Pengembangan: Pastikan Anda telah menyiapkan lingkungan pengembangan .NET. Ini bisa berupa Visual Studio atau IDE lain yang mendukung .NET.
2.  Aspose.PDF untuk .NET: Anda perlu menginstal pustaka Aspose.PDF. Jika Anda belum melakukannya, Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/pdf/net/).
3. Pengetahuan Dasar tentang C#: Tutorial ini mengasumsikan Anda memiliki pemahaman dasar tentang pemrograman C#. Jika Anda baru mengenal C#, jangan khawatir! Kami akan menjelaskannya secara sederhana dan lugas.

## Paket Impor

Untuk memulai Aspose.PDF, Anda perlu mengimpor namespace yang diperlukan dalam proyek C# Anda. Berikut cara melakukannya:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

Ruang nama ini memberi Anda akses ke fungsionalitas inti yang diperlukan untuk bekerja dengan dokumen PDF di Aspose.PDF.

## Langkah 1: Siapkan Direktori Dokumen Anda

Pertama-tama, Anda perlu menentukan jalur ke direktori dokumen Anda. Di sinilah hasil PDF Anda akan disimpan. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya tempat Anda ingin menyimpan berkas PDF. Ini seperti memberi tahu program Anda, “Hei, ini tempat saya menyimpan berkas saya!”

## Langkah 2: Buat Instansiasi Objek Dokumen

 Selanjutnya, Anda perlu membuat instance baru dari`Document` kelas. Ini adalah kanvas tempat Anda akan membuat PDF.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

 Pikirkanlah tentang`Document` objek sebagai selembar kertas kosong. Anda dapat menambahkan konten ke dalamnya sesuai keinginan!

## Langkah 3: Tambahkan Halaman ke PDF

Setelah dokumen Anda siap, saatnya menambahkan halaman. Di sinilah konten Anda akan ditempatkan.

```csharp
doc.Pages.Add();
```

Anda baru saja membuat halaman baru di PDF Anda. Ini seperti menambahkan halaman baru di buku catatan Anda tempat Anda dapat menuliskan pikiran-pikiran Anda.

## Langkah 4: Tambahkan Teks ke Halaman

Mari kita buat halaman ini sedikit lebih menarik dengan menambahkan beberapa teks. Kita akan menambahkan pesan sederhana “Halo Dunia”.

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

Baris kode ini menambahkan fragmen teks ke halaman pertama PDF Anda. Mirip seperti menulis judul di bagian atas halaman!

## Langkah 5: Buat JavaScript untuk Tanggal Kedaluwarsa

Sekarang tibalah bagian yang menyenangkan! Anda akan membuat tindakan JavaScript yang akan memeriksa tanggal kedaluwarsa PDF. Jika tanggal saat ini melebihi tanggal kedaluwarsa, sebuah pesan akan mengingatkan pengguna.

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
```

Inilah yang terjadi:
- Anda menentukan tahun dan bulan kedaluwarsa.
- Anda mendapatkan tanggal hari ini.
- Anda membandingkan tanggal hari ini dengan tanggal kedaluwarsa.
- Jika tanggal hari ini melewati tanggal kedaluwarsa, sebuah pesan akan muncul!

## Langkah 6: Tetapkan JavaScript sebagai PDF Buka Tindakan

Sekarang, Anda perlu menetapkan tindakan JavaScript sebagai tindakan buka untuk dokumen PDF Anda. Ini berarti bahwa JavaScript akan berjalan segera setelah PDF dibuka.

```csharp
doc.OpenAction = javaScript;
```

Baris ini memberi tahu PDF untuk menjalankan JavaScript saat seseorang membukanya. Ini seperti menyetel pengingat yang berbunyi segera setelah Anda membuka kalender!

## Langkah 7: Simpan Dokumen PDF

Akhirnya, saatnya menyimpan dokumen PDF Anda dengan fitur tanggal kedaluwarsa. 

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
doc.Save(dataDir);
```

Baris ini menyimpan PDF Anda ke direktori yang ditentukan dengan nama "SetExpiryDate_out.pdf". Ini seperti meletakkan karya seni Anda yang sudah selesai dalam bingkai!

## Kesimpulan

Nah, itu dia! Anda telah berhasil membuat file PDF dengan tanggal kedaluwarsa menggunakan Aspose.PDF untuk .NET. Fitur ini tidak hanya meningkatkan keamanan tetapi juga memastikan bahwa informasi sensitif tetap terkendali. Baik Anda mengirimkan kontrak, laporan, atau dokumen penting lainnya, menetapkan tanggal kedaluwarsa dapat mengubah segalanya.

## Pertanyaan yang Sering Diajukan

### Apa itu Aspose.PDF untuk .NET?
Aspose.PDF untuk .NET adalah pustaka hebat yang memungkinkan pengembang untuk membuat, memanipulasi, dan mengonversi dokumen PDF dalam aplikasi .NET.

### Dapatkah saya menggunakan Aspose.PDF secara gratis?
 Ya, Anda dapat menggunakan versi uji coba gratis Aspose.PDF. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/).

### Bagaimana cara membeli Aspose.PDF?
Anda dapat membeli Aspose.PDF dengan mengunjungi[halaman pembelian](https://purchase.aspose.com/buy).

### Bagaimana jika saya butuh dukungan?
Jika Anda memiliki pertanyaan atau memerlukan bantuan, Anda dapat mengunjungi[Forum dukungan Aspose](https://forum.aspose.com/c/pdf/10).

### Bisakah saya mendapatkan lisensi sementara untuk Aspose.PDF?
 Ya, Anda dapat meminta lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).