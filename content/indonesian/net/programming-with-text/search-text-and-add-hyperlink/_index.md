---
title: Cari Teks dan Tambahkan Hyperlink
linktitle: Cari Teks dan Tambahkan Hyperlink
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mencari teks dan menambahkan hyperlink dalam PDF menggunakan Aspose.PDF untuk .NET dengan tutorial langkah demi langkah kami.
type: docs
weight: 450
url: /id/net/programming-with-text/search-text-and-add-hyperlink/
---
## Perkenalan

Apakah Anda mencari cara untuk tidak hanya memanipulasi PDF tetapi juga menyempurnakannya dengan menyisipkan hyperlink? Nah, Anda berada di tempat yang tepat! Dengan pustaka Aspose.PDF for .NET yang canggih, Anda dapat mencari pola teks dalam dokumen PDF dan menambahkan hyperlink dengan mudah. Bayangkan memiliki dokumen yang tidak hanya menyampaikan informasi tetapi juga menghubungkan pembaca ke sumber daya yang relevan hanya dengan mengeklik tautan. Kedengarannya menarik, bukan? Dalam tutorial ini, kami akan memandu Anda langkah demi langkah tentang cara mencari teks menggunakan ekspresi reguler dan menambahkan hyperlink dalam PDF Anda. Baik Anda pengembang berpengalaman atau baru memulai, Anda akan menemukan proses ini sederhana dan bermanfaat.

## Prasyarat

Sebelum kita menyelami hal-hal yang lebih mendalam, mari pastikan Anda memiliki semua yang Anda butuhkan untuk mengikutinya. Berikut ini adalah daftar periksa yang praktis:

- .NET Framework: Anda harus menginstal .NET Framework di komputer Anda (versi 4.0 atau lebih tinggi).
- Pustaka Aspose.PDF untuk .NET: Jangan lupa mengunduh dan menambahkan referensi ke pustaka Aspose.PDF di proyek Anda. Anda dapat menemukannya[Di Sini](https://releases.aspose.com/pdf/net/).
- IDE: Anda memerlukan Lingkungan Pengembangan Terpadu (IDE) seperti Visual Studio untuk menulis dan menjalankan kode.
- Contoh Berkas PDF: Ambil contoh berkas PDF yang dapat Anda gunakan untuk menguji kode. Anda dapat membuat PDF sederhana atau menggunakan salah satu dokumen yang sudah ada.

Setelah Anda mencentang semua hal pada daftar ini, kita siap berangkat!

## Paket Impor

Langkah pertama dalam perjalanan kita adalah mengimpor paket-paket yang diperlukan. Di sinilah kita memberi tahu proyek kita alat apa saja yang akan kita gunakan. Berikut ini cara melakukannya:

Dalam file C# Anda, mulailah dengan menyertakan namespace berikut di bagian atas:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
using System;
```

Dengan mengimpor namespace ini, Anda memberi program Anda akses ke semua fitur menarik yang ditawarkan Aspose.PDF.

Setelah semuanya siap, saatnya untuk mulai bertindak. Kita akan membahasnya dalam beberapa langkah, jadi ikuti dengan saksama!

### Langkah 1: Atur Direktori Dokumen Anda

Pertama, Anda perlu menentukan di mana file PDF Anda disimpan. Ubah`dataDir` variabel untuk menunjuk ke direktori dokumen Anda. Berikut cara melakukannya:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Pastikan untuk mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke dokumen Anda.

### Langkah 2: Buat TextFragmentAbsorber

 Selanjutnya, kita memerlukan alat untuk menemukan teks yang ingin kita tautkan. Masukkan`TextFragmentAbsorber`Orang kecil ini akan membantu kita mencari pola teks tertentu dalam PDF kita.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

Di sini, kami mencari pola tertentu: empat digit, tanda hubung, diikuti oleh empat digit lainnya (seperti nomor telepon atau tahun).

### Langkah 3: Aktifkan Pencarian Ekspresi Reguler

 Kami sudah menggunakan ekspresi reguler untuk menemukan pola teks kami, tetapi kami perlu memastikan`absorber` mengetahui bahwa itu diaktifkan. Ini penting agar pencarian dapat dilakukan dengan benar.

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

### Langkah 4: Inisialisasi PdfContentEditor

 Sekarang setelah penyerap kita siap, kita memerlukan`PdfContentEditor` untuk bekerja dengan berkas PDF kita. Kelas ini memungkinkan kita mengikat dan memanipulasi berkas PDF kita.

```csharp
PdfContentEditor editor = new PdfContentEditor();
```

### Langkah 5: Ikat File PDF Sumber Anda

Setelah editor konten kita siap, waktunya untuk mengikatnya ke berkas PDF sesungguhnya yang ingin kita kerjakan.

```csharp
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Pastikan untuk mengganti`"SearchRegularExpressionPage.pdf"` dengan nama berkas PDF Anda.

### Langkah 6: Terima Penyerap untuk Halaman

Kita perlu memberi tahu editor bahwa kita ingin mencari pada halaman tertentu dari dokumen. Dalam kasus ini, mari kita pilih Halaman 1.

```csharp
editor.Document.Pages[1].Accept(absorber);
```

### Langkah 7: Bersiap untuk Melakukan Looping Melalui Fragmen Teks

Sekarang, kita siap untuk mengulang semua fragmen teks yang ditemukan oleh absorber kita. Kita akan mengubah tampilannya dan mengatur hyperlink kita.

```csharp
int[] dashArray = { };
String[] LEArray = { };
Color blue = Color.Blue;
```

Di sini, kami menetapkan beberapa parameter, seperti warna hyperlink kami.

### Langkah 8: Ulangi Setiap Fragmen Teks

Untuk setiap fragmen teks yang cocok dengan pencarian kita, kita akan mengubah warnanya dan membuat hyperlink. Berikut tampilannya:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    Rectangle rect = new Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
    
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, biru, actionName);
    editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
        (float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
```

### Langkah 9: Simpan PDF yang Diedit

Kita hampir selesai! Sekarang saatnya menyimpan perubahan ke file PDF baru.

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
```

### Langkah 10: Tutup Editor

Terakhir, jangan lupa menutup dokumen Anda untuk melepaskan sumber daya!

```csharp
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

Sekarang, Anda baru saja membuat PDF dengan hyperlink yang dibuat secara dinamis berdasarkan hasil pencarian. Keren, bukan?

## Kesimpulan

Nah, itu dia! Dengan mengikuti langkah-langkah ini, Anda telah mempelajari cara menelusuri PDF dan menambahkan hyperlink menggunakan pustaka Aspose.PDF for .NET. Ini dapat membuka banyak kemungkinan, terutama jika Anda bekerja dengan dokumen yang memerlukan interaktivitas. Bayangkan menambahkan tautan ke sumber daya terkait, situs web referensi, atau bahkan halaman internal—semuanya hanya dengan beberapa baris kode!
## Pertanyaan yang Sering Diajukan

### Apa itu Aspose.PDF untuk .NET?  
Aspose.PDF untuk .NET adalah pustaka yang memungkinkan pengembang untuk membuat, memanipulasi, dan mengelola dokumen PDF dalam aplikasi .NET.

### Bagaimana cara mengunduh Aspose.PDF untuk .NET?  
 Anda dapat mengunduh perpustakaan[Di Sini](https://releases.aspose.com/pdf/net/).

### Dapatkah saya mencoba Aspose.PDF secara gratis?  
 Tentu saja! Anda bisa mendapatkan uji coba gratis[Di Sini](https://releases.aspose.com/).

### Apakah ada dukungan yang tersedia untuk produk Aspose?  
 Ya, Anda dapat menemukan dukungan dan diskusi komunitas[Di Sini](https://forum.aspose.com/c/pdf/10).

### Bagaimana cara memperoleh lisensi sementara untuk Aspose.PDF?  
 Anda dapat meminta lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).