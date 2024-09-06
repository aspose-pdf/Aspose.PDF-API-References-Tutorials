---
title: Ambil Bidang Formulir Dalam Urutan Tab
linktitle: Ambil Bidang Formulir Dalam Urutan Tab
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mengambil bidang formulir dalam urutan tab menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 240
url: /id/net/programming-with-forms/retrieve-form-field-in-tab-order/
---
Saat bekerja dengan dokumen PDF di C# menggunakan Aspose.PDF untuk .NET, Anda mungkin menemukan skenario saat Anda perlu mengambil kolom formulir dalam urutan tab tertentu. Ini dapat berguna saat Anda ingin melakukan operasi pada kolom formulir berdasarkan urutan tab. Dalam tutorial ini, kami akan memandu Anda langkah demi langkah tentang cara mengambil kolom formulir dalam urutan tab menggunakan Aspose.PDF untuk .NET.

## Persyaratan

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

- Visual Studio terinstal di sistem Anda
- Pustaka Aspose.PDF untuk .NET terinstal

Sekarang, mari selami langkah-langkah untuk mengambil kolom formulir dalam urutan tab.

## Langkah 1: Mengatur Direktori Dokumen

 Untuk memulai, Anda perlu mengatur direktori dokumen tempat dokumen PDF Anda berada. Anda dapat melakukannya dengan menentukan jalur ke direktori di`dataDir` variabel.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 2: Memuat Dokumen PDF

 Pada langkah ini, kita akan memuat dokumen PDF menggunakan Aspose.PDF untuk .NET.`Document` kelas menyediakan kemampuan untuk memuat dan memanipulasi dokumen PDF.

```csharp
Document doc = new Document(dataDir + "Test2.pdf");
```

 Di Sini,`"Test2.pdf"`adalah nama dokumen PDF yang ingin Anda muat. Pastikan dokumen tersebut ada di direktori dokumen yang ditentukan.

## Langkah 3: Mengambil Bidang Formulir dalam Urutan Tab

 Untuk mengambil bidang formulir dalam urutan tab, kita perlu mengakses`FieldsInTabOrder` milik`Page` class. Properti ini mengembalikan daftar kolom formulir yang diurutkan berdasarkan urutan tab.

```csharp
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
     s += field. PartialName;
}
```

Pada potongan kode di atas, kami mengambil bidang formulir dari halaman kedua (`doc.Pages[1]` ) dan mengulangi setiap bidang untuk menggabungkan nama parsial mereka ke dalam`s` variabel. Anda dapat mengubah potongan kode ini berdasarkan kebutuhan spesifik Anda.

## Langkah 4: Mengubah Urutan Tab

 Jika Anda ingin mengubah urutan tab bidang formulir, Anda dapat melakukannya dengan mengakses`TabOrder` properti setiap bidang dan menetapkan nilai urutan tab baru. Berikut contohnya:

```csharp
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
```

Dalam potongan kode di atas, kami menetapkan nilai pesanan tab baru ke tiga bidang formulir (`doc.Form[3]`, `doc.Form[1]` , Dan`doc.Form[2]`). Sesuaikan indeks bidang dan nilai urutan tab sesuai dengan kebutuhan spesifik Anda.

## Langkah 5: Menyimpan Dokumen yang Dimodifikasi

 Setelah mengubah urutan tab bidang formulir, Anda perlu menyimpan dokumen yang dimodifikasi. Anda dapat melakukannya dengan menggunakan`Save` metode dari`Document` kelas.

```csharp
doc.Save(dataDir + "39522_out.pdf");
```

 Di Sini,`"39522_out.pdf"` adalah nama berkas keluaran tempat dokumen yang dimodifikasi akan disimpan. Tentukan nama dan lokasi yang diinginkan untuk berkas keluaran.

### Contoh kode sumber untuk Ambil Bidang Formulir dalam Urutan Tab menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Test2.pdf");
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
	s += field.PartialName;
}
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
doc.Save(dataDir + "39522_out.pdf");
Document doc1 = new Document(dataDir + "39522_out.pdf");
s = "";
foreach (Field field in doc1.Pages[1].FieldsInTabOrder)
{
	s += field.PartialName;
}
string index = "";
foreach (Field field in doc1.Form)
{
	index += field.TabOrder;
}
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara mengambil kolom formulir dalam urutan tab menggunakan Aspose.PDF untuk .NET. Kita membahas langkah-langkah yang terlibat dalam memuat dokumen PDF, mengambil kolom formulir dalam urutan tab, mengubah urutan tab, dan menyimpan dokumen yang dimodifikasi. Dengan mengikuti langkah-langkah ini, Anda dapat bekerja dengan kolom formulir secara efisien dan menyesuaikan urutan tab sesuai kebutuhan Anda.


### Pertanyaan yang Sering Diajukan

#### T: Bagaimana saya dapat menggunakan bidang formulir yang diambil dalam kode C# saya untuk pemrosesan lebih lanjut?

 A: Anda dapat menggunakan bidang formulir yang diambil dalam kode C# Anda dengan mengakses propertinya seperti`Value`, `Name`, `Rect`dll. Properti ini memungkinkan Anda membaca dan mengubah data bidang formulir sesuai kebutuhan.

#### T: Dapatkah saya mengambil kolom formulir dari semua halaman dokumen PDF dalam urutan tab?

 A: Ya, Anda dapat mengambil bidang formulir dari semua halaman dokumen PDF dengan mengulangi setiap halaman dan mengakses`FieldsInTabOrder` properti seperti yang ditunjukkan dalam tutorial. Ini akan memberi Anda kolom formulir yang diurutkan berdasarkan urutan tab di semua halaman.

#### T: Apakah mungkin untuk mengambil hanya jenis bidang formulir tertentu, seperti bidang teks atau kotak centang, dalam urutan tab?

A: Ya, Anda dapat memfilter kolom formulir berdasarkan jenisnya, seperti kolom teks atau kotak centang, setelah mengambilnya dalam urutan tab. Anda dapat menggunakan pernyataan bersyarat untuk memeriksa jenis setiap kolom formulir dan memprosesnya sesuai dengan itu.

#### T: Bisakah saya mengambil kolom formulir berdasarkan namanya, bukan urutan tab?

 A: Ya, Anda dapat mengambil bidang formulir berdasarkan namanya dengan menggunakan`doc.Form` koleksi dan menentukan nama bidang sebagai indeks. Misalnya,`doc.Form["fieldName"]`akan mengambil bidang formulir dengan nama yang ditentukan.

#### T: Apakah Aspose.PDF untuk .NET mendukung penggunaan dokumen PDF terenkripsi?

A: Ya, Aspose.PDF untuk .NET menyediakan dukungan untuk bekerja dengan dokumen PDF terenkripsi. Anda dapat memuat dan memanipulasi file PDF terenkripsi menggunakan parameter kata sandi yang sesuai.