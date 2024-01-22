---
title: Coret Kata-kata
linktitle: Coret Kata-kata
second_title: Aspose.PDF untuk Referensi .NET API
description: Artikel ini memberikan panduan langkah demi langkah untuk menggunakan Aspose.PDF untuk fitur Strike Out Words .NET, termasuk panduan langkah demi langkah dan penjelasannya
type: docs
weight: 150
url: /id/net/annotations/strikeoutwords/
---
Aspose.PDF untuk .NET adalah perpustakaan manipulasi dan pemrosesan dokumen PDF yang menyediakan berbagai fitur untuk membuat, memodifikasi, dan mengonversi file PDF. Salah satu fitur berguna yang disediakan Aspose.PDF adalah kemampuan untuk mencoret kata atau frasa dalam dokumen PDF menggunakan kode sumber C#. Pada artikel ini, kami akan memberikan panduan langkah demi langkah tentang cara mencoret kata menggunakan Aspose.PDF untuk .NET.

## Langkah 1: Memuat dokumen PDF
Langkah pertama adalah memuat dokumen PDF yang ingin Anda modifikasi. Dalam tutorial ini, kita akan memuat dokumen PDF bernama "input.pdf" dari folder "DIREKTORI DOKUMEN ANDA". 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "input.pdf");
```

## Langkah 2: Mencari fragmen teks
Untuk mencoret kata atau frasa tertentu dalam dokumen PDF, Anda harus mencarinya terlebih dahulu. Aspose.PDF menyediakan kelas TextFragmentAbsorber yang dapat digunakan untuk mencari fragmen teks tertentu dalam dokumen PDF.

```csharp
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

Pada kode di atas, kami mencari fragmen teks "Estoque" di dokumen PDF. Anda dapat memodifikasinya untuk mencari kata atau frasa lain yang ingin Anda coret.

## Langkah 3: Mencoret bagian teks
Setelah menemukan potongan teks, langkah selanjutnya adalah mencoretnya. Aspose.PDF menyediakan kelas StrikeOutAnnotation yang dapat digunakan untuk membuat anotasi coretan untuk fragmen teks. 

```csharp
Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle((float)textFragment.Position.XIndent, (float)textFragment.Position.YIndent, (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width, (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
strikeOut.Opacity = .80f;
strikeOut.Border = new Border(strikeOut);
strikeOut.Color = Aspose.Pdf.Color.Red;
textFragment.Page.Annotations.Add(strikeOut);
```

Dalam kode di atas, kami membuat anotasi coretan untuk setiap fragmen teks yang kami temukan. Kami juga mengatur opasitas, batas, dan warna anotasi yang dicoret.

## Langkah 4: Menyimpan dokumen PDF yang dimodifikasi
Setelah mencoret bagian teks, simpan dokumen yang dimodifikasi.

```csharp
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

### Contoh kode sumber untuk Coret Kata menggunakan Aspose.PDF untuk .NET


```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buka dokumen
Document document = new Document(dataDir + "input.pdf");

// Buat instance TextFragment Absorber untuk mencari fragmen teks tertentu
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
// Iterasi melalui halaman dokumen PDF
for (int i = 1; i <= document.Pages.Count; i++)
{
	// Dapatkan halaman pertama dokumen PDF
	Page page = document.Pages[1];
	page.Accept(textFragmentAbsorber);
}

// Buat kumpulan teks yang diserap
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

//Ulangi koleksi di atas
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

	// Dapatkan dimensi persegi panjang dari objek TextFragment
	Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
				(float)textFragment.Position.XIndent,
				(float)textFragment.Position.YIndent,
				(float)textFragment.Position.XIndent +
				(float)textFragment.Rectangle.Width,
				(float)textFragment.Position.YIndent +
				(float)textFragment.Rectangle.Height);

	// Buat instance Anotasi StrikeOut
	StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
	// Atur opacity untuk anotasi
	strikeOut.Opacity = .80f;
	// Tetapkan batas untuk contoh anotasi
	strikeOut.Border = new Border(strikeOut);
	// Atur warna anotasi
	strikeOut.Color = Aspose.Pdf.Color.Red;
	// Tambahkan anotasi ke koleksi anotasi TextFragment
	textFragment.Page.Annotations.Add(strikeOut);
}
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara menggunakan Aspose.PDF untuk .NET untuk mencoret kata-kata tertentu dalam dokumen PDF. Dengan mengikuti panduan langkah demi langkah dan menggunakan kode sumber C# yang disediakan, Anda dapat dengan mudah memuat dokumen PDF, mencari fragmen teks tertentu, dan membuat anotasi coretan untuk menandai dan mencoret kata-kata tersebut secara visual. Aspose.PDF untuk .NET menyediakan cara sederhana dan efektif untuk memanipulasi dokumen PDF secara terprogram, menjadikannya alat yang berharga bagi pengembang yang bekerja dengan file PDF di aplikasi .NET.

### FAQ

#### T: Apa itu Aspose.PDF untuk .NET?

J: Aspose.PDF untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang membuat, mengedit, dan memanipulasi dokumen PDF secara terprogram dalam aplikasi .NET. Ini menyediakan berbagai fitur untuk bekerja dengan file PDF, termasuk ekstraksi teks, penanganan anotasi, pengisian formulir, dan banyak lagi.

#### T: Dapatkah saya menggunakan Aspose.PDF untuk .NET untuk mencoret kata-kata tertentu dalam dokumen PDF?

J: Ya, Aspose.PDF untuk .NET menyediakan fungsionalitas untuk mencari fragmen teks tertentu dalam dokumen PDF dan kemudian membuat anotasi coretan untuk menandai dan mencoret kata-kata tersebut secara visual.

#### T: Bagaimana cara menentukan teks yang ingin saya coret di dokumen PDF?

 A: Untuk menentukan teks yang ingin dicoret, Anda dapat menggunakan`TextFragmentAbsorber` kelas yang disediakan oleh Aspose.PDF untuk .NET. Ini memungkinkan Anda mencari bagian teks tertentu dalam dokumen PDF berdasarkan kriteria yang Anda inginkan.

#### T: Dapatkah saya menyesuaikan tampilan anotasi yang dicoret?

J: Ya, Anda dapat menyesuaikan berbagai properti anotasi yang dicoret, seperti opasitas, gaya batas, dan warna. Hal ini memungkinkan Anda menyesuaikan tampilan anotasi yang dicoret dengan kebutuhan spesifik Anda.