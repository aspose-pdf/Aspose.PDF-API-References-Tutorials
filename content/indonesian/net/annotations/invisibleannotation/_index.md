---
title: Anotasi Tak Terlihat Dalam File PDF
linktitle: Anotasi Tak Terlihat Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara anotasi tak terlihat dalam file PDF menggunakan kode sumber C# dengan Aspose.PDF untuk .NET. Panduan langkah demi langkah.
type: docs
weight: 100
url: /id/net/annotations/invisibleannotation/
---
Anotasi dalam file PDF adalah fitur canggih yang memungkinkan Anda menambahkan informasi atau catatan tambahan ke dokumen tanpa mengubah konten sebenarnya. Mereka dapat digunakan untuk menyorot teks, menarik perhatian ke area tertentu dari dokumen, atau menambahkan komentar atau umpan balik.

Ada berbagai jenis anotasi yang dapat Anda gunakan dalam dokumen PDF, termasuk:

- Anotasi Teks
- Anotasi Tautan
- Anotasi Stempel
- Anotasi Suara
- Anotasi Lampiran File
- dan masih banyak lagi

## Langkah 1: Membuat Anotasi Tak Terlihat dalam Dokumen PDF Menggunakan Aspose.PDF untuk .NET

 Untuk membuat anotasi tak terlihat dalam dokumen PDF menggunakan Aspose.PDF untuk .NET, pertama-tama kita perlu membuat a`FreeTextAnnotation` objek dan tentukan lokasi dan ukuran anotasi.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buka dokumen
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
```

 Pada kode di atas, kita membuat a`FreeTextAnnotation`objek dan tentukan lokasi anotasi di halaman 2 dokumen PDF. Kami juga menentukan jenis font, ukuran, dan warna untuk teks yang akan ditampilkan dalam anotasi.

## Langkah 2: Menambahkan Karakteristik ke Anotasi Tak Terlihat

Selanjutnya, kita bisa menambahkan beberapa karakteristik pada anotasi, seperti warna tepi, warna latar belakang, atau opacity.

```csharp
annotation.Characteristics.Border = System.Drawing.Color.Red;
```

Pada kode di atas, kita mengatur warna batas anotasi menjadi merah.

## Langkah 3: Mengatur Bendera Anotasi

Setelah kita membuat anotasi dan mengatur karakteristiknya, kita dapat menentukan tanda anotasi. Dalam tutorial ini, kami ingin anotasi dapat dicetak, namun tidak dapat dilihat.

```csharp
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);
```

## Langkah 4: Menyimpan Dokumen PDF yang Dimodifikasi

Terakhir, kita dapat menyimpan dokumen PDF yang dimodifikasi dengan anotasi baru yang tidak terlihat.

```csharp
dataDir = dataDir + "InvisibleAnnotation_out.pdf";
doc.Save(dataDir);
```

## Contoh Kode Sumber Cara Anotasi Tak Terlihat menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buka dokumen
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
annotation.Contents = "ABCDEFG";
annotation.Characteristics.Border = System.Drawing.Color.Red;
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);

dataDir = dataDir + "InvisibleAnnotation_out.pdf";
// Simpan file keluaran
doc.Save(dataDir);
// ExEnd: Anotasi Tak Terlihat
Console.WriteLine("\nAnnotation nvisible successfully.\nFile saved at " + dataDir);
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara membuat anotasi tak terlihat dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Anotasi tak terlihat adalah fitur yang berguna saat Anda ingin menambahkan informasi atau catatan tambahan ke dokumen tanpa menampilkannya kepada pembaca. Dengan mengikuti panduan langkah demi langkah dan menggunakan kode sumber C# yang disediakan, pengembang dapat dengan mudah membuat dan menyesuaikan anotasi tak terlihat dalam dokumen PDF mereka. Aspose.PDF untuk .NET menyediakan seperangkat alat komprehensif untuk bekerja dengan anotasi, memungkinkan Anda meningkatkan interaktivitas dan kegunaan file PDF Anda.

### FAQ

#### T: Apa yang dimaksud dengan anotasi tak terlihat dalam dokumen PDF?

J: Anotasi yang tidak terlihat dalam dokumen PDF adalah anotasi yang tidak terlihat pada halaman tetapi berisi informasi atau catatan tambahan. Ini memungkinkan Anda menambahkan komentar atau umpan balik tanpa menampilkannya kepada pembaca.

#### T: Jenis karakteristik apa yang dapat ditambahkan ke anotasi tak kasat mata?

J: Berbagai karakteristik dapat ditambahkan ke anotasi tak terlihat, seperti warna tepi, warna latar belakang, opasitas, jenis font, ukuran, dan warna teks yang akan ditampilkan.

#### T: Dapatkah saya menyetel tanda anotasi yang berbeda untuk anotasi yang tidak terlihat?

J: Ya, Anda dapat menyetel tanda anotasi yang berbeda untuk anotasi yang tidak terlihat, bergantung pada kebutuhan Anda. Misalnya, Anda dapat membuat anotasi dapat dicetak namun tidak dapat dilihat.

#### T: Bagaimana cara menambahkan anotasi tak terlihat ke halaman tertentu pada dokumen PDF?

 J: Untuk menambahkan anotasi tak kasat mata ke halaman tertentu pada dokumen PDF, Anda perlu membuat a`FreeTextAnnotation` objek dan tentukan lokasi dan ukuran anotasi pada halaman itu.

#### T: Bisakah saya mengubah karakteristik anotasi tak kasat mata yang sudah ada di file PDF?

J: Ya, Anda dapat mengubah karakteristik anotasi tak kasat mata yang ada dalam file PDF menggunakan Aspose.PDF untuk .NET. Anda dapat mengubah jenis font, ukuran, warna, warna tepi, warna latar belakang, opasitas, dan properti anotasi lainnya.