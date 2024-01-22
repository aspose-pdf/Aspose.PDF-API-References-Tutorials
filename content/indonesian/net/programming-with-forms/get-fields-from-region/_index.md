---
title: Dapatkan Bidang Dari Wilayah Dalam File PDF
linktitle: Dapatkan Bidang Dari Wilayah Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Dapatkan bidang dengan mudah dari wilayah tertentu dalam file PDF dengan Aspose.PDF untuk .NET.
type: docs
weight: 130
url: /id/net/programming-with-forms/get-fields-from-region/
---
Dalam tutorial ini, kami akan menunjukkan cara mendapatkan bidang wilayah tertentu dalam file PDF menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber C# langkah demi langkah untuk memandu Anda melalui proses ini.

## Langkah 1: Persiapan

Pastikan Anda telah mengimpor perpustakaan yang diperlukan dan mengatur jalur ke direktori dokumen Anda:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Buka file PDF

Buka file PDFnya:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## Langkah 3: Buat objek persegi panjang untuk membatasi wilayah

Buat objek persegi panjang untuk membatasi wilayah tempat Anda ingin mendapatkan bidang:

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
```

## Langkah 4: Dapatkan formulir PDF

Dapatkan dokumen dalam bentuk PDF:

```csharp
Aspose.Pdf.Forms.Form form = doc.Form;
```

## Langkah 5: Dapatkan bidang di wilayah persegi panjang

Dapatkan bidang yang terletak di wilayah persegi panjang yang ditentukan:

```csharp
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
```

## Langkah 6: Tampilkan nama dan nilai bidang

Ulangi bidang yang dihasilkan dan tampilkan nama dan nilainya:

```csharp
foreach (Field field in fields)
{
Console.Out.WriteLine("Field name: " + field.FullName + "-" + "Field value: " + field.Value);
}
```

### Contoh kode sumber untuk Dapatkan Bidang Dari Wilayah menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka file pdf
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
// Buat objek persegi panjang untuk mendapatkan bidang di area itu
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
// Dapatkan formulir PDF
Aspose.Pdf.Forms.Form form = doc.Form;
// Dapatkan bidang di area persegi panjang
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
// Tampilkan nama dan nilai Bidang
foreach (Field field in fields)
{
	// Tampilkan properti penempatan gambar untuk semua penempatan
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara mendapatkan bidang wilayah tertentu dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah mengekstrak bidang yang terletak di area persegi panjang tertentu pada dokumen PDF Anda menggunakan Aspose.PDF.

### FAQ

#### T: Dapatkah saya menggunakan metode ini untuk mendapatkan bidang dari wilayah non-persegi panjang dalam dokumen PDF?

 A: Tidak, metode yang disediakan`GetFieldsInRect` dirancang khusus untuk mengambil bidang yang terletak dalam wilayah persegi panjang dalam dokumen PDF. Jika Anda perlu mengekstrak bidang dari wilayah non-persegi panjang, Anda perlu menerapkan logika khusus untuk mengidentifikasi dan mengekstrak bidang berdasarkan kriteria lain, seperti koordinat atau nama bidang.

#### T: Bagaimana cara mengubah ukuran atau posisi persegi panjang untuk mendapatkan bidang dari wilayah lain?

 J: Untuk mendapatkan kolom dari wilayah lain, Anda dapat memodifikasi`Aspose.Pdf.Rectangle` parameter objek yang digunakan untuk mendefinisikan persegi panjang pembatas. Itu`Rectangle` konstruktor mengambil empat parameter:`x`, `y`, `width` , Dan`height`yang mewakili koordinat sudut kiri atas dan dimensi persegi panjang. Menyesuaikan parameter ini akan mengubah wilayah dari mana bidang diekstraksi.

#### T: Bagaimana jika tidak ada bidang dalam wilayah persegi panjang yang ditentukan?

 J: Jika tidak ada bidang dalam wilayah persegi panjang yang ditentukan, maka`GetFieldsInRect` metode akan mengembalikan array kosong. Anda dapat memeriksa panjang array untuk menentukan apakah ada bidang apa pun di wilayah tersebut.

#### T: Bisakah saya mendapatkan kolom dari wilayah yang tumpang tindih dalam dokumen PDF?

 J: Ya, Anda bisa mendapatkan bidang dari wilayah yang tumpang tindih dalam dokumen PDF dengan membuat beberapa bidang`Aspose.Pdf.Rectangle` objek dan memanggil`GetFieldsInRect` metode untuk masing-masingnya. Wilayah yang tumpang tindih akan ditangani secara terpisah, dan Anda akan menerima susunan bidang terpisah untuk setiap wilayah.

#### T: Apakah mungkin untuk mendapatkan kolom dari halaman tertentu atau beberapa halaman dalam dokumen PDF?

J: Ya, Anda bisa mendapatkan kolom dari halaman tertentu atau beberapa halaman dalam dokumen PDF. Untuk mencapai hal ini, Anda dapat memuat dokumen PDF, mengakses halaman yang diinginkan menggunakan`doc.Pages` koleksi, dan kemudian menerapkan`GetFieldsInRect` metode untuk wilayah spesifik setiap halaman.