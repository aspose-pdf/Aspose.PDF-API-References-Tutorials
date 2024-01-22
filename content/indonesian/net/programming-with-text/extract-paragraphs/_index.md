---
title: Ekstrak Paragraf Dalam File PDF
linktitle: Ekstrak Paragraf Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara mengekstrak paragraf dalam file PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 160
url: /id/net/programming-with-text/extract-paragraphs/
---
Tutorial ini akan memandu Anda melalui proses mengekstraksi paragraf dalam file PDF menggunakan Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan.

## Persyaratan
Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau kompiler C# lainnya yang diinstal pada mesin Anda.
- Aspose.PDF untuk perpustakaan .NET. Anda dapat mendownloadnya dari situs resmi Aspose atau menggunakan manajer paket seperti NuGet untuk menginstalnya.

## Langkah 1: Siapkan proyek
1. Buat proyek C# baru di lingkungan pengembangan pilihan Anda.
2. Tambahkan referensi ke perpustakaan Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan
Dalam file kode tempat Anda ingin mengekstrak paragraf, tambahkan arahan penggunaan berikut di bagian atas file:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## Langkah 3: Atur direktori dokumen
 Dalam kode, temukan baris yang bertuliskan`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur ke direktori tempat dokumen Anda disimpan.

## Langkah 4: Buka dokumen PDF
 Buka dokumen PDF yang ada menggunakan`Document`konstruktor dan meneruskan jalur ke file PDF masukan.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Langkah 5: Ekstrak paragraf
 Buat instance`ParagraphAbsorber` kelas dan menggunakannya`Visit` metode untuk mengekstrak paragraf dari dokumen.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## Langkah 6: Ulangi paragraf
Ulangi paragraf yang diekstraksi untuk mengakses konten teks. Gunakan loop bersarang untuk melintasi bagian dan garis dalam setiap paragraf.

```csharp
foreach(PageMarkup markup in absorber.PageMarkups)
{
     int i = 1;
     foreach(MarkupSection section in markup.Sections)
     {
         int j = 1;
         foreach(MarkupParagraph paragraph in section.Paragraphs)
         {
             StringBuilder paragraphText = new StringBuilder();
             foreach(List<TextFragment> line in paragraph.Lines)
             {
                 foreach(TextFragment fragment in line)
                 {
                     paragraphText.Append(fragment.Text);
                 }
                 paragraphText. Append("\r\n");
             }
             paragraphText. Append("\r\n");
             Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
             Console.WriteLine(paragraphText.ToString());
             j++;
         }
         i++;
     }
}
```

### Contoh kode sumber untuk Ekstrak Paragraf menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Buka file PDF yang ada
Document doc = new Document(dataDir + "input.pdf");
// Buat instance ParagraphAbsorber
ParagraphAbsorber absorber = new ParagraphAbsorber();
absorber.Visit(doc);
foreach (PageMarkup markup in absorber.PageMarkups)
{
	int i = 1;
	foreach (MarkupSection section in markup.Sections)
	{
		int j = 1;
		foreach (MarkupParagraph paragraph in section.Paragraphs)
		{
			StringBuilder paragraphText = new StringBuilder();
			foreach (List<TextFragment> line in paragraph.Lines)
			{
				foreach (TextFragment fragment in line)
				{
					paragraphText.Append(fragment.Text);
				}
				paragraphText.Append("\r\n");
			}
			paragraphText.Append("\r\n");
			Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
			Console.WriteLine(paragraphText.ToString());
			j++;
		}
		i++;
	}
}
```

## Kesimpulan
Anda telah berhasil mengekstrak paragraf dari dokumen PDF menggunakan Aspose.PDF untuk .NET. Paragraf yang diekstraksi telah ditampilkan di jendela konsol.

### FAQ

#### T: Apa tujuan dari tutorial ini?

J: Tutorial ini bertujuan untuk memandu Anda melalui proses mengekstraksi paragraf dari file PDF menggunakan Aspose.PDF untuk .NET. Kode sumber C# yang menyertainya memberikan langkah-langkah praktis untuk mencapai tugas ini.

#### T: Namespace apa yang harus saya impor?

J: Dalam file kode tempat Anda ingin mengekstrak paragraf, sertakan arahan penggunaan berikut di awal file:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### T: Bagaimana cara menentukan direktori dokumen?

 A: Temukan garisnya`string dataDir = "YOUR DOCUMENT DIRECTORY";` dalam kode dan ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

#### T: Bagaimana cara membuka dokumen PDF yang sudah ada?

 J: Pada Langkah 4, Anda akan membuka dokumen PDF yang ada menggunakan`Document` konstruktor dan menyediakan jalur ke file PDF masukan.

#### T: Bagaimana cara mengekstrak paragraf dari dokumen?

 J: Langkah 5 melibatkan pembuatan sebuah instance dari`ParagraphAbsorber` kelas dan menggunakannya`Visit` metode untuk mengekstrak paragraf dari dokumen PDF.

#### T: Bagaimana cara saya mengulangi paragraf yang diekstraksi?

J: Langkah 6 memandu Anda melalui perulangan paragraf yang diekstraksi. Loop bersarang digunakan untuk melintasi bagian dan baris dalam setiap paragraf, pada akhirnya mengakses dan menampilkan konten teks.

#### T: Apa inti dari tutorial ini?

J: Dengan mengikuti tutorial ini, Anda telah mempelajari cara mengekstrak paragraf dari dokumen PDF menggunakan Aspose.PDF untuk .NET. Paragraf yang diekstraksi telah ditampilkan di jendela konsol, memberi Anda wawasan berharga tentang struktur konten dokumen.