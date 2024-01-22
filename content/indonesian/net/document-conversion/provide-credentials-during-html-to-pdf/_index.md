---
title: Berikan Kredensial Selama HTML Ke PDF
linktitle: Berikan Kredensial Selama HTML Ke PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Panduan langkah demi langkah untuk mengonversi HTML ke PDF dengan memberikan kredensial dengan Aspose.PDF untuk .NET.
type: docs
weight: 240
url: /id/net/document-conversion/provide-credentials-during-html-to-pdf/
---
Dalam tutorial ini, kami akan memandu Anda melalui proses mengonversi file HTML ke PDF sambil memberikan kredensial saat mengakses URL aman menggunakan Aspose.PDF untuk .NET. Dengan mengikuti langkah-langkah di bawah ini, Anda akan dapat mengonversi konten HTML ke PDF menggunakan kredensial yang sesuai.

## Prasyarat
Sebelum memulai, pastikan Anda memenuhi prasyarat berikut:

- Pengetahuan dasar tentang bahasa pemrograman C#.
- Pustaka Aspose.PDF untuk .NET diinstal di sistem Anda.
- Lingkungan pengembangan seperti Visual Studio.

## Langkah 1: Ambil konten HTML yang aman
Pada langkah ini, kami akan mengambil konten HTML aman dari URL menggunakan kredensial yang sesuai. Gunakan kode berikut:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Buat permintaan untuk URL.
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
// Jika diperlukan untuk server, atur kredensial.
request.Credentials = CredentialCache.DefaultCredentials;
// Dapatkan tanggapannya.
HttpWebResponse response = (HttpWebResponse)request.GetResponse();

// Dapatkan aliran yang berisi konten yang dikembalikan oleh server.
Stream dataStream = response. GetResponseStream();
// Buka aliran menggunakan StreamReader untuk memudahkan akses.
StreamReader reader = new StreamReader(dataStream);
// Baca isinya.
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```

 Pastikan untuk mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan direktori sebenarnya tempat Anda ingin menyimpan file PDF yang dihasilkan.

## Langkah 2: Konversi HTML ke PDF dengan memberikan kredensial
Sekarang kami akan memuat konten HTML yang diambil dan mengonversinya ke format PDF sambil memberikan kredensial yang sesuai. Gunakan kode berikut:

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

HtmlLoadOptions options = new HtmlLoadOptions("http://My.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

// Muat file HTML
Document pdfDocument = new Document(stream, options);
```

## Langkah 3: Menyimpan file PDF yang dihasilkan
Terakhir, kami akan menyimpan file PDF yang dihasilkan. Gunakan kode berikut:

```csharp
// Simpan file PDF yang dihasilkan
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

 Kode di atas menyimpan file PDF yang dihasilkan dengan nama file`"ProvideCredentialsDuringHTMLToPDF_out.pdf"`.

### Contoh kode sumber untuk Memberikan Kredensial Selama HTML ke PDF menggunakan Aspose.PDF untuk .NET

```csharp
try
{
	
	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Buat permintaan untuk URL.
	WebRequest request = WebRequest.Create("http:// My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
	// Jika diperlukan oleh server, atur kredensialnya.
	request.Credentials = CredentialCache.DefaultCredentials;
	// Dapatkan tanggapannya.
	HttpWebResponse response = (HttpWebResponse)request.GetResponse();

	// Dapatkan aliran berisi konten yang dikembalikan oleh server.
	Stream dataStream = response.GetResponseStream();
	// Buka aliran menggunakan StreamReader untuk memudahkan akses.
	StreamReader reader = new StreamReader(dataStream);
	// Baca isinya.
	string responseFromServer = reader.ReadToEnd();
	reader.Close();
	dataStream.Close();
	response.Close();

	MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

	HtmlLoadOptions options = new HtmlLoadOptions("http:// My.signchart.com/");
	options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

	// Muat file HTML
	Document pdfDocument = new Document(stream, options);
	// Simpan file yang dihasilkan
	pdfDocument.Save("ProvideCredentialsDuringHTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Kesimpulan
Dalam tutorial ini, kami membahas proses langkah demi langkah mengonversi file HTML ke PDF sambil memberikan kredensial saat mengakses URL aman menggunakan Aspose.PDF untuk .NET. Dengan mengikuti petunjuk yang diuraikan di atas, Anda akan berhasil mengonversi konten HTML ke PDF sambil memberikan kredensial yang benar.

### FAQ

#### T: Apa itu Aspose.PDF untuk .NET?

J: Aspose.PDF untuk .NET adalah perpustakaan tangguh yang memberdayakan pengembang untuk bekerja dengan dokumen PDF dalam aplikasi C#. Ini menawarkan berbagai fungsi, termasuk konversi HTML ke PDF.

#### T: Bagaimana cara mengambil konten HTML yang aman dari URL?

 J: Untuk mengambil konten HTML aman dari URL, Anda dapat menggunakan`WebRequest` kelas di C#. Pastikan untuk mengatur kredensial yang sesuai menggunakan`Credentials` Properti.

#### Q: Apa saja prasyarat untuk tutorial ini?

A: Sebelum melanjutkan tutorial, pastikan Anda memiliki prasyarat berikut:

- Pengetahuan dasar tentang bahasa pemrograman C#.
- Pustaka Aspose.PDF untuk .NET diinstal di sistem Anda.
- Lingkungan pengembangan seperti Visual Studio.

#### T: Bagaimana Aspose.PDF untuk .NET menangani sumber daya eksternal saat mengonversi HTML ke PDF?

 J: Aspose.PDF untuk .NET menyediakan`HtmlLoadOptions`kelas untuk menangani sumber daya eksternal selama konversi HTML ke PDF. Anda dapat mengatur kredensial sumber daya eksternal menggunakan`ExternalResourcesCredentials` Properti.

#### T: Dapatkah saya menyesuaikan nama file untuk file PDF yang dihasilkan?

 A: Ya, Anda dapat menyesuaikan nama file untuk file PDF yang dihasilkan dengan memodifikasi kode yang menyimpan dokumen PDF. Cukup ubah nama file yang diinginkan di`pdfDocument.Save()` metode.