---
title: Ekstrak Teks Kolom Dalam File PDF
linktitle: Ekstrak Teks Kolom Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mengekstrak kolom teks dari file PDF menggunakan Aspose.PDF untuk .NET. Panduan ini menguraikan setiap langkah dengan contoh kode dan penjelasan.
type: docs
weight: 150
url: /id/net/programming-with-text/extract-columns-text/
---
## Perkenalan

Apakah Anda bekerja dengan file PDF dan perlu mengekstrak teks dalam format kolom tertentu? Baik Anda sedang memproses faktur, laporan, atau dokumen terstruktur lainnya, mengekstrak teks secara akurat dari PDF bisa jadi pekerjaan yang sulit. Di sinilah Aspose.PDF for .NET hadir untuk menyederhanakan proses tersebut. Dalam tutorial ini, kami akan memandu Anda untuk mengekstrak kolom teks dari file PDF dengan mudah. 

## Prasyarat

Sebelum menyelami kodenya, mari kita bahas hal-hal penting yang Anda perlukan:

-  Aspose.PDF untuk .NET: Pastikan Anda telah menginstal versi terbaru Aspose.PDF untuk .NET. Jika tidak, Anda dapat[unduh disini](https://releases.aspose.com/pdf/net/).
- Lingkungan Pengembangan: Anda memerlukan Visual Studio atau lingkungan pengembangan .NET lainnya untuk bekerja dengan kode tersebut.
- Dokumen PDF: Siapkan contoh dokumen PDF, sebaiknya yang berisi kolom teks, karena kita akan mengekstrak teks dari dokumen tersebut.

 Jika Anda belum menginstal Aspose.PDF untuk .NET, Anda dapat mengunduhnya[uji coba gratis](https://releases.aspose.com/) atau[beli lisensi](https://purchase.aspose.com/buy) untuk fitur lengkap. Anda juga dapat mengajukan permohonan[lisensi sementara](https://purchase.aspose.com/temporary-license) jika diperlukan.

## Mengimpor Ruang Nama

Untuk menggunakan Aspose.PDF untuk .NET di proyek Anda, Anda perlu mengimpor namespace berikut:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

## Panduan Langkah demi Langkah: Ekstrak Kolom Teks dari PDF

Sekarang, mari kita uraikan setiap bagian kode untuk lebih memahami cara kerjanya. Ikuti langkah demi langkah, sambil menjelaskan setiap segmen proses.

## Langkah 1: Muat Dokumen PDF

 Hal pertama yang perlu Anda lakukan adalah memuat file PDF Anda ke dalam`Document`objek. Beginilah cara Aspose.PDF berinteraksi dengan dokumen Anda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

 Pada langkah ini, kita hanya mendefinisikan direktori tempat dokumen PDF Anda disimpan. Ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur ke file PDF lokal Anda.`Document` objek memuat PDF ke dalam memori, membuatnya dapat diakses untuk pemrosesan lebih lanjut.

## Langkah 2: Siapkan Penyerap Fragmen Teks

 Selanjutnya, kita akan menggunakan`TextFragmentAbsorber` untuk menyerap atau menangkap semua teks dari berkas PDF. Kelas penyerap ini dirancang untuk mengekstrak fragmen teks dari area tertentu di PDF Anda, yang membuatnya ideal untuk mengekstrak kolom teks.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
```

Di sini, kita membuat sebuah instance dari`TextFragmentAbsorber` dan menerapkannya ke semua halaman PDF menggunakan`Accept()` . Itu`TextFragmentCollection` menyimpan teks yang diekstraksi, dan dari koleksi ini, kita dapat memanipulasi atau mengekstrak teks sesuai kebutuhan.

## Langkah 3: Sesuaikan Ukuran Font Teks yang Diekstrak

Setelah Anda menangkap fragmen teks, Anda mungkin ingin mengurangi ukuran fonta, terutama jika teks asli terlalu besar. Dalam contoh ini, kami mengurangi ukuran fonta sebesar 70%.

```csharp
foreach (TextFragment tf in tfc)
{
    // Kurangi ukuran font hingga 70%
    tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

Kode ini berulang melalui setiap`TextFragment` dalam koleksi dan mengurangi ukuran font hingga 70%. Menyesuaikan ukuran font dapat membuat teks yang diekstrak lebih mudah dikelola, terutama jika Anda memformatnya untuk tujuan yang berbeda.

## Langkah 4: Simpan Dokumen ke Aliran Memori

 Setelah mengubah teks, kami menyimpan PDF ke dalam`MemoryStream`Hal ini memungkinkan kita menyimpan dokumen dalam memori untuk diproses lebih lanjut tanpa perlu menuliskannya kembali ke disk.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
```

Di sini, kami menyimpan PDF ke dalam aliran memori lalu memuat ulang dokumen tersebut. Metode ini berguna saat Anda bekerja dengan file besar dan ingin menghindari operasi disk yang tidak perlu.

## Langkah 5: Ekstrak Semua Teks Menggunakan Text Absorber

 Sekarang setelah kita menyiapkan PDF, saatnya mengekstrak teks. Kita akan menggunakan`TextAbsorber` untuk mengambil semua teks dari dokumen.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
```

 Pada langkah ini,`TextAbsorber` menyerap semua teks dari PDF, dan teks yang diekstraksi disimpan di`extractedText` string. Di sinilah keajaiban terjadi—kolom teks Anda sekarang dalam format teks biasa!

## Langkah 6: Simpan Teks yang Diekstrak ke File

 Terakhir, kita simpan teks yang diekstrak ke dalam`.txt` berkas untuk memudahkan akses dan penggunaan lebih lanjut.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

 Kode ini menulis teks yang diekstraksi ke dalam`.txt` file dan menyimpannya di direktori yang Anda tentukan. Sebuah pesan akan ditampilkan di konsol untuk mengonfirmasi bahwa proses tersebut berhasil.

## Kesimpulan

Nah, itu dia! Mengekstrak kolom teks dari file PDF menggunakan Aspose.PDF untuk .NET lebih mudah dari yang Anda kira. Hanya dengan beberapa baris kode, Anda dapat memuat PDF, mengekstrak teks tertentu, menyesuaikan format, dan menyimpan hasilnya ke dalam file teks.

Teknik ini sangat berguna untuk memproses dokumen terstruktur seperti tabel, laporan, atau konten apa pun yang disusun dalam kolom. Baik Anda perlu mengotomatiskan ekstraksi data atau memproses dokumen massal, Aspose.PDF menyediakan alat untuk mewujudkannya secara efisien.

## Pertanyaan yang Sering Diajukan

### Bisakah saya mengekstrak teks dari halaman tertentu di PDF?  
 Ya! Anda dapat mengubah`TextFragmentAbsorber` untuk menargetkan halaman tertentu menggunakan`pdfDocument.Pages[pageIndex].Accept(tfa);` metode.

### Apakah mungkin untuk mengekstrak teks hanya dari satu kolom dalam PDF multi-kolom?  
 Ya, tetapi Anda harus bekerja dengan koordinat fragmen teks menggunakan`TextFragment.Rectangle` untuk menargetkan area tertentu pada dokumen.

### Bagaimana saya dapat meningkatkan akurasi ekstraksi teks?  
 Untuk akurasi yang lebih baik, pastikan struktur PDF terdefinisi dengan baik dan hindari dokumen dengan tata letak yang rumit. Anda juga dapat menyempurnakan`TextFragmentAbsorber` untuk mengekstrak teks berdasarkan gaya font, ukuran, atau wilayah.

### Apakah Aspose.PDF mendukung ekstraksi teks dari dokumen yang dipindai?  
Ya, tetapi Anda perlu menggunakan teknologi OCR (Optical Character Recognition). Aspose juga menyediakan alat untuk ini.

### Bagaimana cara menangani berkas PDF besar dengan ribuan halaman?  
Untuk PDF berukuran besar, proses dokumen dalam potongan-potongan dengan mengekstrak teks dari beberapa halaman sekaligus untuk menghindari penggunaan memori yang tinggi.