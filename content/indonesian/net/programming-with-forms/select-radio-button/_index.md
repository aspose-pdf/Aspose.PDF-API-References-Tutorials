---
title: Pilih Tombol Radio Dalam Dokumen PDF
linktitle: Pilih Tombol Radio Dalam Dokumen PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara memilih tombol radio dalam dokumen PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 250
url: /id/net/programming-with-forms/select-radio-button/
---
Berikut adalah tutorial terperinci tentang cara memilih tombol radio menggunakan Aspose.PDF untuk .NET. Ikuti langkah-langkah berikut:

##  Langkah 1: Mulailah dengan menentukan direktori dokumen Anda dengan menentukan jalur di`dataDir` variable.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

##  Langkah 2: Buka dokumen PDF menggunakan`Document` class and the document path.

```csharp
Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
```

## Langkah 3: Dapatkan bidang tombol radio dari formulir dokumen.

```csharp
RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
```

## Langkah 4: Tentukan indeks tombol radio untuk memilih dari grup.

```csharp
radioField. Selected = 2;
```

## Langkah 5: Tetapkan jalur keluaran untuk berkas PDF yang diedit.

```csharp
dataDir = dataDir + "SelectRadioButton_out.pdf";
```

## Langkah 6: Simpan berkas PDF yang telah dimodifikasi.

```csharp
pdfDocument.Save(dataDir);
```

## Langkah 7: Menampilkan pesan konfirmasi dan lokasi file yang disimpan.

```csharp
Console.WriteLine("\nRadio button successfully selected in group.\nFile saved to location: " + dataDir);
```

### Contoh kode sumber untuk Pilih Tombol Radio menggunakan Aspose.PDF untuk .NET 
```csharp
try
{
	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Buka dokumen
	Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
	// Dapatkan lapangan
	RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
	// Tentukan indeks tombol radio dari grup
	radioField.Selected = 2;
	dataDir = dataDir + "SelectRadioButton_out.pdf";
	// Simpan file PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadioButton from group selected successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara memilih tombol radio menggunakan Aspose.PDF for .NET. Dengan mengikuti langkah-langkah yang diuraikan di atas, Anda dapat memanipulasi dan memodifikasi tombol radio dalam dokumen PDF Anda menggunakan Aspose.PDF for .NET.


### Pertanyaan yang Sering Diajukan

#### T: Dapatkah saya memilih beberapa tombol radio dalam satu grup menggunakan Aspose.PDF untuk .NET?

J: Tidak, tombol radio dalam satu grup dirancang agar saling eksklusif. Anda hanya dapat memilih satu tombol radio dalam satu waktu dalam satu grup, dan memilih satu tombol akan secara otomatis membatalkan pilihan tombol radio yang dipilih sebelumnya dalam grup yang sama.

#### T: Bagaimana cara mengambil tombol radio yang dipilih dalam grup menggunakan Aspose.PDF untuk .NET?

 A: Untuk mengambil tombol radio yang dipilih dalam suatu grup, Anda dapat menggunakan`Selected` milik`RadioButtonField` kelas. Ini akan mengembalikan indeks tombol radio yang dipilih dalam grup.

#### T: Dapatkah saya menyesuaikan tampilan tombol radio yang dipilih dalam dokumen PDF?

A: Ya, Anda dapat menyesuaikan tampilan tombol radio yang dipilih menggunakan Aspose.PDF for .NET. Anda dapat mengubah warna, ukuran, gaya bingkai, dan atribut visual lainnya agar sesuai dengan tampilan yang Anda inginkan.

#### T: Apakah mungkin membuat grup tombol radio baru secara terprogram menggunakan Aspose.PDF untuk .NET?

A: Ya, Anda dapat membuat grup tombol radio baru secara terprogram menggunakan Aspose.PDF for .NET. Anda dapat menambahkan tombol radio baru ke formulir dokumen dan menentukan nama grup yang sama untuk setiap tombol radio guna membuat grup baru.

#### T: Apakah Aspose.PDF untuk .NET mendukung penggunaan formulir PDF interaktif?

A: Ya, Aspose.PDF untuk .NET sepenuhnya mendukung penggunaan formulir PDF interaktif, termasuk tombol radio, kolom teks, kotak centang, dan elemen formulir lainnya. Anda dapat dengan mudah membaca, memodifikasi, dan membuat formulir PDF interaktif menggunakan pustaka tersebut.