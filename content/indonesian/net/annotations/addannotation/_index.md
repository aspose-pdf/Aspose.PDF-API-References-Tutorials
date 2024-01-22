---
title: Tambahkan Anotasi PDF
linktitle: Tambahkan Anotasi
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menambahkan anotasi teks PDF dengan Aspose.PDF untuk .NET menggunakan kode sumber C# ini. Sesuaikan anotasi Anda dengan detail dan ikon spesifik.
type: docs
weight: 10
url: /id/net/annotations/addannotation/
---
Menambahkan anotasi ke dokumen PDF adalah fitur canggih yang dapat meningkatkan proses kolaborasi dan peninjauan. Aspose.PDF untuk .NET memudahkan menambahkan anotasi secara terprogram ke dokumen PDF menggunakan C#. Dalam panduan ini, kami akan menjelaskan langkah demi langkah cara menggunakan Aspose.PDF untuk .NET guna menambahkan anotasi ke dokumen PDF.

## Langkah 1: Buat Proyek Baru dan Instal Aspose.PDF untuk .NET

Sebelum kita mulai menulis kode untuk menambahkan anotasi, kita perlu membuat proyek baru dan menginstal Aspose.PDF untuk .NET. Untuk menginstal Aspose.PDF untuk .NET, ikuti langkah-langkah berikut:

1. Buka Visual Studio dan buat proyek C# baru.
2. Klik kanan pada proyek di Solution Explorer dan pilih "Kelola Paket NuGet".
3. Cari "Aspose.PDF" dan pilih "Instal".

Setelah instalasi selesai, kita dapat mulai menulis kodenya.

## Langkah 2: Buka Dokumen PDF

Langkah pertama dalam menambahkan anotasi adalah membuka dokumen PDF. Kita dapat menggunakan kode berikut untuk membuka dokumen:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");
```

Dalam kode ini, kita menentukan jalur ke dokumen PDF yang ingin kita buka. Pastikan untuk mengganti "DIREKTORI DATA ANDA" dengan jalur sebenarnya ke direktori data Anda.

## Langkah 3: Buat Anotasi

 Untuk menambahkan anotasi, kita perlu membuat instance baru dari`TextAnnotation` kelas. Kita dapat menggunakan kode berikut untuk membuat anotasi teks baru:

```csharp
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;
```

Dalam kode ini, kami membuat anotasi teks baru di halaman kedua dokumen PDF. Kami juga mengatur properti judul, subjek, status, konten, buka, dan ikon anotasi.

## Langkah 4: Sesuaikan Anotasi

 Kita dapat menyesuaikan tampilan anotasi menggunakan`Border` kelas. Kita dapat menggunakan kode berikut untuk menyesuaikan batas anotasi:

```csharp
Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);
```

 Dalam kode ini, kami membuat yang baru`Border`objek dan atur properti lebar dan tanda hubungnya. Kami kemudian mengatur`Border` properti anotasi ke yang baru`Border` obyek. Akhirnya, kami mengatur`Rect` properti anotasi untuk menentukan posisi dan ukurannya.

## Langkah 5: Tambahkan Anotasi ke Dokumen PDF

Setelah kami membuat dan menyesuaikan anotasi, kami perlu menambahkannya ke dokumen PDF. Kita dapat menggunakan kode berikut untuk menambahkan anotasi ke dokumen PDF:

```csharp
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

Dalam kode ini, kami menambahkan anotasi ke kumpulan anotasi halaman kedua dokumen PDF.

## Langkah 6: Simpan File Keluaran

Terakhir, kita perlu menyimpan dokumen PDF dengan anotasi tambahan. Kita dapat menggunakan kode berikut untuk menyimpan file output:

```csharp
dataDir = dataDir + "AddAnnotation_out.pdf";
pdfDocument.Save(dataDir);
```
### Contoh kode sumber untuk Menambahkan Anotasi menggunakan Aspose.PDF untuk .NET


```csharp   
 // Jalur ke direktori dokumen.
string dataDir = "YOUR DATA DIRECTORY";

// Buka dokumen
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");

// Buat anotasi
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;

Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);

// Tambahkan anotasi di kumpulan anotasi halaman
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddAnnotation_out.pdf";
// Simpan file keluaran
pdfDocument.Save(dataDir);
```
Kode ini menunjukkan cara menambahkan anotasi teks dengan judul, subjek, status, konten, dan ikon tertentu ke halaman PDF menggunakan Aspose.PDF untuk .NET. Anda dapat mengubah kode ini sesuai dengan kebutuhan Anda untuk menambahkan anotasi ke dokumen PDF Anda. Ingatlah untuk mengganti DIREKTORI DATA ANDA dengan jalur direktori sebenarnya tempat file PDF Anda berada dan tempat Anda ingin menyimpan file keluaran.

## Kesimpulan

Menambahkan anotasi ke dokumen PDF menggunakan Aspose.PDF untuk .NET menawarkan alat yang berharga untuk meningkatkan kolaborasi dokumen dan proses peninjauan. Dengan mengikuti panduan langkah demi langkah yang disediakan dalam artikel ini, pengembang dapat dengan lancar mengintegrasikan kemampuan anotasi ke dalam aplikasi C# mereka.

### FAQ

#### T: Jenis anotasi apa yang dapat ditambahkan menggunakan Aspose.PDF untuk .NET?

J: Aspose.PDF untuk .NET mendukung berbagai jenis anotasi, termasuk anotasi teks, stempel, tautan, bentuk, dan banyak lagi. Pengembang dapat menyesuaikan tampilan dan properti anotasi ini agar sesuai dengan kebutuhan spesifik mereka.

#### T: Dapatkah saya menambahkan anotasi ke halaman tertentu dalam dokumen PDF multi-halaman?

J: Ya, Aspose.PDF untuk .NET memungkinkan Anda menentukan halaman tempat Anda ingin menambahkan anotasi. Anda dapat memilih halaman tertentu atau menambahkan anotasi ke beberapa halaman sesuai kebutuhan.

#### T: Bagaimana cara menyesuaikan tampilan anotasi?

J: Anotasi dapat dikustomisasi menggunakan properti seperti lebar tepi, warna, gaya tanda hubung, gaya teks, dan lainnya. Aspose.PDF untuk .NET menyediakan serangkaian opsi untuk menyesuaikan tampilan anotasi.

#### T: Apakah mungkin menambahkan hyperlink sebagai anotasi menggunakan Aspose.PDF untuk .NET?

J: Ya, Anda dapat menambahkan hyperlink sebagai anotasi ke dokumen PDF menggunakan Aspose.PDF untuk .NET. Anotasi hyperlink dapat digunakan untuk menautkan ke URL eksternal atau lokasi tertentu dalam dokumen yang sama.

#### T: Bisakah anotasi ditambahkan ke dokumen PDF yang sudah ada tanpa mengubah konten aslinya?

J: Ya, Aspose.PDF untuk .NET menambahkan anotasi sebagai elemen tambahan tanpa mengubah konten asli dokumen PDF. Konten PDF asli tetap utuh.