---
title: Pertahankan Hak
linktitle: Pertahankan Hak
second_title: Aspose.PDF untuk Referensi .NET API
description: Pertahankan hak formulir dalam dokumen PDF Anda dengan Aspose.PDF untuk .NET.
type: docs
weight: 210
url: /id/net/programming-with-forms/preserve-rights/
---
Dalam tutorial ini, kami akan menunjukkan cara mempertahankan hak formulir dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber C# langkah demi langkah untuk memandu Anda melalui proses ini.

## Langkah 1: Persiapan

Pastikan Anda telah mengimpor perpustakaan yang diperlukan dan mengatur jalur ke direktori dokumen Anda:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Buka dokumen

 Buka dokumen PDF sumber menggunakan a`FileStream` dengan izin membaca dan menulis:

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## Langkah 3: Edit Bidang Formulir

Telusuri semua bidang formulir di dokumen dan buat perubahan yang diperlukan. Dalam contoh ini, kami mengubah nilai bidang formulir yang memiliki nama "A1":

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

 Jangan lupa untuk menutupnya`FileStream` objek setelah Anda selesai:

```csharp
fs. Close();
```

### Contoh kode sumber untuk Pertahankan Hak menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Baca formulir PDF sumber dengan FileAccess Baca dan Tulis.
// Kami memerlukan izin ReadWrite karena setelah modifikasi,
// Kita perlu menyimpan konten yang diperbarui dalam dokumen/file yang sama.
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
// Buat instance Dokumen
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Dapatkan nilai dari semua bidang
foreach (Field formField in pdfDocument.Form)
{
	// Jika nama lengkap bidang berisi A1, lakukan operasi
	if (formField.FullName.Contains("A1"))
	{
		// Keluarkan bidang formulir sebagai Kotak Teks
		TextBoxField textBoxField = formField as TextBoxField;
		// Ubah nilai bidang
		textBoxField.Value = "Testing";
	}
}
// Simpan dokumen yang diperbarui di simpan FileStream
pdfDocument.Save();
// Tutup objek File Stream
fs.Close();
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara mempertahankan hak formulir dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Dengan mengikuti langkah-langkah ini, Anda bisa dengan mudah mengakses bidang formulir dan membuat perubahan spesifik sambil mempertahankan akses dan izin menulis.


### FAQ

#### T: Bisakah saya mempertahankan hak kolom formulir tertentu tanpa memengaruhi kolom lain di dokumen PDF?

 A: Ya, dengan menggunakan`FullName` properti bidang formulir, Anda dapat menargetkan bidang formulir tertentu untuk disimpan tanpa memengaruhi yang lain.

#### T: Dapatkah saya mempertahankan hak formulir dalam dokumen PDF yang dilindungi kata sandi?

J: Ya, Aspose.PDF untuk .NET memungkinkan Anda mempertahankan hak formulir bahkan dalam dokumen PDF yang dilindungi kata sandi, selama Anda memberikan kata sandi yang benar untuk mengakses dan memodifikasi file.

#### T: Apa yang terjadi jika saya mencoba mengubah kolom formulir tanpa hak akses yang sesuai?

J: Jika Anda mencoba mengubah kolom formulir tanpa hak akses yang sesuai, perubahan tidak akan disimpan dalam dokumen PDF, dan Anda mungkin menerima pengecualian atau pesan kesalahan.

#### T: Apakah Aspose.PDF untuk .NET kompatibel dengan semua versi .NET Framework?

J: Ya, Aspose.PDF untuk .NET kompatibel dengan semua versi .NET Framework, termasuk .NET Core dan .NET Standard.

#### T: Dapatkah saya mempertahankan hak formulir dalam dokumen PDF secara terprogram dalam bahasa pemrograman lain selain C#?

A: Ya, Aspose.PDF untuk .NET mendukung berbagai bahasa pemrograman, seperti VB.NET dan ASP.NET, selain C#.