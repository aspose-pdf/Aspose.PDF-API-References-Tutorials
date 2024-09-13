---
title: Tombol Radio Dengan Opsi
linktitle: Tombol Radio Dengan Opsi
second_title: Referensi API Aspose.PDF untuk .NET
description: Manfaatkan potensi PDF interaktif dengan menambahkan tombol radio menggunakan Aspose.PDF untuk .NET. Buat formulir yang menarik dengan mudah dan tingkatkan pengalaman pengguna.
type: docs
weight: 230
url: /id/net/programming-with-forms/radio-button-with-options/
---
## Perkenalan

Membuat dokumen PDF interaktif dapat meningkatkan keterlibatan pengguna secara signifikan dan menyederhanakan pengumpulan data. Di antara berbagai elemen yang dapat Anda masukkan, tombol radio menonjol sebagai metode yang mudah digunakan untuk menyajikan berbagai pilihan. Dengan menggunakan Aspose.PDF untuk .NET, Anda dapat dengan mudah menambahkan tombol radio ke dalam formulir PDF, sehingga memudahkan pengguna untuk memilih preferensi mereka. Baik Anda mengerjakan survei, formulir umpan balik, atau aplikasi, panduan ini akan membantu Anda memanfaatkan kekuatan Aspose.PDF untuk menerapkan tombol radio secara efektif.

## Prasyarat

Sebelum kita mulai, ada beberapa hal yang perlu Anda siapkan untuk memastikan perjalanan yang lancar saat kita membuat PDF dengan tombol radio:

1.  Aspose.PDF untuk .NET: Pastikan Anda telah menginstal pustaka Aspose.PDF di proyek Anda. Jika Anda belum memilikinya, Anda dapat mengunduhnya dengan mudah dari[halaman rilis](https://releases.aspose.com/pdf/net/).
2. .NET Framework: Pemahaman dasar mengenai .NET Framework akan membantu Anda mengatasi berbagai masalah yang Anda hadapi.
3. Lingkungan Pengembangan: Anda memerlukan IDE yang sesuai untuk .NET (seperti Visual Studio) tempat Anda dapat menulis dan menguji kode Anda.
4. Keakraban dengan C#: Meskipun Anda tidak perlu menjadi seorang profesional, memahami pemrograman C# pasti akan membuat proses ini lebih mudah dan menyenangkan.
5. Pengetahuan Dasar tentang Struktur PDF: Memahami bagaimana PDF terstruktur dapat membantu saat memecahkan masalah atau menyesuaikan formulir Anda lebih lanjut.

Setelah semua ini beres, Anda siap melepaskan kreativitas Anda ke dunia PDF!

## Paket Impor

Untuk memulai dengan tombol radio di Aspose.PDF, pertama-tama Anda perlu mengimpor paket-paket penting ke dalam proyek C# Anda. Berikut ini cara melakukannya:

### Buka Editor Kode Anda

Buka lingkungan pengembangan Anda (seperti Visual Studio) dan buat proyek C# baru jika Anda belum melakukannya. 

### Tambahkan Referensi Aspose.PDF

Klik kanan pada proyek Anda di Solution Explorer, pilih Add > Reference, dan di bagian Assemblies, cari Aspose.PDF. Jika Anda telah menginstal pustaka dengan benar, pustaka tersebut akan muncul dalam daftar. Cukup centang dan klik OK.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

Sekarang, proyek Anda siap memanfaatkan kekuatan Aspose!

Setelah semuanya siap, mari buat dokumen PDF yang diisi dengan tombol radio langkah demi langkah!

## Langkah 1: Siapkan Dokumen

Pertama, mari buat dokumen PDF baru dan tambahkan halaman ke dalamnya. Ini akan menjadi kanvas tempat kita melukis opsi tombol radio.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
```

 Dalam cuplikan ini, kami sedang membuat yang baru`Document` objek dan menambahkan`Page` untuk konten kami. Pastikan untuk mengganti`YOUR DOCUMENT DIRECTORY` dengan jalur tempat Anda ingin menyimpan PDF Anda.

## Langkah 2: Buat Tabel untuk Tata Letak

Selanjutnya, kita perlu tata letak untuk tombol radio kita. Menggunakan tabel akan memudahkan penempatan tombol-tombol tersebut dengan baik.

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "120 120 120"; // Tentukan lebar kolom
page.Paragraphs.Add(table);
```

 Di sini, kami membuat`Table`objek dan menentukan lebar untuk ketiga kolom kita. Ini menciptakan tata letak yang rapi untuk opsi kita.

## Langkah 3: Tambahkan Baris ke Tabel

Sekarang kita akan menambahkan baris ke tabel dan sel yang akan berisi tombol radio.

```csharp
Row r1 = table.Rows.Add();
Cell c1 = r1.Cells.Add();
Cell c2 = r1.Cells.Add();
Cell c3 = r1.Cells.Add();
```

Kita buat baris baru dan tiga sel di baris tersebut. Setiap sel akan berisi opsi tombol radio.

## Langkah 4: Tambahkan Bidang Tombol Radio

Di sinilah kesenangan dimulai – mari tambahkan bidang tombol radio ke PDF kita!

```csharp
RadioButtonField rf = new RadioButtonField(page);
rf.PartialName = "radio";
doc.Form.Add(rf, 1);
```

 Kami membuat contoh sebuah`RadioButtonField`, tetapkan namanya, lalu tambahkan ke formulir dokumen. Kolom ini akan memungkinkan pengguna membuat pilihan.

## Langkah 5: Konfigurasikan Opsi Tombol Radio

Saatnya membuat opsi untuk tombol radio! Kita akan menambahkan tiga opsi yang dapat dipilih pengguna.

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
RadioButtonOptionField opt2 = new RadioButtonOptionField();
RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt1.OptionName = "Item1";
opt2.OptionName = "Item2";
opt3.OptionName = "Item3";
```

 Di sini, kita membuat tiga`RadioButtonOptionField` contoh untuk setiap pilihan kita dan memberi mereka nama. Berkreasi dengan nama-nama ini dapat membantu memandu pengguna dengan lebih baik tentang apa yang harus dipilih.

## Langkah 6: Tetapkan Dimensi untuk Opsi

Berikutnya, mari atur ukuran opsi tombol radio agar menarik secara visual.

```csharp
opt1.Width = 15;
opt1.Height = 15;
opt2.Width = 15;
opt2.Height = 15;
opt3.Width = 15;
opt3.Height = 15;
```

Dengan kode ini, kita mendefinisikan dimensi setiap tombol radio. Anda dapat menyesuaikan nilai ini jika Anda menginginkan opsi yang lebih besar atau lebih kecil.

## Langkah 7: Tambahkan Opsi ke Bidang Tombol Radio

Sekarang setelah opsi dibuat, kita perlu menambahkannya ke bidang tombol radio.

```csharp
rf.Add(opt1);
rf.Add(opt2);
rf.Add(opt3);
```

Kode ini tidak hanya menambahkan opsi tetapi juga menautkannya ke bidang tombol radio kami, yang memberi pengguna kemampuan untuk memilih salah satu opsi.

## Langkah 8: Berikan Gaya pada Opsi

Untuk menonjolkan pilihan kita, mari kita beri gaya. Kita dapat menambahkan batas dan mengatur warna.

```csharp
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Border.Style = BorderStyle.Solid;
opt1.Characteristics.Border = System.Drawing.Color.Black;
opt1.DefaultAppearance.TextColor = System.Drawing.Color.Red;
opt1.Caption = new TextFragment("Item1");
```

 Ulangi gaya ini untuk`opt2` Dan`opt3`, menyesuaikan teksnya sebagaimana mestinya. Ini memastikan bahwa setiap opsi terlihat profesional dan menarik.

## Langkah 9: Tambahkan Opsi ke Sel

Berikutnya, kita perlu menempatkan tombol radio tersebut ke dalam sel yang sesuai di tabel kita.

```csharp
c1.Paragraphs.Add(opt1);
c2.Paragraphs.Add(opt2);
c3.Paragraphs.Add(opt3);
```

Baris ini menambahkan opsi gaya ke sel yang kita buat sebelumnya, menatanya dengan rapi dalam tabel kita.

## Langkah 10: Simpan Dokumen PDF

Akhirnya, saatnya menyimpan pekerjaan Anda! Langkah ini akan menyimpan semua yang telah kita lakukan ke dalam file PDF.

```csharp
dataDir = dataDir + "RadioButtonWithOptions_out.pdf";
// Simpan file PDF
doc.Save(dataDir);
Console.WriteLine("\nRadio button field with three options added successfully.\nFile saved at " + dataDir);
```

Dengan kode ini, dokumen Anda akan disimpan di direktori yang ditentukan. Kini Anda dapat membuka berkas PDF ini untuk melihat tombol radio yang Anda gunakan. Selamat atas penerapan PDF interaktif pertama Anda!

## Kesimpulan

Menguasai cara membuat elemen interaktif seperti tombol radio dengan Aspose.PDF untuk .NET akan membuka kemungkinan baru untuk dokumen PDF Anda. Dengan mengikuti panduan ini, Anda sekarang akan dapat memasukkan tombol radio ke dalam proyek Anda dengan mudah, meningkatkan pengalaman pengguna dan proses pengumpulan data. Baik untuk survei sederhana atau formulir yang rumit, kemampuan untuk membuat PDF interaktif yang disesuaikan ada di ujung jari Anda.

## Pertanyaan yang Sering Diajukan

### Apa itu Aspose.PDF untuk .NET?
Aspose.PDF untuk .NET adalah pustaka yang memungkinkan pengembang untuk membuat dan memanipulasi dokumen PDF secara terprogram.

### Bagaimana cara menginstal Aspose.PDF untuk .NET?
 Anda dapat mengunduh perpustakaan dari[Halaman rilis Aspose](https://releases.aspose.com/pdf/net/) dan menambahkannya ke proyek Anda.

### Bisakah saya membuat tombol radio dalam PDF menggunakan bahasa pemrograman lain?
Ya, Aspose.PDF juga tersedia untuk Java dan bahasa lain untuk fungsi serupa.

### Apakah ada uji coba gratis untuk Aspose.PDF?
 Ya, Anda dapat menjelajahi fungsionalitas Aspose.PDF dengan mengunduh[versi uji coba gratis](https://releases.aspose.com/).

### Di mana saya bisa mendapatkan dukungan untuk Aspose.PDF?
 Untuk dukungan, Anda dapat mengunjungi[Forum dukungan Aspose](https://forum.aspose.com/c/pdf/10) untuk bantuan dari para ahli dan anggota masyarakat.