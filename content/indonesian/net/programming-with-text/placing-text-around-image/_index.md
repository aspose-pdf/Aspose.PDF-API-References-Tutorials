---
title: Menempatkan Teks di Sekitar Gambar dalam File PDF
linktitle: Menempatkan Teks di Sekitar Gambar dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menempatkan teks di sekitar gambar dalam PDF menggunakan Aspose.PDF untuk .NET. Ikuti panduan langkah demi langkah kami untuk membuat PDF profesional dengan gambar dan teks berdampingan.
type: docs
weight: 260
url: /id/net/programming-with-text/placing-text-around-image/
---
## Perkenalan

Pernahkah Anda mencoba menempatkan teks di sekitar gambar dalam berkas PDF tetapi merasa kesulitan? Jika demikian, Anda berada di tempat yang tepat! Aspose.PDF untuk .NET membuat proses ini menjadi mudah, memungkinkan Anda untuk menempatkan teks di sekitar gambar hanya dengan beberapa baris kode. Baik Anda membuat laporan, dokumen, atau presentasi, fitur ini merupakan cara yang fantastis untuk menyempurnakan tata letak konten Anda dan membuatnya lebih menarik secara visual. Hari ini, kita akan membahas cara menggunakan Aspose.PDF untuk .NET untuk menempatkan teks di sekitar gambar dalam dokumen PDF.

## Prasyarat

Sebelum kita mulai membuat kode, mari kita pastikan semuanya sudah disiapkan. Berikut ini yang Anda perlukan:

-  Aspose.PDF untuk .NET: Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/pdf/net/).
- Visual Studio: Pastikan Anda telah menginstal versi terbaru agar dapat berjalan lancar.
- .NET Framework: Contoh ini menggunakan .NET, jadi pastikan lingkungan Anda disiapkan untuk pengembangan .NET.
-  Lisensi Sementara: Anda dapat meminta lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/) jika Anda mengevaluasi produk.

Jika Anda belum menyiapkan Aspose.PDF untuk .NET, ikuti petunjuk penginstalan di[dokumentasi](https://reference.aspose.com/pdf/net/).

## Mengimpor Ruang Nama

Sebelum kita mulai membuat kode, kita perlu mengimpor namespace yang diperlukan. Berikut cuplikan kode untuk melakukannya:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

 Ruang nama ini penting karena menyediakan akses ke kelas seperti`Document`, `Page`, `Image` , Dan`HtmlFragment`, yang akan kita gunakan untuk membuat dan memanipulasi PDF.

Setelah kita menyiapkan semuanya, mari kita bahas cara menempatkan teks di sekitar gambar dalam berkas PDF Anda menggunakan Aspose.PDF untuk .NET. Kami akan memandu Anda langkah demi langkah.

## Langkah 1: Membuat Instansi Objek Dokumen

 Pertama, Anda perlu membuat dokumen PDF. Di Aspose.PDF, ini dilakukan dengan membuat instance`Document` objek. Objek ini akan berfungsi sebagai fondasi untuk semua konten yang akan kita tambahkan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

Di sini, kami telah membuat dokumen PDF kosong. Dokumen tersebut belum memiliki halaman, tetapi jangan khawatir, kami akan menambahkannya di langkah berikutnya.

## Langkah 2: Tambahkan Halaman ke Dokumen

Setelah dokumen kita jadi, saatnya menambahkan halaman. Anggap saja ini seperti membuat selembar kertas kosong tempat Anda akan menambahkan konten.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

Kode ini menambahkan halaman baru ke dokumen. Secara default, halaman tersebut kosong, tetapi kita akan mengubahnya.

## Langkah 3: Buat Tabel untuk Mengatur Konten

Agar gambar dan teks tetap selaras, kita akan menggunakan tabel. Tabel dalam PDF dapat membantu menyusun tata letak, seperti dalam dokumen Word atau HTML.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

Cuplikan ini membuat tabel dan menambahkannya ke halaman. Anggaplah tabel sebagai kerangka kerja untuk menyelaraskan gambar dan teks Anda.

## Langkah 4: Mengatur Lebar Kolom untuk Tabel

Setelah menambahkan tabel, kita perlu menentukan seberapa lebar kolomnya. Ini memastikan bahwa gambar dan teks berukuran tepat di halaman.

```csharp
table1.ColumnWidths = "120 270";
```

Baris ini mengatur lebar dua kolom—satu untuk gambar dan satu untuk teks. Sesuaikan nilai ini jika gambar atau teks Anda memerlukan lebih banyak atau lebih sedikit ruang.

## Langkah 5: Tentukan Margin dan Padding

Untuk memastikan semuanya terlihat rapi, mari tambahkan beberapa margin dan bantalan pada tabel.

```csharp
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
table1.DefaultCellPadding = margin;
```

Pengaturan ini memastikan tabel Anda memiliki spasi yang konsisten, membuat konten menarik secara visual.

## Langkah 6: Masukkan Gambar ke dalam Tabel

Sekarang, mari kita masuk ke bagian yang menyenangkan—menambahkan gambar. Dalam kasus ini, kita akan menambahkan logo Aspose, tetapi Anda bebas menggunakan gambar apa pun yang Anda suka.

```csharp
Aspose.Pdf.Row row1 = table1.Rows.Add();
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

Inilah yang terjadi:
- Kami memuat gambar dari direktori yang Anda tentukan.
- Kami mengatur tinggi dan lebar gambar.
- Terakhir, kita tambahkan gambar ke sel pertama dalam tabel.

## Langkah 7: Tambahkan Teks di Samping Gambar

Sekarang gambar sudah ada di tempatnya, mari tambahkan beberapa teks di sebelahnya. Untuk contoh ini, kita akan menggunakan teks berformat HTML untuk memberi gaya pada konten.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF document reporting component that enables .NET applications to <b>create PDF documents from scratch</b> without utilizing Adobe Acrobat.</font>";

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

Blok ini menambahkan judul dan deskripsi bergaya di sel di sebelah gambar. Anda dapat memformat teks menggunakan tag HTML untuk kustomisasi lebih lanjut.

## Langkah 8: Sesuaikan Penyelarasan Vertikal

Secara default, konten dalam sel tabel mungkin tidak sejajar dengan yang Anda inginkan. Dalam kasus ini, kami ingin memastikan teks sejajar dengan bagian atas sel.

```csharp
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
```

Ini memastikan bahwa teks berada di bagian atas sel, menjaga tata letak tetap bersih dan profesional.

## Langkah 9: Tambahkan Lebih Banyak Teks di Bawah Gambar dan Deskripsi

Anda mungkin ingin menyertakan lebih banyak konten di bawah gambar dan teks. Mari tambahkan baris lain ke tabel untuk tujuan ini.

```csharp
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
SecondRow.Cells[0].ColSpan = 2;
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

Di sini, kami telah menambahkan baris lain dengan teks tambahan, yang mencakup kedua kolom untuk menjaga keseimbangan dalam tata letak.

## Langkah 10: Simpan Dokumen PDF

Terakhir, kita perlu menyimpan dokumen tersebut sehingga Anda dapat melihat perubahannya.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

Ini menyimpan PDF dengan gambar dan teks yang diformat sesuai keinginan kita.

## Kesimpulan

Menempatkan teks di sekitar gambar dalam PDF mungkin tampak seperti tugas yang sulit, tetapi Aspose.PDF untuk .NET menyederhanakan prosesnya. Dengan memanfaatkan tabel, gambar, dan teks bergaya, Anda dapat membuat PDF yang tampak profesional dengan usaha minimal. Hanya dengan beberapa baris kode, Anda dapat menempatkan konten tepat di tempat yang Anda inginkan, memberikan dokumen Anda tampilan yang rapi dan tertata dengan baik.

## Pertanyaan yang Sering Diajukan

### Bisakah saya menggunakan metode ini untuk menempatkan beberapa gambar dengan teks?
Ya, cukup tambahkan lebih banyak baris dan sel ke tabel Anda untuk menyertakan gambar dan teks tambahan.

### Bisakah saya mengubah perataan gambar?
Tentu saja! Anda dapat mengubah perataan gambar dengan menyesuaikan properti perataan sel.

### Bagaimana cara memberi gaya pada teks lebih lanjut?
 Anda dapat menggunakan tag HTML di dalam`HtmlFragment` objek untuk menerapkan berbagai gaya seperti tebal, miring, atau font yang berbeda.

### Bisakah saya mengontrol jarak antara teks dan gambar?
 Ya, menggunakan`MarginInfo` Objek ini memungkinkan Anda untuk mengontrol padding dan margin antar elemen.

### Apakah mungkin untuk menambahkan tautan ke teks?
 Tentu saja! Anda dapat menyematkan hyperlink dalam teks berformat HTML menggunakan`<a>` menandai.