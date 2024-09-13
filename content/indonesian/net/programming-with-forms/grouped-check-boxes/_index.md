---
title: Kotak Centang yang Dikelompokkan dalam Dokumen PDF
linktitle: Kotak Centang yang Dikelompokkan dalam Dokumen PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara membuat kotak centang yang dikelompokkan (tombol radio) dalam dokumen PDF menggunakan Aspose.PDF untuk .NET dengan tutorial langkah demi langkah ini.
type: docs
weight: 170
url: /id/net/programming-with-forms/grouped-check-boxes/
---
## Perkenalan

Membuat PDF interaktif tidak sesulit kedengarannya, terutama jika Anda memiliki alat canggih seperti Aspose.PDF for .NET. Salah satu elemen interaktif yang mungkin perlu Anda tambahkan ke dokumen PDF adalah kotak centang berkelompok, atau lebih tepatnya, tombol radio yang memungkinkan pengguna memilih satu opsi dari sekumpulan opsi. Tutorial ini akan memandu Anda melalui proses penambahan kotak centang berkelompok (tombol radio) ke dokumen PDF menggunakan Aspose.PDF for .NET. Baik Anda seorang pemula atau pengembang berpengalaman, Anda akan merasa panduan ini menarik, terperinci, dan mudah diikuti.

## Prasyarat

Sebelum kita menyelami panduan langkah demi langkah, mari kita bahas beberapa prasyarat penting:

1.  Aspose.PDF untuk .NET: Pastikan Anda telah menginstal pustaka Aspose.PDF. Jika tidak, Anda dapat[unduh disini](https://releases.aspose.com/pdf/net/).
2. IDE: Anda harus menyiapkan lingkungan pengembangan, seperti Visual Studio.
3. .NET Framework: Proyek harus menargetkan versi .NET Framework yang kompatibel dengan Aspose.PDF.
4. Pengetahuan Dasar C#: Keakraban dengan C# dan manipulasi PDF diperlukan untuk mengikutinya dengan lancar.
5.  Lisensi: Aspose.PDF memerlukan lisensi untuk fungsionalitas penuh. Anda dapat[memperoleh lisensi sementara](https://purchase.aspose.com/temporary-license/) jika diperlukan.

## Paket Impor

Sebelum memulai, pastikan Anda telah mengimpor namespace yang diperlukan ke proyek Anda:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Forms;
```

Paket-paket ini akan memberi Anda akses ke semua kelas dan metode yang diperlukan untuk memanipulasi dokumen PDF, termasuk membuat tombol radio dan menentukan propertinya.

Di bagian ini, kami akan menguraikan proses pembuatan kotak centang berkelompok (tombol radio) menjadi langkah-langkah yang jelas dan mudah diikuti.

## Langkah 1: Buat Dokumen PDF Baru

 Langkah pertama adalah membuat instance dari`Document` objek, yang akan mewakili berkas PDF Anda. Lalu, tambahkan halaman kosong ke dokumen Anda tempat Anda akan menempatkan kotak centang yang dikelompokkan.

```csharp
// Membuat instance objek Dokumen
Document pdfDocument = new Document();

// Tambahkan halaman ke file PDF
Page page = pdfDocument.Pages.Add();
```

Ini menyiapkan fondasi untuk menambahkan elemen apa pun, seperti tombol radio, ke PDF.

## Langkah 2: Inisialisasi Bidang Tombol Radio

Selanjutnya, kita perlu membuat`RadioButtonField` objek, yang akan menampung kotak centang yang dikelompokkan (tombol radio). Bidang ini ditambahkan ke halaman tertentu tempat kotak centang akan muncul.

```csharp
// Buat instance objek RadioButtonField dan tetapkan ke halaman pertama
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

Anggap ini sebagai wadah yang akan mengelompokkan opsi tombol radio individual bersama-sama.

## Langkah 3: Tambahkan Opsi Tombol Radio

 Sekarang, mari tambahkan opsi tombol radio individual ke kolom. Dalam contoh ini, kita akan menambahkan dua tombol radio dan menentukan posisinya menggunakan`Rectangle` obyek.

```csharp
// Tambahkan opsi tombol radio pertama dan tentukan posisinya menggunakan Persegi Panjang
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));

// Tetapkan nama opsi untuk identifikasi
opt1.OptionName = "Option1";
opt2.OptionName = "Option2";
```

 Di sini,`Rectangle` Objek mendefinisikan koordinat dan ukuran setiap tombol radio pada halaman.

## Langkah 4: Sesuaikan Gaya Tombol Radio

 Anda dapat menyesuaikan tampilan tombol radio dengan mengaturnya`Style` properti. Misalnya, Anda mungkin menginginkan kotak centang berbentuk persegi atau berbentuk silang.

```csharp
// Mengatur gaya tombol radio
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Cross;
```

Hal ini memungkinkan Anda untuk mengontrol tampilan dan nuansa kotak centang, menjadikannya lebih mudah digunakan dan menarik secara visual.

## Langkah 5: Konfigurasikan Properti Perbatasan

Batas memainkan peran penting dalam membuat kotak centang mudah dikenali. Di sini, kita akan menambahkan batas solid di sekitar setiap opsi tombol radio dan menentukan lebar dan warnanya.

```csharp
// Konfigurasikan batas tombol radio pertama
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt1.Characteristics.Border = Color.Black;

// Konfigurasikan batas tombol radio kedua
opt2.Border = new Border(opt2);
opt2.Border.Style = BorderStyle.Solid;
opt2.Border.Width = 1;
opt2.Characteristics.Border = Color.Black;
```

Langkah ini memastikan bahwa setiap tombol radio memiliki batas yang jelas, sehingga meningkatkan keterbacaan dokumen.

## Langkah 6: Tambahkan Opsi Tombol Radio ke Formulir

Sekarang, kita akan menambahkan tombol radio ke formulir dokumen. Ini adalah langkah terakhir dalam mengelompokkan kotak centang bersama-sama di bawah satu bidang.

```csharp
// Tambahkan bidang tombol radio ke objek formulir dokumen
pdfDocument.Form.Add(radio);
```

Objek formulir berfungsi sebagai wadah untuk semua elemen interaktif, termasuk kotak centang yang dikelompokkan.

## Langkah 7: Simpan Dokumen PDF

Terakhir, setelah semuanya disiapkan, Anda dapat menyimpan dokumen PDF ke lokasi yang Anda inginkan.

```csharp
// Tentukan jalur file keluaran
string dataDir = "YOUR DOCUMENT DIRECTORY" + "GroupedCheckBoxes_out.pdf";

// Simpan dokumen PDF
pdfDocument.Save(dataDir);

// Konfirmasikan pembuatan yang berhasil
Console.WriteLine("Grouped checkboxes added successfully. File saved at " + dataDir);
```

Selesai! Anda telah berhasil membuat PDF dengan kotak centang yang dikelompokkan menggunakan Aspose.PDF untuk .NET.

## Kesimpulan

Menambahkan elemen interaktif seperti kotak centang yang dikelompokkan ke dokumen PDF mungkin tampak rumit pada awalnya, tetapi dengan Aspose.PDF untuk .NET, hal itu menjadi mudah. Dengan mengikuti panduan langkah demi langkah ini, Anda telah mempelajari cara menyiapkan dokumen PDF dasar, menambahkan tombol radio yang dikelompokkan, menyesuaikan tampilannya, dan menyimpan hasil akhirnya. Baik Anda membuat formulir, survei, atau jenis PDF interaktif lainnya, panduan ini memberi Anda dasar yang kuat untuk memulai.

## Pertanyaan yang Sering Diajukan

### Bisakah saya menambahkan lebih dari dua tombol radio ke satu grup?
 Tentu saja! Cukup buat instance tambahan`RadioButtonOptionField` objek dan menambahkannya ke`RadioButtonField` seperti yang ditunjukkan dalam tutorial.

### Bagaimana cara menangani beberapa kelompok kotak centang dalam satu dokumen?
Untuk membuat beberapa grup, buat instance terpisah`RadioButtonField` objek untuk setiap kelompok.

### Apakah ada batasan jumlah kotak centang yang dapat saya tambahkan?
Tidak, Aspose.PDF untuk .NET tidak memberlakukan batasan apa pun pada jumlah kotak centang yang dapat Anda tambahkan ke PDF.

### Bisakah saya mengubah tampilan kotak centang setelah ditambahkan?
Ya, Anda dapat mengubah properti seperti gaya batas, lebar, dan warna setelah kotak centang ditambahkan.

### Apakah mungkin untuk menggunakan gambar sebagai tombol radio?
 Ya, Aspose.PDF memungkinkan Anda menggunakan gambar kustom sebagai tombol radio dengan mengatur`Appearance` properti setiap opsi tombol radio.