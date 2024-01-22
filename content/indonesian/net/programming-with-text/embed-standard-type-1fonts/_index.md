---
title: Sematkan Font Tipe 1 Standar Dalam File PDF
linktitle: Sematkan Font Tipe 1 Standar Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menyematkan font Tipe 1 standar dalam file PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 140
url: /id/net/programming-with-text/embed-standard-type-1fonts/
---
Tutorial ini akan memandu Anda melalui proses penyematan font standar Tipe 1 dalam file PDF menggunakan Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan.

## Persyaratan
Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau kompiler C# lainnya yang diinstal pada mesin Anda.
- Aspose.PDF untuk perpustakaan .NET. Anda dapat mendownloadnya dari situs resmi Aspose atau menggunakan manajer paket seperti NuGet untuk menginstalnya.

## Langkah 1: Siapkan proyek
1. Buat proyek C# baru di lingkungan pengembangan pilihan Anda.
2. Tambahkan referensi ke perpustakaan Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan
Dalam file kode tempat Anda ingin menyematkan font standar Tipe 1, tambahkan arahan penggunaan berikut di bagian atas file:

```csharp
using Aspose.Pdf;
```

## Langkah 3: Atur direktori dokumen
 Dalam kode, temukan baris yang bertuliskan`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur ke direktori tempat dokumen Anda disimpan.

## Langkah 4: Muat dokumen PDF yang ada
 Muat dokumen PDF yang ada menggunakan`Document`konstruktor dan meneruskan jalur ke file PDF masukan.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Langkah 5: Atur properti EmbedStandardFonts
 Mengatur`EmbedStandardFonts` milik dokumen ke`true` untuk mengaktifkan penyematan font Tipe 1 standar.

```csharp
pdfDocument.EmbedStandardFonts = true;
```

## Langkah 6: Sematkan font di setiap halaman
 Ulangi setiap halaman dokumen PDF dan periksa apakah font sudah tertanam. Jika tidak, atur`IsEmbedded` properti ke`true` untuk menyematkan font.

```csharp
foreach(Page page in pdfDocument.Pages)
{
     if (page.Resources.Fonts != null)
     {
         foreach(Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
         {
             if (!pageFont.IsEmbedded)
             {
                 pageFont.IsEmbedded = true;
             }
         }
     }
}
```

## Langkah 7: Simpan dokumen PDF yang diperbarui
 Simpan dokumen PDF yang diperbarui menggunakan`Save` metode`Document` objek, menentukan jalur file keluaran.

```csharp
pdfDocument.Save(dataDir + "EmbeddedFonts-updated_out.pdf");
```

### Contoh kode sumber untuk Embed Standard Type 1Fonts menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Muat Dokumen PDF yang ada
Document pdfDocument = new Document(dataDir + "input.pdf");
// Tetapkan properti dokumen EmbedStandardFonts
pdfDocument.EmbedStandardFonts = true;
foreach (Aspose.Pdf.Page page in pdfDocument.Pages)
{
	if (page.Resources.Fonts != null)
	{
		foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
		{
			// Periksa apakah font sudah tertanam
			if (!pageFont.IsEmbedded)
			{
				pageFont.IsEmbedded = true;
			}
		}
	}
}
pdfDocument.Save(dataDir + "EmbeddedFonts-updated_out.pdf");
```

## Kesimpulan
Anda telah berhasil menyematkan font Tipe 1 standar dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. File PDF yang diperbarui dengan font tertanam telah disimpan di jalur file keluaran yang ditentukan.

### FAQ

#### Q: Apa fokus dari tutorial ini?

J: Tutorial ini memberikan panduan langkah demi langkah untuk menyematkan font Tipe 1 standar dalam file PDF menggunakan pustaka Aspose.PDF untuk .NET. Kode sumber C# yang menyertainya menunjukkan prosedur yang diperlukan.

#### T: Namespace manakah yang perlu saya impor?

J: Dalam file kode tempat Anda ingin menyematkan font standar Tipe 1, sertakan namespace berikut di bagian atas file:

```csharp
using Aspose.Pdf;
```

#### T: Bagaimana cara menentukan direktori dokumen?

 A: Temukan garisnya`string dataDir = "YOUR DOCUMENT DIRECTORY";` dalam kode dan ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

#### T: Bagaimana cara memuat dokumen PDF yang sudah ada?

 J: Pada Langkah 4, Anda akan memuat dokumen PDF yang sudah ada menggunakan`Document` konstruktor dan menyediakan jalur ke file PDF masukan.

####  T: Apa tujuan dari`EmbedStandardFonts` property?

 J: Pada Langkah 5, Anda akan mengatur`EmbedStandardFonts` milik dokumen ke`true`, memungkinkan penyematan font Tipe 1 standar.

#### T: Bagaimana cara menyematkan font di setiap halaman?

 J: Langkah 6 melibatkan perulangan setiap halaman dokumen PDF. Untuk font yang belum disematkan, Anda akan mengaturnya`IsEmbedded` properti ke`true` untuk menyematkan font.

#### T: Bagaimana cara menyimpan dokumen PDF yang diperbarui?

 J: Pada Langkah 7, Anda akan menggunakan`Save` metode`Document` objek untuk menyimpan dokumen PDF yang diperbarui, menentukan jalur file keluaran.

#### T: Apa pentingnya menyematkan font dalam dokumen PDF?

J: Menyematkan font memastikan bahwa font yang digunakan dalam PDF disertakan dalam file itu sendiri. Hal ini menjamin tampilan teks yang konsisten meskipun sistem penerima tidak menginstal font yang diperlukan.

#### T: Apa manfaat utama dari tutorial ini?

J: Dengan mengikuti tutorial ini, Anda memperoleh pengetahuan dan keterampilan untuk menyematkan font standar Tipe 1 dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Hal ini memastikan rendering teks yang tepat di berbagai sistem.