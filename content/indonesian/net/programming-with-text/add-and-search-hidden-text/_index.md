---
title: Tambahkan dan Cari Teks Tersembunyi Dalam File PDF
linktitle: Tambahkan dan Cari Teks Tersembunyi Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menambahkan dan mencari teks tersembunyi dalam dokumen PDF menggunakan Aspose.PDF for .NET. Panduan langkah demi langkah dengan contoh kode disertakan.
type: docs
weight: 20
url: /id/net/programming-with-text/add-and-search-hidden-text/
---
## Perkenalan

Dalam tutorial ini, kami akan memandu Anda langkah demi langkah tentang cara menambahkan dan mencari teks tersembunyi dalam file PDF menggunakan Aspose.PDF untuk .NET. Baik Anda pengembang berpengalaman atau pemula yang ingin meningkatkan keterampilan pemrograman, artikel ini akan memberi Anda wawasan yang Anda butuhkan untuk memasukkan fungsionalitas teks tersembunyi ke dalam aplikasi Anda.

## Prasyarat

Sebelum menyelami bagian pengkodean, ada beberapa prasyarat yang perlu Anda perhatikan:

### Daftar Periksa Persyaratan
- Visual Studio: Pastikan Anda telah menginstal Visual Studio. Tutorial ini mengasumsikan Anda menggunakan .NET Framework.
-  Aspose.PDF untuk .NET: Anda perlu memiliki pustaka Aspose.PDF untuk .NET. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/pdf/net/).
- Pengetahuan dasar C#: Keakraban dengan pemrograman C# akan membantu Anda memahami potongan kode dengan lebih baik.

## Paket Impor

Sebelum Anda dapat mulai menggunakan kode, Anda perlu memastikan bahwa Anda mengimpor namespace Aspose.PDF yang diperlukan. Berikut cara melakukannya:

### Siapkan Proyek Anda
1. Buka Visual Studio dan buat proyek C# baru atau gunakan yang sudah ada.
2.  Instal Aspose.PDF dengan menambahkan paket NuGet. Anda dapat melakukannya dengan membuka Pengelola Paket NuGet dan mencari`Aspose.PDF`. 
3.  Atau, Anda dapat langsung mengunduh perpustakaan dari[Di Sini](https://releases.aspose.com/pdf/net/) dan menambahkannya sebagai referensi dalam proyek Anda.

### Mengimpor Ruang Nama yang Diperlukan
Di bagian atas file C# Anda, impor namespace berikut:

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Langkah ini penting karena namespace ini berisi kelas dan metode yang diperlukan untuk memanipulasi dokumen PDF.

## Membuat Dokumen PDF dengan Teks Tersembunyi

Sekarang setelah Anda menyiapkannya, mari kita lihat langkah-langkah untuk membuat dokumen PDF yang berisi teks tampak dan tak tampak.

### Langkah 1: Tentukan Direktori Dokumen
Pertama, Anda perlu mengatur jalur penyimpanan PDF. Di sinilah keajaiban dimulai!

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Ubah ini ke direktori Anda
```

 Baris ini menentukan di mana PDF yang Anda hasilkan akan disimpan. Jangan lupa untuk mengganti`YOUR DOCUMENT DIRECTORY` dengan jalur Anda yang sebenarnya.

### Langkah 2: Buat Dokumen PDF
Selanjutnya, mari buat dokumen PDF baru dan tambahkan halaman ke dalamnya.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
```

Di sini, kita menginisialisasi dokumen baru dan menambahkan halaman tempat kita akan meletakkan fragmen teks kita.

### Langkah 3: Tambahkan Teks Terlihat dan Tersembunyi
Sekarang kita akan menambahkan teks yang terlihat dan tidak terlihat ke PDF kita.

```csharp
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
```

 Dalam cuplikan ini,`frag1` akan terlihat, sedangkan`frag2` Akan diatur menjadi tidak terlihat selanjutnya.

### Langkah 4: Atur Teks menjadi Tidak Terlihat
 Untuk membuat teks`frag2` tidak terlihat, Anda cukup memodifikasinya`TextState`.

```csharp
frag2.TextState.Invisible = true;
```

 Dengan mengatur properti ini, teks apa pun yang terkait dengan`frag2` tidak akan ditampilkan saat PDF dilihat.

### Langkah 5: Tambahkan Fragmen Teks ke Halaman
Terakhir, kami menambahkan fragmen teks ini ke halaman dan menyimpan PDF.

```csharp
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

Bagian kode ini menambahkan fragmen teks ke halaman. Setelah itu, kita menyimpan dan membuang dokumen dengan benar.

## Mencari Teks Tersembunyi di PDF

Sekarang setelah kita membuat PDF dengan teks yang terlihat dan tersembunyi, bagaimana cara mencari teks tersembunyi tersebut? Mari kita uraikan.

### Langkah 1: Muat Dokumen PDF
Untuk mencari teks dalam PDF, pertama-tama kita perlu memuat dokumen yang baru kita buat.

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
```

### Langkah 2: Buat Penyerap Fragmen Teks
 Kami akan menggunakan`TextFragmentAbsorber` untuk menangkap semua fragmen teks dalam PDF.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
```

Di sini, kami tentukan bahwa kami ingin menyerap semua fragmen teks dari halaman pertama.

### Langkah 3: Ulangi Melalui Fragmen
Sekarang, kita dapat menelusuri fragmen teks yang dikumpulkan untuk mengetahui mana yang terlihat dan mana yang tersembunyi.

```csharp
foreach (TextFragment fragment in absorber.TextFragments)
{
    Console.WriteLine("Text '{0}' on pos {1} invisibility: {2}",
        fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
```

 Loop ini memeriksa setiap fragmen teks dan mencetak isinya beserta posisi dan status visibilitasnya. Jika`fragment.TextState.Invisible` disetel ke true, artinya teks disembunyikan!

### Langkah 4: Buang Dokumen
Terakhir, ingatlah untuk membuang dokumen tersebut lagi setelah Anda selesai.

```csharp
doc.Dispose();
```

## Kesimpulan

Dalam tutorial ini, kami membahas proses menarik dalam menambahkan dan mencari teks tersembunyi dalam file PDF menggunakan Aspose.PDF for .NET. Kami mempelajari cara membuat dokumen PDF dengan teks yang terlihat dan tersembunyi, serta cara mencari teks tersembunyi tersebut secara terprogram. Kemampuan ini dapat sangat berguna dalam berbagai aplikasi, baik Anda perlu menyimpan informasi rahasia atau memberikan pengalaman pengguna yang unik dalam dokumen Anda.

Saat Anda semakin terbiasa dengan ASPose.PDF, kemungkinannya menjadi tak terbatas. Teruslah bereksperimen dan dorong batasan apa yang dapat Anda capai dengan dokumen PDF Anda!

## Pertanyaan yang Sering Diajukan

### Bisakah Aspose.PDF menangani berkas PDF yang terenkripsi?  
Ya, Aspose.PDF mendukung enkripsi dan dekripsi dokumen PDF. Anda dapat dengan mudah mengamankan PDF Anda dengan kata sandi.

### Apakah ada versi uji coba yang tersedia untuk Aspose.PDF?  
 Tentu saja! Anda dapat mengunduh uji coba gratis dari[Di Sini](https://releases.aspose.com/).

### Bahasa pemrograman apa yang didukung Aspose.PDF?  
Aspose.PDF menyediakan dukungan untuk berbagai bahasa, termasuk C#, Java, dan Python.

### Di mana saya dapat menemukan dokumentasi untuk Aspose.PDF?  
 Anda dapat mengakses dokumentasi[Di Sini](https://reference.aspose.com/pdf/net/).

### Bagaimana saya bisa mendapatkan dukungan jika saya mengalami masalah?  
 Untuk dukungan, Anda dapat mengunjungi forum Aspose[Di Sini](https://forum.aspose.com/c/pdf/10).