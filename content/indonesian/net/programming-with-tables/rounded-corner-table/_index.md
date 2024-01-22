---
title: Meja Sudut Bulat Dalam Dokumen PDF
linktitle: Meja Sudut Bulat Dalam Dokumen PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara membuat tabel sudut membulat dalam dokumen PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 190
url: /id/net/programming-with-tables/rounded-corner-table/
---
Dalam tutorial ini, kami akan memandu Anda langkah demi langkah membuat tabel sudut membulat di dokumen PDF menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber C# yang disediakan dan menunjukkan cara mengimplementasikannya.

## Langkah 1: Membuat tabel
Pertama, kita akan membuat tabelnya dengan menggunakan kode berikut:

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Langkah 2: Pengaturan Gaya Sudut Bulat
Selanjutnya, kita akan mengonfigurasi gaya sudut membulat untuk tabel:

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## Langkah 3: Pengaturan Batas Tabel
Untuk memberikan batas sudut membulat pada tabel, kita perlu membuat objek BorderInfo dan mengonfigurasinya dengan parameter yang sesuai:

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

### Contoh kode sumber Rounded Corner Table menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
// Buat objek BorderInfo kosong
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
// Atur batas menjadi batas bulat dengan radius putaran 15
bInfo.RoundedBorderRadius = 15;
// Atur gaya Sudut meja menjadi Bulat.
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
// Atur informasi batas tabel
tab1.Border = bInfo;
```

## Kesimpulan
Selamat! Anda sekarang telah mempelajari cara membuat tabel sudut membulat dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Panduan langkah demi langkah ini menunjukkan kepada Anda cara mengatur gaya sudut membulat dan batas tabel. Sekarang Anda dapat menerapkan pengetahuan ini pada proyek Anda sendiri.

### FAQ untuk meja sudut membulat dalam dokumen PDF

#### T: Dapatkah saya menyesuaikan radius sudut membulat untuk meja?

J: Ya, Anda dapat menyesuaikan radius sudut membulat untuk tabel dengan mengubah nilainya`bInfo.RoundedBorderRadius` properti dalam kode sumber C# yang disediakan. Cukup atur nilai radius yang diinginkan (dalam poin) untuk mendapatkan tampilan sudut membulat yang diinginkan.

#### T: Bisakah saya menerapkan sudut membulat ke masing-masing sel dalam tabel?

A: Tidak, gaya sudut membulat diterapkan ke seluruh tabel secara keseluruhan. Aspose.PDF untuk .NET saat ini tidak menyediakan dukungan bawaan untuk menerapkan sudut membulat ke sel individual dalam tabel.

#### T: Dapatkah saya mengubah warna batas sudut membulat?

 J: Ya, Anda dapat mengubah warna batas sudut membulat dengan mengubah nilai`graph.Color` properti dalam kode sumber C#. Cukup berikan warna yang diinginkan, seperti`Aspose.Pdf.Color.Red` atau representasi warna valid lainnya.

#### T: Apakah mungkin untuk menerapkan gaya sudut yang berbeda (misalnya persegi dan bulat) ke tabel berbeda dalam dokumen PDF yang sama?

J: Ya, dimungkinkan untuk menerapkan gaya sudut berbeda ke tabel berbeda dalam dokumen PDF yang sama. Anda dapat membuat beberapa tabel dan mengonfigurasi gaya sudutnya satu per satu berdasarkan kebutuhan Anda.

#### T: Dapatkah saya menyesuaikan ketebalan tepi sudut membulat?

 J: Ya, Anda dapat menyesuaikan ketebalan batas sudut membulat dengan memodifikasi`BorderInfo` properti objek dalam kode sumber C#. Misalnya, Anda dapat mengatur`bInfo.Width` properti untuk menyesuaikan ketebalan perbatasan.