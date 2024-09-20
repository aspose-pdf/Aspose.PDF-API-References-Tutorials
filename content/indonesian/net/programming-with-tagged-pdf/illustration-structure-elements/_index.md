---
title: Elemen Struktur Ilustrasi
linktitle: Elemen Struktur Ilustrasi
second_title: Referensi API Aspose.PDF untuk .NET
description: Buat PDF terstruktur dengan elemen ilustrasi di Aspose.PDF untuk .NET dengan mengikuti tutorial langkah demi langkah kami.
type: docs
weight: 100
url: /id/net/programming-with-tagged-pdf/illustration-structure-elements/
---
## Perkenalan

Apakah Anda siap membuat PDF yang menakjubkan dan terstruktur dalam aplikasi .NET Anda? Baik Anda sedang mengerjakan proyek yang memerlukan pemberian tag pada konten atau sekadar ingin membawa PDF Anda ke tingkat berikutnya, Aspose.PDF untuk .NET memiliki semua alat yang Anda butuhkan untuk bekerja dengan elemen struktur ilustrasi. Dalam tutorial ini, saya akan memandu Anda melalui proses ini langkah demi langkah, memastikan bahkan bagian yang paling rumit pun menjadi sangat jelas.

## Prasyarat

Sebelum kita membahas detailnya, mari pastikan Anda memiliki semua yang dibutuhkan agar dapat mengikutinya dengan lancar.

1.  Aspose.PDF untuk .NET – Anda memerlukan pustaka Aspose.PDF yang terinstal. Belum memilikinya? Anda dapat[unduh disini](https://releases.aspose.com/pdf/net/) Jika Anda ingin mengujinya terlebih dahulu, Anda dapat mengambil[uji coba gratis](https://releases.aspose.com/).
2. Visual Studio – Kami akan membuat kode dalam C#, jadi pastikan Visual Studio atau IDE yang kompatibel telah terpasang.
3. .NET Framework – Pastikan Anda memiliki versi yang kompatibel dengan Aspose.PDF untuk .NET.
4.  Lisensi Sementara – Aspose.PDF hadir dengan beberapa batasan dalam mode uji coba, jadi dapatkan lisensi sementara.[lisensi sementara](https://purchase.aspose.com/temporary-license/) untuk membuka fitur lengkap.

Selesai! Sekarang mari impor namespace yang diperlukan dan lanjutkan dengan pengkodean.

## Mengimpor Ruang Nama

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Ini adalah fondasinya—tanpa mengimpor namespace ini, kita tidak dapat berinteraksi dengan fitur Aspose.PDF atau menangani konten PDF yang diberi tag. Sekarang mari kita uraikan langkah-langkahnya secara terperinci.

## Langkah 1: Menyiapkan Direktori Dokumen Anda

Sebelum Anda mulai membuat PDF, Anda perlu menentukan jalur ke direktori dokumen tempat file akan disimpan. Ini adalah folder di sistem tempat gambar atau aset lainnya disimpan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Langkah ini sederhana, tetapi penting. Anda memberi tahu program tempat menemukan dan menyimpan file yang akan Anda kerjakan. Ini seperti memiliki basis untuk PDF Anda. Ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya di mesin Anda.

## Langkah 2: Membuat Dokumen PDF Baru

Sekarang, saatnya membuat dokumen PDF. Pada langkah ini, kita akan memulai dokumen PDF kosong, yang akan kita modifikasi dan tingkatkan pada langkah berikutnya.
 Buat Dokumen

```csharp
Document document = new Document();
```

Baris ini melakukan semua keajaiban. Baris ini membuat berkas PDF baru yang benar-benar kosong, menunggu Anda untuk menambahkan konten ke dalamnya. Anggap saja ini seperti membuka kanvas baru.

## Langkah 3: Mengakses Konten PDF yang Ditandai

Untuk bekerja dengan elemen struktur ilustrasi, kita perlu memanfaatkan Konten Berlabel dokumen. Ini memungkinkan kita untuk menentukan label tertentu, sehingga PDF menjadi lebih terstruktur dan mudah diakses.

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

 Di sinilah keajaiban terjadi!`TaggedContent` objek memungkinkan kita menentukan bagaimana elemen-elemen dalam PDF ditafsirkan. Jika Anda bekerja dengan aksesibilitas atau struktur, langkah ini sangat penting.

## Langkah 4: Mengatur Judul dan Bahasa Dokumen

Kami membuat PDF terstruktur, jadi penting untuk menentukan judul dan bahasa. Ini tidak hanya membantu aksesibilitas tetapi juga membuat dokumen lebih profesional dan mudah dicari.

```csharp
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
```

Dengan menentukan judul dan bahasa, pada dasarnya Anda memberikan sedikit kepribadian pada PDF Anda. Judul akan muncul di properti dokumen, dan pengaturan bahasa akan memastikan kompatibilitas dengan pembaca layar dan alat aksesibilitas lainnya.

## Langkah 5: Membuat Elemen Ilustrasi (Gambar)

Sekarang tibalah bagian yang menarik—menambahkan ilustrasi! Dalam kasus ini, kita akan membuat elemen figur yang menyertakan gambar, deskripsi teks alternatif, dan judul.

```csharp
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
```

Kode ini membuat elemen gambar baru dan menambahkannya ke elemen akar dokumen. Anggap saja ini seperti menambahkan tempat penampung gambar ke dokumen Anda.

## Langkah 6: Menambahkan Teks Alternatif, Judul, dan Gambar

Untuk memastikan PDF Anda dapat diakses, sebaiknya sertakan teks alternatif dan judul untuk ilustrasi Anda. Kami juga akan melampirkan gambar.

```csharp
figure1.AlternativeText = "Figure One";
figure1.Title = "Image 1";
figure1.SetTag("Fig1");
figure1.SetImage(dataDir + "image.jpg");
```

 Ini adalah sentuhan terakhir. Kami memberikan teks alt deskriptif pada gambar kami (yang berguna untuk pembaca layar), judul, dan pengaturan berkas gambar yang sebenarnya.`SetTag`metode menandai gambar, sehingga lebih mudah untuk dirujuk nanti.

 Catatan Penting: Pastikan jalur gambar di`SetImage` menunjuk ke berkas gambar yang valid pada komputer Anda.

## Langkah 7: Menyimpan Dokumen PDF yang Ditandai

Setelah semua konten ditambahkan dan terstruktur, saatnya menyimpan PDF. Langkah ini menyelesaikan semuanya dan menghasilkan file yang sebenarnya.

```csharp
document.Save(dataDir + "IllustrationStructureElements.pdf");
```

Sederhana, bukan? Perintah ini mengambil semua pekerjaan yang telah Anda lakukan dan membuat file PDF baru di direktori yang Anda tentukan sebelumnya. Sekarang, periksa folder Anda, dan voila—Anda memiliki PDF terstruktur dengan elemen ilustrasi!

## Kesimpulan

Selamat! Anda baru saja mempelajari cara membuat PDF berlabel dengan elemen struktur ilustrasi menggunakan Aspose.PDF untuk .NET. Pendekatan ini memastikan bahwa PDF Anda tidak hanya menarik secara visual tetapi juga terstruktur dan mudah diakses. Dengan memberi label pada konten dan menambahkan teks alternatif, Anda memastikan semua orang, termasuk mereka yang menggunakan teknologi bantuan, dapat menikmati dokumen Anda.

## Pertanyaan yang Sering Diajukan

### Apa itu konten PDF yang diberi tag?
PDF yang diberi tag adalah PDF yang menyertakan tag atau label untuk mengidentifikasi berbagai elemen, seperti judul, paragraf, dan gambar, sehingga membuat dokumen lebih mudah diakses.

### Bagaimana pengaturan teks alternatif membantu?
Teks alternatif menyediakan deskripsi untuk gambar, yang dapat dibaca oleh pembaca layar, meningkatkan aksesibilitas bagi pengguna yang memiliki gangguan penglihatan.

### Bisakah saya menambahkan beberapa gambar ke PDF yang diberi tag?
 Ya! Anda dapat membuat beberapa`FigureElement` objek dan menambahkan masing-masing objek ke dokumen Anda, seperti yang kita lakukan dengan gambar tunggal.

### Apakah saya memerlukan lisensi untuk menggunakan Aspose.PDF untuk .NET?
 Ya, Aspose.PDF adalah pustaka berbayar, tetapi Anda bisa mendapatkannya[lisensi sementara](https://purchase.aspose.com/temporary-license/) atau mulai dengan[uji coba gratis](https://releases.aspose.com/).

### Apakah mungkin untuk mengubah elemen gambar setelah membuat PDF?
Setelah PDF disimpan, Anda tidak dapat mengubahnya secara langsung, tetapi Anda dapat membuka kembali dokumen tersebut, membuat perubahan, dan menyimpannya lagi menggunakan Aspose.PDF.