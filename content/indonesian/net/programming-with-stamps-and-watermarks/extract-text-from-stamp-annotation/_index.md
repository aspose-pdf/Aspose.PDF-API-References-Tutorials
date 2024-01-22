---
title: Ekstrak Teks Dari Anotasi Stempel
linktitle: Ekstrak Teks Dari Anotasi Stempel
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara mengekstrak teks dengan mudah dari anotasi prangko di dokumen PDF Anda dengan Aspose.PDF untuk .NET.
type: docs
weight: 80
url: /id/net/programming-with-stamps-and-watermarks/extract-text-from-stamp-annotation/
---
Dalam tutorial ini, kami akan memandu Anda langkah demi langkah tentang cara mengekstrak teks dari anotasi stempel dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Kami akan menunjukkan kepada Anda cara menggunakan kode sumber C# yang disediakan untuk mengekstrak teks dari anotasi stempel tertentu pada halaman tertentu di dokumen PDF.

## Langkah 1: Menyiapkan lingkungan

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Lingkungan pengembangan .NET yang terinstal.
- Pustaka Aspose.PDF untuk .NET diunduh dan direferensikan dalam proyek Anda.

## Langkah 2: Memuat dokumen PDF

Langkah pertama adalah memuat dokumen PDF yang ada ke dalam proyek Anda. Begini caranya:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Muat dokumen
Document doc = new Document(dataDir + "test.pdf");
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori tempat dokumen PDF Anda berada.

## Langkah 3: Ekstrak teks dari anotasi prangko

Sekarang setelah Anda memuat dokumen PDF, Anda dapat mengekstrak teks dari anotasi stempel tertentu. Begini caranya:

```csharp
// Ambil anotasi buffer
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;

// Buat penyerap teks
TextAbsorber ta = new TextAbsorber();

// Kunjungi tampilan anotasi
XForm ap = annot. Appearance["N"];
ta.Visit(ap);

// Tampilkan teks yang diekstraksi
Console.WriteLine(ta.Text);
```

Kode di atas mengambil anotasi stempel dari halaman tertentu pada dokumen PDF dan kemudian menggunakan penyerap teks untuk mengekstrak teks dari tampilan anotasi. Teks yang diekstraksi kemudian ditampilkan di output.

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

Selamat! Anda telah mempelajari cara mengekstrak teks dari anotasi stempel dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Anda sekarang dapat menggunakan metode ini untuk mengekstrak teks dari anotasi lain di dokumen PDF Anda.

### FAQ untuk mengekstrak teks dari anotasi prangko

#### T: Apa yang dimaksud dengan anotasi prangko dalam dokumen PDF, dan mengapa saya perlu mengekstrak teks dari anotasi tersebut?

J: Anotasi stempel dalam dokumen PDF adalah elemen grafis yang dapat digunakan untuk memberikan informasi tambahan, seperti tanda air atau stempel karet. Mengekstrak teks dari anotasi prangko berguna saat Anda ingin mengambil konten berbasis teks dari anotasi tersebut, yang dapat mencakup catatan, label, atau informasi tekstual lainnya.

#### T: Bagaimana cara kode sumber C# yang disediakan mengekstrak teks dari anotasi prangko?

 J: Kode sumber yang disediakan menunjukkan cara mengekstrak teks dari anotasi stempel tertentu pada halaman tertentu di dokumen PDF. Ia menggunakan perpustakaan Aspose.PDF untuk mengambil anotasi prangko, kunjungi tampilannya menggunakan a`TextAbsorber`, lalu menampilkan teks yang diekstraksi di output.

#### T: Bisakah saya mengekstrak teks dari berbagai jenis anotasi menggunakan pendekatan serupa?

J: Ya, Anda dapat menggunakan pendekatan serupa untuk mengekstrak teks dari jenis anotasi lain, seperti anotasi teks atau anotasi popup. Anda perlu memodifikasi kode untuk menargetkan jenis anotasi tertentu yang teksnya ingin Anda ekstrak.

####  T: Apa tujuan dari`TextAbsorber` class in the code?

 J: Itu`TextAbsorber` kelas digunakan untuk mengekstrak teks dari berbagai bagian dokumen PDF, termasuk anotasi stempel. Ini "menyerap" atau menangkap konten teks yang ditemukan di area atau elemen PDF tertentu.

#### T: Bagaimana cara mengidentifikasi anotasi prangko tertentu yang teksnya ingin saya ekstrak?

 A: Dalam kode yang diberikan, anotasi stempel diidentifikasi dengan mengakses`Annotations` kumpulan halaman tertentu dan menggunakan indeks untuk mengambil anotasi yang diinginkan. Anda dapat menyesuaikan indeks atau menggunakan kriteria lain untuk mengidentifikasi anotasi target.

#### T: Dapatkah saya mengekstrak teks dari beberapa anotasi prangko pada halaman yang sama?

 J: Ya, Anda dapat memodifikasi kode untuk mengulang`Annotations`kumpulan halaman, menyaring anotasi prangko, dan mengekstrak teks dari masing-masing halaman.

#### T: Bagaimana jika anotasi prangko tidak memiliki konten tekstual? Apakah kodenya akan tetap berfungsi?

J: Kode akan tetap berfungsi, tetapi akan mengekstrak dan menampilkan string kosong jika tampilan anotasi stempel tidak berisi konten tekstual apa pun.

#### T: Bagaimana cara menyimpan teks yang diekstrak ke file alih-alih menampilkannya di output?

 J: Anda dapat mengubah kode untuk menyimpan teks yang diekstraksi ke file alih-alih menampilkannya di konsol. Cukup ganti`Console.WriteLine` pernyataan dengan kode untuk menulis teks ke file.

#### T: Bagaimana cara menggunakan teks yang diekstraksi dalam pemrosesan atau analisis lebih lanjut?

J: Setelah Anda mengekstrak teks menggunakan metode yang disediakan, Anda dapat menyimpannya dalam variabel, memanipulasinya, menganalisisnya, atau mengintegrasikannya ke bagian lain aplikasi Anda sesuai kebutuhan.