---
title: Dapatkan Koordinat Bidang Formulir PDF
linktitle: Dapatkan Koordinat Bidang Formulir PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Dapatkan koordinat bidang formulir PDF dengan mudah di dokumen PDF Anda dengan Aspose.PDF untuk .NET.
type: docs
weight: 120
url: /id/net/programming-with-forms/get-coordinates/
---
Dalam tutorial ini, kami akan menunjukkan cara mendapatkan koordinat bidang formulir PDF menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber C# langkah demi langkah untuk memandu Anda melalui proses ini.

## Langkah 1: Persiapan

Pastikan Anda telah mengimpor pustaka yang diperlukan dan mengatur jalur ke direktori dokumen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Muat dokumen keluaran

Muat dokumen PDF keluaran:

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## Langkah 3: Temukan bidang yang ditambahkan

Temukan kolom formulir yang ditambahkan (dalam contoh ini, kami menggunakan kolom "Item1", "Item2", dan "Item3"):

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## Langkah 4: Menampilkan posisi sub-item untuk setiap bidang

Beralihlah melalui pilihan untuk setiap bidang dan lihat koordinat untuk setiap sub-item:

```csharp
foreach(RadioButtonOptionField option in field0)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field1)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field2)
{
Console.WriteLine(option.Rect);
}
```

### Contoh kode sumber untuk Mendapatkan Koordinat menggunakan Aspose.PDF untuk .NET 
```csharp
try
{
	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Muat dokumen keluaran
	Document doc1 = new Document( dataDir + "input.pdf");
	// Temukan bidang yang ditambahkan
	RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
	RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
	RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
	// Dan menunjukkan posisi sub item untuk masing-masingnya.
	foreach (RadioButtonOptionField option in field0)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field1)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field2)
	{
		Console.WriteLine(option.Rect);
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara mendapatkan koordinat kolom formulir menggunakan Aspose.PDF untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah mengambil koordinat sub-elemen kolom formulir dalam dokumen PDF Anda menggunakan Aspose.PDF.

### Pertanyaan yang Sering Diajukan

#### T: Dapatkah saya menggunakan metode ini untuk mendapatkan koordinat untuk jenis bidang formulir apa pun di Aspose.PDF untuk .NET?

A: Ya, Anda dapat menggunakan metode ini untuk mendapatkan koordinat untuk berbagai jenis bidang formulir di Aspose.PDF for .NET. Kode sumber C# yang disediakan menunjukkan cara mendapatkan koordinat untuk bidang RadioButton, tetapi Anda dapat mengadaptasi pendekatan yang sama untuk jenis bidang formulir lainnya, seperti TextBox, CheckBox, ListBox, dan lainnya.

#### T: Bagaimana cara mengubah atau menyesuaikan koordinat kolom formulir?

A: Koordinat bidang formulir didasarkan pada sistem koordinat dokumen PDF, di mana titik asal (0,0) terletak di sudut kiri bawah halaman. Untuk mengubah atau menyesuaikan koordinat bidang formulir, Anda dapat memperbarui`Rect` properti dari bidang formulir masing-masing atau sub-itemnya, seperti RadioButtonOptionField.

#### T: Dapatkah saya menambahkan koordinat bidang formulir secara terprogram ke dokumen PDF?

A: Ya, Anda bisa mendapatkan koordinat kolom formulir yang ditambahkan secara terprogram ke dokumen PDF. Aspose.PDF untuk .NET memungkinkan Anda menambahkan kolom formulir secara dinamis, dan setelah ditambahkan, Anda dapat mengambil koordinatnya menggunakan pendekatan yang ditunjukkan dalam tutorial ini.

#### T: Apa tujuan mengambil koordinat bidang formulir?

A: Mengambil koordinat bidang formulir dapat membantu saat Anda perlu melakukan operasi terkait tata letak atau validasi tertentu pada bidang formulir dalam dokumen PDF. Hal ini memungkinkan Anda untuk memposisikan dan menyelaraskan bidang formulir secara akurat berdasarkan koordinatnya, memastikan bahwa bidang tersebut muncul dengan benar dalam dokumen dan memberikan pengalaman pengguna yang lancar.

#### T: Apakah koordinat bidang formulir dinyatakan dalam poin atau satuan lain?

J: Koordinat bidang formulir di Aspose.PDF untuk .NET dinyatakan dalam poin. Satu poin setara dengan 1/72 inci, menjadikannya satuan ukuran standar dalam format PDF.