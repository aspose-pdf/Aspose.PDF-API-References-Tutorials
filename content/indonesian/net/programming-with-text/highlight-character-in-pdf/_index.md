---
title: Sorot Karakter Dalam File PDF
linktitle: Sorot Karakter Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menyorot karakter dalam berkas PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 240
url: /id/net/programming-with-text/highlight-character-in-pdf/
---
Dalam tutorial ini, kami akan menjelaskan cara menyorot karakter dalam file PDF menggunakan pustaka Aspose.PDF untuk .NET. Kami akan membahas proses langkah demi langkah untuk menyorot karakter dalam PDF menggunakan kode sumber C# yang disediakan.

## Persyaratan

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Pustaka Aspose.PDF untuk .NET terinstal.
- Pemahaman dasar tentang pemrograman C#.

## Langkah 1: Siapkan Direktori Dokumen

 Pertama, Anda perlu mengatur jalur ke direktori tempat file PDF input Anda berada. Ganti`"YOUR DOCUMENT DIRECTORY"` di dalam`dataDir` variabel dengan jalur ke berkas PDF Anda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Muat Dokumen PDF

 Selanjutnya kita muat dokumen PDF input menggunakan`Aspose.Pdf.Document` kelas.

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## Langkah 3: Ubah PDF ke Gambar

 Untuk menyorot karakter, kami mengonversi dokumen PDF menjadi gambar menggunakan`PdfConverter` kelas. Kami mengatur resolusi untuk konversi dan mengambil gambar sebagai`Bitmap` obyek.

```csharp
int resolution = 150;
using (MemoryStream ms = new MemoryStream())
{
     PdfConverter conv = new PdfConverter(pdfDocument);
     conv. Resolution = new Resolution(resolution, resolution);
     conv. GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
     Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```

## Langkah 4: Sorot Karakter

 Kami mengulang setiap halaman dokumen PDF dan menggunakan`TextFragmentAbsorber` objek untuk menemukan semua kata di halaman. Kami kemudian mengulangi fragmen teks, segmen, dan karakter untuk menyorotnya menggunakan persegi panjang.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     // Atur skala dan transformasi
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     // Berulang melalui halaman
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         //Temukan semua kata di halaman
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         // Ulangi melalui fragmen teks
         foreach(TextFragment textFragment in textFragmentCollection)
         {
             if (i == 0)
             {
                 // Sorot karakter
                 gr.DrawRectangle(
                     Think.Yellow,
                     (float)textFragment.Position.XIndent,
                     (float)textFragment.Position.YIndent,
                     (float)textFragment.Rectangle.Width,
                     (float)textFragment.Rectangle.Height);

                 // Ulangi melalui segmen
                 foreach(TextSegment segment in textFragment.Segments)
                 {
                     // Sorot segmen
                     gr.DrawRectangle(
                         Think Green,
                         (float)segment.Rectangle.LLX,
                         (float)segment.Rectangle.LLY,
                         (float)segment.Rectangle.Width,
                         (float)segment.Rectangle.Height);

                     // Ulangi melalui karakter
                     foreach(CharInfo characterInfo in segment.Characters)
                     {
                         // Sorot karakter
                         gr.DrawRectangle(
                             Think.Black,
                             (float)characterInfo.Rectangle.LLx,
                             (float)characterInfo.Rectangle.LLY,
                             (float)characterInfo.Rectangle.Width,
                             (float)characterInfo.Rectangle.Height);
                     }
                 }
             }
         }
     }
}
```

## Langkah 5: Simpan Gambar Output

Terakhir, kami menyimpan gambar yang dimodifikasi dengan karakter yang disorot ke file keluaran yang ditentukan.

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### Contoh kode sumber untuk Menyorot Karakter dalam PDF menggunakan Aspose.PDF untuk .NET 
```csharp
try
{
	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	int resolution = 150;
	Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
	using (MemoryStream ms = new MemoryStream())
	{
		PdfConverter conv = new PdfConverter(pdfDocument);
		conv.Resolution = new Resolution(resolution, resolution);
		conv.GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
		using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
		{
			float scale = resolution / 72f;
			gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);
			for (int i = 0; i < pdfDocument.Pages.Count; i++)
			{
				Page page = pdfDocument.Pages[1];
				// Buat objek TextAbsorber untuk menemukan semua kata
				TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
				textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
				page.Accept(textFragmentAbsorber);
				// Dapatkan fragmen teks yang diekstraksi
				TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
				// Ulangi melalui fragmen
				foreach (TextFragment textFragment in textFragmentCollection)
				{
					if (i == 0)
					{
						gr.DrawRectangle(
						Pens.Yellow,
						(float)textFragment.Position.XIndent,
						(float)textFragment.Position.YIndent,
						(float)textFragment.Rectangle.Width,
						(float)textFragment.Rectangle.Height);
						for (int segNum = 1; segNum <= textFragment.Segments.Count; segNum++)
						{
							TextSegment segment = textFragment.Segments[segNum];
							for (int charNum = 1; charNum <= segment.Characters.Count; charNum++)
							{
								CharInfo characterInfo = segment.Characters[charNum];
								Aspose.Pdf.Rectangle rect = page.GetPageRect(true);
								Console.WriteLine("TextFragment = " + textFragment.Text + "    Page URY = " + rect.URY +
												  "   TextFragment URY = " + textFragment.Rectangle.URY);
								gr.DrawRectangle(
								Pens.Black,
								(float)characterInfo.Rectangle.LLX,
								(float)characterInfo.Rectangle.LLY,
								(float)characterInfo.Rectangle.Width,
								(float)characterInfo.Rectangle.Height);
							}
							gr.DrawRectangle(
							Pens.Green,
							(float)segment.Rectangle.LLX,
							(float)segment.Rectangle.LLY,
							(float)segment.Rectangle.Width,
							(float)segment.Rectangle.Height);
						}
					}
				}
			}
		}
		dataDir = dataDir + "HighlightCharacterInPDF_out.png";
		bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
	}
	Console.WriteLine("\nCharacters highlighted successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara menyorot karakter dalam dokumen PDF menggunakan pustaka Aspose.PDF untuk .NET. Dengan mengikuti panduan langkah demi langkah dan menjalankan kode C# yang disediakan, Anda dapat menyorot karakter dalam PDF dan menyimpan hasilnya sebagai gambar.

### Pertanyaan yang Sering Diajukan

#### T: Apa tujuan dari tutorial "Menyorot Karakter dalam Berkas PDF"?

J: Tutorial "Sorot Karakter dalam Berkas PDF" menjelaskan cara menggunakan pustaka Aspose.PDF untuk .NET guna menyorot karakter dalam dokumen PDF. Tutorial ini menyediakan panduan langkah demi langkah dan kode sumber C# untuk mencapainya.

#### T: Mengapa saya ingin menyorot karakter dalam dokumen PDF?

A: Menyorot karakter dalam dokumen PDF dapat berguna untuk berbagai tujuan, seperti menekankan konten tertentu atau membuat teks tertentu lebih terlihat dan dapat dibedakan.

#### T: Bagaimana cara mengatur direktori dokumen?

A: Untuk mengatur direktori dokumen:

1.  Mengganti`"YOUR DOCUMENT DIRECTORY"` di dalam`dataDir` variabel dengan jalur ke direktori tempat berkas PDF masukan Anda berada.

#### T: Bagaimana cara memuat dokumen PDF dan mengubahnya menjadi gambar?

 A: Dalam tutorialnya,`Aspose.Pdf.Document` kelas digunakan untuk memuat dokumen PDF input. Kemudian,`PdfConverter` kelas digunakan untuk mengubah dokumen PDF menjadi gambar. Resolusi gambar diatur, dan gambar diambil sebagai`Bitmap` obyek.

#### T: Bagaimana cara menyorot karakter pada gambar dokumen PDF?

A: Tutorial ini memandu Anda melalui proses perulangan melalui setiap halaman dokumen PDF, menemukan kata-kata menggunakan`TextFragmentAbsorber`, dan mengulangi fragmen teks, segmen, dan karakter untuk menyorotnya menggunakan persegi panjang.

#### T: Dapatkah saya menyesuaikan tampilan karakter dan segmen yang disorot?

A: Ya, Anda dapat menyesuaikan tampilan karakter dan segmen yang disorot dengan memodifikasi warna dan gaya yang digunakan dalam operasi menggambar.

#### T: Bagaimana cara menyimpan gambar yang dimodifikasi dengan karakter yang disorot?

 A: Tutorial ini menunjukkan cara menyimpan gambar yang dimodifikasi dengan karakter yang disorot ke file keluaran yang ditentukan menggunakan`Save` metode dari`Bitmap` kelas.

#### T: Apakah Lisensi Aspose yang valid diperlukan untuk tutorial ini?

A: Ya, Lisensi Aspose yang valid diperlukan agar tutorial ini dapat berfungsi dengan benar. Anda dapat membeli lisensi penuh atau memperoleh lisensi sementara selama 30 hari dari situs web Aspose.