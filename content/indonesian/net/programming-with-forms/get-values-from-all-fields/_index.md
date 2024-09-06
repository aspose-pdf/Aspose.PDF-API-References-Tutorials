---
title: Dapatkan Nilai Dari Semua Bidang Dalam Dokumen PDF
linktitle: Dapatkan Nilai Dari Semua Bidang Dalam Dokumen PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Dapatkan nilai semua bidang formulir dalam dokumen PDF dengan mudah dengan Aspose.PDF untuk .NET.
type: docs
weight: 150
url: /id/net/programming-with-forms/get-values-from-all-fields/
---
Dalam tutorial ini, kami akan menunjukkan cara mendapatkan nilai semua kolom formulir dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber C# langkah demi langkah untuk memandu Anda melalui proses ini.

## Langkah 1: Persiapan

Pastikan Anda telah mengimpor pustaka yang diperlukan dan mengatur jalur ke direktori dokumen Anda:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Buka dokumen

Buka dokumen PDF:

```csharp
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
```

## Langkah 3: Dapatkan nilai untuk semua bidang

Ulangi semua bidang formulir dalam dokumen dan dapatkan nama dan nilainya:

```csharp
foreach(Field formField in pdfDocument.Form)
{
Console.WriteLine("Field name: {0} ", formField.PartialName);
Console.WriteLine("Value: {0}", formField.Value);
}
```

### Contoh kode sumber untuk Mendapatkan Nilai Dari Semua Bidang menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
// Dapatkan nilai dari semua bidang
foreach (Field formField in pdfDocument.Form)
{
	Console.WriteLine("Field Name : {0} ", formField.PartialName);
	Console.WriteLine("Value : {0} ", formField.Value);
}
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara mendapatkan nilai semua kolom formulir dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah mengekstrak nilai semua kolom formulir dari dokumen PDF Anda menggunakan Aspose.PDF.

### Pertanyaan yang Sering Diajukan

#### T: Dapatkah saya mengubah nilai kolom formulir saat mengambilnya menggunakan Aspose.PDF untuk .NET?

 A: Ya, Anda dapat mengubah nilai kolom formulir saat mengambilnya menggunakan Aspose.PDF untuk .NET. Setelah Anda memiliki`Field` objek yang mewakili bidang formulir, Anda dapat memperbaruinya`Value`properti dengan nilai yang diinginkan. Setelah melakukan perubahan yang diperlukan, Anda dapat menyimpan dokumen PDF yang diperbarui untuk mencerminkan perubahan tersebut.

#### T: Bagaimana cara memfilter dan mengambil kolom formulir tertentu berdasarkan jenisnya (misalnya, kolom teks, kotak centang)?

 A: Untuk mengambil kolom formulir tertentu berdasarkan jenisnya, Anda dapat menggunakan pernyataan kondisional atau kueri LINQ untuk memfilter kolom yang diinginkan. Anda dapat memeriksa jenis setiap kolom formulir menggunakan bidang`FieldType` properti, lalu mengambil nilai yang sesuai.

#### T: Apa yang terjadi jika dokumen PDF tidak memiliki kolom formulir?

 A: Jika dokumen PDF tidak berisi kolom formulir apa pun,`pdfDocument.Form` properti akan mengembalikan koleksi kosong. Dalam kasus seperti itu, loop untuk mengambil nilai tidak akan dijalankan, dan tidak ada nilai yang akan ditampilkan.

#### T: Dapatkah saya mengekstrak nilai kolom formulir dalam urutan tertentu atau mengurutkannya berdasarkan abjad?

J: Urutan pengambilan kolom formulir bergantung pada struktur dasar dokumen PDF. Aspose.PDF untuk .NET mengembalikan kolom formulir sesuai urutan penambahannya ke dokumen. Jika Anda ingin menampilkan atau memproses kolom formulir dalam urutan tertentu, Anda dapat menerapkan logika penyortiran khusus berdasarkan kebutuhan Anda.

#### T: Bagaimana saya dapat menangani dokumen PDF terenkripsi dengan kolom formulir yang dilindungi kata sandi?

 A: Aspose.PDF untuk .NET menyediakan fitur untuk bekerja dengan dokumen PDF terenkripsi dan kolom formulir yang dilindungi kata sandi. Sebelum memuat dokumen, Anda dapat mengatur kata sandi menggunakan`pdfDocument.Password` properti untuk mengakses dokumen PDF yang diamankan dan bidang formulirnya.