---
title: Ekstrak Paragraf Dalam File PDF
linktitle: Ekstrak Paragraf Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mengekstrak paragraf dalam berkas PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 160
url: /id/net/programming-with-text/extract-paragraphs/
---
Tutorial ini akan memandu Anda melalui proses mengekstrak paragraf dalam file PDF menggunakan Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan.

## Persyaratan
Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau kompiler C# lainnya terinstal di komputer Anda.
- Aspose.PDF untuk pustaka .NET. Anda dapat mengunduhnya dari situs web resmi Aspose atau menggunakan pengelola paket seperti NuGet untuk menginstalnya.

## Langkah 1: Siapkan proyek
1. Buat proyek C# baru di lingkungan pengembangan pilihan Anda.
2. Tambahkan referensi ke pustaka Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan
Dalam berkas kode tempat Anda ingin mengekstrak paragraf, tambahkan perintah penggunaan berikut di bagian atas berkas:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## Langkah 3: Mengatur direktori dokumen
 Dalam kode, temukan baris yang bertuliskan`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur ke direktori tempat dokumen Anda disimpan.

## Langkah 4: Buka dokumen PDF
 Buka dokumen PDF yang ada menggunakan`Document`konstruktor dan meneruskan jalur ke berkas PDF masukan.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Langkah 5: Ekstrak paragraf
 Membuat contoh`ParagraphAbsorber` kelas dan menggunakannya`Visit` metode untuk mengekstrak paragraf dari dokumen.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## Langkah 6: Ulangi melalui paragraf
Ulangi paragraf yang diekstrak untuk mengakses konten teks. Gunakan pengulangan bersarang untuk menelusuri bagian dan baris dalam setiap paragraf.

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
// Buka file PDF yang ada
Document doc = new Document(dataDir + "input.pdf");
// Buat Instansi ParagraphAbsorber
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
Anda telah berhasil mengekstrak paragraf dari dokumen PDF menggunakan Aspose.PDF untuk .NET. Paragraf yang diekstrak telah ditampilkan di jendela konsol.

### Pertanyaan yang Sering Diajukan

#### T: Apa tujuan dari tutorial ini?

J: Tutorial ini bertujuan untuk memandu Anda melalui proses mengekstrak paragraf dari file PDF menggunakan Aspose.PDF untuk .NET. Kode sumber C# yang disertakan menyediakan langkah-langkah praktis untuk menyelesaikan tugas ini.

#### T: Namespace apa yang harus saya impor?

A: Pada berkas kode tempat Anda ingin mengekstrak paragraf, sertakan perintah penggunaan berikut di awal berkas:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### T: Bagaimana cara menentukan direktori dokumen?

 A: Temukan garisnya`string dataDir = "YOUR DOCUMENT DIRECTORY";` dalam kode dan ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

#### T: Bagaimana cara membuka dokumen PDF yang sudah ada?

 A: Pada Langkah 4, Anda akan membuka dokumen PDF yang ada menggunakan`Document` konstruktor dan menyediakan jalur ke berkas PDF masukan.

#### T: Bagaimana cara mengekstrak paragraf dari dokumen?

 A: Langkah 5 melibatkan pembuatan instance dari`ParagraphAbsorber` kelas dan menggunakannya`Visit` metode untuk mengekstrak paragraf dari dokumen PDF.

#### T: Bagaimana cara mengulangi paragraf yang diekstrak?

A: Langkah 6 memandu Anda melalui perulangan melalui paragraf yang diekstrak. Perulangan bersarang digunakan untuk melintasi bagian dan baris dalam setiap paragraf, yang pada akhirnya mengakses dan menampilkan konten teks.

#### T: Apa inti sari dari tutorial ini?

A: Dengan mengikuti tutorial ini, Anda telah mempelajari cara mengekstrak paragraf dari dokumen PDF menggunakan Aspose.PDF for .NET. Paragraf yang diekstrak telah ditampilkan di jendela konsol, memberi Anda wawasan berharga tentang struktur konten dokumen.