---
title: Masuk Dengan Kartu Cerdas Menggunakan Bidang Tanda Tangan
linktitle: Masuk Dengan Kartu Cerdas Menggunakan Bidang Tanda Tangan
second_title: Aspose.PDF untuk Referensi .NET API
description: Tanda tangani file PDF Anda dengan aman menggunakan kartu pintar menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 120
url: /id/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
Penandatanganan digital dengan kartu pintar adalah cara aman untuk menandatangani file PDF. Dengan Aspose.PDF untuk .NET, Anda dapat dengan mudah menandatangani file PDF menggunakan bidang tanda tangan dan kartu pintar dengan mengikuti kode sumber berikut:

## Langkah 1: Impor perpustakaan yang diperlukan

Sebelum memulai, Anda perlu mengimpor perpustakaan yang diperlukan untuk proyek C# Anda. Berikut adalah arahan impor yang diperlukan:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Langkah 2: Tetapkan jalur ke folder dokumen

 Pada langkah ini, Anda perlu menentukan jalur ke folder yang berisi file PDF yang ingin Anda tandatangani. Mengganti`"YOUR DOCUMENTS DIRECTORY"`dalam kode berikut dengan jalur sebenarnya ke folder dokumen Anda:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 3: Salin dan buka dokumen PDF

Sekarang kita akan menyalin dan membuka dokumen PDF yang akan ditandatangani menggunakan kode berikut:

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);

using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
     using (Document doc = new Document(fs))
     {
         // Buat bidang tanda tangan
         SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));

         // Pilih sertifikat di toko
         X509Store store = new X509Store(StoreLocation.CurrentUser);
         store.Open(OpenFlags.ReadOnly);
         X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
        
         // Buat tanda tangan eksternal dengan informasi yang diperlukan
         ExternalSignature externalSignature = new ExternalSignature(sel[0])
         {
             Authority = "Me",
             Reason = "Reason",
             ContactInfo = "Contact"
         };

         field1.PartialName = "sig1";
         doc.Form.Add(field1, 1);
         field1.Sign(externalSignature);
         doc.Save();
     }
}
```

## Langkah 4: Verifikasi Tanda Tangan

 Terakhir, kami memverifikasi tanda tangan file PDF yang ditandatangani menggunakan`PdfFileSignature` kelas. Kami mendapatkan nama tanda tangan dan memeriksanya satu per satu. Jika tanda tangan gagal verifikasi, pengecualian akan diberikan. Ini kode yang sesuai:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
{
     IList<string> sigNames = pdfSign. GetSignNames();
     for (int index = 0; index <= sigNames.Count - 1; index++)
     {
         if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
         {
             throw new ApplicationException("Unverified");
         }
     }
}
```

### Contoh kode sumber untuk Masuk Dengan Kartu Cerdas Menggunakan Bidang Tanda Tangan menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
	using (Document doc = new Document(fs))
	{
		SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
		// Masuk dengan pilihan sertifikat di penyimpanan sertifikat windows
		System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
		store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
		// Pilih sertifikat di toko secara manual
		System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
		Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0])
		{
			Authority = "Me",
			Reason = "Reason",
			ContactInfo = "Contact"
		};
		field1.PartialName = "sig1";
		doc.Form.Add(field1, 1);
		field1.Sign(externalSignature);
		doc.Save();
	}
}
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
{
	IList<string> sigNames = pdfSign.GetSignNames();
	for (int index = 0; index <= sigNames.Count - 1; index++)
	{
		if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
		{
			throw new ApplicationException("Not verified");
		}
	}
}
```

## Kesimpulan

Selamat! Anda sekarang memiliki panduan langkah demi langkah untuk menandatangani file PDF dengan kartu pintar menggunakan bidang tanda tangan dengan Aspose.PDF untuk .NET. Anda dapat menggunakan kode ini untuk menambahkan tanda tangan digital yang aman ke dokumen PDF Anda.

Pastikan untuk memeriksa dokumentasi resmi Aspose.PDF untuk informasi lebih lanjut tentang fitur tanda tangan digital dan manajemen sertifikat tingkat lanjut.

### FAQ

#### T: Apa keuntungan menggunakan kolom tanda tangan untuk penandatanganan digital dengan kartu pintar?

J: Menggunakan bidang tanda tangan untuk penandatanganan digital dengan kartu pintar menyediakan area khusus dalam PDF tempat tanda tangan diterapkan. Hal ini meningkatkan kejelasan dokumen dan memastikan keaslian tanda tangan.

#### T: Bagaimana perpustakaan Aspose.PDF untuk .NET memfasilitasi penandatanganan digital berbasis kartu pintar dengan bidang tanda tangan?

J: Aspose.PDF untuk .NET menyederhanakan proses pembuatan bidang tanda tangan, memilih sertifikat kartu pintar, dan menerapkan tanda tangan digital ke area tertentu dalam dokumen PDF.

#### T: Mengapa memilih sertifikat tertentu penting untuk penandatanganan berbasis kartu pintar?

J: Memilih sertifikat tertentu memungkinkan Anda mengidentifikasi penandatangan secara unik dan memastikan integritas tanda tangan. Hal ini membantu membangun kepercayaan dan kepatuhan terhadap standar penandatanganan digital.

#### T: Bagaimana kode sumber yang disediakan menangani proses penandatanganan berbasis kartu pintar dengan kolom tanda tangan?

J: Kode sumber menunjukkan cara membuat bidang tanda tangan, memilih sertifikat kartu pintar, dan menerapkan tanda tangan digital dengan informasi penandatanganan tertentu. Ini juga menunjukkan cara memverifikasi validitas tanda tangan.

#### T: Dapatkah saya menyesuaikan tampilan kolom tanda tangan?

J: Ya, Anda dapat menyesuaikan tampilan bidang tanda tangan, seperti ukuran, posisi, dan representasi visualnya, agar selaras dengan tata letak dokumen Anda.

#### T: Apa yang terjadi jika tanda tangan gagal diverifikasi pada tahap verifikasi?

J: Jika tanda tangan gagal verifikasi, pengecualian akan diberikan, yang menunjukkan bahwa tanda tangan tersebut tidak valid. Hal ini memastikan bahwa hanya tanda tangan sah dan terpercaya yang diterima.

#### T: Dapatkah saya menerapkan beberapa bidang tanda tangan dan tanda tangan berbasis kartu pintar ke satu dokumen PDF?

J: Tentu saja, Anda dapat menerapkan beberapa bidang tanda tangan dan tanda tangan berbasis kartu pintar ke area berbeda pada dokumen PDF yang sama, sehingga memberikan keamanan berlapis.

#### T: Bagaimana cara menggunakan bidang tanda tangan meningkatkan proses penandatanganan dokumen secara keseluruhan?

J: Menggunakan bidang tanda tangan menyederhanakan proses penandatanganan dokumen, karena memandu penanda tangan untuk menempatkan tanda tangannya di area yang ditentukan, menjadikan proses penandatanganan lebih terorganisir dan mudah digunakan.

#### T: Apakah ada batasan dalam menggunakan kolom tanda tangan dengan penandatanganan berbasis kartu pintar?

J: Tidak ada batasan yang melekat dalam menggunakan bidang tanda tangan dengan penandatanganan berbasis kartu pintar. Namun, penting untuk memastikan bahwa lokasi bidang tanda tangan yang dipilih tidak mengaburkan konten dokumen penting.

#### T: Di mana saya bisa mendapatkan bantuan atau dukungan lebih lanjut untuk menerapkan penandatanganan berbasis kartu pintar dengan kolom tanda tangan?

J: Untuk panduan dan dukungan tambahan, Anda dapat merujuk ke dokumentasi resmi Aspose.PDF dan forum komunitas, yang menawarkan wawasan dan solusi berharga untuk menerapkan tanda tangan digital yang aman.