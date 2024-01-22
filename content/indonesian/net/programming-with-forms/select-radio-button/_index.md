---
title: Pilih Tombol Radio Dalam Dokumen PDF
linktitle: Pilih Tombol Radio Dalam Dokumen PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara memilih tombol radio di dokumen PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 250
url: /id/net/programming-with-forms/select-radio-button/
---
Berikut adalah tutorial mendetail tentang cara memilih tombol radio menggunakan Aspose.PDF untuk .NET. Ikuti langkah ini:

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

## Langkah 4: Tentukan indeks tombol radio yang akan dipilih dari grup.

```csharp
radioField. Selected = 2;
```

## Langkah 5: Tetapkan jalur keluaran untuk file PDF yang diedit.

```csharp
dataDir = dataDir + "SelectRadioButton_out.pdf";
```

## Langkah 6: Simpan file PDF yang dimodifikasi.

```csharp
pdfDocument.Save(dataDir);
```

## Langkah 7: Tampilkan pesan konfirmasi dan lokasi file yang disimpan.

```csharp
Console.WriteLine("\nRadio button successfully selected in group.\nFile saved to location: " + dataDir);
```

### Contoh kode sumber untuk Select Radio Button menggunakan Aspose.PDF untuk .NET 
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
	// Simpan file PDFnya
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadioButton from group selected successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara memilih tombol radio menggunakan Aspose.PDF untuk .NET. Dengan mengikuti langkah-langkah yang diuraikan di atas, Anda dapat memanipulasi dan memodifikasi tombol radio di dokumen PDF Anda menggunakan Aspose.PDF untuk .NET.


### FAQ

#### T: Bisakah saya memilih beberapa tombol radio dalam satu grup menggunakan Aspose.PDF untuk .NET?

J: Tidak, tombol radio dalam grup dirancang untuk saling eksklusif. Anda hanya dapat memilih satu tombol radio pada satu waktu dalam grup, dan memilih salah satu tombol radio secara otomatis akan membatalkan pilihan tombol radio yang dipilih sebelumnya dalam grup yang sama.

#### T: Bagaimana cara mengambil tombol radio yang dipilih dalam grup menggunakan Aspose.PDF untuk .NET?

 A: Untuk mengambil tombol radio yang dipilih dalam grup, Anda dapat menggunakan`Selected` properti dari`RadioButtonField` kelas. Ini akan mengembalikan indeks tombol radio yang dipilih dalam grup.

#### T: Bisakah saya menyesuaikan tampilan tombol radio yang dipilih di dokumen PDF?

J: Ya, Anda dapat menyesuaikan tampilan tombol radio yang dipilih menggunakan Aspose.PDF untuk .NET. Anda dapat memodifikasi warna, ukuran, gaya tepi, dan atribut visual lainnya agar sesuai dengan tampilan yang Anda inginkan.

#### T: Apakah mungkin membuat grup tombol radio baru secara terprogram menggunakan Aspose.PDF untuk .NET?

J: Ya, Anda dapat membuat grup tombol radio baru secara terprogram menggunakan Aspose.PDF untuk .NET. Anda dapat menambahkan tombol radio baru ke formulir dokumen dan menentukan nama grup yang sama untuk setiap tombol radio untuk membuat grup baru.

#### T: Apakah Aspose.PDF untuk .NET mendukung penggunaan formulir PDF interaktif?

J: Ya, Aspose.PDF untuk .NET sepenuhnya mendukung penggunaan formulir PDF interaktif, termasuk tombol radio, bidang teks, kotak centang, dan elemen formulir lainnya. Anda dapat dengan mudah membaca, memodifikasi, dan membuat formulir PDF interaktif menggunakan perpustakaan.