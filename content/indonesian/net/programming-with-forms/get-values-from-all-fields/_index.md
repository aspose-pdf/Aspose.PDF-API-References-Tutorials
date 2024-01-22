---
title: Dapatkan Nilai Dari Semua Bidang Dalam Dokumen PDF
linktitle: Dapatkan Nilai Dari Semua Bidang Dalam Dokumen PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Dapatkan nilai semua bidang formulir dalam dokumen PDF dengan mudah menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 150
url: /id/net/programming-with-forms/get-values-from-all-fields/
---
Dalam tutorial ini, kami akan menunjukkan cara mendapatkan nilai semua bidang formulir dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber C# langkah demi langkah untuk memandu Anda melalui proses ini.

## Langkah 1: Persiapan

Pastikan Anda telah mengimpor perpustakaan yang diperlukan dan mengatur jalur ke direktori dokumen Anda:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Buka dokumen

Buka dokumen PDF:

```csharp
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
```

## Langkah 3: Dapatkan nilai untuk semua bidang

Ulangi semua bidang formulir di dokumen dan dapatkan nama serta nilainya:

```csharp
foreach(Field formField in pdfDocument.Form)
{
Console.WriteLine("Field name: {0} ", formField.PartialName);
Console.WriteLine("Value: {0}", formField.Value);
}
```

### Contoh kode sumber untuk Dapatkan Nilai Dari Semua Bidang menggunakan Aspose.PDF untuk .NET 
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

Dalam tutorial ini, kita mempelajari cara mendapatkan nilai semua bidang formulir dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah mengekstrak nilai semua bidang formulir dari dokumen PDF Anda menggunakan Aspose.PDF.

### FAQ

#### T: Bisakah saya mengubah nilai kolom formulir saat mengambilnya menggunakan Aspose.PDF untuk .NET?

 J: Ya, Anda dapat mengubah nilai bidang formulir sambil mengambilnya menggunakan Aspose.PDF untuk .NET. Setelah Anda memilikinya`Field` objek yang mewakili bidang formulir, Anda dapat memperbaruinya`Value`properti dengan nilai yang diinginkan. Setelah melakukan perubahan yang diperlukan, Anda dapat menyimpan dokumen PDF yang diperbarui untuk mencerminkan perubahan tersebut.

#### T: Bagaimana cara memfilter dan mengambil kolom formulir tertentu berdasarkan tipenya (misalnya, kolom teks, kotak centang)?

 J: Untuk mengambil bidang formulir tertentu berdasarkan tipenya, Anda bisa menggunakan pernyataan kondisional atau kueri LINQ untuk memfilter bidang minat. Anda dapat memeriksa jenis setiap bidang formulir menggunakan bidang tersebut`FieldType` properti, dan kemudian mengambil nilai yang sesuai.

#### T: Apa yang terjadi jika dokumen PDF tidak memiliki kolom formulir?

 J: Jika dokumen PDF tidak berisi kolom formulir apa pun, file`pdfDocument.Form` properti akan mengembalikan koleksi kosong. Dalam kasus seperti ini, perulangan untuk mengambil nilai tidak akan dijalankan, dan tidak ada nilai yang akan ditampilkan.

#### T: Dapatkah saya mengekstrak nilai bidang formulir dalam urutan tertentu atau mengurutkannya berdasarkan abjad?

J: Urutan pengambilan kolom formulir bergantung pada struktur dasar dokumen PDF. Aspose.PDF untuk .NET mengembalikan kolom formulir sesuai urutan penambahannya ke dokumen. Jika Anda ingin menampilkan atau memproses bidang formulir dalam urutan tertentu, Anda bisa menerapkan logika pengurutan kustom berdasarkan kebutuhan Anda.

#### T: Bagaimana cara menangani dokumen PDF terenkripsi dengan kolom formulir yang dilindungi kata sandi?

 J: Aspose.PDF untuk .NET menyediakan fitur untuk bekerja dengan dokumen PDF terenkripsi dan bidang formulir yang dilindungi kata sandi. Sebelum memuat dokumen, Anda dapat mengatur kata sandi menggunakan`pdfDocument.Password` properti untuk mengakses dokumen PDF yang diamankan dan bidang formulirnya.