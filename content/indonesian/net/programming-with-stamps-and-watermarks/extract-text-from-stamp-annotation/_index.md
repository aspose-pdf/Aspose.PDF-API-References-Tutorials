---
title: Ekstrak Teks Dari Anotasi Prangko
linktitle: Ekstrak Teks Dari Anotasi Prangko
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mengekstrak teks dari anotasi prangko dalam PDF menggunakan Aspose.PDF untuk .NET dengan tutorial langkah demi langkah ini, lengkap dengan contoh kode terperinci.
type: docs
weight: 80
url: /id/net/programming-with-stamps-and-watermarks/extract-text-from-stamp-annotation/
---
## Perkenalan

Saat bekerja dengan file PDF, mengekstrak data tertentu seperti teks dari anotasi bisa sangat berguna. Dalam tutorial ini, kami akan memandu Anda langkah demi langkah tentang cara mengekstrak teks dari anotasi prangko dalam dokumen PDF menggunakan Aspose.PDF for .NET. Pustaka canggih ini memungkinkan pengembang untuk memanipulasi file PDF, memungkinkan tugas-tugas seperti ekstraksi teks, manajemen anotasi, dan banyak lagi. Mari kita bahas detailnya dan uraikan semuanya!

## Prasyarat

Sebelum kita masuk ke tutorial, ada beberapa hal yang Anda perlukan:

-  Aspose.PDF untuk .NET: Anda harus menginstal Aspose.PDF untuk .NET. Anda dapat[unduh versi terbaru di sini](https://releases.aspose.com/pdf/net/).
- Visual Studio: Panduan ini mengasumsikan Anda menggunakan Visual Studio sebagai lingkungan pengembangan terintegrasi (IDE).
- Pengetahuan Dasar C#: Anda harus memiliki pemahaman dasar tentang pemrograman C#.

Pastikan Anda telah menyiapkan alat-alat ini sehingga Anda dapat mengikuti tutorialnya.

## Paket Impor

Langkah pertama dalam setiap proyek .NET adalah mengimpor namespace yang diperlukan. Dengan Aspose.PDF, Anda hanya memerlukan beberapa impor kunci untuk memulai:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

Impor ini menghadirkan fungsionalitas yang dibutuhkan untuk bekerja dengan dokumen PDF, anotasi, dan ekstraksi teks.

Mari kita telusuri proses mengekstraksi teks dari anotasi prangko. Proses ini melibatkan pemuatan dokumen PDF, identifikasi anotasi prangko, dan ekstraksi konten teks.

## Langkah 1: Muat Dokumen PDF

Hal pertama yang perlu Anda lakukan adalah memuat berkas PDF tempat anotasi prangko berada. Dalam contoh ini, kami akan memuat berkas PDF contoh dari direktori lokal Anda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "test.pdf");
```

 Di sini, kami menggunakan`Document` kelas yang disediakan oleh Aspose.PDF untuk membuka dan berinteraksi dengan file PDF.`dataDir` variabel mewakili jalur ke file Anda. Ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya tempat PDF Anda disimpan.

## Langkah 2: Identifikasi Anotasi Prangko

Anotasi PDF diidentifikasi berdasarkan jenis dan posisinya dalam dokumen. Dalam kasus kami, kami ingin menemukan Anotasi Stempel pada halaman tertentu. Berikut cara melakukannya:

```csharp
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;
```

Pada baris kode ini:
- `doc.Pages[1]`: Mengakses halaman pertama dokumen.
- `Annotations[3]`: Mengacu pada anotasi keempat pada halaman (karena pengindeksan dimulai pada 0).
- `as StampAnnotation` : Melemparkan anotasi ke dalam`StampAnnotation` objek, yang merupakan jenis anotasi spesifik yang sedang kita hadapi.

## Langkah 3: Buat Penyerap Teks

Untuk mengekstrak teks dari anotasi prangko, kita perlu menggunakan Text Absorber. Alat ini akan membantu kita menyerap atau menangkap teks dari area tertentu di PDF, dalam hal ini, anotasi.

```csharp
TextAbsorber ta = new TextAbsorber();
```

 Itu`TextAbsorber` Kelas ini dirancang untuk mengekstrak teks dari bagian mana pun dalam dokumen, dan kita akan menggunakannya untuk menargetkan tampilan anotasi.

## Langkah 4: Ekstrak Tampilan Anotasi Prangko

Anotasi stempel dalam PDF memiliki tampilan terkait, biasanya disimpan dalam bentuk XForm. Kita perlu mengambil tampilan ini untuk mengakses teks sebenarnya di dalam stempel.

```csharp
XForm ap = annot.Appearance["N"];
```

Di Sini:
- `annot.Appearance["N"]`: Mengambil aliran tampilan bernama "N" (yang mewakili tampilan normal anotasi).

## Langkah 5: Ekstrak Konten Teks

 Sekarang setelah kita memiliki tampilannya, kita dapat menggunakan`TextAbsorber` untuk mengunjungi penampilan dan menangkap teks.

```csharp
ta.Visit(ap);
```

 Itu`Visit` metode memungkinkan`TextAbsorber` untuk menganalisis tampilan dan mengekstrak konten tekstual yang tertanam di dalamnya.

## Langkah 6: Menampilkan Teks yang Diekstrak

Akhirnya, setelah teks diekstraksi, kita dapat menampilkannya ke konsol atau menyimpannya untuk digunakan lebih lanjut.

```csharp
Console.WriteLine(ta.Text);
```

Baris kode sederhana ini menampilkan teks yang diekstrak di jendela konsol. Anda juga dapat menyimpannya ke dalam file atau memanipulasinya lebih lanjut tergantung pada kebutuhan Anda.

## Kesimpulan

Bekerja dengan anotasi dalam dokumen PDF, terutama anotasi stempel, dapat menambahkan fungsionalitas yang signifikan ke aplikasi Anda. Dengan Aspose.PDF untuk .NET, Anda memiliki seperangkat alat yang kuat yang memudahkan untuk mengekstrak data, memanipulasi anotasi, dan berinteraksi dengan PDF dengan cara yang bermakna. Dalam tutorial ini, kami menunjukkan kepada Anda cara mengekstrak teks dari anotasi stempel hanya dalam beberapa langkah sederhana. Sekarang giliran Anda untuk bereksperimen dengan fitur-fitur ini dalam proyek Anda!

## Pertanyaan yang Sering Diajukan

### Bisakah saya mengekstrak teks dari jenis anotasi lain menggunakan Aspose.PDF?  
Ya, Aspose.PDF memungkinkan Anda mengekstrak teks dari berbagai jenis anotasi seperti anotasi teks, anotasi teks bebas, dan banyak lagi, bukan hanya anotasi stempel.

### Apakah Aspose.PDF mendukung penambahan anotasi khusus?  
Tentu saja! Aspose.PDF mendukung pembuatan dan penambahan anotasi khusus ke dokumen PDF, memberikan Anda fleksibilitas dalam cara mengelola dan menyajikan data.

### Bisakah saya mengekstrak gambar dari anotasi prangko?  
Ya, Anda dapat mengekstrak gambar dari anotasi prangko menggunakan metode serupa dengan mengakses tampilan dan mengambil data gambar.

### Fitur apa lagi yang ditawarkan Aspose.PDF untuk .NET?  
Aspose.PDF untuk .NET menawarkan berbagai fitur termasuk manipulasi teks, penanganan bidang formulir, konversi dokumen, dan banyak lagi.

### Apakah Aspose.PDF untuk .NET gratis?  
 Aspose.PDF untuk .NET menawarkan uji coba gratis, tetapi untuk mengakses rangkaian fitur lengkap, Anda perlu membeli lisensi. Anda juga dapat mengajukan permohonan[lisensi sementara](https://purchase.aspose.com/temporary-license/).