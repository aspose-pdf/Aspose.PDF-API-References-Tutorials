---
title: Ekstrak Teks Dari Anotasi Prangko
linktitle: Ekstrak Teks Dari Anotasi Prangko
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mudah mengekstrak teks dari anotasi prangko di dokumen PDF Anda dengan Aspose.PDF untuk .NET.
type: docs
weight: 80
url: /id/net/programming-with-stamps-and-watermarks/extract-text-from-stamp-annotation/
---
Dalam tutorial ini, kami akan memandu Anda langkah demi langkah tentang cara mengekstrak teks dari anotasi prangko dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Kami akan menunjukkan kepada Anda cara menggunakan kode sumber C# yang disediakan untuk mengekstrak teks dari anotasi prangko tertentu pada halaman tertentu dalam dokumen PDF.

## Langkah 1: Menyiapkan lingkungan

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Lingkungan pengembangan .NET yang terinstal.
- Pustaka Aspose.PDF untuk .NET diunduh dan dirujuk dalam proyek Anda.

## Langkah 2: Memuat dokumen PDF

Langkah pertama adalah memuat dokumen PDF yang ada ke dalam proyek Anda. Berikut caranya:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Muat dokumen
Document doc = new Document(dataDir + "test.pdf");
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori tempat dokumen PDF Anda berada.

## Langkah 3: Ekstrak teks dari anotasi prangko

Sekarang setelah Anda memuat dokumen PDF, Anda dapat mengekstrak teks dari anotasi prangko tertentu. Berikut caranya:

```csharp
// Ambil anotasi buffer
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;

// Membuat penyerap teks
TextAbsorber ta = new TextAbsorber();

// Kunjungi tampilan anotasi
XForm ap = annot. Appearance["N"];
ta.Visit(ap);

// Menampilkan teks yang diekstraksi
Console.WriteLine(ta.Text);
```

Kode di atas mengambil anotasi stempel dari halaman tertentu pada dokumen PDF, lalu menggunakan penyerap teks untuk mengekstrak teks dari tampilan anotasi. Teks yang diekstrak kemudian ditampilkan dalam output.

### Contoh kode sumber untuk Ekstrak Teks Dari Anotasi Stempel menggunakan Aspose.PDF untuk .NET 
```csharp

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "test.pdf");
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;
TextAbsorber ta = new TextAbsorber();
XForm ap = annot.Appearance["N"];
ta.Visit(ap);
Console.WriteLine(ta.Text);

```

## Kesimpulan

Selamat! Anda telah mempelajari cara mengekstrak teks dari anotasi prangko dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Kini Anda dapat menggunakan metode ini untuk mengekstrak teks dari anotasi lain dalam dokumen PDF Anda.

### FAQ untuk mengekstrak teks dari anotasi prangko

#### T: Apa yang dimaksud dengan anotasi prangko dalam dokumen PDF, dan mengapa saya perlu mengekstrak teks darinya?

A: Anotasi prangko dalam dokumen PDF adalah elemen grafis yang dapat digunakan untuk memberikan informasi tambahan, seperti tanda air atau stempel karet. Mengekstrak teks dari anotasi prangko berguna saat Anda ingin mengambil konten berbasis teks dari anotasi ini, yang dapat mencakup catatan, label, atau informasi tekstual lainnya.

#### T: Bagaimana kode sumber C# yang disediakan mengekstrak teks dari anotasi prangko?

 A: Kode sumber yang diberikan menunjukkan cara mengekstrak teks dari anotasi prangko tertentu pada halaman tertentu dari dokumen PDF. Kode ini menggunakan pustaka Aspose.PDF untuk mengambil anotasi prangko, melihat tampilannya menggunakan`TextAbsorber`, lalu menampilkan teks yang diekstrak pada output.

#### T: Dapatkah saya mengekstrak teks dari berbagai jenis anotasi menggunakan pendekatan yang sama?

A: Ya, Anda dapat menggunakan pendekatan serupa untuk mengekstrak teks dari jenis anotasi lain, seperti anotasi teks atau anotasi popup. Anda perlu mengubah kode untuk menargetkan jenis anotasi tertentu yang teksnya ingin Anda ekstrak.

####  T: Apa tujuan dari`TextAbsorber` class in the code?

 Sebuah:`TextAbsorber` Kelas ini digunakan untuk mengekstrak teks dari berbagai bagian dokumen PDF, termasuk anotasi stempel. Kelas ini "menyerap" atau menangkap konten teks yang ditemukan di area atau elemen PDF yang ditentukan.

#### T: Bagaimana cara mengidentifikasi anotasi prangko tertentu yang teksnya ingin saya ekstrak?

 A: Dalam kode yang diberikan, anotasi prangko diidentifikasi dengan mengakses`Annotations` kumpulan halaman tertentu dan menggunakan indeks untuk mengambil anotasi yang diinginkan. Anda dapat menyesuaikan indeks atau menggunakan kriteria lain untuk mengidentifikasi anotasi target.

#### T: Dapatkah saya mengekstrak teks dari beberapa anotasi prangko di halaman yang sama?

 A: Ya, Anda dapat mengubah kode untuk melakukan pengulangan`Annotations`kumpulan halaman, menyaring anotasi prangko, dan mengekstrak teks dari masing-masing anotasi.

#### T: Bagaimana jika anotasi prangko tidak memiliki konten tekstual? Apakah kodenya masih berfungsi?

A: Kode tersebut akan tetap berfungsi, tetapi akan mengekstrak dan menampilkan string kosong jika tampilan anotasi prangko tidak mengandung konten tekstual apa pun.

#### T: Bagaimana cara menyimpan teks yang diekstrak ke dalam file alih-alih menampilkannya dalam output?

 A: Anda dapat mengubah kode untuk menyimpan teks yang diekstrak ke dalam file alih-alih menampilkannya di konsol. Cukup ganti`Console.WriteLine` pernyataan dengan kode untuk menulis teks ke dalam berkas.

#### T: Bagaimana saya dapat menggunakan teks yang diekstrak untuk pemrosesan atau analisis lebih lanjut?

A: Setelah Anda mengekstrak teks menggunakan metode yang disediakan, Anda dapat menyimpannya dalam variabel, memanipulasinya, menganalisisnya, atau mengintegrasikannya ke bagian lain aplikasi Anda sesuai kebutuhan.