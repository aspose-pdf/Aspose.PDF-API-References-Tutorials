---
title: Pertahankan Hak
linktitle: Pertahankan Hak
second_title: Referensi API Aspose.PDF untuk .NET
description: Pertahankan hak bentuk dalam dokumen PDF Anda dengan Aspose.PDF untuk .NET.
type: docs
weight: 210
url: /id/net/programming-with-forms/preserve-rights/
---
Dalam tutorial ini, kami akan menunjukkan cara mempertahankan hak formulir dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber C# langkah demi langkah untuk memandu Anda melalui proses ini.

## Langkah 1: Persiapan

Pastikan Anda telah mengimpor pustaka yang diperlukan dan mengatur jalur ke direktori dokumen Anda:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Buka dokumen

 Buka dokumen PDF sumber menggunakan`FileStream` dengan izin membaca dan menulis:

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## Langkah 3: Edit Bidang Formulir

Telusuri semua kolom formulir dalam dokumen dan buat perubahan yang diperlukan. Dalam contoh ini, kami mengubah nilai kolom formulir yang namanya "A1":

```csharp
foreach(Field formField in pdfDocument.Form)
{
if (formField.FullName.Contains("A1"))
{
TextBoxField textBoxField = formField as TextBoxField;
textBoxField.Value = "Testing";
}
}
```

## Langkah 4: Simpan dokumen yang diperbarui

Simpan dokumen PDF yang dimodifikasi:

```csharp
pdfDocument.Save();
```

##  Langkah 5: Tutup`FileStream`

 Jangan lupa untuk menutupnya`FileStream` keberatan saat Anda sudah selesai:

```csharp
fs. Close();
```

### Contoh kode sumber untuk Preserve Rights menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Baca formulir PDF sumber dengan FileAccess Baca dan Tulis.
// Kami memerlukan izin ReadWrite karena setelah modifikasi,
// Kita perlu menyimpan konten yang diperbarui dalam dokumen/berkas yang sama.
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
// Membuat contoh dokumen
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Dapatkan nilai dari semua bidang
foreach (Field formField in pdfDocument.Form)
{
	// Jika nama lengkap bidang berisi A1, lakukan operasi
	if (formField.FullName.Contains("A1"))
	{
		// Ubah bidang formulir menjadi Kotak Teks
		TextBoxField textBoxField = formField as TextBoxField;
		// Ubah nilai bidang
		textBoxField.Value = "Testing";
	}
}
// Simpan dokumen yang diperbarui di save FileStream
pdfDocument.Save();
// Tutup objek File Stream
fs.Close();
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara mempertahankan hak formulir dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah mengakses kolom formulir dan membuat perubahan tertentu sambil mempertahankan akses dan izin menulis.


### Pertanyaan yang Sering Diajukan

#### T: Dapatkah saya mempertahankan hak pada bidang formulir tertentu tanpa memengaruhi bidang lain dalam dokumen PDF?

 A: Ya, dengan menggunakan`FullName` properti bidang formulir, Anda dapat menargetkan bidang formulir tertentu untuk pelestarian dan membiarkan bidang lainnya tidak terpengaruh.

#### T: Dapatkah saya menyimpan hak formulir dalam dokumen PDF yang dilindungi kata sandi?

A: Ya, Aspose.PDF untuk .NET memungkinkan Anda mempertahankan hak formulir bahkan dalam dokumen PDF yang dilindungi kata sandi, selama Anda memberikan kata sandi yang benar untuk mengakses dan memodifikasi file tersebut.

#### T: Apa yang terjadi jika saya mencoba mengubah kolom formulir tanpa hak akses yang sesuai?

A: Jika Anda mencoba mengubah kolom formulir tanpa hak akses yang sesuai, perubahan tersebut tidak akan disimpan dalam dokumen PDF, dan Anda mungkin menerima pengecualian atau pesan kesalahan.

#### T: Apakah Aspose.PDF untuk .NET kompatibel dengan semua versi .NET Framework?

A: Ya, Aspose.PDF untuk .NET kompatibel dengan semua versi .NET Framework, termasuk .NET Core dan .NET Standard.

#### T: Dapatkah saya mempertahankan hak formulir dalam dokumen PDF secara terprogram dalam bahasa pemrograman lain selain C#?

A: Ya, Aspose.PDF untuk .NET mendukung berbagai bahasa pemrograman, seperti VB.NET dan ASP.NET, selain C#.