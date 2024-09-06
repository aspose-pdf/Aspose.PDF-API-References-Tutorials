---
title: Berikan Kredensial Selama HTML Ke PDF
linktitle: Berikan Kredensial Selama HTML Ke PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mengonversi HTML ke PDF menggunakan Aspose.PDF untuk .NET dengan panduan langkah demi langkah ini. Sempurna bagi pengembang yang ingin menyederhanakan pembuatan dokumen.
type: docs
weight: 240
url: /id/net/document-conversion/provide-credentials-during-html-to-pdf/
---
## Perkenalan

Dalam dunia pengembangan perangkat lunak, mengonversi HTML ke PDF merupakan persyaratan umum. Baik Anda membuat laporan, faktur, atau dokumen lainnya, memiliki pustaka yang andal untuk menangani tugas ini dapat menghemat banyak waktu dan tenaga Anda. Gunakan Aspose.PDF untuk .NET, pustaka canggih yang memungkinkan pengembang membuat, memanipulasi, dan mengonversi dokumen PDF dengan mudah. Dalam tutorial ini, kami akan memandu Anda melalui proses penggunaan Aspose.PDF untuk mengonversi HTML ke PDF sekaligus memberikan kredensial untuk akses yang aman. Jadi, ambil topi koding Anda, dan mari kita mulai!

## Prasyarat

Sebelum kita memulai, ada beberapa hal yang perlu Anda siapkan:

1. Visual Studio: Pastikan Anda telah menginstal Visual Studio di komputer Anda. Ini akan menjadi lingkungan pengembangan kita.
2.  Aspose.PDF untuk .NET: Anda dapat mengunduh pustaka dari[situs web](https://releases.aspose.com/pdf/net/) Jika Anda ingin mencobanya terlebih dahulu, Anda juga bisa mendapatkan[uji coba gratis](https://releases.aspose.com/).
3. Pengetahuan Dasar C#: Keakraban dengan pemrograman C# akan membantu Anda memahami contoh-contohnya dengan lebih baik.
4. Akses Internet: Karena kami akan mengambil konten HTML dari URL, pastikan Anda memiliki koneksi internet aktif.

## Paket Impor

Untuk memulai dengan Aspose.PDF, Anda perlu mengimpor paket-paket yang diperlukan ke dalam proyek Anda. Berikut ini cara melakukannya:

1. Buka proyek Visual Studio Anda.
2. Klik kanan pada proyek Anda di Solution Explorer dan pilih "Kelola Paket NuGet."
3. Cari "Aspose.PDF" dan instal versi terbaru.

```csharp
using System.IO;
using Aspose.Pdf;
using System;
using System.Net;
```
Sekarang setelah semuanya disiapkan, mari kita uraikan proses mengonversi HTML ke PDF dengan kredensial ke dalam langkah-langkah yang lebih mudah dikelola.

## Langkah 1: Siapkan Direktori Dokumen Anda

Sebelum kita dapat mengonversi HTML ke PDF, kita perlu menentukan di mana output PDF kita akan disimpan. Ini dilakukan dengan menentukan jalur ke direktori dokumen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya tempat Anda ingin menyimpan berkas PDF. Ini bisa berupa folder di desktop atau lokasi lain di sistem Anda.

## Langkah 2: Buat Permintaan Web

 Selanjutnya, kita perlu membuat permintaan untuk mengambil konten HTML dari URL tertentu. Di sinilah kita akan menggunakan`WebRequest` kelas.

```csharp
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
```

Di sini, kami membuat permintaan ke URL yang berisi HTML yang ingin kami ubah. Pastikan untuk mengganti URL dengan yang ingin Anda gunakan.

## Langkah 3: Tetapkan Kredensial (Jika Diperlukan)

Jika server memerlukan kredensial untuk mengakses konten, kita perlu mengaturnya. Ini dilakukan dengan menggunakan`CredentialCache.DefaultCredentials`.

```csharp
request.Credentials = CredentialCache.DefaultCredentials;
```

 Baris ini memastikan bahwa permintaan menggunakan kredensial default dari pengguna saat ini. Jika Anda perlu memberikan kredensial tertentu, Anda dapat membuat yang baru`NetworkCredential` obyek.

## Langkah 4: Dapatkan Respons

Setelah permintaan kita disiapkan, waktunya untuk mendapatkan respons dari server.

```csharp
HttpWebResponse response = (HttpWebResponse)request.GetResponse();
```

Baris ini mengirimkan permintaan dan menunggu server merespons. Jika semuanya berjalan lancar, kita akan menerima konten HTML yang kita butuhkan.

## Langkah 5: Baca Aliran Respons

 Setelah kita mendapatkan respons, kita perlu membaca konten yang dikembalikan oleh server. Ini dilakukan dengan menggunakan`StreamReader`.

```csharp
Stream dataStream = response.GetResponseStream();
StreamReader reader = new StreamReader(dataStream);
string responseFromServer = reader.ReadToEnd();
reader.Close();
dataStream.Close();
response.Close();
```

 Di sini, kita membaca seluruh konten aliran respons ke dalam variabel string yang disebut`responseFromServer`Jangan lupa untuk menutup pembaca dan aliran untuk mengosongkan sumber daya.

## Langkah 6: Ubah HTML ke PDF

Sekarang tibalah bagian yang menarik! Kita akan mengonversi konten HTML menjadi dokumen PDF menggunakan Aspose.PDF.

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
HtmlLoadOptions options = new HtmlLoadOptions("http://My.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

Document pdfDocument = new Document(stream, options);
```

Pada langkah ini, kita membuat sebuah`MemoryStream` dari konten HTML dan pengaturan`HtmlLoadOptions`Hal ini memungkinkan kita menentukan URL dasar untuk sumber daya eksternal apa pun (seperti gambar atau style sheet) yang mungkin dirujuk oleh HTML.

## Langkah 7: Simpan Dokumen PDF

Terakhir, kita perlu menyimpan dokumen PDF yang dihasilkan ke direktori yang ditentukan.

```csharp
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

 Baris ini menyimpan file PDF dengan nama`ProvideCredentialsDuringHTMLToPDF_out.pdf` di direktori yang kita tentukan sebelumnya.

## Kesimpulan

Nah, itu dia! Anda telah berhasil mengonversi HTML ke PDF menggunakan Aspose.PDF untuk .NET sekaligus memberikan kredensial untuk akses yang aman. Pustaka canggih ini memudahkan penanganan dokumen PDF, dan hanya dengan beberapa baris kode, Anda dapat menghasilkan PDF yang tampak profesional dari konten HTML. 

## Pertanyaan yang Sering Diajukan

### Apa itu Aspose.PDF untuk .NET?
Aspose.PDF untuk .NET adalah pustaka yang memungkinkan pengembang untuk membuat, memanipulasi, dan mengonversi dokumen PDF dalam aplikasi .NET.

### Bagaimana cara menginstal Aspose.PDF?
 Anda dapat menginstal Aspose.PDF melalui NuGet Package Manager di Visual Studio atau mengunduhnya dari[situs web](https://releases.aspose.com/pdf/net/).

### Dapatkah saya menggunakan Aspose.PDF secara gratis?
Ya, Aspose menawarkan versi uji coba gratis yang dapat Anda gunakan untuk mengevaluasi pustaka sebelum membeli.

### Jenis dokumen apa yang dapat saya buat dengan Aspose.PDF?
Anda dapat membuat berbagai macam dokumen, termasuk laporan, faktur, dan formulir, menggunakan Aspose.PDF.

### Di mana saya dapat menemukan dukungan untuk Aspose.PDF?
 Anda dapat menemukan dukungan dan mengajukan pertanyaan di[Forum dukungan Aspose](https://forum.aspose.com/c/pdf/10).