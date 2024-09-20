---
title: Pengaturan Bahasa dan Judul
linktitle: Pengaturan Bahasa dan Judul
second_title: Referensi API Aspose.PDF untuk .NET
description: Panduan langkah demi langkah untuk mengonfigurasi bahasa dan judul dokumen PDF dengan Aspose.PDF untuk .NET. Buat dokumen multibahasa yang dipersonalisasi.
type: docs
weight: 140
url: /id/net/programming-with-tagged-pdf/setup-language-and-title/
---
## Perkenalan

Membuat PDF yang diberi tag merupakan aktivitas penting untuk memastikan aksesibilitas dan menyediakan format terstruktur untuk dokumen. Seiring dengan semakin inklusifnya lingkungan digital, pemahaman tentang cara membuat dokumen yang diberi tag menjadi semakin penting. Panduan komprehensif ini akan memandu Anda melalui proses pengaturan bahasa dan judul dalam PDF yang diberi tag menggunakan Aspose.PDF untuk .NET. Kami akan menguraikannya menjadi beberapa langkah yang mudah dipahami sehingga meskipun Anda baru memulai, Anda akan merasa seperti seorang profesional pada akhirnya. 

## Prasyarat

Sebelum menyelami dunia PDF yang diberi tag, mari kita kumpulkan semua yang Anda butuhkan. Berikut ini yang harus Anda siapkan:

- Pengetahuan Dasar tentang .NET: Meskipun Anda tidak perlu menjadi seorang coder yang hebat, keakraban dengan konsep .NET akan membuat perjalanan ini lebih lancar.
-  Aspose.PDF untuk .NET Terpasang: Pastikan Anda telah memasang pustaka tersebut. Anda dapat mengunduhnya untuk evaluasi atau membeli lisensi. Periksa[halaman unduhan di sini](https://releases.aspose.com/pdf/net/).
- Visual Studio: Di sinilah Anda akan menulis dan menguji kode Anda. Jika Anda tidak memilikinya, unduh dari situs web Microsoft.
- Kemahiran Bahasa C#: Panduan ini ditulis dalam bahasa C#. Sedikit pengalaman dengan C# pasti akan membantu Anda memahami bagian-bagian kode dengan mudah.

## Paket Impor

Setelah Anda menyiapkan prasyarat, saatnya mengimpor paket yang diperlukan. Anda dapat melakukannya dengan menambahkan perintah berikut di bagian atas berkas C# Anda:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Ruang nama ini memungkinkan Anda mengakses komponen yang diperlukan untuk membuat dan memanipulasi PDF dengan konten yang diberi tag. Anda mungkin bertanya-tanya, "Mengapa mengimpor paket?" Ini seperti menyiapkan kotak peralatan sebelum membangun sesuatu—Anda memerlukan peralatan yang tepat.

## Langkah 1: Inisialisasi Dokumen

Langkah pertama dalam perjalanan kita adalah membuat objek dokumen baru. Anda dapat menganggapnya sebagai peletakan fondasi untuk sebuah rumah—semuanya akan dibangun di atasnya.

```csharp
Document document = new Document();
```

Di sini, kami membuat dokumen PDF baru. Di sinilah semua konten Anda akan berada. 

## Langkah 2: Tentukan Direktori Dokumen

Berikutnya adalah menentukan di mana dokumen Anda akan disimpan. Anda memerlukan tempat untuk menyimpan berkas PDF yang baru Anda buat.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Pastikan untuk mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya tempat Anda ingin menyimpan PDF. Ini sama seperti mencari tempat parkir untuk mobil baru Anda.

## Langkah 3: Dapatkan Konten yang Ditandai

Sekarang, mari kita akses konten yang diberi tag pada dokumen kita. Konten yang diberi tag berfungsi sebagai tulang punggung untuk membuat PDF yang mudah diakses. 

```csharp
Tagged.ITaggedContent taggedContent = document.TaggedContent;
```

Dengan melakukan ini, Anda mengaktifkan potensi untuk menyusun PDF Anda, seperti membuat kerangka buku sebelum benar-benar menulisnya.

## Langkah 4: Atur Judul dan Bahasa

Setelah konten yang diberi tag siap, saatnya menentukan judul dokumen dan bahasa utama. 

```csharp
taggedContent.SetTitle("Example Tagged Document");
taggedContent.SetLanguage("en-US");
```

Anggaplah langkah ini sebagai pemberian identitas pada dokumen Anda. Judul mewakili esensi dari isi dokumen, sementara bahasanya mengomunikasikan konteks linguistik utama kepada pembaca.

## Langkah 5: Buat Elemen Header

PDF terstruktur sering kali menyertakan tajuk untuk membantu memandu pembaca. Mari buat elemen tajuk.

```csharp
LogicalStructure.HeaderElement h1 = taggedContent.CreateHeaderElement(1);
h1.SetText("Phrase on different languages");
taggedContent.RootElement.AppendChild(h1);
```

Di sini, kami membuat header (H1) dengan teks. Ini seperti menanam rambu yang mengarahkan pembaca ke apa yang akan mereka baca selanjutnya. 

## Langkah 6: Tambahkan Paragraf dalam Beberapa Bahasa

Di sinilah bagian yang menyenangkan dimulai—menambahkan konten dalam berbagai bahasa. Kita akan menambahkan beberapa paragraf untuk mewakili berbagai bahasa.

### Menambahkan Paragraf Bahasa Inggris

Mari kita mulai dengan bahasa Inggris:

```csharp
LogicalStructure.ParagraphElement pEN = taggedContent.CreateParagraphElement();
pEN.SetText("Hello, World!");
pEN.Language = "en-US";
taggedContent.RootElement.AppendChild(pEN);
```

Baris ini menambahkan sapaan ramah dalam bahasa Inggris. Seperti menyapa pembaca Anda dalam bahasa pilihan mereka.

### Menambahkan Paragraf Bahasa Jerman

Selanjutnya, mari kita tambahkan paragraf bahasa Jerman:

```csharp
LogicalStructure.ParagraphElement pDE = taggedContent.CreateParagraphElement();
pDE.SetText("Hallo Welt!");
pDE.Language = "de-DE";
taggedContent.RootElement.AppendChild(pDE);
```

Dengan ini, Anda menjangkau audiens berbahasa Jerman dan memperluas aksesibilitas dokumen Anda.

### Menambahkan Paragraf Bahasa Prancis

Demikian pula untuk bahasa Prancis:

```csharp
LogicalStructure.ParagraphElement pFR = taggedContent.CreateParagraphElement();
pFR.SetText("Bonjour le monde!");
pFR.Language = "fr-FR";
taggedContent.RootElement.AppendChild(pFR);
```

Sekali lagi, kami merangkul keberagaman dengan menyertakan teks bahasa Prancis. 

### Menambahkan Paragraf Bahasa Spanyol

Terakhir, mari kita bahas bahasa Spanyol:

```csharp
LogicalStructure.ParagraphElement pSP = taggedContent.CreateParagraphElement();
pSP.SetText("¡Hola Mundo!");
pSP.Language = "es-ES";
taggedContent.RootElement.AppendChild(pSP);
```

Dengan tambahan ini, Anda menunjukkan bahwa dokumen Anda berbicara dalam banyak bahasa, sehingga mendorong inklusivitas.

## Langkah 7: Simpan Dokumen PDF yang Ditandai

Sekarang setelah Anda membuat dokumen dengan berbagai bahasa, waktunya menyimpannya. 

```csharp
document.Save(dataDir + "SetupLanguageAndTitle.pdf");
```

Dan begitu saja, kreasi Anda selesai dan disimpan! Anggap saja ini seperti menyegel amplop sebelum mengirim surat Anda.

## Kesimpulan

Membuat PDF yang diberi tag dengan Aspose.PDF untuk .NET bukan hanya tentang pengodean; ini tentang membuat dokumen Anda mudah diakses dan ramah bagi semua pembaca. Anda telah mempelajari cara mengatur judul, bahasa, dan bahkan menambahkan beberapa paragraf multibahasa ke PDF Anda. Dengan keterampilan ini, Anda berada di jalur yang tepat untuk menghasilkan konten digital yang inklusif. 


## Pertanyaan yang Sering Diajukan

### Apa itu PDF yang diberi tag?
PDF yang diberi tag adalah jenis dokumen PDF yang berisi informasi tambahan yang memungkinkan pembacaan terstruktur atas kontennya. Ini khususnya bermanfaat untuk teknologi bantuan.

### Bagaimana Aspose.PDF untuk .NET membantu dalam membuat PDF yang diberi tag?
Aspose.PDF untuk .NET menyediakan berbagai kelas dan metode yang memungkinkan Anda membuat dan memanipulasi PDF dengan mudah, termasuk menambahkan konten yang diberi tag untuk aksesibilitas.

### Bisakah saya membuat PDF yang diberi tag dalam berbagai bahasa?
Ya! Aspose.PDF mendukung berbagai bahasa, sehingga Anda dapat menambahkan konten dalam berbagai bahasa dalam dokumen PDF yang sama.

### Apakah saya memerlukan lisensi untuk menggunakan Aspose.PDF?
Meskipun Anda dapat mencobanya secara gratis, lisensi diperlukan untuk penggunaan produksi. Pertimbangkan untuk mengunjungi[halaman pembelian](https://purchase.aspose.com/buy) untuk informasi lebih lanjut.

### Di mana saya dapat menemukan informasi lebih lanjut tentang Aspose.PDF?
 Anda dapat menemukan dokumentasi dan dukungan lengkap untuk Aspose.PDF[Di Sini](https://reference.aspose.com/pdf/net/).