---
title: Tombol Radio Horizontal dan Vertikal
linktitle: Tombol Radio Horizontal dan Vertikal
second_title: Referensi API Aspose.PDF untuk .NET
description: Buat tombol radio horizontal dan vertikal dengan mudah di dokumen PDF Anda dengan Aspose.PDF untuk .NET.
type: docs
weight: 180
url: /id/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
Dalam tutorial ini, kami akan menunjukkan cara membuat tombol radio yang disusun secara horizontal dan vertikal dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber C# langkah demi langkah untuk memandu Anda melalui proses ini.

## Langkah 1: Persiapan

Pastikan Anda telah mengimpor pustaka yang diperlukan dan mengatur jalur ke direktori dokumen Anda:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Muat dokumen

Muat dokumen PDF yang ada:

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## Langkah 3: Sesuaikan opsi tombol radio

Sesuaikan opsi tombol radio dengan mengatur properti berikut:

```csharp
formEditor. RadioGap = 4; // Jarak antara dua opsi tombol radio
formEditor. RadioHoriz = true; //Tata letak tombol radio horizontal
formEditor.RadioButtonItemSize = 20; // Ukuran tombol radio
formEditor.Facade.BorderWidth = 1; // Lebar batas tombol radio
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Warna batas tombol radio
```

## Langkah 4: Tambahkan Tombol Radio Horizontal

Tambahkan tombol radio yang disusun secara horizontal dengan menentukan opsi dan posisi bidang:

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## Langkah 5: Tambahkan tombol radio vertikal

Tambahkan tombol radio yang disusun secara vertikal dengan menentukan opsi dan posisi bidang:

```csharp
formEditor. RadioHoriz = false; // Tata letak vertikal tombol radio
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## Langkah 6: Simpan dokumen

Simpan dokumen PDF yang dimodifikasi:

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
```

### Contoh kode sumber untuk Tombol Radio Horizontal dan Vertikal menggunakan Aspose.PDF untuk .NET 
```csharp
try
{
	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Muat dokumen yang disimpan sebelumnya
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	// RadioGap adalah jarak antara dua pilihan tombol radio.
	formEditor.RadioGap = 4;
	// Tambahkan tombol radio horizontal
	formEditor.RadioHoriz = true;
	// RadioButtonItemSize jika ukuran item tombol radio.
	formEditor.RadioButtonItemSize = 20;
	formEditor.Facade.BorderWidth = 1;
	formEditor.Facade.BorderColor = System.Drawing.Color.Black;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
	// Tambahkan tombol radio lain yang terletak secara vertikal
	formEditor.RadioHoriz = false;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
	dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
	// Simpan dokumen PDF
	formEditor.Save(dataDir);
	Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara membuat tombol radio yang disusun secara horizontal dan vertikal dalam dokumen PDF menggunakan Aspose.PDF for .NET. Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah menyesuaikan tata letak tombol radio dan menambahkannya ke dokumen PDF Anda menggunakan Aspose.PDF.

### Pertanyaan yang Sering Diajukan

#### T: Apa itu tombol radio yang tersusun secara horizontal dan vertikal dalam dokumen PDF?

J: Tombol radio yang disusun secara horizontal dan vertikal dalam dokumen PDF mengacu pada orientasi tata letak opsi tombol radio. Tata letak horizontal menempatkan opsi tombol radio berdampingan, yang memungkinkan pengguna membuat pilihan dari kiri ke kanan. Di sisi lain, tata letak vertikal menumpuk opsi tombol radio di atas satu sama lain, yang memungkinkan pengguna membuat pilihan dari atas ke bawah.

#### T: Bagaimana cara menyesuaikan tampilan opsi tombol radio di Aspose.PDF untuk .NET?

A: Anda dapat menyesuaikan tampilan opsi tombol radio di Aspose.PDF untuk .NET dengan menyesuaikan beberapa properti. API menyediakan opsi untuk mengatur jarak antara dua opsi tombol radio (`RadioGap`), orientasi tata letak (`RadioHoriz`), ukuran item tombol radio (`RadioButtonItemSize`), lebar batas dan warna tombol radio, dan banyak lagi.

#### T: Dapatkah saya menambahkan tombol radio horizontal dan vertikal ke dokumen PDF yang sama?

J: Ya, Anda dapat menambahkan tombol radio horizontal dan vertikal ke dokumen PDF yang sama menggunakan Aspose.PDF untuk .NET. Contoh kode sumber yang disediakan dalam tutorial ini menunjukkan cara menambahkan tombol radio yang disusun secara horizontal terlebih dahulu, lalu menambahkan serangkaian tombol radio lain yang disusun secara vertikal ke dokumen PDF yang sama.

#### T: Dapatkah saya mengatur opsi tombol radio yang berbeda untuk setiap grup tombol radio?

 A: Ya, Anda dapat mengatur opsi tombol radio yang berbeda untuk setiap grup tombol radio. Setiap grup harus memiliki opsi yang unik.`RadioButtonField` objek, dan`RadioButtonOptionField` Objek dalam setiap grup harus berbagi halaman yang sama dan nama yang unik untuk opsinya. Ini memastikan bahwa tombol radio dalam setiap grup berfungsi dengan benar, dan pilihannya saling eksklusif.

#### T: Apakah pengaturan tata letak dan tampilan tombol radio didukung di semua penampil dan aplikasi PDF?

J: Ya, tata letak dan pengaturan tampilan tombol radio didukung di semua penampil dan aplikasi PDF yang sesuai standar. Spesifikasi PDF mendefinisikan tombol radio dan berbagai atributnya, sehingga dapat dikenali secara universal dalam format PDF. Namun, penting untuk menguji tampilan dan perilaku tombol radio di berbagai penampil PDF guna memastikan tampilan yang konsisten di berbagai platform.