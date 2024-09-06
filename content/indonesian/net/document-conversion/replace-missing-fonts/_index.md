---
title: Ganti Font yang Hilang
linktitle: Ganti Font yang Hilang
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mengganti font yang hilang dalam dokumen PDF menggunakan Aspose.PDF untuk .NET dengan panduan langkah demi langkah ini.
type: docs
weight: 260
url: /id/net/document-conversion/replace-missing-fonts/
---
## Perkenalan

Pernahkah Anda membuka dokumen PDF dan mendapati beberapa font hilang? Hal ini bisa membuat frustrasi, bukan? Font yang hilang dapat menyebabkan dokumen terlihat sangat berbeda dari yang diinginkan pembuatnya. Untungnya, dengan Aspose.PDF untuk .NET, Anda dapat dengan mudah mengganti font yang hilang dan memastikan dokumen PDF Anda tetap terlihat seperti yang diinginkan. Dalam tutorial ini, kami akan memandu Anda melalui proses ini langkah demi langkah, membuatnya sederhana dan mudah.

## Prasyarat

Sebelum kita memulai, ada beberapa hal yang perlu Anda siapkan:

1.  Aspose.PDF untuk .NET: Pastikan Anda telah menginstal pustaka Aspose.PDF. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/pdf/net/).
2. Visual Studio: Lingkungan pengembangan tempat Anda dapat menulis dan menguji kode Anda.
3. Pengetahuan Dasar C#: Keakraban dengan pemrograman C# akan membantu Anda memahami potongan kode dengan lebih baik.

## Paket Impor

Untuk memulai, Anda perlu mengimpor paket yang diperlukan ke dalam proyek C# Anda. Berikut cara melakukannya:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Langkah 1: Siapkan Direktori Dokumen Anda

Pertama, Anda perlu menentukan jalur ke direktori dokumen Anda. Di sinilah berkas PDF masukan Anda berada dan di mana berkas keluaran akan disimpan.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Inisialisasi Font Asli

Berikutnya, Anda akan mencoba dan menemukan font asli yang mungkin hilang. Dalam kasus ini, kami mencari "AgencyFB."

```csharp
Aspose.Pdf.Text.Font originalFont = null;
try
{
    originalFont = FontRepository.FindFont("AgencyFB");
}
catch (Exception)
{
    //Font tidak ada di mesin tujuan
    FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
```

Di sini, kami mencoba menemukan fon tersebut. Jika tidak ditemukan, kami akan menemukan pengecualian dan menggantinya dengan fon yang lebih umum, "Arial." Ini memastikan bahwa dokumen Anda tetap terlihat bagus meskipun fon aslinya tidak tersedia.

## Langkah 3: Muat Dokumen PDF

Sekarang, mari kita muat dokumen PDF yang ingin Anda proses. Anda perlu menentukan jalur berkas input.

```csharp
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");
```

 Pada langkah ini, kita membuat yang baru`FileInfo` objek untuk file keluaran dan memuat dokumen PDF masukan ke dalam yang baru`Document` obyek.

## Langkah 4: Konversi Dokumen PDF

Sebelum menyimpan dokumen, ada baiknya Anda mengonversinya ke format PDF tertentu. Dalam kasus ini, kami akan mengonversinya ke format PDF/A-1B, yang merupakan standar untuk pengarsipan dokumen elektronik jangka panjang.

```csharp
pdf.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
```

Baris ini mengonversi PDF dan mencatat semua kesalahan ke file XML tertentu. Jika ada masalah selama konversi, masalah tersebut akan dicatat dalam "log.xml."

## Langkah 5: Simpan Dokumen PDF yang Diperbarui

Akhirnya, saatnya menyimpan dokumen PDF yang diperbarui dengan font yang diganti.

```csharp
pdf.Save(fileNew.FullName);
```

Baris ini menyimpan PDF yang dimodifikasi ke jalur file keluaran yang ditentukan. Dan begitu saja, Anda telah berhasil mengganti font yang hilang dalam dokumen PDF Anda!

## Kesimpulan

Mengganti font yang hilang dalam dokumen PDF tidak harus menjadi tugas yang sulit. Dengan Aspose.PDF untuk .NET, Anda dapat dengan mudah mengelola penggantian font dan memastikan dokumen Anda terlihat sebagaimana mestinya. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat menjaga integritas file PDF Anda, bahkan saat font tertentu tidak tersedia. Jadi, lain kali Anda mengalami masalah font yang hilang, Anda akan tahu persis apa yang harus dilakukan!

## Pertanyaan yang Sering Diajukan

### Apa itu Aspose.PDF untuk .NET?
Aspose.PDF untuk .NET adalah pustaka hebat yang memungkinkan pengembang untuk membuat, memanipulasi, dan mengonversi dokumen PDF secara terprogram.

### Dapatkah saya menggunakan Aspose.PDF secara gratis?
 Ya, Aspose menawarkan versi uji coba gratis yang dapat Anda gunakan untuk mengevaluasi pustaka. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/).

### Apa yang harus saya lakukan jika font yang saya butuhkan tidak tersedia?
Anda dapat mengganti font yang hilang dengan font yang lebih umum menggunakan fitur substitusi font di Aspose.PDF.

### Apakah mungkin untuk mengonversi PDF ke format lain?
Tentu saja! Aspose.PDF mendukung konversi ke berbagai format, termasuk PDF/A, DOCX, dan banyak lagi.

### Di mana saya dapat menemukan dukungan untuk Aspose.PDF?
 Anda dapat menemukan dukungan dan mengajukan pertanyaan di forum Aspose[Di Sini](https://forum.aspose.com/c/pdf/10).