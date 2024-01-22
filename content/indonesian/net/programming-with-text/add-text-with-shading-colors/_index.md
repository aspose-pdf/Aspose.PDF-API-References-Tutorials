---
title: Tambahkan Teks Dengan Warna Bayangan Dalam File PDF
linktitle: Tambahkan Teks Dengan Warna Bayangan Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menambahkan teks dengan warna arsiran dalam file PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 80
url: /id/net/programming-with-text/add-text-with-shading-colors/
---
Tutorial ini akan memandu Anda melalui proses menambahkan teks dengan warna arsiran dalam file PDF menggunakan Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan.

## Persyaratan
Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau kompiler C# lainnya yang diinstal pada mesin Anda.
- Aspose.PDF untuk perpustakaan .NET. Anda dapat mendownloadnya dari situs resmi Aspose atau menggunakan manajer paket seperti NuGet untuk menginstalnya.

## Langkah 1: Siapkan proyek
1. Buat proyek C# baru di lingkungan pengembangan pilihan Anda.
2. Tambahkan referensi ke perpustakaan Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan
Dalam file kode di mana Anda ingin menambahkan teks dengan warna arsiran, tambahkan arahan penggunaan berikut di bagian atas file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## Langkah 3: Atur direktori dokumen
 Dalam kode, temukan baris yang bertuliskan`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur ke direktori tempat dokumen Anda disimpan.

## Langkah 4: Muat dokumen PDF
 Muat dokumen PDF yang ada menggunakan`Document` konstruktor dan menyediakan jalur ke file dokumen.

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Kode ada di sini...
}
```

## Langkah 5: Temukan teks yang akan diubah
 Menggunakan`TextFragmentAbsorber` untuk menemukan teks yang diinginkan dalam dokumen. Pada kode yang diberikan, terlihat teks "Lorem ipsum".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorb);
TextFragment textFragment = absorb.TextFragments[1];
```

## Langkah 6: Tetapkan warna bayangan untuk teks
 Buat yang baru`Color` objek dengan ruang warna pola dan tentukan warna bayangan gradien. Tetapkan warna ini ke`ForegroundColor` properti dari`TextState` dari`TextFragment` obyek.

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

## Langkah 7: Terapkan pemformatan teks tambahan (opsional)
 Anda dapat menerapkan pemformatan tambahan pada fragmen teks, misalnya menggarisbawahi, dengan memodifikasi properti`TextState` obyek.

```csharp
textFragment.TextState.Underline = true;
```

## Langkah 8: Simpan dokumen PDF yang dimodifikasi
 Simpan dokumen PDF yang dimodifikasi menggunakan`Save` metode`Document` obyek.

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

### Contoh kode sumber untuk Menambahkan Teks Dengan Warna Bayangan menggunakan Aspose.PDF untuk .NET 
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
Anda telah berhasil menambahkan teks dengan warna arsiran ke dokumen PDF Anda menggunakan Aspose.PDF untuk .NET. File PDF yang dihasilkan sekarang dapat ditemukan di jalur file keluaran yang ditentukan.

### FAQ

#### Q: Apa fokus utama tutorial ini?

J: Tutorial ini memandu Anda melalui proses menambahkan teks dengan warna arsiran ke file PDF menggunakan pustaka Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan untuk mencapai hal ini.

#### T: Namespace manakah yang perlu saya impor untuk tutorial ini?

A: Dalam file kode di mana Anda ingin menambahkan teks dengan warna arsir, impor namespace berikut di awal file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

#### T: Bagaimana cara menentukan direktori dokumen?

 A: Di dalam kode, temukan barisnya`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

#### T: Bagaimana cara memuat dokumen PDF yang sudah ada?

 J: Pada Langkah 4, Anda akan memuat dokumen PDF yang sudah ada menggunakan`Document` konstruktor dan menyediakan jalur ke file dokumen:

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Kode ada di sini...
}
```

#### T: Bagaimana cara menemukan dan mengubah teks tertentu dalam dokumen PDF?

 J: Pada Langkah 5, Anda akan menggunakan`TextFragmentAbsorber`untuk menemukan teks yang diinginkan dalam dokumen. Kemudian, Anda dapat mengubah propertinya:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorber);
TextFragment textFragment = absorber.TextFragments[1];
```

#### T: Bagaimana cara mengatur warna bayangan pada teks?

 J: Pada Langkah 6, Anda akan membuat yang baru`Color` objek dengan ruang warna pola dan tentukan warna bayangan gradien. Tetapkan warna ini ke`ForegroundColor` properti dari`TextState` dari`TextFragment` obyek:

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

#### T: Dapatkah saya menerapkan pemformatan teks tambahan pada teks yang diubah?

 J: Ya, pada Langkah 7, Anda dapat menerapkan pemformatan teks tambahan seperti garis bawah dengan memodifikasi properti`TextState` obyek:

```csharp
textFragment.TextState.Underline = true;
```

#### T: Bagaimana cara menyimpan dokumen PDF yang dimodifikasi?

 J: Pada Langkah 8, Anda akan menyimpan dokumen PDF yang dimodifikasi menggunakan`Save` metode`Document` obyek:

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

#### T: Apa manfaat utama dari tutorial ini?

J: Dengan mengikuti tutorial ini, Anda telah berhasil mempelajari cara menyempurnakan dokumen PDF Anda dengan menambahkan teks dengan warna arsir menggunakan Aspose.PDF untuk .NET. Ini bisa sangat berguna untuk menyorot dan menekankan konten teks tertentu dalam file PDF Anda.