---
title: Ambil Bidang Formulir Dalam Urutan Tab
linktitle: Ambil Bidang Formulir Dalam Urutan Tab
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara mengambil bidang formulir dalam urutan tab menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 240
url: /id/net/programming-with-forms/retrieve-form-field-in-tab-order/
---
Saat bekerja dengan dokumen PDF di C# menggunakan Aspose.PDF untuk .NET, Anda mungkin menemukan skenario di mana Anda perlu mengambil bidang formulir dalam urutan tab tertentu. Ini bisa berguna ketika Anda ingin melakukan operasi pada bidang formulir berdasarkan urutan tabnya. Dalam tutorial ini, kami akan memandu Anda langkah demi langkah tentang cara mengambil kolom formulir dalam urutan tab menggunakan Aspose.PDF untuk .NET.

## Persyaratan

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

- Visual Studio diinstal pada sistem Anda
- Aspose.PDF untuk perpustakaan .NET diinstal

Sekarang, mari selami langkah-langkah untuk mengambil kolom formulir dalam urutan tab.

## Langkah 1: Mengatur Direktori Dokumen

 Untuk memulainya, Anda perlu mengatur direktori dokumen tempat dokumen PDF Anda berada. Anda dapat melakukan ini dengan menentukan jalur ke direktori di`dataDir` variabel.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 2: Memuat Dokumen PDF

 Pada langkah ini, kita akan memuat dokumen PDF menggunakan Aspose.PDF untuk .NET. Itu`Document` kelas menyediakan kemampuan untuk memuat dan memanipulasi dokumen PDF.

```csharp
Document doc = new Document(dataDir + "Test2.pdf");
```

 Di Sini,`"Test2.pdf"`adalah nama dokumen PDF yang ingin Anda muat. Pastikan dokumen tersebut ada di direktori dokumen yang ditentukan.

## Langkah 3: Mengambil Bidang Formulir di Urutan Tab

 Untuk mengambil kolom formulir dalam urutan tab, kita perlu mengakses`FieldsInTabOrder` properti dari`Page` kelas. Properti ini mengembalikan daftar bidang formulir yang diurutkan berdasarkan urutan tabnya.

```csharp
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
     s += field. PartialName;
}
```

Dalam cuplikan kode di atas, kita mengambil kolom formulir dari halaman kedua (`doc.Pages[1]` ) dan ulangi setiap bidang untuk menggabungkan nama sebagiannya ke dalam`s` variabel. Anda dapat mengubah cuplikan kode ini berdasarkan kebutuhan spesifik Anda.

## Langkah 4: Memodifikasi Urutan Tab

 Jika Anda ingin mengubah urutan tab bidang formulir, Anda dapat melakukannya dengan mengakses`TabOrder` properti setiap bidang dan menetapkan nilai urutan tab baru. Berikut ini contohnya:

```csharp
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
```

Dalam cuplikan kode di atas, kami menetapkan nilai urutan tab baru ke tiga bidang formulir (`doc.Form[3]`, `doc.Form[1]` , Dan`doc.Form[2]`). Sesuaikan indeks bidang dan nilai urutan tab sesuai dengan kebutuhan spesifik Anda.

## Langkah 5: Menyimpan Dokumen yang Dimodifikasi

 Setelah mengubah urutan tab bidang formulir, Anda perlu menyimpan dokumen yang dimodifikasi. Anda dapat melakukan ini menggunakan`Save` metode`Document` kelas.

```csharp
doc.Save(dataDir + "39522_out.pdf");
```

 Di Sini,`"39522_out.pdf"` adalah nama file keluaran tempat dokumen yang dimodifikasi akan disimpan. Tentukan nama dan lokasi yang diinginkan untuk file keluaran.

### Contoh kode sumber untuk Ambil Bidang Formulir Dalam Urutan Tab menggunakan Aspose.PDF untuk .NET 
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

Dalam tutorial ini, kita mempelajari cara mengambil kolom formulir dalam urutan tab menggunakan Aspose.PDF untuk .NET. Kami membahas langkah-langkah yang terlibat dalam memuat dokumen PDF, mengambil kolom formulir dalam urutan tab, mengubah urutan tab, dan menyimpan dokumen yang dimodifikasi. Dengan mengikuti langkah-langkah ini, Anda dapat bekerja secara efisien dengan bidang formulir dan mengkustomisasi urutan tabnya sesuai kebutuhan Anda.


### FAQ

#### T: Bagaimana cara menggunakan kolom formulir yang diambil dalam kode C# saya untuk pemrosesan lebih lanjut?

 J: Anda dapat menggunakan kolom formulir yang diambil dalam kode C# Anda dengan mengakses propertinya seperti`Value`, `Name`, `Rect`dll. Properti ini memungkinkan Anda membaca dan mengubah data bidang formulir sesuai kebutuhan.

#### T: Bisakah saya mengambil kolom formulir dari semua halaman dokumen PDF dalam urutan tab?

 J: Ya, Anda dapat mengambil kolom formulir dari semua halaman dokumen PDF dengan mengulangi setiap halaman dan mengakses`FieldsInTabOrder` properti seperti yang ditunjukkan dalam tutorial. Ini akan memberi Anda bidang formulir yang diurutkan berdasarkan urutan tabnya di semua halaman.

#### T: Apakah mungkin untuk mengambil hanya tipe bidang formulir tertentu, seperti bidang teks atau kotak centang, dalam urutan tab?

J: Ya, Anda bisa memfilter kolom formulir berdasarkan tipenya, seperti kolom teks atau kotak centang, setelah mengambilnya dalam urutan tab. Anda dapat menggunakan pernyataan kondisional untuk memeriksa jenis setiap bidang formulir dan memprosesnya sesuai dengan itu.

#### T: Bisakah saya mengambil kolom formulir berdasarkan namanya, bukan berdasarkan urutan tab?

 A: Ya, Anda dapat mengambil kolom formulir berdasarkan namanya dengan menggunakan`doc.Form` koleksi dan menentukan nama bidang sebagai indeks. Misalnya,`doc.Form["fieldName"]`akan mengambil bidang formulir dengan nama yang ditentukan.

#### T: Apakah Aspose.PDF untuk .NET mendukung pekerjaan dengan dokumen PDF terenkripsi?

J: Ya, Aspose.PDF untuk .NET menyediakan dukungan untuk bekerja dengan dokumen PDF terenkripsi. Anda dapat memuat dan memanipulasi file PDF terenkripsi menggunakan parameter kata sandi yang sesuai.