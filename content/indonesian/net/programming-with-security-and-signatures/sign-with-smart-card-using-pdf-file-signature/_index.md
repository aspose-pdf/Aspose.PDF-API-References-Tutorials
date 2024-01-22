---
title: Masuk Dengan Kartu Cerdas Menggunakan Tanda Tangan File PDF
linktitle: Masuk Dengan Kartu Cerdas Menggunakan Tanda Tangan File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Tanda tangani file PDF Anda dengan aman menggunakan kartu pintar menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 110
url: /id/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
Penandatanganan digital dengan kartu pintar adalah cara aman untuk menandatangani file PDF. Dengan Aspose.PDF untuk .NET, Anda dapat dengan mudah menandatangani file PDF menggunakan kartu pintar dengan mengikuti kode sumber berikut:

## Langkah 1: Impor perpustakaan yang diperlukan

Sebelum memulai, Anda perlu mengimpor perpustakaan yang diperlukan untuk proyek C# Anda. Berikut adalah arahan impor yang diperlukan:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Langkah 2: Tetapkan jalur ke folder dokumen

 Pada langkah ini, Anda perlu menentukan jalur ke folder yang berisi file PDF yang ingin Anda tandatangani. Mengganti`"YOUR DOCUMENTS DIRECTORY"`dalam kode berikut dengan jalur sebenarnya ke folder dokumen Anda:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 3: Muat dokumen PDF

Sekarang kita akan memuat dokumen PDF yang akan ditandatangani menggunakan kode berikut:

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## Langkah 4: Lakukan tanda tangan dengan kartu pintar

 Pada langkah ini, kita akan melakukan tanda tangan dengan kartu pintar menggunakan`PdfFileSignature` kelas dari`Facades`perpustakaan. Kami memilih sertifikat kartu pintar dari penyimpanan sertifikat Windows dan menentukan informasi penandatanganan yang diperlukan. Ini kode yang sesuai:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature())
{
     pdfSign.BindPdf(doc);

     // Pilih sertifikat di toko
     X509Store store = new X509Store(StoreLocation.CurrentUser);
     store.Open(OpenFlags.ReadOnly);
     X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
     ExternalSignature externalSignature = new ExternalSignature(sel[0]);

     pdfSign.SignatureAppearance = dataDir + "demo.png";
     pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
     pdfSign.Save(dataDir + "externalSignature2.pdf");
}
```

## Langkah 5: Verifikasi Tanda Tangan

 Terakhir, kami memverifikasi tanda tangan file PDF yang ditandatangani menggunakan`PdfFileSignature` kelas. Kami mendapatkan nama tanda tangan dan memeriksanya satu per satu. Jika tanda tangan gagal verifikasi, pengecualian akan diberikan. Ini kode yang sesuai:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
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

### Contoh kode sumber untuk Masuk Dengan Kartu Cerdas Menggunakan Tanda Tangan File Pdf menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	// Masuk dengan pilihan sertifikat di penyimpanan sertifikat windows
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	// Pilih sertifikat di toko secara manual
	System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
	Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
	pdfSign.SignatureAppearance = dataDir + "demo.png";
	pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
	pdfSign.Save(dataDir + "externalSignature2.pdf");
}
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
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

Selamat! Anda sekarang memiliki panduan langkah demi langkah untuk menandatangani file PDF dengan kartu pintar menggunakan Aspose.PDF untuk .NET. Anda dapat menggunakan kode ini untuk menambahkan tanda tangan digital yang aman ke dokumen PDF Anda.

Pastikan untuk memeriksa dokumentasi resmi Aspose.PDF untuk informasi lebih lanjut tentang fitur tanda tangan digital dan manajemen sertifikat tingkat lanjut.

### FAQ

#### T: Mengapa saya harus mempertimbangkan untuk menandatangani file PDF dengan kartu pintar?

J: Menandatangani file PDF dengan kartu pintar meningkatkan keamanan dengan memastikan keaslian dan integritas dokumen. Tanda tangan berbasis kartu pintar memberikan tingkat kepercayaan dan kepatuhan yang lebih tinggi.

#### T: Bagaimana cara kerja penandatanganan digital berbasis kartu pintar?

J: Penandatanganan digital berbasis kartu pintar melibatkan penggunaan kunci kriptografi yang disimpan di kartu pintar untuk membuat tanda tangan digital unik. Tanda tangan ini dilampirkan pada file PDF, memungkinkan penerima memverifikasi asal dan integritas dokumen.

#### T: Apa peran Aspose.PDF untuk .NET dalam penandatanganan berbasis kartu pintar?

J: Aspose.PDF untuk .NET menyediakan seperangkat alat dan perpustakaan lengkap untuk memfasilitasi penandatanganan digital file PDF berbasis kartu pintar. Ini menyederhanakan proses dan memastikan penandatanganan dokumen aman.

#### T: Dapatkah saya memilih sertifikat kartu pintar tertentu untuk ditandatangani?

J: Ya, Anda dapat memilih sertifikat kartu pintar tertentu dari penyimpanan sertifikat Windows untuk ditandatangani. Aspose.PDF untuk .NET memungkinkan Anda mengintegrasikan pemilihan sertifikat ke dalam aplikasi Anda dengan lancar.

#### T: Bagaimana kode sumber yang disediakan menangani penandatanganan berbasis kartu pintar?

J: Kode sumber menunjukkan cara mengikat dokumen PDF, memilih sertifikat kartu pintar, menentukan informasi penandatanganan, dan membuat tanda tangan digital. Ini juga menunjukkan cara memverifikasi validitas tanda tangan.

#### T: Bisakah saya menerapkan banyak tanda tangan menggunakan kartu pintar dalam satu file PDF?

J: Tentu saja, Anda dapat menerapkan beberapa tanda tangan berbasis kartu pintar ke satu file PDF. Setiap tanda tangan bersifat unik dan berkontribusi terhadap keamanan dokumen secara keseluruhan.

#### T: Bagaimana jika tanda tangan gagal diverifikasi pada tahap verifikasi?

J: Jika tanda tangan gagal verifikasi, pengecualian akan diberikan, yang menunjukkan bahwa tanda tangan tersebut tidak valid. Hal ini memastikan bahwa hanya tanda tangan sah dan terpercaya yang diterima.

#### T: Apakah penandatanganan berbasis kartu pintar kompatibel dengan semua jenis dokumen PDF?

J: Ya, penandatanganan berbasis kartu pintar kompatibel dengan semua jenis dokumen PDF. Anda dapat menerapkan tanda tangan digital ke berbagai jenis file PDF, termasuk formulir, laporan, dan lainnya.

#### T: Bagaimana cara mempelajari lebih lanjut tentang tanda tangan digital tingkat lanjut dan manajemen sertifikat?

J: Jelajahi dokumentasi resmi Aspose.PDF untuk wawasan mendetail tentang fitur tanda tangan digital tingkat lanjut, manajemen sertifikat, dan praktik terbaik untuk memastikan keamanan dokumen.

#### T: Di mana saya bisa mendapatkan bantuan atau dukungan lebih lanjut untuk menerapkan penandatanganan berbasis kartu pintar?

J: Untuk panduan dan dukungan tambahan, hubungi forum komunitas Aspose.PDF atau lihat dokumentasi untuk informasi komprehensif tentang penandatanganan berbasis kartu pintar.