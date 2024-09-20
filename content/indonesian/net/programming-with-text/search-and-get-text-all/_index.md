---
title: Cari dan Dapatkan Semua Teks
linktitle: Cari dan Dapatkan Semua Teks
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mencari dan mendapatkan teks dari semua halaman dokumen PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 420
url: /id/net/programming-with-text/search-and-get-text-all/
---
## Perkenalan

Pernahkah Anda perlu mengekstrak teks tertentu dari PDF tetapi merasa kesulitan? PDF terkadang terasa seperti wadah terkunci, sehingga sulit mendapatkan informasi yang Anda butuhkan. Namun, inilah kabar baiknya: dengan Aspose.PDF untuk .NET, Anda dapat dengan mudah mencari dan mengambil teks dari PDF mana pun. Pustaka canggih ini menyediakan semua yang Anda butuhkan untuk bekerja dengan PDF di aplikasi .NET Anda, sehingga ekstraksi teks menjadi mudah. Dalam tutorial ini, kami akan memandu Anda melalui proses pencarian dan ekstraksi teks dari file PDF menggunakan Aspose.PDF untuk .NET. Baik Anda sedang membangun alat analisis teks atau hanya perlu mengotomatiskan ekstraksi data dari laporan PDF, Anda berada di tempat yang tepat!

## Prasyarat

Sebelum kita masuk ke kode, mari pastikan Anda sudah menyiapkan semuanya:

1. Aspose.PDF untuk .NET: Anda perlu mengunduh dan menginstal Aspose.PDF untuk .NET. Anda bisa mendapatkannya dari halaman unduhan[Di Sini](https://releases.aspose.com/pdf/net/).
2. Lingkungan .NET: Pastikan Anda telah menyiapkan .NET Framework atau .NET Core di mesin pengembangan Anda.
3. Pengetahuan Dasar C##: Disarankan untuk memiliki pengetahuan tentang C# dan bekerja dengan proyek .NET.
4.  Dokumen PDF: Contoh file PDF yang akan kita ekstrak teksnya. Dalam contoh ini, kita akan menggunakan`SearchAndGetTextFromAll.pdf`.

## Paket Impor

Sebelum menulis kode apa pun, Anda perlu mengimpor namespace yang diperlukan ke dalam proyek Anda untuk bekerja dengan Aspose.PDF.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Ruang nama ini menyediakan akses ke model objek dokumen PDF dan memungkinkan kita memanipulasi teks dalam berkas.

Mari kita uraikan prosesnya menjadi beberapa langkah sederhana agar Anda dapat mengikutinya dengan mudah.

## Langkah 1: Mengatur Direktori Dokumen

Pertama-tama, Anda perlu menentukan jalur ke direktori tempat PDF Anda berada. Ini membantu aplikasi menemukan berkas tempat Anda akan mengekstrak teks.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  Itu`dataDir` variabel harus menunjuk ke direktori tempat Anda`SearchAndGetTextFromAll.pdf` berkas disimpan.
-  Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya di mesin Anda.

## Langkah 2: Buka Dokumen PDF

Selanjutnya, kita akan membuka dokumen PDF menggunakan Aspose.PDF`Document` obyek.

```csharp
// Buka dokumen
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

-  Kami membuat contoh baru dari`Document` kelas dengan meneruskan jalur file PDF secara lengkap.
- Ini akan memuat PDF ke dalam memori, membuatnya siap untuk diproses.

## Langkah 3: Buat Penyerap Teks

 Itu`TextFragmentAbsorber` Objek digunakan untuk mencari teks tertentu dalam PDF. Dalam kasus ini, kita akan mencari kata “teks.”

```csharp
// Buat objek TextAbsorber untuk menemukan semua contoh frasa pencarian input
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

-  Itu`TextFragmentAbsorber` diinisialisasi dengan string`"text"`Artinya, alat ini akan mencari setiap kemunculan kata “teks” dalam dokumen PDF.

## Langkah 4: Terima Penyerap untuk Semua Halaman

Sekarang, kita akan menginstruksikan dokumen PDF untuk menerima penyerap dan mencari teks di semua halamannya.

```csharp
// Terima penyerap untuk semua halaman
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

-  Itu`Accept` metode ini diterapkan pada halaman dokumen. Ini akan mencari semua halaman untuk teks yang ditentukan.

## Langkah 5: Ekstrak Fragmen Teks

Setelah penyerap memindai dokumen, kita dapat mengambil fragmen teks yang diekstraksi.

```csharp
// Dapatkan fragmen teks yang diekstraksi
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

-  Itu`TextFragments` milik`TextFragmentAbsorber` mengembalikan kumpulan semua fragmen teks yang cocok dengan istilah pencarian.

## Langkah 6: Ulangi Fragmen Teks

Sekarang setelah kita memiliki koleksi fragmen teks, kita akan mengulanginya dan mengekstrak detailnya.

```csharp
// Ulangi melalui fragmen
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text : {0} ", textFragment.Text);
    Console.WriteLine("Position : {0} ", textFragment.Position);
    Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

-  Itu`foreach` loop berulang melalui setiap`TextFragment` dalam koleksi.
- Kami mencetak berbagai properti setiap fragmen, seperti teks sebenarnya, posisinya di halaman, detail font, dan ukuran font.
-  Itu`XIndent` Dan`YIndent` properti memberikan koordinat yang tepat dari fragmen teks dalam PDF.

## Kesimpulan

Nah, itu dia! Hanya dengan beberapa baris kode, kami telah berhasil mencari dan mengekstrak teks dari PDF menggunakan Aspose.PDF untuk .NET. Fleksibilitas Aspose.PDF memungkinkan Anda untuk memanipulasi PDF dalam berbagai cara, menjadikannya pilihan yang sangat baik bagi pengembang yang membutuhkan solusi PDF yang tangguh di lingkungan .NET. Anda dapat dengan mudah memperluas contoh ini untuk mencari kata lain, mengekstrak lebih banyak detail, atau bahkan memanipulasi konten PDF berdasarkan kebutuhan Anda. Semoga panduan ini telah memberi Anda pendekatan yang jelas dan lugas untuk bekerja dengan PDF. Silakan dan cobalah dengan PDF Anda sendiri!

## Pertanyaan yang Sering Diajukan

### Bisakah saya mencari beberapa kata sekaligus?  
 Ya, Anda dapat memodifikasi`TextFragmentAbsorber` untuk mencari beberapa frasa dengan menyesuaikan rangkaian pencarian sebagaimana mestinya.

### Bagaimana jika teksnya mencakup beberapa baris?  
Aspose.PDF akan tetap mengenali dan mengekstrak teks meskipun teks tersebut mencakup beberapa baris. Anda dapat menangani fragmen-fragmen ini secara individual.

### Bagaimana cara menyimpan teks yang diekstrak ke dalam berkas?  
 Anda dapat menulis teks yang diekstrak ke dalam file menggunakan operasi I/O file C# standar, seperti`StreamWriter`.

### Apakah Aspose.PDF mendukung pengambilan teks dari PDF yang dipindai?  
Aspose.PDF tidak mendukung OCR. Untuk PDF yang dipindai, Anda memerlukan alat OCR untuk mengenali teks.

### Bagaimana cara menangani PDF yang terenkripsi?  
Jika PDF Anda dilindungi kata sandi, Anda dapat membukanya menggunakan Aspose.PDF dengan memberikan kata sandi saat memuat dokumen.