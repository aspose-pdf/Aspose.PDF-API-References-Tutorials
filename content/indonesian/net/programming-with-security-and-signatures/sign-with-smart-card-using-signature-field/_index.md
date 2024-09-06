---
title: Tanda Tangan Dengan Kartu Pintar Menggunakan Kolom Tanda Tangan
linktitle: Tanda Tangan Dengan Kartu Pintar Menggunakan Kolom Tanda Tangan
second_title: Referensi API Aspose.PDF untuk .NET
description: Tanda tangani berkas PDF Anda dengan aman dengan kartu pintar menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 120
url: /id/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
Penandatanganan digital dengan kartu pintar merupakan cara yang aman untuk menandatangani berkas PDF. Dengan Aspose.PDF untuk .NET, Anda dapat dengan mudah menandatangani berkas PDF menggunakan kolom tanda tangan dan kartu pintar dengan mengikuti kode sumber berikut:

## Langkah 1: Impor pustaka yang diperlukan

Sebelum memulai, Anda perlu mengimpor pustaka yang diperlukan untuk proyek C# Anda. Berikut ini adalah perintah impor yang diperlukan:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Langkah 2: Tetapkan jalur ke folder dokumen

 Pada langkah ini, Anda perlu menentukan jalur ke folder yang berisi file PDF yang ingin Anda tandatangani. Ganti`"YOUR DOCUMENTS DIRECTORY"` dalam kode berikut dengan jalur sebenarnya ke folder dokumen Anda:

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

 Terakhir, kami memverifikasi tanda tangan file PDF yang ditandatangani menggunakan`PdfFileSignature` class. Kami mendapatkan nama tanda tangan dan memeriksanya satu per satu. Jika tanda tangan gagal diverifikasi, pengecualian akan dilemparkan. Berikut kode yang sesuai:

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

### Contoh kode sumber untuk Menandatangani dengan Kartu Pintar Menggunakan Bidang Tanda Tangan menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
	using (Document doc = new Document(fs))
	{
		SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
		// Masuk dengan pemilihan sertifikat di penyimpanan sertifikat Windows
		System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
		store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
		// Memilih sertifikat secara manual di toko
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

Selamat! Kini Anda memiliki panduan langkah demi langkah untuk menandatangani berkas PDF dengan kartu pintar menggunakan kolom tanda tangan dengan Aspose.PDF untuk .NET. Anda dapat menggunakan kode ini untuk menambahkan tanda tangan digital yang aman ke dokumen PDF Anda.

Pastikan untuk memeriksa dokumentasi resmi Aspose.PDF untuk informasi lebih lanjut tentang fitur tanda tangan digital dan manajemen sertifikat tingkat lanjut.

### Pertanyaan yang Sering Diajukan

#### T: Apa manfaat menggunakan kolom tanda tangan untuk penandatanganan digital dengan kartu pintar?

A: Menggunakan kolom tanda tangan untuk penandatanganan digital dengan kartu pintar menyediakan area khusus di dalam PDF tempat tanda tangan diterapkan. Hal ini meningkatkan kejelasan dokumen dan memastikan keaslian tanda tangan.

#### T: Bagaimana pustaka Aspose.PDF untuk .NET memfasilitasi penandatanganan digital berbasis kartu pintar dengan bidang tanda tangan?

A: Aspose.PDF untuk .NET menyederhanakan proses pembuatan bidang tanda tangan, memilih sertifikat kartu pintar, dan menerapkan tanda tangan digital ke area tertentu dalam dokumen PDF.

#### T: Mengapa pemilihan sertifikat tertentu penting untuk penandatanganan berbasis kartu pintar?

J: Memilih sertifikat tertentu memungkinkan Anda mengidentifikasi penanda tangan secara unik dan memastikan integritas tanda tangan. Ini membantu membangun kepercayaan dan kepatuhan terhadap standar penandatanganan digital.

#### T: Bagaimana kode sumber yang disediakan menangani proses penandatanganan berbasis kartu pintar dengan bidang tanda tangan?

A: Kode sumber menunjukkan cara membuat bidang tanda tangan, memilih sertifikat kartu pintar, dan menerapkan tanda tangan digital dengan informasi penandatanganan tertentu. Kode sumber juga menunjukkan cara memverifikasi keabsahan tanda tangan.

#### T: Dapatkah saya menyesuaikan tampilan kolom tanda tangan?

A: Ya, Anda dapat menyesuaikan tampilan bidang tanda tangan, seperti ukuran, posisi, dan representasi visualnya, agar selaras dengan tata letak dokumen Anda.

#### T: Apa yang terjadi jika tanda tangan gagal diverifikasi selama langkah verifikasi?

A: Jika tanda tangan gagal diverifikasi, pengecualian akan muncul, yang menunjukkan bahwa tanda tangan tersebut tidak valid. Ini memastikan bahwa hanya tanda tangan yang valid dan tepercaya yang diterima.

#### T: Dapatkah saya menerapkan beberapa bidang tanda tangan dan tanda tangan berbasis kartu pintar ke satu dokumen PDF?

A: Tentu saja, Anda dapat menerapkan beberapa bidang tanda tangan dan tanda tangan berbasis kartu pintar ke area berbeda dalam dokumen PDF yang sama, menyediakan beberapa lapisan keamanan.

#### T: Bagaimana penggunaan kolom tanda tangan meningkatkan proses penandatanganan dokumen secara keseluruhan?

A: Menggunakan kolom tanda tangan memperlancar proses penandatanganan dokumen, karena kolom ini memandu penanda tangan untuk meletakkan tanda tangannya di area yang ditentukan, sehingga proses penandatanganan menjadi lebih terorganisasi dan mudah digunakan.

#### T: Apakah ada batasan dalam penggunaan bidang tanda tangan dengan penandatanganan berbasis kartu pintar?

J: Tidak ada batasan yang melekat pada penggunaan kolom tanda tangan dengan penandatanganan berbasis kartu pintar. Namun, penting untuk memastikan bahwa lokasi kolom tanda tangan yang dipilih tidak mengaburkan konten dokumen penting.

#### T: Di mana saya dapat menemukan bantuan atau dukungan lebih lanjut untuk menerapkan penandatanganan berbasis kartu pintar dengan bidang tanda tangan?

A: Untuk panduan dan dukungan tambahan, Anda dapat merujuk ke dokumentasi resmi Aspose.PDF dan forum komunitas, yang menawarkan wawasan dan solusi berharga untuk menerapkan tanda tangan digital yang aman.