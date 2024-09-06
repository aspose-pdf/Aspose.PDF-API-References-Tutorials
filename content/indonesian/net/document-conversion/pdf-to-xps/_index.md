---
title: PDF ke XPS
linktitle: PDF ke XPS
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mengonversi PDF ke XPS menggunakan Aspose.PDF untuk .NET dengan panduan langkah demi langkah ini. Sempurna untuk pengembang dan penggemar pemrosesan dokumen.
type: docs
weight: 220
url: /id/net/document-conversion/pdf-to-xps/
---
## Perkenalan

Di dunia digital saat ini, kebutuhan untuk mengonversi dokumen dari satu format ke format lain lebih umum dari sebelumnya. Apakah Anda seorang pengembang yang ingin mengintegrasikan pemrosesan dokumen ke dalam aplikasi Anda atau seorang profesional bisnis yang perlu berbagi file dalam format yang diterima secara universal, memahami cara mengonversi file PDF ke XPS (Spesifikasi Kertas XML) bisa sangat berguna. Dalam tutorial ini, kita akan menyelami proses konversi PDF ke XPS menggunakan pustaka Aspose.PDF yang canggih untuk .NET.

## Prasyarat

Sebelum kita memulai, ada beberapa prasyarat yang perlu Anda penuhi:

1. Visual Studio: Pastikan Anda telah menginstal Visual Studio di komputer Anda. Di sinilah Anda akan menulis dan menjalankan kode .NET Anda.
2. .NET Framework: Keakraban dengan framework .NET sangatlah penting, karena kita akan menggunakan C# sebagai contoh.
3.  Pustaka Aspose.PDF: Anda perlu menginstal pustaka Aspose.PDF. Anda dapat mengunduhnya dari[Halaman rilis Aspose PDF untuk .NET](https://releases.aspose.com/pdf/net/).
4. Pengetahuan Dasar C#: Pemahaman mendasar tentang pemrograman C# akan membantu Anda mengikuti contoh-contohnya.

## Paket Impor

Untuk memulai dengan Aspose.PDF, Anda perlu mengimpor paket-paket yang diperlukan ke dalam proyek Anda. Berikut ini cara melakukannya:

1. Buka Visual Studio: Luncurkan Visual Studio dan buat proyek baru.
2. Tambahkan Referensi: Klik kanan pada proyek Anda di Solution Explorer, pilih "Kelola Paket NuGet," dan cari "Aspose.PDF." Instal paket tersebut ke proyek Anda.
3. Menggunakan Direktif: Di bagian atas file C# Anda, sertakan direktif penggunaan berikut:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
```

Sekarang setelah semuanya siap, mari kita uraikan proses konversi menjadi langkah-langkah yang lebih mudah dikelola.

## Langkah 1: Siapkan Direktori Dokumen Anda

Sebelum Anda dapat mengonversi PDF ke XPS, Anda perlu menentukan direktori tempat file PDF Anda berada. Hal ini penting karena program perlu mengetahui tempat menemukan file input.

Pada langkah ini, Anda akan menentukan variabel string yang menyimpan jalur ke direktori dokumen Anda. Jalur ini harus mengarah ke lokasi berkas PDF Anda.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya pada komputer Anda tempat berkas PDF disimpan.

## Langkah 2: Muat Dokumen PDF

Sekarang setelah Anda menyiapkan direktori dokumen, langkah berikutnya adalah memuat dokumen PDF yang ingin Anda konversi.

 Anda akan membuat sebuah instance dari`Document` kelas dari pustaka Aspose.PDF dan berikan jalur berkas PDF Anda ke konstruktornya. Ini akan memuat dokumen PDF ke dalam memori.

```csharp
// Muat dokumen PDF
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Pastikan untuk mengganti`"input.pdf"` dengan nama berkas PDF Anda sebenarnya.

## Langkah 3: Buat Opsi Penyimpanan XPS

 Sebelum menyimpan dokumen dalam format XPS, Anda perlu membuat contoh`XpsSaveOptions` Kelas ini memungkinkan Anda menentukan berbagai opsi untuk menyimpan dokumen.

 Dengan melakukan instansiasi`XpsSaveOptions`Anda dapat menyesuaikan cara konversi PDF ke XPS. Untuk konversi dasar ini, Anda dapat menggunakan pengaturan default.

```csharp
// Membuat contoh opsi Simpan XPS
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();
```

## Langkah 4: Simpan Dokumen sebagai XPS

Akhirnya, saatnya menyimpan dokumen PDF yang dimuat sebagai file XPS. Di sinilah keajaiban terjadi!

 Anda akan menelepon`Save` metode pada`pdfDocument` objek, melewati nama file keluaran yang diinginkan dan`saveOptions` Anda buat sebelumnya.

```csharp
// Simpan dokumen XPS
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

 Baris kode ini akan membuat file XPS bernama`PDFToXPS_out.xps` di direktori proyek Anda.

## Kesimpulan

Selamat! Anda telah berhasil mengonversi dokumen PDF ke format XPS menggunakan Aspose.PDF untuk .NET. Pustaka yang sederhana namun canggih ini memungkinkan Anda menangani berbagai tugas pemrosesan dokumen dengan mudah. Baik Anda mengonversi file untuk kompatibilitas yang lebih baik atau sekadar mengarsipkan dokumen dalam format yang berbeda, Aspose.PDF siap membantu Anda.

## Pertanyaan yang Sering Diajukan

### Apa itu format XPS?
XPS (XML Paper Specification) adalah format dokumen yang dikembangkan oleh Microsoft yang mempertahankan tata letak dan tampilan dokumen.

### Bisakah saya mengonversi beberapa berkas PDF ke XPS sekaligus?
Ya, Anda dapat mengulang beberapa berkas PDF dalam satu direktori dan mengonversi masing-masing berkas ke XPS menggunakan metode yang sama.

### Apakah Aspose.PDF gratis untuk digunakan?
 Aspose.PDF menawarkan uji coba gratis, tetapi untuk fungsionalitas penuh, Anda perlu membeli lisensi. Anda dapat menemukan informasi lebih lanjut di[halaman pembelian](https://purchase.aspose.com/buy).

### Bagaimana jika saya menemui masalah selama konversi?
 Anda dapat mencari bantuan dari komunitas Aspose di[forum dukungan](https://forum.aspose.com/c/pdf/10).

### Bisakah saya mendapatkan lisensi sementara untuk Aspose.PDF?
 Ya, Anda dapat meminta lisensi sementara untuk tujuan evaluasi dari[halaman lisensi sementara](https://purchase.aspose.com/temporary-license/).