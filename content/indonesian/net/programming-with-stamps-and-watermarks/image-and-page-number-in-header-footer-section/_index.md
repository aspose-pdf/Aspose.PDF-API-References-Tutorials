---
title: Gambar dan Nomor Halaman di Bagian Header dan Footer
linktitle: Gambar dan Nomor Halaman di Bagian Header dan Footer
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menambahkan gambar dan nomor halaman ke header dan footer PDF Anda menggunakan Aspose.PDF untuk .NET dalam tutorial langkah demi langkah ini.
type: docs
weight: 110
url: /id/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
## Perkenalan

Jika berbicara tentang pembuatan dokumen PDF tingkat profesional, memiliki kendali atas detail kecil seperti header dan footer sangatlah penting. Anda ingin dokumen Anda terlihat rapi dan terorganisasi dengan baik, bukan? Nah, dengan Aspose.PDF untuk .NET, Anda dapat menambahkan gambar dan nomor halaman dengan mudah ke bagian header dan footer dokumen Anda. Dalam tutorial ini, kami akan memandu Anda melalui setiap langkah, sehingga mudah diikuti.

## Prasyarat

Sebelum menyelami inti tutorial ini, pastikan Anda sudah menyiapkan hal berikut:

1. .NET Framework: Anda perlu menginstal versi .NET Framework apa pun di komputer Anda. Jika belum memilikinya, Anda dapat mengunduhnya dengan mudah dari situs web Microsoft.
2.  Aspose.PDF untuk .NET: Karena kita akan menggunakan Aspose.PDF, pastikan Anda telah menginstalnya di proyek Anda. Anda dapat mengunduh versi uji coba[Di Sini](https://releases.aspose.com/pdf/net/).
3. Pengetahuan Dasar C#: Keakraban dengan pemrograman C# dasar tentu akan membantu Anda memahami kode tanpa banyak kesulitan.
4. Berkas Gambar: Anda memerlukan gambar yang ingin Anda masukkan di tajuk dokumen PDF, seperti logo. Simpan di direktori yang mudah diakses. 
5. IDE: Gunakan Lingkungan Pengembangan Terpadu (IDE) pilihan Anda, seperti Visual Studio, untuk bekerja dengan proyek .NET Anda.

Setelah Anda menyiapkan prasyaratnya, Anda akan siap membuat berkas PDF yang luar biasa!

## Paket Impor

Untuk mulai menggunakan Aspose.PDF untuk .NET, Anda perlu mengimpor namespace yang diperlukan. Di bagian atas file C#, Anda akan menambahkan:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Image;
```

Ruang nama ini akan memberi Anda akses ke kelas-kelas yang dibutuhkan untuk memanipulasi berkas PDF.

Sekarang mari kita mulai! Ikuti langkah-langkah berikut untuk membuat dokumen PDF Anda, dengan menyertakan gambar di header dan nomor halaman di footer.

## Langkah 1: Atur Direktori Dokumen Anda

Setiap proyek yang baik dimulai dengan pengorganisasian. Tentukan direktori dokumen tempat Anda akan menyimpan file dan tempat gambar Anda berada. Berikut cara melakukannya:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ingat untuk mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya tempat Anda ingin menyimpan PDF dan tempat gambar Anda berada.

## Langkah 2: Buat Dokumen PDF Baru

Berikutnya, kita akan membuat dokumen PDF baru di mana semua keajaiban akan terjadi:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

Pada titik ini, Anda telah membuat dokumen PDF kosong. Menarik, bukan?

## Langkah 3: Tambahkan Halaman ke Dokumen

PDF berisi banyak halaman. Mari tambahkan halaman baru ke dokumen kita menggunakan:

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

Sekarang Anda memiliki kanvas tempat Anda dapat mulai mendesain!

## Langkah 4: Buat Bagian Header

Header Anda akan berisi gambar (seperti logo) yang ingin Anda tampilkan. Buat bagian header dengan kode berikut:

```csharp
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
page.Header = header;
```

Sekarang Anda memiliki header yang dapat Anda sesuaikan!

## Langkah 5: Tambahkan Gambar ke Header

Sekarang kita sampai pada bagian yang menyenangkan! Anda perlu menambahkan gambar ke header Anda. Pertama, buat objek gambar:

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
```

Tetapkan jalur file gambar Anda:

```csharp
image1.File = dataDir + "aspose-logo.jpg";
```

Terakhir, tambahkan gambar ke header Anda:

```csharp
header.Paragraphs.Add(image1);
```

Selamat! Anda baru saja menambahkan gambar ke header PDF Anda.

## Langkah 6: Buat Bagian Footer

Sekarang mari kita kerjakan bagian footer. Mirip dengan proses header, buat objek footer:

```csharp
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();
page.Footer = footer;
```

Di sinilah Anda akan menempatkan nomor halaman Anda. 

## Langkah 7: Tambahkan Teks ke Footer

Buat fragmen teks yang akan memuat nomor halaman:

```csharp
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");
```

Kemudian tambahkan fragmen teks ini ke footer:

```csharp
footer.Paragraphs.Add(txt);
```

Lihat betapa mudahnya? Anda telah mengatur nomor halaman secara dinamis!

## Langkah 8: Simpan Dokumen PDF

Langkah terakhir dalam petualangan kita adalah menyimpan dokumen. Gunakan perintah ini untuk menyimpan PDF yang baru Anda buat:

```csharp
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

Dan begitu saja, PDF Anda sudah siap dan dimuat dengan gambar header dan nomor halaman di footer!

## Kesimpulan

Nah, itu dia! Anda baru saja membuat PDF dengan gambar di header dan nomor halaman dinamis di footer menggunakan Aspose.PDF for .NET. Sungguh luar biasa bagaimana beberapa baris kode dapat menghasilkan output yang sangat bagus. Baik untuk laporan perusahaan atau dokumen yang dipersonalisasi, menambahkan elemen-elemen ini akan mengubah corak dan profesionalisme PDF Anda.

## Pertanyaan yang Sering Diajukan

### Dapatkah saya menggunakan Aspose.PDF pada platform .NET apa pun?
Ya, Aspose.PDF untuk .NET mendukung beberapa platform .NET termasuk .NET Framework, .NET Core, dan banyak lagi.

### Apakah ada uji coba gratis yang tersedia untuk Aspose.PDF?
 Tentu saja! Anda dapat mengunduh versi uji coba gratis[Di Sini](https://releases.aspose.com/).

### Format gambar apa yang didukung untuk header?
Aspose.PDF mendukung sebagian besar format gambar umum seperti JPG, PNG, dan BMP untuk header dan footer.

### Bisakah saya menyesuaikan format nomor halaman?
Ya, Anda dapat dengan mudah menyesuaikan teks dan format footer sesuai kebutuhan Anda.

### Apakah dukungan teknis tersedia?
 Ya, Aspose menyediakan dukungan khusus melalui forum mereka. Anda dapat menghubungi kami untuk meminta bantuan[Di Sini](https://forum.aspose.com/c/pdf/10).