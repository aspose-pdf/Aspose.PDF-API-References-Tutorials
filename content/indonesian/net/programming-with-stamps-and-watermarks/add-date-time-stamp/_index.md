---
title: Tambahkan Cap Tanggal Waktu Dalam File PDF
linktitle: Tambahkan Cap Tanggal Waktu Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menambahkan cap tanggal dan waktu ke berkas PDF Anda menggunakan Aspose.PDF for .NET dengan panduan langkah demi langkah ini. Sempurna untuk meningkatkan keaslian dokumen.
type: docs
weight: 10
url: /id/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
## Perkenalan

Dalam hal mengelola dokumen, terutama PDF, menambahkan cap tanggal dan waktu dapat menjadi pengubah permainan. Baik Anda mengerjakan dokumen hukum, laporan proyek, atau faktur, cap waktu tidak hanya menambah keaslian tetapi juga memberikan catatan yang jelas tentang kapan dokumen tersebut dibuat atau dimodifikasi. Dalam panduan ini, kami akan memandu Anda melalui proses menambahkan cap tanggal dan waktu ke file PDF menggunakan pustaka Aspose.PDF untuk .NET. 

Artikel ini dirancang agar mudah dipahami dan diikuti, jadi meskipun Anda baru mengenal pemrograman atau pustaka Aspose.PDF, Anda akan dapat menerapkan fitur ini dengan percaya diri. Mari kita mulai!

## Prasyarat

Sebelum kita memulai, ada beberapa prasyarat yang perlu Anda penuhi:

1. Visual Studio: Pastikan Anda telah menginstal Visual Studio di komputer Anda. Di sinilah Anda akan menulis dan menjalankan kode Anda.
2. Aspose.PDF untuk .NET: Anda perlu mengunduh dan menginstal pustaka Aspose.PDF. Anda dapat menemukan versi terbaru[Di Sini](https://releases.aspose.com/pdf/net/).
3. Pengetahuan Dasar C#: Keakraban dengan pemrograman C# akan membantu Anda memahami contoh-contohnya dengan lebih baik, tetapi jangan khawatir jika Anda baru memulai; kami akan menjelaskan semuanya langkah demi langkah.
4.  File PDF: Siapkan contoh file PDF. Untuk contoh kita, kita akan menggunakan file bernama`AddTextStamp.pdf`.

Setelah Anda memiliki prasyarat ini, Anda siap untuk mulai menambahkan cap tanggal dan waktu ke file PDF Anda!

## Paket Impor

Untuk memulai, Anda perlu mengimpor namespace yang diperlukan dalam proyek C# Anda. Berikut cara melakukannya:

### Buat Proyek Baru

1. Buka Visual Studio: Luncurkan aplikasi Visual Studio Anda.
2. Buat Proyek Baru: Pilih “Buat proyek baru” dari layar awal.
3. Pilih Aplikasi Konsol: Pilih “Aplikasi Konsol (.NET Framework)” dari daftar templat proyek.
4.  Beri Nama Proyek Anda: Berikan nama pada proyek Anda, misalnya,`PDFDateTimeStamp`.

### Tambahkan Referensi Aspose.PDF

1. Klik kanan pada Referensi: Di Solution Explorer, klik kanan pada folder “Referensi” pada proyek Anda.
2. Pilih “Tambahkan Referensi”: Pilih “Tambahkan Referensi” dari menu konteks.
3. Telusuri Aspose.PDF: Arahkan ke lokasi tempat Anda mengunduh Aspose.PDF dan pilih. Klik “OK” untuk menambahkannya ke proyek Anda.

### Mengimpor Ruang Nama yang Diperlukan

 Di bagian atas Anda`Program.cs` file, Anda perlu mengimpor namespace berikut:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Annotations;
```

Sekarang setelah semuanya disiapkan, mari kita uraikan proses penambahan cap tanggal dan waktu ke berkas PDF ke dalam langkah-langkah yang jelas dan mudah dikelola.

## Langkah 1: Mengatur Direktori Dokumen

Pertama, Anda perlu menentukan direktori tempat file PDF Anda berada. Hal ini penting karena kode akan mencari PDF di direktori ini.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Ganti dengan jalur Anda yang sebenarnya
```

 Pastikan untuk mengganti`YOUR DOCUMENT DIRECTORY` dengan jalur sebenarnya ke berkas PDF Anda.

## Langkah 2: Buka Dokumen PDF

Berikutnya, Anda akan membuka dokumen PDF tempat Anda ingin menambahkan stempel waktu. 

```csharp
// Buka dokumen
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

 Baris kode ini menginisialisasi`Document` kelas dan memuat file PDF Anda ke dalam`pdfDocument` obyek.

## Langkah 3: Buat Cap Tanggal Waktu

Sekarang saatnya membuat cap tanggal dan waktu. Anda akan memformatnya untuk ditampilkan dengan cara tertentu. 

```csharp
string annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");
```

 Di Sini,`DateTime.Now` mendapatkan tanggal dan waktu saat ini, dan`ToString` memformatnya ke format yang Anda inginkan.

## Langkah 4: Buat Stempel Teks

Dengan rangkaian tanggal dan waktu yang siap, Anda sekarang dapat membuat stempel teks yang akan ditambahkan ke PDF Anda.

```csharp
// Buat stempel teks
TextStamp textStamp = new TextStamp(annotationText);
```

 Baris ini membuat contoh baru dari`TextStamp` menggunakan format tanggal dan waktu.

## Langkah 5: Mengatur Properti Prangko

Anda dapat menyesuaikan tampilan dan posisi prangko. Berikut cara mengatur propertinya:

```csharp
// Mengatur properti prangko
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

Pada langkah ini, kita mengatur margin dan menyelaraskan stempel ke sudut kanan bawah halaman PDF.

## Langkah 6: Tambahkan Stempel ke PDF

Sekarang saatnya menambahkan stempel teks ke dokumen PDF Anda. 

```csharp
// Menambahkan prangko pada koleksi prangko
pdfDocument.Pages[1].AddStamp(textStamp);
```

Baris ini menambahkan stempel pada halaman pertama PDF. Anda dapat mengubah nomor halaman jika ingin meletakkannya di halaman lain.

## Langkah 7: Buat Anotasi Teks Gratis (Opsional)

Jika Anda ingin menambahkan anotasi pada prangko, Anda dapat membuatnya`FreeTextAnnotation` sebagai berikut:

```csharp
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;
```

Langkah opsional ini membuat anotasi teks bebas yang dapat memberikan konteks atau informasi tambahan tentang prangko.

## Langkah 8: Konfigurasikan Batas Anotasi

Jika Anda ingin menyesuaikan batas anotasi Anda, Anda juga dapat melakukannya:

```csharp
Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

Potongan kode ini menetapkan lebar batas menjadi 0, membuatnya tidak terlihat, dan menambahkan anotasi ke PDF.

## Langkah 9: Simpan Dokumen PDF

Terakhir, Anda perlu menyimpan dokumen PDF yang telah dimodifikasi. 

```csharp
dataDir = dataDir + "AddDateTimeStamp_out.pdf"; // Tentukan nama file keluaran
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);
```

Baris ini menyimpan PDF dengan stempel waktu yang ditambahkan ke file baru. Anda dapat memeriksa direktori yang ditentukan untuk melihat hasilnya.

## Kesimpulan

Selamat! Anda telah berhasil menambahkan cap tanggal dan waktu ke berkas PDF menggunakan Aspose.PDF untuk .NET. Fitur sederhana namun efektif ini dapat menyempurnakan dokumen Anda, membuatnya lebih profesional, dan memberikan catatan yang jelas tentang kapan dokumen tersebut dibuat atau dimodifikasi. 

## Pertanyaan yang Sering Diajukan

### Bisakah saya menyesuaikan format tanggal di stempel waktu?
 Ya, Anda dapat memodifikasi`ToString`metode untuk mengubah format tanggal sesuai keinginan Anda.

### Apakah Aspose.PDF gratis untuk digunakan?
 Aspose.PDF menawarkan uji coba gratis, tetapi untuk fitur lengkap, Anda perlu membeli lisensi. Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).

### Bisakah saya menambahkan beberapa stempel waktu ke PDF?
 Tentu saja! Anda dapat membuat beberapa`TextStamp` contoh dan menambahkannya ke halaman atau posisi berbeda dalam PDF.

### Bagaimana jika saya tidak memiliki Visual Studio?
Anda dapat menggunakan IDE C# atau editor teks apa pun, tetapi untuk menjalankan dan men-debug proyek Anda, Visual Studio direkomendasikan.

### Di mana saya dapat menemukan lebih banyak contoh penggunaan Aspose.PDF?
 Anda dapat menjelajahi lebih banyak contoh dan tutorial di[Dokumentasi Aspose.PDF](https://reference.aspose.com/pdf/net/).