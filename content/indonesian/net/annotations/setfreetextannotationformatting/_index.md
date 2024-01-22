---
title: Atur Pemformatan Anotasi Teks Gratis
linktitle: Atur Pemformatan Anotasi Teks Gratis
second_title: Aspose.PDF untuk Referensi .NET API
description: Artikel ini memberikan panduan langkah demi langkah tentang cara membuat anotasi teks bebas dan menentukan kontennya menggunakan Aspose.PDF untuk .NET
type: docs
weight: 140
url: /id/net/annotations/setfreetextannotationformatting/
---
Aspose.PDF untuk .NET adalah API manipulasi dokumen PDF yang kuat dan mudah digunakan yang memungkinkan Anda bekerja dengan file PDF secara terprogram di aplikasi .NET Anda. Salah satu fitur yang disediakan Aspose.PDF untuk .NET adalah kemampuan untuk mengatur format anotasi teks bebas dalam dokumen PDF. Pada artikel ini, kami akan memandu Anda melalui proses langkah demi langkah dalam mengatur pemformatan anotasi teks gratis menggunakan Aspose.PDF untuk .NET.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

- Microsoft Visual Studio 2010 atau lebih baru
- Aspose.PDF untuk .NET
- Pengetahuan dasar C#



## Langkah 1: Buat aplikasi konsol C# baru

Pertama, buat aplikasi konsol C# baru di Microsoft Visual Studio. Untuk membuat aplikasi konsol baru, pilih "File" > "Baru" > "Proyek" > "Visual C#" > "Aplikasi Konsol" dari menu utama.

## Langkah 2: Tambahkan referensi ke Aspose.PDF untuk .NET

Selanjutnya, tambahkan referensi ke Aspose.PDF untuk .NET di proyek Anda. Untuk melakukannya, klik kanan proyek Anda di panel "Solution Explorer", pilih "Tambah" > "Referensi", lalu telusuri ke lokasi tempat Anda menyimpan file Aspose.PDF untuk .NET DLL. Pilih file DLL dan klik "OK" untuk menambahkan referensi ke proyek Anda.

## Langkah 3: Siapkan lingkungan

Setelah menambahkan referensi ke Aspose.PDF untuk .NET, Anda perlu menyiapkan lingkungan. Untuk melakukan ini, buat variabel string baru bernama "dataDir" dan setel ke jalur direktori tempat dokumen PDF Anda berada. Ganti "DIREKTORI DOKUMEN ANDA" pada kode di bawah ini dengan jalur sebenarnya dari direktori dokumen Anda:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 4: Buka dokumen PDF

Setelah Anda mengatur lingkungan, Anda dapat membuka dokumen PDF menggunakan kode berikut:

```csharp
// Buka dokumen
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");
```

Ganti "SetFreeTextAnnotationFormatting.pdf" dengan nama sebenarnya dokumen PDF Anda.

## Langkah 5: Atur tampilan default

Untuk mengatur tampilan default anotasi teks bebas, Anda perlu membuat instance objek DefaultAppearance dengan font, ukuran font, dan warna yang diinginkan. Dalam tutorial ini, kita mengatur font menjadi "Arial", ukuran font menjadi 28, dan warna menjadi merah.

```csharp
// Buat instance objek DefaultAppearance
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
```

## Langkah 6: Buat anotasi teks bebas

Sekarang Anda telah menyiapkan tampilan default, Anda dapat membuat anotasi teks bebas menggunakan kode berikut:

```csharp
// Buat anotasi
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
```

Kode di atas membuat anotasi teks bebas baru di halaman kedua dokumen PDF. Anotasi akan ditempatkan pada (200, 400) dan akan memiliki lebar 400 dan tinggi 600.

## Langkah 7: Tentukan isi anotasi

Setelah membuat anotasi teks bebas, Anda dapat menentukan isi anotasi menggunakan kode berikut:

```csharp
// Tentukan isi anotasi
freetext.Contents = "Free Text
```

### Contoh kode sumber untuk Mengatur Pemformatan Anotasi Teks Gratis menggunakan Aspose.PDF untuk .NET
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buka dokumen
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");

// Buat instance objek DefaultAppearance
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
// Buat anotasi
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
// Tentukan isi anotasi
freetext.Contents = "Free Text";
// Tambahkan anotasi ke kumpulan anotasi halaman
pdfDocument.Pages[1].Annotations.Add(freetext);
dataDir = dataDir + "SetFreeTextAnnotationFormatting_out.pdf";
// Simpan dokumen yang diperbarui
pdfDocument.Save(dataDir);            
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara mengatur pemformatan anotasi teks bebas dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Pustaka ini menyediakan cara yang mudah dan efisien untuk bekerja dengan dokumen PDF secara terprogram, memungkinkan pengembang membuat dan menyesuaikan berbagai jenis anotasi, termasuk anotasi teks bebas. Dengan mengikuti panduan langkah demi langkah dan menggunakan kode sumber C# yang disediakan, Anda dapat dengan mudah mengatur lingkungan, membuka dokumen PDF, dan membuat anotasi teks gratis dengan format khusus. Aspose.PDF untuk .NET adalah API yang kuat dan andal yang menyederhanakan tugas manipulasi dokumen PDF, menjadikannya alat yang berharga bagi pengembang .NET yang bekerja dengan file PDF.

### FAQ

#### T: Apa yang dimaksud dengan anotasi teks bebas dalam dokumen PDF?

J: Anotasi teks bebas dalam dokumen PDF adalah jenis anotasi yang memungkinkan Anda menambahkan teks ke dokumen tanpa terikat pada lokasi atau struktur tertentu. Biasanya digunakan untuk memberikan komentar, catatan, atau informasi tambahan lainnya pada dokumen.

#### T: Dapatkah saya menyesuaikan tampilan anotasi teks bebas menggunakan Aspose.PDF untuk .NET?

J: Ya, Anda dapat menyesuaikan berbagai properti anotasi teks bebas, seperti font, ukuran font, warna, posisi, dan lainnya.

#### T: Bagaimana cara menentukan konten anotasi teks bebas?

 A: Untuk menentukan isi anotasi teks bebas, Anda dapat mengatur`Contents` properti dari`FreeTextAnnotation` objek pada teks yang diinginkan.

#### T: Dapatkah saya menambahkan beberapa anotasi teks bebas ke dokumen PDF menggunakan Aspose.PDF untuk .NET?

 J: Ya, Anda dapat membuat beberapa anotasi teks bebas dalam dokumen PDF dengan membuat beberapa contoh`FreeTextAnnotation`objek dan menambahkannya ke halaman atau lokasi berbeda dalam dokumen.