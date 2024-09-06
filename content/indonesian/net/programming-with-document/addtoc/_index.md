---
title: Tambahkan Daftar Isi ke File PDF
linktitle: Tambahkan Daftar Isi ke File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menambahkan Daftar Isi ke PDF menggunakan Aspose.PDF untuk .NET. Panduan langkah demi langkah ini menyederhanakan proses dan memastikan navigasi yang mudah dalam dokumen Anda.
type: docs
weight: 40
url: /id/net/programming-with-document/addtoc/
---
## Perkenalan

Pernahkah Anda menggulir PDF yang panjang tanpa henti, berharap PDF tersebut memiliki Daftar Isi yang terorganisasi dengan baik? Nah, hari ini adalah hari keberuntungan Anda! Dalam tutorial ini, Anda akan mempelajari cara menambahkan TOC ke berkas PDF Anda menggunakan Aspose.PDF untuk .NET. Baik Anda sedang mengerjakan laporan yang rumit, eBook, atau proposal bisnis, TOC dapat mengubah dokumen Anda menjadi mahakarya yang profesional dan mudah dipahami.

## Prasyarat

Sebelum kita masuk ke kode, mari pastikan Anda sudah memiliki semua yang dibutuhkan:

1. Aspose.PDF untuk .NET: Pastikan Anda telah mengunduh dan menginstal pustaka Aspose.PDF. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/pdf/net/).
   
2. Lingkungan Pengembangan: Pastikan Anda memiliki lingkungan pengembangan .NET seperti Visual Studio yang disiapkan di komputer Anda.

3.  Lisensi: Jika Anda tidak memiliki lisensi, Anda bisa mendapatkan uji coba gratis atau meminta lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).

## Paket Impor

Untuk memulai, pastikan untuk mengimpor namespace yang diperlukan di awal berkas kode Anda. Berikut caranya:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Ruang nama ini memungkinkan Anda mengakses fungsionalitas khusus PDF dan memanipulasi elemen teks dalam dokumen Anda.

Mari kita bagi tugas ini menjadi beberapa langkah kecil. Setiap langkah akan memandu Anda melalui proses pembuatan dan penyisipan Daftar Isi ke dalam dokumen PDF Anda.

## Langkah 1: Muat Dokumen PDF

Hal pertama yang perlu kita lakukan adalah memuat berkas PDF yang ada di mana kita ingin menambahkan TOC.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

 Pada langkah ini, kami menentukan jalur ke direktori dokumen dan memuat PDF menggunakan`Document` objek. Pastikan untuk mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke berkas Anda.

## Langkah 2: Masukkan Halaman Baru untuk Daftar Isi

Selanjutnya, kita sisipkan halaman baru di awal dokumen PDF. Halaman ini akan memuat Daftar Isi.

```csharp
Page tocPage = doc.Pages.Insert(1);
```

Dengan menyisipkan halaman TOC di awal, kami memastikan bahwa halaman tersebut muncul sebagai hal pertama yang dilihat pembaca dalam PDF.

## Langkah 3: Buat Objek Informasi TOC

Sekarang, mari kita buat objek yang akan mewakili informasi TOC. Kita juga akan menambahkan judul pada TOC agar terlihat menonjol.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

Di sini, kami menetapkan judul TOC sebagai "Daftar Isi", memperbesar ukuran font, dan membuatnya tebal untuk penekanan.

## Langkah 4: Tentukan Elemen Daftar Isi

Pada langkah ini, kami menentukan elemen (atau judul) yang akan ditampilkan di TOC. Elemen-elemen ini akan membantu pembaca menavigasi ke bagian-bagian tertentu dari dokumen.

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
```

Kami telah membuat serangkaian string yang akan berfungsi sebagai item Daftar Isi, yang sesuai dengan berbagai halaman dalam PDF.

## Langkah 5: Buat Judul Daftar Isi

Kini tibalah pada bagian krusialnya—menambahkan judul pada Daftar Isi dan menautkannya ke halaman masing-masing.

```csharp
for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;
    segment2.Text = titles[i];

    tocPage.Paragraphs.Add(heading2);
}
```

Inilah yang terjadi:
- Judul: Kami membuat`Heading` objek dan tambahkan`TextSegment` untuk itu.
- Halaman Tujuan: Kami menetapkan halaman yang akan ditautkan ke setiap judul.
- Posisi Teratas: Kami menentukan posisi pada halaman di mana judul akan ditunjuk.
- Teks: Setiap judul mendapatkan judulnya masing-masing dari array yang kita buat sebelumnya.

Lingkaran ini membuat judul untuk dua elemen pertama dalam Daftar Isi dan menautkannya ke halaman terkait.

## Langkah 6: Simpan PDF dengan TOC

Terakhir, setelah kita menambahkan semua elemen TOC, saatnya menyimpan PDF yang telah diperbarui.

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
```

File sekarang tersimpan dengan Daftar Isi yang ditambahkan ke PDF. Selamat—Anda telah berhasil menambahkan Daftar Isi!

## Langkah 7: Pesan Konfirmasi

Untuk memberi tahu pengguna bahwa prosesnya telah selesai, kami akan menampilkan pesan sederhana di konsol.

```csharp
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## Kesimpulan

Nah, itu dia! Dengan Aspose.PDF untuk .NET, menambahkan Daftar Isi ke PDF tidak hanya mudah, tetapi juga dapat disesuaikan. Baik Anda perlu membuat tautan navigasi sederhana atau struktur yang rumit, alat ini dapat membantu Anda. Jadi, lain kali Anda mengerjakan PDF yang panjang, jangan lupa untuk menambahkan Daftar Isi untuk sentuhan profesional!

## Pertanyaan yang Sering Diajukan

### Bisakah saya menyesuaikan tampilan TOC di Aspose.PDF?  
Ya, Anda dapat sepenuhnya menyesuaikan tampilan TOC, termasuk gaya font, ukuran, dan perataan.

### Bagaimana cara menambahkan subjudul ke Daftar Isi?  
 Anda dapat menambahkan subjudul dengan menyesuaikan`Heading` tingkat (misalnya,`Heading(2)`) untuk membuat TOC hierarkis.

### Apakah mungkin untuk memperbarui TOC secara otomatis jika dokumen berubah?  
Tidak, TOC tidak akan diperbarui secara otomatis. Anda perlu membuatnya ulang jika struktur dokumen berubah.

### Bisakah saya menautkan entri TOC ke dokumen eksternal?  
Ya, Anda dapat menggunakan hyperlink untuk menautkan entri TOC ke PDF atau URL eksternal.

### Apakah Aspose.PDF mendukung TOC multi-level?  
Ya, Aspose.PDF mendukung TOC multi-level untuk dokumen kompleks dengan sub-bagian.