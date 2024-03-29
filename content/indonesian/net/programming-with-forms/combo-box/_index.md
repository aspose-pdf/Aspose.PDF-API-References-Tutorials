---
title: Kotak kombo
linktitle: Kotak kombo
second_title: Aspose.PDF untuk Referensi .NET API
description: Buat daftar kotak kombo dengan mudah di dokumen PDF Anda menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 30
url: /id/net/programming-with-forms/combo-box/
---
Dalam tutorial ini, kami akan menunjukkan cara membuat daftar kotak kombo menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber C# langkah demi langkah untuk memandu Anda melalui proses ini.

## Langkah 1: Persiapan

Pertama, pastikan Anda telah mengimpor perpustakaan yang diperlukan dan mengatur jalur ke direktori dokumen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Buat Objek Dokumen

Buat objek Dokumen untuk menampung formulir PDF:

```csharp
Document doc = new Document();
```

## Langkah 3: Tambahkan halaman

Tambahkan halaman ke dokumen:

```csharp
doc.Pages.Add();
```

## Langkah 4: Buat instance Objek ComboBoxField

Buat instance objek ComboBoxField dengan dimensi yang diinginkan:

```csharp
ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
```

## Langkah 5: Tambahkan opsi ke daftar drop-down

Tambahkan opsi yang diinginkan ke daftar drop-down:

```csharp
combo.AddOption("Red");
combo.AddOption("Yellow");
combo.AddOption("Green");
combo.AddOption("Blue");
```

## Langkah 6: Tambahkan daftar kotak kombo ke formulir

Tambahkan objek ComboBoxField ke koleksi Bidang Formulir Dokumen:

```csharp
doc.Form.Add(combo);
```

## Langkah 7: Simpan dokumen

Simpan dokumen PDF:

```csharp
dataDir = dataDir + "ComboBox_out.pdf";
doc.Save(dataDir);
```

### Contoh kode sumber untuk Combo Box menggunakan Aspose.PDF untuk .NET 
```csharp
try
{
	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Buat objek Dokumen
	Document doc = new Document();
	// Tambahkan halaman ke objek dokumen
	doc.Pages.Add();
	// Buat instance objek Bidang ComboBox
	ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
	// Tambahkan opsi ke ComboBox
	combo.AddOption("Red");
	combo.AddOption("Yellow");
	combo.AddOption("Green");
	combo.AddOption("Blue");
	// Tambahkan objek kotak kombo ke kumpulan bidang formulir objek dokumen
	doc.Form.Add(combo);
	dataDir = dataDir + "ComboBox_out.pdf";
	// Simpan dokumen PDF
	doc.Save(dataDir);
	Console.WriteLine("\nCombobox field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara membuat daftar kotak kombo menggunakan Aspose.PDF untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah menambahkan daftar kotak kombo ke dokumen PDF Anda menggunakan Aspose.PDF.

### FAQ

#### T: Bisakah saya mengkustomisasi tampilan daftar kotak kombo menggunakan Aspose.PDF untuk .NET?

A: Ya, Anda dapat menyesuaikan tampilan daftar kotak kombo menggunakan Aspose.PDF untuk .NET. Anda dapat mengatur properti seperti ukuran font, warna, warna latar belakang, gaya tepi, dan lainnya agar sesuai dengan tampilan dan nuansa yang Anda inginkan.

#### T: Dapatkah saya menetapkan pilihan default yang dipilih dalam daftar kotak kombo?

 A: Ya, Anda dapat mengatur pilihan default yang dipilih dalam daftar kotak kombo menggunakan Aspose.PDF untuk .NET. Anda dapat menggunakan`Selected` properti dari`ComboBoxField` objek untuk menandai satu atau lebih opsi sebagai yang dipilih secara default.

#### T: Bagaimana cara mengambil nilai yang dipilih dari daftar kotak kombo setelah pengguna membuat pilihan?

 J: Anda dapat mengambil nilai yang dipilih dari daftar kotak kombo menggunakan Aspose.PDF untuk .NET. Setelah pengguna membuat pilihan, Anda dapat mengakses`Value` properti dari`ComboBoxField`objek untuk mendapatkan nilai yang dipilih.

#### T: Apakah mungkin untuk menambahkan event handler atau tindakan ke daftar kotak kombo?

 J: Ya, Aspose.PDF untuk .NET memungkinkan Anda menambahkan event handler atau tindakan ke daftar kotak kombo. Anda dapat mengaitkan tindakan JavaScript, seperti`OnValueChanged`, ke daftar kotak kombo untuk melakukan tindakan tertentu saat pengguna memilih opsi.

#### T: Dapatkah saya menambahkan keterangan alat atau deskripsi pada opsi di daftar kotak kombo?

 J: Ya, Anda dapat menambahkan tooltips atau deskripsi ke opsi di daftar kotak kombo menggunakan Aspose.PDF untuk .NET. Anda dapat mengatur`AlternateName` properti setiap opsi untuk memberikan tooltip atau deskripsi yang akan ditampilkan saat pengguna mengarahkan kursor ke opsi tersebut.