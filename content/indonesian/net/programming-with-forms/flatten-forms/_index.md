---
title: Ratakan Formulir Dalam Dokumen PDF
linktitle: Ratakan Formulir Dalam Dokumen PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Ratakan formulir dalam dokumen PDF dengan mudah menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 100
url: /id/net/programming-with-forms/flatten-forms/
---
Dalam tutorial ini, kami akan menunjukkan cara meratakan formulir menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber C# langkah demi langkah untuk memandu Anda melalui proses ini.

## Langkah 1: Persiapan

Pertama, pastikan Anda telah mengimpor perpustakaan yang diperlukan dan mengatur jalur ke direktori dokumen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Muat formulir PDF sumber

Muat formulir PDF sumber:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Langkah 3: Ratakan formulir

Pertama periksa apakah ada kolom formulir di dokumen. Jika demikian, ulangi setiap bidang dan terapkan perataan:

```csharp
if (doc.Form.Fields.Count() > 0)
{
foreach (var item in doc.Form.Fields)
{
item. Flatten();
}
}
```

## Langkah 4: Simpan dokumen yang diperbarui

Simpan dokumen PDF yang diperbarui:

```csharp
dataDir = dataDir + "FlattenForms_out.pdf";
doc.Save(dataDir);
```

### Contoh kode sumber untuk Flatten Forms menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Muat formulir PDF sumber
Document doc = new Document(dataDir + "input.pdf");
// Ratakan Bentuk
if (doc.Form.Fields.Count() > 0)
{
	foreach (var item in doc.Form.Fields)
	{
		item.Flatten();
	}
}
dataDir = dataDir + "FlattenForms_out.pdf";
// Simpan dokumen yang diperbarui
doc.Save(dataDir);
Console.WriteLine("\nForms flattened successfully.\nFile saved at " + dataDir);
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara meratakan formulir menggunakan Aspose.PDF untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah meratakan formulir di dokumen PDF Anda, membuat bidang tidak dapat diedit, dan menggabungkan anotasi dengan konten dokumen.

### FAQ

#### T: Apa yang dimaksud dengan "perataan formulir" di Aspose.PDF untuk .NET?

J: Meratakan formulir di Aspose.PDF untuk .NET mengacu pada proses membuat kolom formulir di dokumen PDF tidak dapat diedit dan menggabungkan anotasi (seperti kolom formulir, anotasi, dan tanda tangan digital) dengan konten dokumen. Setelah formulir diratakan, pengguna tidak dapat mengubah kolom formulir, dan tampilan visual kolom formulir menjadi bagian dari konten statis dokumen PDF.

#### T: Dapatkah saya membalikkan proses perataan dan membuat kolom formulir dapat diedit kembali?

J: Tidak, setelah kolom formulir diratakan, prosesnya tidak dapat diubah menggunakan Aspose.PDF untuk .NET. Perataan secara permanen menggabungkan tampilan bidang formulir dengan konten PDF, dan elemen bidang formulir individual tidak lagi dapat diakses atau diedit.

#### T: Kapan saya harus meratakan formulir di dokumen PDF?

J: Meratakan formulir berguna ketika Anda ingin mempertahankan tampilan visual bidang formulir dan anotasi dalam dokumen PDF sekaligus mencegah pengguna mengubah data. Hal ini biasanya dilakukan ketika Anda ingin berbagi dokumen PDF dengan data formulir yang telah diisi sebelumnya atau anotasi yang tidak boleh diubah oleh penerima.

#### T: Apakah perataan formulir akan memengaruhi anotasi lain, seperti tanda tangan digital?

J: Ya, perataan formulir akan menggabungkan semua anotasi, termasuk tanda tangan digital, dengan konten PDF. Setelah formulir diratakan, tanda tangan digital apa pun yang ada akan menjadi bagian permanen dari dokumen, dan pengguna tidak dapat mengubah atau menghapusnya.

#### T: Dapatkah saya meratakan kolom formulir tertentu secara selektif dan membiarkan kolom lainnya dapat diedit?

J: Ya, Anda dapat secara selektif meratakan bidang formulir tertentu dalam dokumen PDF dan membiarkan bidang lainnya dapat diedit. Daripada menggunakan kode untuk meratakan semua bidang formulir, Anda bisa memilih untuk meratakan hanya bidang formulir yang diinginkan berdasarkan nama atau kriteria lainnya.