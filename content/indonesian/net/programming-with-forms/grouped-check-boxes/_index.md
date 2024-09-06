---
title: Kotak Centang yang Dikelompokkan dalam Dokumen PDF
linktitle: Kotak Centang yang Dikelompokkan dalam Dokumen PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Buat kotak centang yang dikelompokkan dengan mudah dalam dokumen PDF dengan Aspose.PDF untuk .NET.
type: docs
weight: 170
url: /id/net/programming-with-forms/grouped-check-boxes/
---
Dalam tutorial ini, kami akan menunjukkan cara membuat kotak centang berkelompok dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber C# langkah demi langkah untuk memandu Anda melalui proses ini.

## Langkah 1: Persiapan

Pastikan Anda telah mengimpor pustaka yang diperlukan dan mengatur jalur ke direktori dokumen Anda:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Membuat Instansi Objek Dokumen

Membuat instance objek Dokumen:

```csharp
Document pdfDocument = new Document();
```

## Langkah 3: Tambahkan halaman ke dokumen PDF

Tambahkan halaman ke dokumen PDF:

```csharp
Page page = pdfDocument.Pages.Add();
```

## Langkah 4: Membuat Instansiasi Objek RadioButtonField

Buat instance objek RadioButtonField dengan nomor halaman sebagai argumen:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Langkah 5: Tambahkan opsi tombol radio

Tambahkan opsi tombol radio menggunakan objek RadioButtonOptionField dan tentukan posisinya menggunakan objek Rectangle:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## Langkah 6: Sesuaikan opsi tombol radio

Sesuaikan opsi tombol radio dengan mengatur gaya, batas, dan tampilannya:

```csharp
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Square;
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Border.Style = BorderStyle.Solid;
```

## Langkah 7: Tambahkan tombol radio ke formulir

Tambahkan tombol radio ke objek formulir dokumen:

```csharp
pdfDocument.Form.Add(radio);
```

## Langkah 8: Simpan dokumen

Simpan dokumen PDF:

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### Contoh kode sumber untuk Kotak Centang yang Dikelompokkan menggunakan Aspose.PDF untuk .NET 
```csharp
try
{
	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Membuat instance objek Dokumen
	Document pdfDocument = new Document();
	// Tambahkan halaman ke file PDF
	Page page = pdfDocument.Pages.Add();
	// Buat objek RadioButtonField dengan nomor halaman sebagai argumen
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Tambahkan opsi tombol radio pertama dan tentukan juga asalnya menggunakan objek Persegi Panjang
	RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
	RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
	opt1.OptionName = "Test1";
	opt2.OptionName = "Test2";
	radio.Add(opt1);
	radio.Add(opt2);
	opt1.Style = BoxStyle.Square;
	opt2.Style = BoxStyle.Square;
	opt1.Style = BoxStyle.Cross;
	opt2.Style = BoxStyle.Cross;
	opt1.Border = new Border(opt1);
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	// Tambahkan tombol radio ke objek formulir objek Dokumen
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
	// Simpan dokumen PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nGrouped checkboxes added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara membuat kotak centang yang dikelompokkan dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah menambahkan opsi tombol radio khusus dan menggabungkannya dalam dokumen PDF Anda menggunakan Aspose.PDF.

### Pertanyaan yang Sering Diajukan

#### T: Apa itu kotak centang yang dikelompokkan dalam dokumen PDF?

A: Kotak centang yang dikelompokkan dalam dokumen PDF merujuk pada serangkaian opsi tombol radio yang dikelompokkan bersama. Tombol radio memungkinkan pengguna untuk memilih hanya satu opsi dari sekelompok pilihan yang saling eksklusif. Ketika satu tombol radio dipilih, tombol radio lainnya dalam kelompok yang sama akan otomatis tidak dipilih. Perilaku pengelompokan ini berguna ketika Anda ingin menyajikan beberapa opsi kepada pengguna tetapi membatasi pilihan mereka hanya pada satu pilihan.

#### T: Dapatkah saya menyesuaikan tampilan kotak centang yang dikelompokkan dalam Aspose.PDF untuk .NET?

A: Ya, Anda dapat menyesuaikan tampilan kotak centang yang dikelompokkan di Aspose.PDF untuk .NET. API menyediakan berbagai opsi untuk mengatur gaya, batas, dan tampilan opsi tombol radio. Anda dapat menentukan posisi setiap opsi, memilih di antara berbagai gaya kotak (misalnya, persegi, lingkaran, silang), dan menyesuaikan properti batas untuk mencapai representasi visual yang diinginkan.

#### T: Bagaimana cara menambahkan kotak centang yang dikelompokkan ke halaman tertentu dalam dokumen PDF?

A: Untuk menambahkan kotak centang yang dikelompokkan ke halaman tertentu dalam dokumen PDF, Anda perlu membuat instance`RadioButtonField` objek dengan nomor halaman yang diinginkan sebagai argumen. Kemudian, buat`RadioButtonOptionField` objek yang mewakili setiap opsi tombol radio dan menentukan posisinya menggunakan`Rectangle` objek. Terakhir, tambahkan opsi ini ke`RadioButtonField` dan menyesuaikan tampilannya sesuai kebutuhan sebelum menambahkan`RadioButtonField` ke formulir dokumen.

#### T: Dapatkah saya menambahkan beberapa grup kotak centang ke satu dokumen PDF?

 A: Ya, Anda dapat menambahkan beberapa grup kotak centang ke satu dokumen PDF. Setiap grup harus memiliki nama yang unik.`RadioButtonField` objek, dan`RadioButtonOptionField` Objek dalam setiap grup harus berbagi halaman yang sama dan nama yang unik untuk opsinya. Ini memastikan bahwa tombol radio dalam setiap grup berfungsi dengan benar, dan pilihannya saling eksklusif.

#### T: Apakah kotak centang yang dikelompokkan didukung di semua penampil dan aplikasi PDF?

J: Ya, kotak centang yang dikelompokkan didukung di semua penampil dan aplikasi PDF yang sesuai standar. Spesifikasi PDF mendefinisikan tombol radio dan perilaku pengelompokannya, sehingga dikenal secara universal dalam format PDF. Namun, penting untuk menguji fungsionalitas di berbagai penampil PDF guna memastikan perilaku yang konsisten di berbagai platform.