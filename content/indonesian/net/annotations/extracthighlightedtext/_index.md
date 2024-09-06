---
title: Ekstrak Teks yang Disorot Dalam File PDF
linktitle: Ekstrak Teks yang Disorot Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mengekstrak teks yang disorot dari file PDF secara efisien menggunakan Aspose.PDF for .NET dengan tutorial ini. Sempurna untuk analisis data dan peninjauan konten.
type: docs
weight: 60
url: /id/net/annotations/extracthighlightedtext/
---
## Perkenalan

Saat bekerja dengan file PDF, mengekstrak teks yang disorot dapat menjadi tugas penting, baik untuk analisis data, peninjauan konten, atau sekadar mengatur catatan Anda. Jika Anda menggunakan Aspose.PDF untuk .NET, proses ini mudah dan efisien. Dalam tutorial ini, kami akan memandu Anda melalui cara mengekstrak teks yang disorot dari dokumen PDF menggunakan Aspose.PDF untuk .NET. Kami akan membahas semuanya mulai dari prasyarat hingga panduan langkah demi langkah, memastikan Anda memiliki pemahaman yang komprehensif pada akhirnya.

## Prasyarat

Sebelum menyelami kode, ada beberapa hal yang perlu Anda siapkan:

-  Pustaka Aspose.PDF untuk .NET: Pastikan Anda telah menginstal pustaka Aspose.PDF. Jika belum, Anda dapat mengunduhnya dari[halaman rilis](https://releases.aspose.com/pdf/net/).
- Lingkungan Pengembangan: Anda harus menyiapkan lingkungan pengembangan yang berfungsi, seperti Visual Studio.
- Pengetahuan Dasar C#: Keakraban dengan bahasa pemrograman C# dan pemrograman berorientasi objek sangat penting.
-  Lisensi Aspose yang Valid: Meskipun Anda dapat memulai dengan uji coba gratis, pertimbangkan untuk mendapatkan lisensi Aspose yang Valid.[lisensi sementara](https://purchase.aspose.com/temporary-license/) atau membeli satu dari[Di Sini](https://purchase.aspose.com/buy) untuk penggunaan tanpa batas.

## Paket Impor

Untuk memulai, Anda perlu mengimpor namespace yang diperlukan dalam proyek C# Anda. Ini penting untuk mengakses kelas dan metode yang disediakan oleh Aspose.PDF untuk .NET.

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Sekarang, mari kita bahas proses mengekstrak teks yang disorot dari file PDF menggunakan Aspose.PDF untuk .NET. Setiap langkah dijelaskan secara terperinci untuk membantu Anda memahami konsep dasar dan penerapannya.

## Langkah 1: Siapkan Direktori Proyek Anda

Pertama-tama, Anda perlu menyiapkan direktori proyek tempat file PDF Anda berada. Di sinilah keajaiban terjadi.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"`dengan jalur sebenarnya ke direktori tempat file PDF berada. Direktori ini adalah tempat aplikasi akan mengambil PDF untuk diproses.

## Langkah 2: Muat Dokumen PDF

 Selanjutnya, Anda perlu memuat dokumen PDF tempat Anda ingin mengekstrak teks yang disorot. Ini dilakukan dengan menggunakan`Document` kelas disediakan oleh Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

 Itu`Document` kelas diwujudkan dengan jalur ke file PDF. Di sini,`"ExtractHighlightedText.pdf"` adalah nama berkas PDF yang berisi teks yang disorot. Pastikan berkas ini ada di direktori yang ditentukan.

## Langkah 3: Akses Koleksi Anotasi

Setelah dokumen PDF dimuat, langkah selanjutnya adalah mengakses anotasi pada halaman pertama dokumen. Anotasi digunakan dalam PDF untuk menambahkan informasi tambahan seperti sorotan, komentar, dan lain-lain.

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
```

 Itu`Annotations` milik`Page` Objek menyediakan akses ke semua anotasi pada halaman tertentu PDF. Di sini, kita mengulang setiap anotasi pada halaman pertama.

## Langkah 4: Filter untuk Anotasi Teks yang Disorot

Sekarang setelah kita memiliki akses ke semua anotasi, kita perlu memfilter hanya anotasi teks yang disorot. Ini dicapai dengan memeriksa jenis setiap anotasi.

```csharp
if (annotation is TextMarkupAnnotation)
{
    TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
```

 Itu`TextMarkupAnnotation` kelas digunakan untuk mewakili anotasi markup teks, termasuk sorotan.`is` kata kunci memeriksa apakah anotasi bertipe`TextMarkupAnnotation` , dan jika ya, maka ia akan memberikan anotasi ke`TextMarkupAnnotation`.

## Langkah 5: Ekstrak Teks yang Disorot

Setelah anotasi yang disorot sudah teridentifikasi, langkah berikutnya adalah mengekstrak teks yang terkait dengan sorotan tersebut.

```csharp
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
foreach (TextFragment tf in collection)
{
    Console.WriteLine(tf.Text);
}
```

 Itu`GetMarkedTextFragments()` metode mengembalikan koleksi`TextFragment` objek, masing-masing mewakili sebagian teks yang disorot. Kami mengulang koleksi ini dan mencetak teks setiap fragmen ke konsol.

## Kesimpulan

Mengekstrak teks yang disorot dari PDF menggunakan Aspose.PDF untuk .NET merupakan fitur hebat yang dapat memperlancar alur kerja Anda, terutama jika Anda menangani dokumen berukuran besar. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat dengan mudah menerapkan fungsi ini dalam proyek Anda sendiri. Baik Anda mengatur catatan, menyiapkan laporan, atau melakukan analisis data, metode ini menawarkan solusi yang mudah untuk mengekstrak dan memanfaatkan teks yang disorot.

## Pertanyaan yang Sering Diajukan

### Bisakah saya mengekstrak jenis anotasi lain menggunakan metode ini?  
 Ya, Anda dapat mengekstrak jenis anotasi lain dengan memodifikasi`if` kondisi untuk memeriksa berbagai jenis anotasi, seperti`TextAnnotation`, `StampAnnotation`, dll.

### Apakah mungkin untuk mengekstrak teks yang disorot dari semua halaman PDF?  
Tentu saja! Anda dapat mengulang setiap halaman dokumen PDF dan menerapkan logika ekstraksi yang sama untuk mengumpulkan teks yang disorot dari setiap halaman.

### Apakah saya memerlukan lisensi untuk menggunakan Aspose.PDF untuk .NET?  
 Meskipun Anda dapat memulai dengan uji coba gratis, disarankan untuk mendapatkan versi uji coba gratis.[lisensi sementara](https://purchase.aspose.com/temporary-license/)atau membeli lisensi penuh untuk akses tak terbatas ke semua fitur.

### Bisakah saya menyimpan teks yang diekstrak ke dalam sebuah berkas alih-alih mencetaknya ke konsol?  
Ya, Anda dapat dengan mudah memodifikasi kode untuk menyimpan teks yang diekstrak ke berkas teks atau format lain yang diinginkan.

### Apakah Aspose.PDF mendukung platform lain selain .NET?  
Ya, Aspose.PDF juga mendukung Java dan platform lainnya, menawarkan fungsionalitas serupa di berbagai lingkungan.