---
title: Atur Batas Dalam PDF Ke Tabel
linktitle: Atur Batas Dalam PDF Ke Tabel
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara mengatur batas dalam PDF ke tabel dengan Aspose.PDF untuk .NET.
type: docs
weight: 200
url: /id/net/programming-with-tables/set-border/
---
Dalam tutorial ini, kami akan memandu Anda langkah demi langkah untuk mengatur batas dalam tabel dokumen PDF menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber C# yang disediakan dan menunjukkan cara mengimplementasikannya.

## Langkah 1: Membuat Instansiasi objek Dokumen
Pertama, kita akan membuat instance objek Dokumen:

```csharp
Document doc = new Document();
```

## Langkah 2: Menambahkan halaman ke dokumen PDF
Selanjutnya, kami akan menambahkan halaman ke dokumen PDF:

```csharp
Page page = doc.Pages.Add();
```

## Langkah 3: Membuat objek BorderInfo
Sekarang kita akan membuat objek BorderInfo untuk menentukan batas tabel:

```csharp
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
```

## Langkah 4: Menentukan batas atas dan bawah
Kami akan menentukan bahwa batas atas dan bawah akan menjadi ganda:

```csharp
border.Top.IsDoubled = true;
border.Bottom.IsDoubled = true;
```

## Langkah 5: Membuat Instansiasi objek Tabel
Sekarang mari kita membuat instance objek Tabel:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Langkah 6: Menentukan lebar kolom
Kami akan menentukan lebar kolom tabel:

```csharp
table. ColumnWidths = "100";
```

## Langkah 7: Membuat Objek Baris
Kami akan membuat objek Row:

```csharp
Aspose.Pdf.Row row = table.Rows.Add();
```

## Langkah 8: Menambahkan sel ke baris
Selanjutnya, kita akan menambahkan sel ke baris:

```csharp
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
```

## Langkah 9: Mengatur batas sel
Kita akan mendefinisikan batas sel (batas ganda):

```csharp
cell. Border = border;
```

## Langkah 10: Menambahkan tabel ke halaman
Sekarang mari tambahkan tabel ke halaman dokumen:

```csharp
page.Paragraphs.Add(table);
```

## Langkah 11: Simpan dokumen PDF
Terakhir, kami akan menyimpan dokumen PDF:

```csharp
dataDir = dataDir + "TableBorderTest_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

### Contoh kode sumber untuk Set Border menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat instance objek Dokumen
Document doc = new Document();
// Tambahkan halaman ke dokumen PDF
Page page = doc.Pages.Add();
// Buat objek BorderInfo
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
//Tentukan bahwa Batas atas akan menjadi dua kali lipat
border.Top.IsDoubled = true;
// Tentukan bahwa batas bawah akan menjadi dua kali lipat
border.Bottom.IsDoubled = true;
// Buat instance objek Tabel
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Tentukan informasi lebar Kolom
table.ColumnWidths = "100";
// Buat objek Baris
Aspose.Pdf.Row row = table.Rows.Add();
// Tambahkan sel Tabel ke kumpulan baris sel
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
// Mengatur batas objek sel (batas ganda)
cell.Border = border;
// Tambahkan tabel ke kumpulan paragraf Halaman
page.Paragraphs.Add(table);
dataDir = dataDir + "TableBorderTest_out.pdf";
// Simpan dokumen PDF
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

## Kesimpulan
Selamat! Anda sekarang telah mempelajari cara mengatur batas dalam tabel dokumen PDF menggunakan Aspose.PDF untuk .NET. Panduan langkah demi langkah ini menunjukkan kepada Anda cara membuat dokumen, menambahkan halaman, mengonfigurasi batas tabel, dan menyimpan dokumen PDF. Sekarang Anda dapat menerapkan pengetahuan ini pada proyek Anda sendiri.

### FAQ

#### T: Dapatkah saya mengatur gaya batas yang berbeda (misalnya, putus-putus atau putus-putus) untuk batas atas dan bawah tabel?

 J: Ya, Anda dapat mengatur gaya batas yang berbeda untuk batas atas dan bawah tabel dengan memodifikasinya`border.Top.Style` Dan`border.Bottom.Style`properti dalam kode sumber C# yang disediakan. Aspose.PDF untuk .NET memungkinkan Anda memilih dari berbagai gaya batas, termasuk Solid, Dashed, Dotted, Double, dan banyak lagi.

#### Q: Bagaimana cara mengatur warna tepi tabel?

 A: Anda dapat mengatur warna batas tabel dengan memodifikasi`border.Color` properti dalam kode sumber C#. Cukup berikan warna yang diinginkan, seperti`Aspose.Pdf.Color.Red` atau representasi warna valid lainnya, untuk menyesuaikan warna batas.

#### T: Apakah mungkin untuk menerapkan batas pada masing-masing sel dalam tabel dengan pengaturan berbeda (misalnya, warna atau gaya batas berbeda)?

 J: Ya, Anda dapat menerapkan batas ke sel individual dalam tabel dengan pengaturan berbeda dengan mengonfigurasinya`cell.Border` properti untuk setiap sel secara individual. Ini memungkinkan Anda memiliki gaya dan warna batas sel tertentu berdasarkan kebutuhan Anda.

#### T: Dapatkah saya menghapus batas dari sisi tertentu pada tabel (misalnya batas kiri dan kanan)?

 J: Ya, Anda dapat menghapus batas dari sisi tertentu tabel dengan memodifikasi`border.Left`, `border.Right`, `border.Top` , Dan`border.Bottom`properti dalam kode sumber C#. Menyetel properti ini ke`null` akan menghapus batas dari sisi tabel yang sesuai.

#### T: Bagaimana cara menyesuaikan ketebalan tepian tabel?

 A: Anda dapat mengatur ketebalan tepian tabel dengan memodifikasi`border.Width` properti dalam kode sumber C#. Cukup atur lebar batas yang diinginkan (dalam poin) untuk mencapai ketebalan yang diinginkan.