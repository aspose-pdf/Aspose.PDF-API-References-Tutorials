---
title: Mengekstrak Gambar
linktitle: Mengekstrak Gambar
second_title: Aspose.PDF untuk Referensi .NET API
description: Ekstrak gambar dengan mudah dari dokumen PDF dengan Aspose.PDF untuk .NET.
type: docs
weight: 70
url: /id/net/programming-with-security-and-signatures/extracting-image/
---
Mengekstrak gambar dari dokumen PDF dapat berguna dalam banyak kasus. Dengan Aspose.PDF untuk .NET, Anda dapat mengekstrak gambar dengan mudah menggunakan kode sumber berikut:

## Langkah 1: Impor perpustakaan yang diperlukan

Sebelum memulai, Anda perlu mengimpor perpustakaan yang diperlukan untuk proyek C# Anda. Berikut adalah arahan impor yang diperlukan:

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## Langkah 2: Tetapkan jalur ke folder dokumen

 Pada langkah ini, Anda perlu menentukan jalur ke folder yang berisi file PDF tempat Anda ingin mengekstrak gambarnya. Mengganti`"YOUR DOCUMENTS DIRECTORY"`dalam kode berikut dengan jalur sebenarnya ke folder dokumen Anda:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## Langkah 3: Ekstrak gambar dari dokumen PDF

Sekarang kita akan mengekstrak gambar dari dokumen PDF menggunakan kode berikut:

```csharp
using (Document pdfDocument = new Document(input))
{
foreach(Field field in pdfDocument.Form)
{
SignatureField sf = field as SignatureField;
if (sf != null)
{
string outFile = dataDir + @"output_out.jpg";
using (Stream imageStream = sf.ExtractImage())
{
if (imageStream != null)
{
using (Image image = Bitmap.FromStream(imageStream))
{
image.Save(outFile, ImageFormat.Jpeg);
}
}
}
}
}
}
```

Dalam contoh ini, kita mengulang setiap bidang formulir di dokumen PDF. Jika bidang tanda tangan ditemukan, kami mengekstrak gambar terkait dan menyimpannya ke file JPEG.

### Contoh kode sumber untuk Mengekstraksi Gambar menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir+ @"ExtractingImage.pdf";
using (Document pdfDocument = new Document(input))
{
	foreach (Field field in pdfDocument.Form)
	{
		SignatureField sf = field as SignatureField;
		if (sf != null)
		{
			string outFile = dataDir+ @"output_out.jpg";
			using (Stream imageStream = sf.ExtractImage())
			{
				if (imageStream != null)
				{
					using (System.Drawing.Image image = Bitmap.FromStream(imageStream))
					{
						image.Save(outFile, System.Drawing.Imaging.ImageFormat.Jpeg);
					}
				}
			}
		}
	}
}
```

## Kesimpulan

Selamat! Sekarang Anda memiliki panduan langkah demi langkah untuk mengekstrak gambar dari dokumen PDF menggunakan Aspose.PDF untuk .NET. Anda dapat mengintegrasikan kode ini ke dalam proyek Anda sendiri untuk mengekstrak gambar dan menggunakannya sesuai kebutuhan.

Pastikan untuk memeriksa dokumentasi resmi Aspose.PDF untuk informasi lebih lanjut tentang ekstraksi gambar tingkat lanjut dan fitur manipulasi dokumen PDF.


### FAQ

#### T: Apakah Aspose.PDF untuk .NET cocok untuk pemula?

J: Meskipun pemahaman tentang pemrograman C# sangat membantu, tutorial kami dirancang agar ramah bagi pemula, memandu Anda melalui setiap langkah.

#### T: Bisakah saya mengekstrak banyak gambar sekaligus?

J: Tentu saja! Dengan menerapkan loop dan mengadaptasi kode yang disediakan, Anda dapat mengekstrak banyak gambar dari satu dokumen PDF.

#### T: Apakah Aspose.PDF untuk .NET merupakan satu-satunya solusi untuk ekstraksi gambar?

J: Meskipun ada alat lain yang tersedia, Aspose.PDF untuk .NET terkenal dengan efisiensi dan fiturnya yang lengkap.

#### T: Dapatkah saya menggunakan gambar yang diekstrak untuk tujuan komersial?

A: Ya, setelah diekstraksi, gambar tersebut menjadi milik Anda untuk digunakan sesuai kebutuhan, termasuk untuk proyek komersial.

#### T: Di mana saya dapat menemukan lebih banyak sumber daya tentang manipulasi PDF dengan Aspose.PDF?

J: Kunjungi dokumentasi resmi kami untuk mendapatkan banyak sumber daya dan wawasan tentang manipulasi PDF tingkat lanjut dengan Aspose.PDF untuk .NET.