---
title: Tetapkan Properti Callout Dalam File PDF
linktitle: Tetapkan Properti Callout Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mengatur properti callout dalam file PDF menggunakan Aspose.PDF untuk .NET dalam tutorial langkah demi langkah terperinci ini.
type: docs
weight: 130
url: /id/net/annotations/setcalloutproperty/
---
## Perkenalan

Membuat dokumen PDF yang profesional dan menarik secara visual sering kali memerlukan penambahan anotasi yang menarik perhatian ke konten tertentu. Salah satu anotasi tersebut adalah callout, yang seperti gelembung ucapan yang Anda lihat dalam komik. Anotasi tersebut membantu memperjelas atau menekankan teks dalam PDF Anda. Aspose.PDF untuk .NET memudahkan Anda untuk menambahkan anotasi tersebut ke dokumen Anda, dan dalam tutorial ini, kami akan memandu Anda tentang cara menyetel properti callout dalam file PDF menggunakan pustaka yang canggih ini. Baik Anda seorang pengembang berpengalaman atau baru memulai, di akhir panduan ini, Anda akan memiliki pemahaman yang jelas tentang cara bekerja dengan callout dalam file PDF.

## Prasyarat

Sebelum kita masuk ke kode, mari kita bahas hal-hal penting yang Anda perlukan untuk memulai.

1.  Aspose.PDF untuk .NET: Pastikan Anda telah menginstal pustaka Aspose.PDF untuk .NET. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/pdf/net/).
2. IDE: Lingkungan pengembangan seperti Visual Studio.
3. .NET Framework: Pastikan Anda telah menginstal .NET di komputer Anda.
4. Lisensi Sementara: Jika Anda ingin mencoba fitur lengkap Aspose.PDF tanpa batasan, dapatkan lisensi sementara.[lisensi sementara](https://purchase.aspose.com/temporary-license/).

## Paket Impor

Sebelum Anda mulai menulis kode, Anda perlu mengimpor paket yang diperlukan yang memungkinkan Anda bekerja dengan file PDF dan anotasi.

```csharp
using Aspose.Pdf.Annotations;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

Impor ini akan memberi Anda semua kelas dan metode yang diperlukan untuk memanipulasi dokumen PDF dan membuat anotasi seperti keterangan.

## Langkah 1: Inisialisasi Dokumen PDF

Langkah pertama dalam perjalanan kita adalah menginisialisasi dokumen PDF baru tempat kita akan menambahkan anotasi keterangan. Anggap saja ini seperti menyiapkan kanvas kosong tempat Anda dapat mulai menambahkan elemen.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Inisialisasi dokumen PDF baru
Document doc = new Document();
```
 Di sini, kita membuat yang baru`Document` objek yang akan berfungsi sebagai file PDF kita.`dataDir` variabel diatur ke direktori tempat Anda ingin menyimpan berkas PDF setelah selesai.

## Langkah 2: Tambahkan Halaman Baru ke Dokumen

Dokumen PDF dapat memiliki beberapa halaman, dan pada langkah ini, kita akan menambahkan halaman baru ke dokumen kita. Halaman ini akan menjadi tempat anotasi keterangan kita.

```csharp
//Tambahkan halaman baru ke dokumen
Page page = doc.Pages.Add();
```
 Itu`Pages.Add()`metode ini digunakan untuk menambahkan halaman baru ke`doc` objek. Halaman baru disimpan di`page` variabel, yang akan kita gunakan nanti saat menambahkan anotasi.

## Langkah 3: Tentukan Tampilan Default

Anotasi, seperti keterangan, memiliki tampilan visual yang dapat Anda sesuaikan. Pada langkah ini, kita akan menentukan bagaimana teks dalam keterangan akan terlihat.

```csharp
// Tentukan tampilan default untuk anotasi
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```
 Kami menciptakan sebuah`DefaultAppearance` objek yang menentukan warna teks dan ukuran fon. Di sini, teks akan berwarna merah, dan ukuran fon ditetapkan ke 10. Tampilan ini akan diterapkan pada anotasi keterangan.

## Langkah 4: Buat Anotasi Teks Bebas

Sekarang saatnya membuat anotasi yang sebenarnya. Anotasi teks bebas memungkinkan kita menambahkan keterangan dengan teks dan gaya tertentu.

```csharp
// Buat FreeTextAnnotation dengan callout
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
```
 Kami menciptakan sebuah`FreeTextAnnotation` objek dengan koordinat tertentu, yang menentukan posisinya di halaman.`Intent` diatur untuk`FreeTextCallout` , yang menunjukkan bahwa ini adalah anotasi panggilan.`EndingStyle` diatur untuk`OpenArrow`yang berarti baris keterangan akan diakhiri dengan panah terbuka.

## Langkah 5: Tentukan Titik Garis Panggilan

Anotasi keterangan memiliki garis yang menunjuk ke area yang diinginkan. Di sini, kita akan menentukan titik-titik yang membentuk garis ini.

```csharp
// Tentukan titik untuk garis panggilan
fta.Callout = new Point[]
{
    new Point(428.25, 651.75), 
    new Point(462.75, 681.375), 
    new Point(474, 681.375)
};
```
 Itu`Callout` properti adalah sebuah array`Point` objek, yang masing-masing mewakili koordinat pada halaman. Titik-titik ini menentukan jalur baris keterangan, sehingga memberikan tampilan gelembung ucapan klasik.

## Langkah 6: Tambahkan Anotasi ke Halaman

Setelah membuat dan mengonfigurasi anotasi, langkah berikutnya adalah menambahkannya ke halaman.

```csharp
// Tambahkan anotasi ke halaman
page.Annotations.Add(fta);
```
 Itu`Annotations.Add()` Metode ini digunakan untuk menempatkan anotasi pada halaman yang kita buat sebelumnya. Langkah ini secara efektif "menggambar" keterangan pada halaman PDF.

## Langkah 7: Mengatur Konten Teks Kaya

Anotasi keterangan dapat menyertakan teks kaya, yang memungkinkan konten yang diformat dalam gelembung. Mari tambahkan beberapa contoh teks.

```csharp
// Tetapkan teks kaya untuk anotasi
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"><span style=\"font-size:9.0pt;font-family:Helvetica\">Ini adalah contoh</span></p></body>";
```
 Itu`RichText` properti diatur dengan konten HTML. Hal ini memungkinkan pemformatan terperinci dalam keterangan, seperti menentukan ukuran font, warna, dan gaya.

## Langkah 8: Simpan Dokumen PDF

Terakhir, setelah menyiapkan semuanya, kita perlu menyimpan dokumen. Langkah ini menyelesaikan pembuatan PDF dengan anotasi callout.

```csharp
// Simpan dokumen
doc.Save(dataDir + "SetCalloutProperty.pdf");
```
 Itu`Save()` metode menyimpan dokumen ke direktori yang ditentukan dengan nama file "SetCalloutProperty.pdf". Langkah ini mengakhiri proses pembuatan PDF kita.

## Kesimpulan

Nah, itu dia! Anda baru saja membuat dokumen PDF dengan anotasi callout menggunakan Aspose.PDF untuk .NET. Anotasi ini dapat sangat berguna untuk menyorot atau menjelaskan bagian tertentu dari dokumen Anda. Aspose.PDF menawarkan API canggih yang membuat manipulasi PDF menjadi mudah dan fleksibel. Baik Anda menambahkan anotasi, mengonversi dokumen, atau menangani tugas PDF yang rumit, Aspose.PDF siap membantu Anda.

## Pertanyaan yang Sering Diajukan

### Bisakah saya menyesuaikan tampilan keterangan lebih lanjut?

Tentu saja! Anda dapat menyesuaikan berbagai aspek seperti warna garis, ketebalan, serta jenis dan gaya font teks.

### Bisakah saya menambahkan beberapa keterangan pada satu halaman?

Ya, Anda dapat menambahkan keterangan sebanyak-banyaknya sesuai kebutuhan dengan mengulangi langkah-langkah untuk setiap anotasi.

### Bagaimana cara mengubah posisi keterangan?

 Cukup ubah koordinat di`Rectangle` Dan`Callout` properti untuk memposisikan ulang anotasi.

### Bisakah saya menambahkan jenis anotasi lain menggunakan Aspose.PDF?

Ya, Aspose.PDF mendukung berbagai jenis anotasi, termasuk sorotan, stempel, dan lampiran file.

### Apakah konten teks kaya terbatas pada HTML?

 Itu`RichText` Properti mendukung sebagian kecil HTML, yang memungkinkan Anda menyertakan teks bergaya dan format dasar.