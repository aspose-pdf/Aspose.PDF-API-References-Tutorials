---
title: Sematkan Font Standar Tipe 1 Dalam File PDF
linktitle: Sematkan Font Standar Tipe 1 Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menanamkan font Tipe 1 standar dalam berkas PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 140
url: /id/net/programming-with-text/embed-standard-type-1fonts/
---
Tutorial ini akan memandu Anda melalui proses penyematan font Tipe 1 standar dalam file PDF menggunakan Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan.

## Persyaratan
Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau kompiler C# lainnya terinstal di komputer Anda.
- Aspose.PDF untuk pustaka .NET. Anda dapat mengunduhnya dari situs web resmi Aspose atau menggunakan pengelola paket seperti NuGet untuk menginstalnya.

## Langkah 1: Siapkan proyek
1. Buat proyek C# baru di lingkungan pengembangan pilihan Anda.
2. Tambahkan referensi ke pustaka Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan
Pada berkas kode tempat Anda ingin menanamkan font Tipe 1 standar, tambahkan perintah using berikut di bagian atas berkas:

```csharp
using Aspose.Pdf;
```

## Langkah 3: Mengatur direktori dokumen
 Dalam kode, temukan baris yang bertuliskan`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur ke direktori tempat dokumen Anda disimpan.

## Langkah 4: Muat dokumen PDF yang ada
 Memuat dokumen PDF yang ada menggunakan`Document`konstruktor dan meneruskan jalur ke berkas PDF masukan.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Langkah 5: Atur properti EmbedStandardFonts
 Mengatur`EmbedStandardFonts` properti dokumen untuk`true` untuk mengaktifkan penyematan font Tipe 1 standar.

```csharp
pdfDocument.EmbedStandardFonts = true;
```

## Langkah 6: Sematkan font di setiap halaman
 Ulangi setiap halaman dokumen PDF dan periksa apakah font sudah tertanam. Jika belum, atur`IsEmbedded` properti untuk`true` untuk menanamkan font.

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
 Simpan dokumen PDF yang diperbarui menggunakan`Save` metode dari`Document` objek, yang menentukan jalur berkas keluaran.

```csharp
pdfDocument.Save(dataDir + "EmbeddedFonts-updated_out.pdf");
```

### Contoh kode sumber untuk Embed Standard Type 1Fonts menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Memuat Dokumen PDF yang ada
Document pdfDocument = new Document(dataDir + "input.pdf");
// Tetapkan properti EmbedStandardFonts dari dokumen
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
Anda telah berhasil menyematkan font Tipe 1 standar dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. File PDF yang diperbarui dengan font yang disematkan telah disimpan di jalur file keluaran yang ditentukan.

### Pertanyaan yang Sering Diajukan

#### T: Apa fokus dari tutorial ini?

J: Tutorial ini menyediakan panduan langkah demi langkah untuk menyematkan font Tipe 1 standar dalam file PDF menggunakan pustaka Aspose.PDF for .NET. Kode sumber C# yang disertakan menunjukkan prosedur yang diperlukan.

#### T: Namespace mana yang perlu saya impor?

A: Pada berkas kode tempat Anda bermaksud menanamkan font Tipe 1 standar, sertakan namespace berikut di bagian atas berkas:

```csharp
using Aspose.Pdf;
```

#### T: Bagaimana cara menentukan direktori dokumen?

 A: Temukan garisnya`string dataDir = "YOUR DOCUMENT DIRECTORY";` dalam kode dan ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

#### T: Bagaimana cara memuat dokumen PDF yang ada?

 A: Pada Langkah 4, Anda akan memuat dokumen PDF yang ada menggunakan`Document` konstruktor dan menyediakan jalur ke berkas PDF masukan.

####  T: Apa tujuan dari`EmbedStandardFonts` property?

 A: Pada Langkah 5, Anda akan mengatur`EmbedStandardFonts` properti dokumen untuk`true`, yang memungkinkan penyematan font Tipe 1 standar.

#### T: Bagaimana cara menyematkan font di setiap halaman?

 A: Langkah 6 melibatkan pengulangan melalui setiap halaman dokumen PDF. Untuk font yang belum tertanam, Anda akan mengatur`IsEmbedded` properti untuk`true` untuk menanamkan font.

#### T: Bagaimana cara menyimpan dokumen PDF yang diperbarui?

 A: Pada Langkah 7, Anda akan menggunakan`Save` metode dari`Document` objek untuk menyimpan dokumen PDF yang diperbarui dan menentukan jalur berkas keluaran.

#### T: Apa pentingnya menyematkan font dalam dokumen PDF?

J: Penyematan font memastikan bahwa font yang digunakan dalam PDF disertakan dalam berkas itu sendiri. Ini menjamin tampilan teks yang konsisten meskipun sistem penerima tidak memiliki font yang diperlukan terpasang.

#### T: Apa hasil utama dari tutorial ini?

A: Dengan mengikuti tutorial ini, Anda telah memperoleh pengetahuan dan keterampilan untuk menanamkan font Tipe 1 standar dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Ini memastikan teks ditampilkan dengan benar di berbagai sistem.