---
title: Tambahkan Teks Dengan Warna Bayangan Dalam File PDF
linktitle: Tambahkan Teks Dengan Warna Bayangan Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menambahkan teks dengan warna bayangan dalam berkas PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 80
url: /id/net/programming-with-text/add-text-with-shading-colors/
---
Tutorial ini akan memandu Anda melalui proses penambahan teks dengan warna bayangan dalam berkas PDF menggunakan Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan.

## Persyaratan
Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau kompiler C# lainnya terinstal di komputer Anda.
- Aspose.PDF untuk pustaka .NET. Anda dapat mengunduhnya dari situs web resmi Aspose atau menggunakan pengelola paket seperti NuGet untuk menginstalnya.

## Langkah 1: Siapkan proyek
1. Buat proyek C# baru di lingkungan pengembangan pilihan Anda.
2. Tambahkan referensi ke pustaka Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan
Pada berkas kode tempat Anda ingin menambahkan teks dengan warna bayangan, tambahkan perintah using berikut di bagian atas berkas:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## Langkah 3: Mengatur direktori dokumen
 Dalam kode, temukan baris yang bertuliskan`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur ke direktori tempat dokumen Anda disimpan.

## Langkah 4: Muat dokumen PDF
 Muat dokumen PDF yang ada menggunakan`Document` konstruktor dan menyediakan jalur ke berkas dokumen.

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Kodenya ada di sini...
}
```

## Langkah 5: Temukan teks yang akan dimodifikasi
Menggunakan`TextFragmentAbsorber` untuk menemukan teks yang diinginkan dalam dokumen. Dalam kode yang diberikan, teks "Lorem ipsum" dicari.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorb);
TextFragment textFragment = absorb.TextFragments[1];
```

## Langkah 6: Mengatur warna bayangan untuk teks
 Buat yang baru`Color` objek dengan ruang warna pola dan tentukan warna bayangan gradien. Tetapkan warna ini ke`ForegroundColor` milik`TextState` dari`TextFragment` obyek.

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

## Langkah 7: Terapkan format teks tambahan (opsional)
 Anda dapat menerapkan pemformatan tambahan ke fragmen teks, seperti menggarisbawahi, dengan memodifikasi properti`TextState` obyek.

```csharp
textFragment.TextState.Underline = true;
```

## Langkah 8: Simpan dokumen PDF yang dimodifikasi
 Simpan dokumen PDF yang dimodifikasi menggunakan`Save` metode dari`Document` obyek.

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

### Contoh kode sumber untuk Menambahkan Teks dengan Warna Bayangan menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
	TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
	pdfDocument.Pages.Accept(absorber);
	TextFragment textFragment = absorber.TextFragments[1];
	// Buat warna baru dengan ruang warna pola
	textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
	{
		PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
	};
	textFragment.TextState.Underline = true;
	pdfDocument.Save(dataDir + "text_out.pdf");
}
```

## Kesimpulan
Anda telah berhasil menambahkan teks dengan warna bayangan ke dokumen PDF Anda menggunakan Aspose.PDF untuk .NET. File PDF yang dihasilkan sekarang dapat ditemukan di jalur file keluaran yang ditentukan.

### Pertanyaan yang Sering Diajukan

#### T: Apa fokus utama tutorial ini?

J: Tutorial ini memandu Anda melalui proses penambahan teks dengan warna bayangan ke berkas PDF menggunakan pustaka Aspose.PDF for .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan untuk mencapainya.

#### T: Namespace mana yang perlu saya impor untuk tutorial ini?

A: Pada berkas kode tempat Anda ingin menambahkan teks dengan warna bayangan, impor namespace berikut di awal berkas:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

#### T: Bagaimana cara menentukan direktori dokumen?

 A: Pada kode tersebut, temukan baris`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

#### T: Bagaimana cara memuat dokumen PDF yang ada?

 A: Pada Langkah 4, Anda akan memuat dokumen PDF yang ada menggunakan`Document` konstruktor dan menyediakan jalur ke berkas dokumen:

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Kodenya ada di sini...
}
```

#### T: Bagaimana cara menemukan dan mengubah teks tertentu dalam dokumen PDF?

 A: Pada Langkah 5, Anda akan menggunakan`TextFragmentAbsorber` untuk menemukan teks yang diinginkan dalam dokumen. Kemudian, Anda dapat mengubah propertinya:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorber);
TextFragment textFragment = absorber.TextFragments[1];
```

#### T: Bagaimana cara mengatur warna bayangan untuk teks?

 A: Pada Langkah 6, Anda akan membuat yang baru`Color` objek dengan ruang warna pola dan tentukan warna bayangan gradien. Tetapkan warna ini ke`ForegroundColor` milik`TextState` dari`TextFragment` obyek:

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

#### T: Dapatkah saya menerapkan format teks tambahan pada teks yang dimodifikasi?

A: Ya, pada Langkah 7, Anda dapat menerapkan pemformatan teks tambahan seperti garis bawah dengan memodifikasi properti`TextState` obyek:

```csharp
textFragment.TextState.Underline = true;
```

#### T: Bagaimana cara menyimpan dokumen PDF yang dimodifikasi?

 A: Pada Langkah 8, Anda akan menyimpan dokumen PDF yang dimodifikasi menggunakan`Save` metode dari`Document` obyek:

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

#### T: Apa hasil utama dari tutorial ini?

A: Dengan mengikuti tutorial ini, Anda telah berhasil mempelajari cara menyempurnakan dokumen PDF Anda dengan menambahkan teks dengan warna bayangan menggunakan Aspose.PDF untuk .NET. Ini dapat sangat berguna untuk menyorot dan menekankan konten teks tertentu dalam file PDF Anda.