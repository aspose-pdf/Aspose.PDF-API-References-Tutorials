---
title: Tombol Radio
linktitle: Tombol Radio
second_title: Referensi API Aspose.PDF untuk .NET
description: Tambahkan tombol radio dengan mudah ke dokumen PDF Anda dengan Aspose.PDF untuk .NET.
type: docs
weight: 220
url: /id/net/programming-with-forms/radio-button/
---
Dalam tutorial ini, kami akan menunjukkan cara menambahkan tombol radio dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber C# langkah demi langkah untuk memandu Anda melalui proses ini.

## Langkah 1: Persiapan

Pastikan Anda telah mengimpor pustaka yang diperlukan dan mengatur jalur ke direktori dokumen Anda:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Membuat Instansi Objek Dokumen

Buat instance objek Dokumen untuk membuat dokumen PDF baru:

```csharp
Document pdfDocument = new Document();
```

## Langkah 3: Tambahkan halaman

Tambahkan halaman ke dokumen PDF:

```csharp
pdfDocument.Pages.Add();
```

## Langkah 4: Membuat Instansiasi Objek RadioButtonField

Buat objek RadioButtonField dengan menentukan nomor halaman sebagai argumen:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Langkah 5: Tambahkan opsi tombol radio

Tambahkan opsi tombol radio ke objek RadioButtonField dengan menentukan koordinat setiap opsi dengan objek Rectangle:

```csharp
radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
```

## Langkah 6: Tambahkan tombol radio ke formulir

Tambahkan tombol radio ke objek Formulir dokumen:

```csharp
pdfDocument.Form.Add(radio);
```

## Langkah 7: Simpan Dokumen PDF

Simpan dokumen PDF yang dibuat:

```csharp
dataDir = dataDir + "RadioButton_out.pdf";
pdfDocument.Save(dataDir);
```

### Contoh kode sumber untuk Tombol Radio menggunakan Aspose.PDF untuk .NET 
```csharp
try
{
	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Membuat instance objek Dokumen
	Document pdfDocument = new Document();
	// Tambahkan halaman ke file PDF
	pdfDocument.Pages.Add();
	// Buat objek RadioButtonField dengan nomor halaman sebagai argumen
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Tambahkan opsi tombol radio pertama dan tentukan juga asalnya menggunakan objek Persegi Panjang
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	// Tambahkan opsi tombol radio kedua
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	// Tambahkan tombol radio ke objek formulir objek Dokumen
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "RadioButton_out.pdf";
	// Simpan file PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadio button field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara menambahkan tombol radio dalam dokumen PDF menggunakan Aspose.PDF for .NET. Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah membuat tombol radio dan meletakkannya di halaman tertentu dalam dokumen PDF Anda.


### Pertanyaan yang Sering Diajukan

#### T: Dapatkah saya menyesuaikan tampilan tombol radio, seperti ukuran dan warnanya?

 A: Ya, Anda dapat menyesuaikan tampilan tombol radio menggunakan`Rectangle` koordinat objek untuk menentukan ukuran dan posisinya. Aspose.PDF untuk .NET memungkinkan Anda menyesuaikan tampilan tombol radio sesuai kebutuhan.

#### T: Dapatkah saya menambahkan beberapa tombol radio dengan grup berbeda di halaman yang sama?

A: Ya, Anda dapat menambahkan beberapa tombol radio dengan grup yang berbeda di halaman yang sama. Setiap grup tombol radio dapat memiliki nama yang unik, dan hanya satu opsi dalam setiap grup yang dapat dipilih pada satu waktu.

#### T: Bagaimana cara menambahkan label atau deskripsi teks ke opsi tombol radio?

 A: Untuk menambahkan label atau deskripsi teks ke opsi tombol radio, Anda dapat menggunakan`TextStamp`kelas dari Aspose.PDF untuk .NET untuk melapisi teks pada dokumen PDF pada koordinat tertentu.

#### T: Apakah Aspose.PDF untuk .NET kompatibel dengan semua versi .NET Framework?

A: Ya, Aspose.PDF untuk .NET kompatibel dengan semua versi .NET Framework, termasuk .NET Core dan .NET Standard.

#### T: Dapatkah saya mengontrol pemilihan opsi tombol radio dalam dokumen PDF secara terprogram?

 A: Ya, Anda dapat mengontrol pemilihan opsi tombol radio secara terprogram menggunakan`IsSelected` milik`RadioButtonOption` class. Properti ini memungkinkan Anda untuk menetapkan opsi tertentu sebagai yang dipilih.