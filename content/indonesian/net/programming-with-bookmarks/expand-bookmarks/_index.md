---
title: Perluas Bookmark Dalam File PDF
linktitle: Perluas Bookmark Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Perluas bookmark dalam file PDF dengan mudah untuk meningkatkan navigasi dengan Aspose.PDF untuk .NET.
type: docs
weight: 50
url: /id/net/programming-with-bookmarks/expand-bookmarks/
---
Memperluas bookmark dalam file PDF akan menampilkan semua bookmark yang terbuka secara default. Dengan Aspose.PDF untuk .NET, Anda dapat dengan mudah memperluas bookmark dengan mengikuti kode sumber berikut:

## Langkah 1: Impor perpustakaan yang diperlukan

Sebelum memulai, Anda perlu mengimpor perpustakaan yang diperlukan untuk proyek C# Anda. Berikut adalah arahan impor yang diperlukan:

```csharp
using Aspose.Pdf;
```

## Langkah 2: Tetapkan jalur ke folder dokumen

 Pada langkah ini, Anda perlu menentukan jalur ke folder yang berisi file PDF yang ingin Anda perluas bookmarknya. Mengganti`"YOUR DOCUMENT DIRECTORY"`dalam kode berikut dengan jalur sebenarnya ke folder dokumen Anda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 3: Buka dokumen PDF

Sekarang kita akan membuka dokumen PDF yang bookmarknya ingin kita perluas menggunakan kode berikut:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Langkah 4: Atur Mode Tampilan Halaman

Pada langkah ini, kami akan mengatur mode tampilan halaman untuk menampilkan bookmark secara default. Kami menggunakan`PageMode` properti dari`doc` objek untuk mengatur mode halaman yang diinginkan. Ini kode yang sesuai:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

## Langkah 5: Jelajahi bookmark dan perluas

 Sekarang kita akan menelusuri setiap item bookmark dalam koleksi bookmark dokumen dan mengatur status terbuka setiap item`true` untuk memperluasnya secara default. Ini kode yang sesuai:

```csharp
foreach(OutlineItemCollection item in doc.Outlines)
{
     item. Open = true;
}
```

## Langkah 6: Simpan file yang diperbarui

 Terakhir, kami menyimpan file PDF yang diperbarui menggunakan`Save` metode`doc` obyek. Ini kode yang sesuai:

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

### Contoh kode sumber untuk Perluas Bookmark menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document doc = new Document(dataDir + "input.pdf");
// Atur mode tampilan halaman yaitu tampilkan thumbnail, layar penuh, tampilkan panel lampiran
doc.PageMode = PageMode.UseOutlines;
// Telusuri setiap item Ouline dalam kumpulan garis besar file PDF
foreach (OutlineItemCollection item in doc.Outlines)
{
	// Tetapkan status terbuka untuk item kerangka
	item.Open = true;
}
dataDir = dataDir + "ExpandBookmarks_out.pdf";
// Simpan keluaran
doc.Save(dataDir);
Console.WriteLine("\nBookmarks expanded successfully.\nFile saved at " + dataDir);
```

## Kesimpulan

Selamat! Anda sekarang memiliki panduan langkah demi langkah untuk mengembangkan bookmark dengan Aspose.PDF untuk .NET. Anda dapat menggunakan kode ini untuk menampilkan semua bookmark default di dokumen PDF Anda.

Pastikan untuk memeriksa dokumentasi resmi Aspose.PDF untuk informasi lebih lanjut tentang fitur manipulasi bookmark tingkat lanjut.

### FAQ untuk memperluas bookmark dalam file PDF

#### T: Apa yang dimaksud dengan bookmark dalam file PDF?

J: Penanda dalam file PDF adalah alat bantu navigasi yang memungkinkan pengguna melompat ke bagian atau halaman tertentu dalam dokumen dengan cepat. Mereka menyediakan cara mudah untuk mengakses berbagai bagian dokumen.

#### T: Mengapa saya ingin memperluas bookmark di file PDF?

J: Memperluas bookmark dapat meningkatkan pengalaman pengguna dengan menampilkan semua bookmark dalam keadaan diperluas secara default. Ini memberi pengguna gambaran yang jelas tentang struktur dokumen dan memungkinkan mereka menavigasi dengan mudah ke bagian yang berbeda.

#### T: Bagaimana cara mengimpor perpustakaan yang diperlukan untuk proyek C# saya?

J: Untuk mengimpor perpustakaan yang diperlukan untuk proyek C# Anda, gunakan perintah impor berikut:

```csharp
using Aspose.Pdf;
```

Arahan ini memungkinkan Anda untuk memanfaatkan kelas dan metode yang disediakan oleh Aspose.PDF untuk .NET.

#### T: Bagaimana cara menentukan jalur ke folder dokumen?

 A: Di kode sumber yang disediakan, ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke folder yang berisi file PDF yang ingin Anda kerjakan. Ini memastikan bahwa kode dapat menemukan file PDF target.

#### T: Bagaimana cara membuka dokumen PDF untuk memperluas bookmarknya?

A: Untuk membuka dokumen PDF untuk memperluas bookmark, gunakan kode berikut:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 Mengganti`"input.pdf"` dengan nama file sebenarnya.

#### T: Bagaimana cara mengatur mode tampilan halaman untuk menampilkan bookmark secara default?

J: Untuk mengatur mode tampilan halaman agar menampilkan bookmark secara default, gunakan`PageMode` properti dari`doc` obyek:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

#### T: Bagaimana cara memperluas semua bookmark di dokumen PDF?

 J: Untuk memperluas semua penanda, telusuri setiap item penanda dalam kumpulan kerangka dokumen dan atur`Open` properti ke`true`:

```csharp
foreach (OutlineItemCollection item in doc.Outlines)
{
    item.Open = true;
}
```

#### T: Apa yang terjadi jika sebuah bookmark memiliki bookmark anak bertumpuk?

J: Jika suatu penanda mempunyai penanda anak yang bertumpuk, memperluas penanda induk juga akan memperluas penanda anak, sehingga memberikan tampilan komprehensif tentang struktur dokumen.

#### T: Bagaimana cara menyimpan file PDF yang diperbarui setelah memperluas bookmark?

A: Untuk menyimpan file PDF yang diperbarui setelah memperluas bookmark, gunakan kode berikut:

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

#### T: Dapatkah saya menyesuaikan tampilan bookmark yang diperluas?

J: Meskipun tutorial ini berfokus pada memperluas bookmark secara default, Anda dapat menyesuaikan tampilan bookmark menggunakan fitur dan properti Aspose.PDF lainnya.