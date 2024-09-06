---
title: Meja Sudut Bulat Dalam Dokumen PDF
linktitle: Meja Sudut Bulat Dalam Dokumen PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara membuat tabel sudut melengkung dalam dokumen PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 190
url: /id/net/programming-with-tables/rounded-corner-table/
---
Dalam tutorial ini, kami akan memandu Anda langkah demi langkah untuk membuat tabel sudut membulat dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber C# yang disediakan dan menunjukkan cara mengimplementasikannya.

## Langkah 1: Membuat tabel
Pertama, kita akan membuat tabel menggunakan kode berikut:

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Langkah 2: Pengaturan Gaya Sudut Bulat
Berikutnya, kita akan mengonfigurasi gaya sudut membulat untuk tabel:

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## Langkah 3: Pengaturan Batas Tabel
Untuk memberi batas sudut membulat pada tabel, kita perlu membuat objek BorderInfo dan mengonfigurasinya dengan parameter yang sesuai:

```csharp
// Buat objek GraphInfo untuk mengatur warna batas
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;

// Buat objek BorderInfo kosong
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);

// Atur radius batas bulat menjadi 15
bInfo.RoundedBorderRadius = 15;

// Terapkan informasi perbatasan ke tabel
tab1.Border = bInfo;
```

### Contoh kode sumber untuk Rounded Corner Table menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
// Buat objek BorderInfo kosong
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
// Tetapkan batas batas yang lebih bulat di mana radius bulatnya adalah 15
bInfo.RoundedBorderRadius = 15;
// Atur gaya sudut tabel menjadi Bulat.
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
// Mengatur informasi batas tabel
tab1.Border = bInfo;
```

## Kesimpulan
Selamat! Anda sekarang telah mempelajari cara membuat tabel sudut membulat dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Panduan langkah demi langkah ini menunjukkan kepada Anda cara mengatur gaya sudut membulat dan batas tabel. Sekarang Anda dapat menerapkan pengetahuan ini ke proyek Anda sendiri.

### FAQ untuk meja sudut bundar dalam dokumen PDF

#### T: Dapatkah saya menyesuaikan radius sudut melengkung pada meja?

A: Ya, Anda dapat menyesuaikan radius sudut membulat untuk tabel dengan mengubah nilai`bInfo.RoundedBorderRadius` properti dalam kode sumber C# yang disediakan. Cukup atur nilai radius yang diinginkan (dalam poin) untuk mendapatkan tampilan sudut membulat yang diinginkan.

#### T: Dapatkah saya menerapkan sudut membulat pada sel individual dalam tabel?

J: Tidak, gaya sudut membulat diterapkan ke seluruh tabel secara keseluruhan. Aspose.PDF untuk .NET saat ini tidak menyediakan dukungan bawaan untuk menerapkan sudut membulat ke sel-sel individual dalam tabel.

#### T: Bisakah saya mengubah warna batas sudut melengkung?

 A: Ya, Anda dapat mengubah warna batas sudut membulat dengan mengubah nilai`graph.Color` properti dalam kode sumber C#. Cukup berikan warna yang diinginkan, seperti`Aspose.Pdf.Color.Red` atau representasi warna valid lainnya.

#### T: Apakah mungkin untuk menerapkan gaya sudut yang berbeda (misalnya, persegi dan bulat) ke tabel yang berbeda dalam dokumen PDF yang sama?

A: Ya, Anda dapat menerapkan gaya sudut yang berbeda ke tabel yang berbeda dalam dokumen PDF yang sama. Anda dapat membuat beberapa tabel dan mengonfigurasi gaya sudutnya secara individual berdasarkan kebutuhan Anda.

#### T: Dapatkah saya menyesuaikan ketebalan pinggiran sudut melengkung?

 A: Ya, Anda dapat menyesuaikan ketebalan batas sudut membulat dengan memodifikasi`BorderInfo` properti objek dalam kode sumber C#. Misalnya, Anda dapat mengatur`bInfo.Width` properti untuk menyesuaikan ketebalan batas.