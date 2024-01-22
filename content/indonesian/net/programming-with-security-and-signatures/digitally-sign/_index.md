---
title: Masuk File PDF Secara Digital
linktitle: Masuk File PDF Secara Digital
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara masuk secara digital ke file PDF dengan Aspose.PDF untuk .NET.
type: docs
weight: 40
url: /id/net/programming-with-security-and-signatures/digitally-sign/
---
Dalam tutorial ini, kami akan memandu Anda melalui proses penandatanganan file PDF secara digital menggunakan Aspose.PDF untuk .NET. Tanda tangan digital menjamin keaslian dan integritas dokumen, dengan menambahkan sidik jari elektronik yang unik.

## Langkah 1: Prasyarat

Sebelum memulai, pastikan Anda memiliki prasyarat berikut:

- Pengetahuan dasar tentang bahasa pemrograman C#
- Menginstal Visual Studio di mesin Anda
- Pustaka Aspose.PDF untuk .NET diinstal

## Langkah 2: Pengaturan lingkungan

Untuk memulai, ikuti langkah-langkah berikut untuk menyiapkan lingkungan pengembangan Anda:

1. Buka Visual Studio dan buat proyek C# baru.
2. Impor namespace yang diperlukan ke dalam file kode Anda:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
```

## Langkah 3: Tanda tangan digital

Langkah pertama adalah menandatangani file PDF secara digital. Kode yang diberikan menunjukkan cara membuat tanda tangan digital dengan Aspose.PDF untuk .NET.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pbxFile = "";
string inFile = dataDir + @"DigitallySign.pdf";
string outFile = dataDir + @"DigitallySign_out.pdf";
using (Document document = new Document(inFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pbxFile, "WebSales");
         DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
         signature.Certify(1, "Reason for signing", "Contact", "Location", true, rect, docMdpSignature);
         signature.Save(outFile);
     }
}
```

Kode ini memuat file PDF, membuat tanda tangan digital dengan tampilan tertentu, lalu menyimpan file PDF dengan tanda tangan tambahan.

## Langkah 4: Verifikasi Tanda Tangan

Setelah menambahkan tanda tangan digital, Anda dapat memeriksa apakah file PDF berisi tanda tangan yang valid.

```csharp
using(Document document = new Document(outFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         IList<string> sigNames = signature. GetSignNames();
         if (sigNames.Count > 0)
         {
             if (signature.VerifySigned(sigNames[0] as string))
             {
                 if (signature.IsCertified)
                 {
                     if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms)
                     {
                         // Lakukan sesuatu
                     }
                 }
             }
         }
     }
}
```

Kode ini memverifikasi tanda tangan pertama dari file PDF dan melakukan tindakan tambahan jika tanda tangan tersebut bersertifikat dan memiliki izin khusus.

### Contoh kode sumber untuk Tanda Tangan Digital menggunakan Aspose.PDF untuk .NET 
```csharp
try
{
	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string pbxFile = "";
	string inFile = dataDir + @"DigitallySign.pdf";
	string outFile = dataDir + @"DigitallySign_out.pdf";
	using (Document document = new Document(inFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			PKCS7 pkcs = new PKCS7(pbxFile, "WebSales"); // Gunakan objek PKCS7/PKCS7Detached
			DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
			System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
			// Atur tampilan tanda tangan
			signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
			// Buat salah satu dari tiga jenis tanda tangan
			signature.Certify(1, "Signature Reason", "Contact", "Location", true, rect, docMdpSignature);
			// Simpan file PDF keluaran
			signature.Save(outFile);
		}
	}
	using (Document document = new Document(outFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			IList<string> sigNames = signature.GetSignNames();
			if (sigNames.Count > 0) // Ada tanda tangan?
			{
				if (signature.VerifySigned(sigNames[0] as string)) // Verifikasi yang pertama
				{
					if (signature.IsCertified) // Bersertifikat?
					{
						if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms) // Dapatkan izin akses
						{
							// Lakukan sesuatu
						}
					}
				}
			}
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Kesimpulan

Selamat! Anda telah berhasil melakukan tanda tangan digital pada file PDF menggunakan Aspose.PDF untuk .NET. Tutorial ini mencakup proses langkah demi langkah, mulai dari menambahkan tanda tangan digital hingga memverifikasi validitasnya. Anda sekarang dapat menggunakan fitur ini untuk mengamankan file PDF Anda dengan tanda tangan digital.

### FAQ

#### T: Apa tujuan dari tutorial ini?

J: Tutorial ini memandu Anda melalui proses penandatanganan file PDF secara digital menggunakan Aspose.PDF untuk .NET. Tanda tangan digital menambahkan sidik jari elektronik untuk memastikan keaslian dan integritas dokumen.

#### Q: Prasyarat apa saja yang diperlukan sebelum memulai?

J: Sebelum memulai, pastikan Anda memiliki pemahaman dasar tentang bahasa pemrograman C#, telah menginstal Visual Studio, dan telah menginstal pustaka Aspose.PDF untuk .NET.

#### T: Bagaimana cara menyiapkan lingkungan pengembangan?

J: Ikuti langkah-langkah yang disediakan untuk menyiapkan lingkungan pengembangan Anda, termasuk membuat proyek C# baru di Visual Studio, dan mengimpor namespace yang diperlukan.

#### T: Bagaimana cara menambahkan tanda tangan digital ke file PDF?

 J: Kode contoh yang diberikan menunjukkan cara memuat file PDF, membuat tanda tangan digital, menentukan tampilan, dan menyimpan file PDF yang ditandatangani. Tanda tangan digital ditambahkan menggunakan`Certify` metode`PdfFileSignature` obyek.

#### T: Bagaimana cara memverifikasi keabsahan tanda tangan digital?

A: Setelah menambahkan tanda tangan digital, Anda dapat menggunakan kode contoh untuk memverifikasi validitas tanda tangan. Ia memeriksa apakah tanda tangan disertifikasi dan memiliki izin akses khusus.

####  T: Apa yang dimaksud dengan`PKCS7` object represent?

 J: Itu`PKCS7` objek digunakan untuk menyediakan fungsionalitas kriptografi untuk tanda tangan digital. Ini digunakan untuk membuat tanda tangan digital dalam kode contoh yang disediakan.

#### T: Dapatkah saya menyesuaikan tampilan tanda tangan digital?

 J: Ya, Anda dapat menyesuaikan tampilan tanda tangan digital dengan menentukan jalur ke gambar di`SignatureAppearance` properti dari`PdfFileSignature` obyek.

#### Q: Apa jadinya jika tanda tangan tidak sah?

J: Jika tanda tangan tidak valid, proses verifikasi akan gagal, dan tindakan terkait dalam blok kode verifikasi tidak akan dijalankan.

#### T: Bagaimana cara memastikan keamanan tanda tangan digital saya?

J: Tanda tangan digital aman berdasarkan desain dan menggunakan teknik kriptografi untuk memastikan keaslian dan integritas. Pastikan Anda menyimpan kunci pribadi Anda dengan aman dan mengikuti praktik terbaik dalam menangani tanda tangan digital.

#### T: Bisakah saya menambahkan beberapa tanda tangan digital ke PDF?

 J: Ya, Anda dapat menambahkan beberapa tanda tangan digital ke file PDF menggunakan`PdfFileSignature` objek`Sign` atau`Certify` metode. Setiap tanda tangan akan memiliki tampilan dan konfigurasinya sendiri.