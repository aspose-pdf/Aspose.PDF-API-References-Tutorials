---
title: Ekstrak Info Tanda Tangan
linktitle: Ekstrak Info Tanda Tangan
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mengekstrak tanda tangan digital dan informasi sertifikat dari dokumen PDF menggunakan Aspose.PDF untuk .NET. Panduan langkah demi langkah lengkap untuk pengembang C#.
type: docs
weight: 80
url: /id/net/programming-with-security-and-signatures/extract-signature-info/
---
## Perkenalan

Di dunia digital saat ini, memastikan keamanan dan integritas dokumen sangatlah penting. Salah satu metode umum yang digunakan untuk mengamankan PDF adalah dengan menambahkan tanda tangan digital. Namun, mengambil dan memverifikasi detail tanda tangan terkadang bisa menjadi tantangan, terutama saat Anda berurusan dengan berbagai sertifikat. Dalam panduan ini, kami akan memandu Anda melalui proses mengekstrak informasi tanda tangan dari dokumen PDF menggunakan Aspose.PDF for .NET, sehingga memudahkan tugas tersebut. Anda akan mempelajari cara mengakses kolom tanda tangan, mengekstrak informasi sertifikat, dan menyimpannya ke dalam file.

## Prasyarat

Sebelum kita mulai, mari pastikan Anda telah menyiapkan segalanya untuk memulai.

-  Aspose.PDF untuk Pustaka .NET: Jika Anda belum memilikinya, Anda dapat mengunduhnya dari[Halaman unduhan Aspose.PDF untuk .NET](https://releases.aspose.com/pdf/net/). 
- Lingkungan Pengembangan .NET: Anda memerlukan IDE seperti Visual Studio.
- Pengetahuan Dasar C#: Keakraban dengan C# berguna untuk memahami potongan kode dalam tutorial ini.
- Dokumen PDF dengan Tanda Tangan Digital: Untuk tujuan pengujian, pastikan Anda memiliki file PDF yang berisi setidaknya satu tanda tangan digital.

## Mengimpor Ruang Nama yang Diperlukan

Sebelum masuk ke kode, penting untuk mengimpor namespace yang diperlukan. Namespace ini akan memungkinkan Anda mengakses fungsionalitas Aspose.PDF dan bekerja dengan dokumen PDF.

```csharp
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf;
using System;
```

Sekarang setelah Anda menyiapkan hal-hal penting, mari beralih ke proses sebenarnya untuk mengekstrak info tanda tangan dari PDF.

## Langkah 1: Menyiapkan Direktori Dokumen

 Sebelum mengerjakan dokumen PDF, Anda perlu menentukan lokasi file yang akan Anda gunakan. Anda dapat mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya dari direktori tempat PDF Anda disimpan.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

Di sini, kami tentukan direktori yang berisi file PDF dan nama file itu sendiri. Pastikan file tersebut ada di direktori tersebut!

## Langkah 2: Memuat Dokumen PDF

 Sekarang setelah Anda menyiapkan direktori Anda, langkah selanjutnya adalah memuat dokumen PDF menggunakan`Document` kelas dari Aspose.PDF.

```csharp
using (Document pdfDocument = new Document(input))
{
    // Proses PDF di sini.
}
```

 Baris kode ini menginisialisasi`Document`objek yang mewakili file PDF.`using` pernyataan memastikan bahwa sumber daya dibersihkan setelah dokumen diproses.

## Langkah 3: Mengakses Bidang Formulir

Pada langkah ini, kita akan mengulang semua kolom formulir dalam dokumen PDF. Karena tanda tangan biasanya disimpan sebagai kolom formulir, langkah ini akan membantu kita mengidentifikasi kolom tanda tangan.

```csharp
foreach (Field field in pdfDocument.Form)
{
    // Identifikasi bidang tanda tangan di sini.
}
```

 Dengan mengulangi melalui`Form` milik`Document` objek, kita dapat memeriksa setiap bidang formulir untuk memeriksa apakah itu bidang tanda tangan.

## Langkah 4: Mengidentifikasi Bidang Tanda Tangan

 Setelah Anda mengakses kolom formulir, langkah selanjutnya adalah mengidentifikasi kolom mana yang merupakan kolom tanda tangan. Kita dapat melakukannya dengan mentransmisikan setiap kolom ke`SignatureField` obyek.

```csharp
SignatureField sf = field as SignatureField;
if (sf != null)
{
    // Ekstrak info tanda tangan.
}
```

 Di sini, kami menggunakan`as` kata kunci untuk mencoba mentransmisikan setiap bidang formulir ke`SignatureField`Jika pengecoran berhasil, kita tahu bahwa bidang tersebut adalah tanda tangan.

## Langkah 5: Mengekstrak Sertifikat

Setelah Anda mengidentifikasi bidang tanda tangan, tugas selanjutnya adalah mengekstrak sertifikat dari tanda tangan tersebut. Sertifikat berisi informasi penting tentang penanda tangan dan validitas tanda tangan.

```csharp
Stream cerStream = sf.ExtractCertificate();
```

 Itu`ExtractCertificate` metode mengembalikan`Stream` objek yang berisi data sertifikat. Aliran ini dapat digunakan untuk menyimpan sertifikat untuk analisis atau penyimpanan lebih lanjut.

## Langkah 6: Menyimpan Sertifikat ke File

 Setelah Anda mengekstrak sertifikat, langkah terakhir adalah menyimpannya ke dalam sebuah mengajukan. Dalam kasus ini, kami akan menyimpan sertifikat sebagai`.cer` file.

```csharp
if (cerStream != null)
{
    using (cerStream)
    {
        byte[] bytes = new byte[cerStream.Length];
        using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
        {
            cerStream.Read(bytes, 0, bytes.Length);
            fs.Write(bytes, 0, bytes.Length);
        }
    }
}
```

Dalam blok kode ini, kita:

1. Periksa apakah aliran sertifikat tidak null.
2. Membaca data sertifikat ke dalam array byte.
3.  Tuliskan array byte ke`.cer` file dalam direktori dokumen.

## Kesimpulan

Mengekstrak tanda tangan digital dan informasi sertifikat terkait dari dokumen PDF menggunakan Aspose.PDF untuk .NET cukup mudah jika dipecah menjadi beberapa langkah sederhana. Baik Anda mengaudit dokumen, memverifikasi tanda tangan, atau sekadar menyimpan sertifikat untuk diamankan, tutorial ini membekali Anda dengan pengetahuan untuk menyelesaikannya secara efisien. Ingat, mengamankan dan memverifikasi dokumen sangat penting di dunia digital saat ini, dan menggunakan alat seperti Aspose.PDF untuk .NET membuatnya jauh lebih mudah untuk ditangani.

## Pertanyaan yang Sering Diajukan

### Bisakah saya mengekstrak beberapa tanda tangan dari PDF menggunakan Aspose.PDF untuk .NET?
Ya, kode tersebut berulang melalui semua bidang formulir dalam dokumen, yang memungkinkan Anda mengekstrak beberapa tanda tangan jika ada.

### Apa yang terjadi jika tidak ditemukan tanda tangan dalam PDF?
Jika tidak ada kolom tanda tangan, kode akan melewatinya begitu saja tanpa menimbulkan kesalahan.

### Dapatkah saya menggunakan pendekatan ini untuk memverifikasi keabsahan tanda tangan?
Meskipun Anda dapat mengekstrak sertifikat, memverifikasi keabsahan tanda tangan memerlukan langkah-langkah tambahan, seperti memeriksa rantai kepercayaan sertifikat.

### Apakah mungkin untuk mengekstrak data bidang formulir lain menggunakan Aspose.PDF untuk .NET?
Ya, Aspose.PDF memungkinkan Anda mengakses dan memanipulasi berbagai jenis bidang formulir dalam PDF, bukan hanya bidang tanda tangan.

### Bagaimana saya dapat melihat rincian sertifikat yang diekstrak?
 Setelah sertifikat disimpan sebagai`.cer` file, Anda dapat membukanya menggunakan penampil sertifikat apa pun atau mengimpornya ke penyimpanan sertifikat sistem untuk pemeriksaan lebih lanjut.