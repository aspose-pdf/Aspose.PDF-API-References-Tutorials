---
title: Tanda Tangan Digital Dengan Cap Waktu Dalam File PDF
linktitle: Tanda Tangan Digital Dengan Cap Waktu Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara membuat tanda tangan digital dengan cap waktu di berkas PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 50
url: /id/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
Dalam tutorial ini, kami akan memandu Anda melalui proses penandatanganan digital pada berkas PDF dengan cap waktu menggunakan Aspose.PDF untuk .NET. Tanda tangan digital dengan cap waktu menjamin keaslian dan integritas dokumen, dengan menambahkan sidik jari elektronik dengan cap waktu.

## Langkah 1: Prasyarat

Sebelum memulai, pastikan Anda memiliki prasyarat berikut:

- Pengetahuan dasar tentang bahasa pemrograman C#
- Menginstal Visual Studio di komputer Anda
- Pustaka Aspose.PDF untuk .NET terinstal

## Langkah 2: Pengaturan lingkungan

Untuk memulai, ikuti langkah-langkah berikut untuk menyiapkan lingkungan pengembangan Anda:

1. Buka Visual Studio dan buat proyek C# baru.
2. Impor namespace yang diperlukan ke dalam berkas kode Anda:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

## Langkah 3: Tanda tangan digital dengan stempel waktu

Langkah pertama adalah melakukan tanda tangan digital dengan stempel waktu pada berkas PDF. Kode yang diberikan menunjukkan cara memperoleh tanda tangan ini dengan Aspose.PDF untuk .NET.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
         TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password");
         pkcs. TimestampSettings = timestampSettings;
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.Sign(1, "Reason for signing", "Contact", "Location", true, rect, pkcs);
         signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
     }
}
```

Kode ini memuat berkas PDF, membuat tanda tangan digital dengan stempel waktu menggunakan berkas PFX (kunci pribadi) dan parameter stempel waktu yang ditentukan. Tanda tangan tersebut kemudian ditambahkan ke berkas PDF dan disimpan dengan sufiks "_keluar".

### Contoh kode sumber untuk Menandatangani Secara Digital dengan Cap Waktu menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
	using (PdfFileSignature signature = new PdfFileSignature(document))
	{
		PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
		TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password"); // Pengguna/Kata Sandi dapat dihilangkan
		pkcs.TimestampSettings = timestampSettings;
		System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
		// Buat salah satu dari tiga jenis tanda tangan
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		// Simpan file PDF keluaran
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## Kesimpulan

Selamat! Anda telah berhasil membuat tanda tangan digital dengan stempel waktu pada file PDF menggunakan Aspose.PDF untuk .NET. Tutorial ini membahas proses langkah demi langkah mulai dari membuat tanda tangan hingga menyimpan file PDF yang diperbarui. Kini Anda dapat menggunakan fitur ini untuk menambahkan tanda tangan digital dengan stempel waktu ke file PDF Anda.

### FAQ untuk menandatangani secara digital dengan cap waktu dalam file PDF

#### T: Apa tujuan penandatanganan digital dengan stempel waktu?

A: Penandatanganan digital dengan stempel waktu menambahkan sidik jari elektronik dengan stempel waktu ke berkas PDF, memastikan keaslian dan integritas dokumen pada titik waktu tertentu.

#### T: Prasyarat apa yang dibutuhkan untuk memulai tutorial ini?

A: Sebelum memulai, pastikan Anda memiliki pemahaman dasar tentang bahasa pemrograman C#, telah menginstal Visual Studio, dan telah menginstal pustaka Aspose.PDF untuk .NET.

#### T: Bagaimana saya dapat mengatur lingkungan pengembangan saya?

A: Ikuti langkah-langkah yang disediakan untuk menyiapkan lingkungan pengembangan Anda, termasuk membuat proyek C# baru di Visual Studio dan mengimpor namespace yang diperlukan.

#### T: Bagaimana cara menambahkan tanda tangan digital dengan stempel waktu ke PDF?

A: Kode contoh yang disediakan menunjukkan cara memuat file PDF, membuat tanda tangan digital dengan stempel waktu menggunakan file PFX (kunci pribadi) dan pengaturan stempel waktu yang ditentukan, menambahkan tanda tangan ke file PDF, dan menyimpan file yang diperbarui.

#### T: Apa itu file PFX, dan mengapa file itu digunakan dalam contoh tersebut?

J: File PFX (Personal Exchange Format) berisi kunci pribadi dan sertifikat. Kunci tersebut digunakan di sini untuk menyediakan fungsionalitas kriptografi untuk tanda tangan digital. Pastikan Anda mengganti placeholder dengan file PFX dan kata sandi Anda.

#### T: Apa itu TimestampSettings?

A: TimestampSettings menentukan pengaturan untuk server stempel waktu yang digunakan untuk menambahkan stempel waktu elektronik ke tanda tangan. Ini mencakup URL server stempel waktu dan kredensial pengguna opsional.

#### T: Dapatkah saya menggunakan server stempel waktu selain yang ada dalam contoh?
 A: Ya, Anda dapat menggunakan server stempel waktu yang kompatibel. Ganti URL dan, jika diperlukan, berikan kredensial pengguna yang sesuai di`TimestampSettings` obyek.

#### T: Apa tujuan menentukan persegi panjang tanda tangan?

A: Persegi panjang tanda tangan menentukan posisi dan dimensi tampilan tanda tangan digital pada halaman PDF. Sesuaikan nilai ini untuk memposisikan tanda tangan sesuai keinginan.

#### T: Apa yang terjadi jika server stempel waktu tidak tersedia selama penandatanganan?

J: Jika server stempel waktu tidak tersedia selama penandatanganan, prosesnya mungkin gagal atau memerlukan waktu lebih lama. Pastikan server stempel waktu Anda andal dan dapat diakses.

#### T: Bagaimana saya dapat memverifikasi keberadaan stempel waktu di PDF yang ditandatangani?

 A: Anda dapat memeriksa PDF yang ditandatangani menggunakan kode contoh yang diberikan.`TimestampSettings` yang Anda gunakan saat penandatanganan harus tersedia dalam rincian tanda tangan.

#### T: Apakah tanda tangan digital dengan stempel waktu mengikat secara hukum?

J: Tanda tangan digital dengan stempel waktu memiliki nilai hukum di banyak yurisdiksi dan sering dianggap lebih dapat diandalkan daripada tanda tangan digital biasa. Konsultasikan dengan pakar hukum di yurisdiksi Anda untuk peraturan khusus.

#### T: Dapatkah saya menambahkan beberapa tanda tangan digital dengan stempel waktu ke PDF?

A: Ya, Anda dapat menambahkan beberapa tanda tangan digital dengan stempel waktu ke berkas PDF dengan memanggil proses pembuatan tanda tangan beberapa kali. Setiap tanda tangan akan memiliki stempel waktunya sendiri.