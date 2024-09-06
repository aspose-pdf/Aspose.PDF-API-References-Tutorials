---
title: Buat Dokumen
linktitle: Buat Dokumen
second_title: Referensi API Aspose.PDF untuk .NET
description: Buat dokumen dengan tombol radio dengan mudah menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 40
url: /id/net/programming-with-forms/create-doc/
---
Dalam tutorial ini, kami akan menunjukkan cara membuat dokumen dengan tombol radio menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber C# langkah demi langkah untuk memandu Anda melalui proses ini.

##Langkah 1: Persiapan

Pertama, pastikan Anda telah mengimpor pustaka yang diperlukan dan mengatur jalur ke direktori dokumen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Buat dokumen baru

Buat objek Dokumen baru untuk menampung dokumen PDF:

```csharp
Document doc = new Document();
```

## Langkah 3: Tambahkan halaman

Tambahkan halaman baru ke dokumen:

```csharp
Page page = doc.Pages.Add();
```

## Langkah 4: Tambahkan bidang tombol radio

Buat bidang tombol radio dan atur posisi dan ukurannya:

```csharp
RadioButtonField field = new RadioButtonField(page);
field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
field. PartialName = "NewField";
```

## Langkah 5: Tambahkan opsi tombol radio

Tambahkan opsi yang diinginkan ke kolom tombol radio. Anda dapat mengatur koordinat dan ukuran setiap opsi sesuai kebutuhan:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
opt1.OptionName = "Item1";
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt2 = new RadioButtonOptionField();
opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
opt2.OptionName = "Item2";
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
opt3.OptionName = "Item3";
opt3.Border = new Border(opt3);
opt3.Border.Width = 1;
opt3.Characteristics.Border = System.Drawing.Color.Black;

field. Add(opt1);
field. Add(opt2);
field. Add(opt3);
```

## Langkah 6: Tambahkan bidang tombol radio ke formulir

Tambahkan bidang tombol radio ke koleksi Bidang Formulir Dokumen:

```csharp
doc.Form.Add(field);
```

## Langkah 7: Simpan dokumen

Simpan dokumen PDF:

```csharp
dataDir = dataDir + "CreateDoc_out.pdf";
doc.Save(dataDir);
```

### Contoh kode sumber untuk Membuat Dokumen menggunakan Aspose.PDF untuk .NET 
```csharp
try
{
	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Buat dokumen baru
	Document doc = new Document();
	Page page = doc.Pages.Add();
	// Tambahkan bidang tombol radio
	RadioButtonField field = new RadioButtonField(page);
	field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
	field.PartialName = "NewField";
	// Tambahkan opsi tombol radio. Harap perhatikan bahwa opsi ini terletak
	// Tidak horizontal maupun vertikal.
	// Anda dapat mencoba mengatur koordinat apa pun (dan bahkan ukuran) untuknya.
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
	opt1.OptionName = "Item1";
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
	opt2.OptionName = "Item2";
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
	opt3.OptionName = "Item3";
	opt3.Border = new Border(opt3);
	opt3.Border.Width = 1;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	field.Add(opt1);
	field.Add(opt2);
	field.Add(opt3);
	doc.Form.Add(field);
	dataDir = dataDir + "CreateDoc_out.pdf";
	// Simpan dokumen PDF
	doc.Save(dataDir);
	Console.WriteLine("\nNew doc with 3 items radio button created successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara membuat dokumen dengan tombol radio menggunakan Aspose.PDF untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah menambahkan tombol radio ke dokumen PDF Anda menggunakan Aspose.PDF.

### Pertanyaan yang Sering Diajukan

#### T: Dapatkah saya menyesuaikan tampilan tombol radio dalam dokumen menggunakan Aspose.PDF untuk .NET?

A: Ya, Anda dapat menyesuaikan tampilan tombol radio dalam dokumen menggunakan Aspose.PDF for .NET. Anda dapat mengatur properti seperti ukuran, warna, gaya border, dan lainnya untuk menyesuaikan tampilan tombol radio.

#### T: Bagaimana cara menambahkan grup tombol radio dengan opsi yang saling eksklusif?

J: Untuk membuat opsi yang saling eksklusif, Anda dapat menambahkan beberapa kolom tombol radio dengan nama yang sama. Ini akan memastikan bahwa saat satu opsi dipilih, opsi lain dengan nama yang sama akan otomatis tidak dipilih.

#### T: Apakah mungkin untuk menetapkan opsi pilihan default untuk tombol radio?

A: Ya, Anda dapat mengatur opsi pilihan default untuk tombol radio menggunakan Aspose.PDF untuk .NET. Anda dapat menggunakan`Selected` milik`RadioButtonOptionField` objek untuk menandai opsi sebagai dipilih secara default.

#### T: Dapatkah saya menambahkan pengendali peristiwa ke tombol radio?

 A: Ya, Anda dapat menambahkan event handler ke tombol radio menggunakan Aspose.PDF untuk .NET. Anda dapat mengaitkan tindakan JavaScript, seperti`OnValueChanged`, ke tombol radio untuk melakukan tindakan tertentu saat pengguna memilih opsi.

#### T: Bagaimana cara mengambil opsi yang dipilih dari grup tombol radio setelah pengguna membuat pilihan?

 A: Anda dapat mengambil opsi yang dipilih dari grup tombol radio menggunakan Aspose.PDF untuk .NET. Setelah pengguna membuat pilihan, Anda dapat mengakses`Selected` milik`RadioButtonOptionField` objek untuk memeriksa opsi mana yang dipilih.