---
title: Mengatur Java Script
linktitle: Mengatur Java Script
second_title: Referensi API Aspose.PDF untuk .NET
description: Manfaatkan kekuatan Aspose.PDF untuk .NET. Pelajari cara mengatur JavaScript pada kolom formulir dengan panduan langkah demi langkah kami.
type: docs
weight: 270
url: /id/net/programming-with-forms/set-java-script/
---
## Perkenalan

Membuat PDF yang dinamis dan interaktif dapat meningkatkan pengalaman pengguna secara signifikan, terutama saat mengintegrasikan formulir dan kolom dalam dokumen. Salah satu pustaka canggih yang memungkinkan hal ini adalah Aspose.PDF untuk .NET. Dalam artikel ini, kita akan membahas secara mendalam tentang pengaturan JavaScript untuk kolom formulir menggunakan Aspose.PDF, yang memastikan PDF Anda tidak hanya terlihat bagus tetapi juga berfungsi dengan baik.

## Prasyarat

Sebelum kita mulai membuat kode, pastikan Anda memiliki semua yang dibutuhkan agar dapat mengikutinya dengan lancar:

- Visual Studio (atau IDE .NET apa pun): Pastikan Anda telah menginstal dan mengaturnya dengan benar.
  
-  Pustaka Aspose.PDF: Anda memerlukan versi terbaru dari pustaka ini. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/pdf/net/).

- Pengetahuan Dasar C#: Keakraban dengan pemrograman C# akan membantu Anda lebih memahami cuplikan kode.

-  File PDF: Anda harus memiliki file PDF yang siap untuk pengujian. Dalam contoh kita, kita akan menggunakan file bernama`SetJavaScript.pdf`.

- Direktori Dokumen Anda: Ketahui di mana berkas dokumen Anda disimpan. Kami akan merujuk jalur ini dalam kode kami.

Setelah Anda menyiapkan prasyarat ini, alat apa yang akan kita manfaatkan? Mari kita bahas apa saja yang dapat dilakukan Aspose.PDF.

## Paket Impor

Untuk memulai, Anda perlu menyertakan namespace yang diperlukan dalam proyek C# Anda. Buka file C# utama Anda dan tambahkan pernyataan impor berikut:

```csharp
using System;
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

Ruang nama ini menyediakan akses ke PDF dan fungsionalitas terkait formulir dalam pustaka Aspose.PDF.

Siap membuat PDF Anda interaktif? Ambil topi coding Anda, dan mari kita bahas langkah demi langkah!

## Langkah 1: Tentukan Jalur Dokumen

Pertama, kita perlu menentukan lokasi file PDF kita. Ini akan menjadi dasar untuk semua langkah berikutnya. Berikut cara melakukannya:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya tempat file PDF Anda berada. Anggap saja ini seperti pengaturan koordinat untuk peta harta karun—Anda perlu tahu di mana 'X' menandai lokasi tersebut!

## Langkah 2: Muat Dokumen PDF

Setelah kita menentukan direktori, kita akan memuat berkas PDF kita. 

```csharp
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

Baris ini membuka berkas PDF yang Anda tentukan dan mempersiapkannya untuk manipulasi. 

## Langkah 3: Akses Bidang Formulir

Berikutnya, kita ingin mengakses kolom formulir di mana kita akan menerapkan JavaScript. 

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

 Di sini, kami berasumsi ada kotak teks di PDF Anda yang bernama`textbox1`Jika Anda tidak memiliki kolom dengan nama ini, Anda dapat mengganti namanya atau menyesuaikan kodenya. 

## Langkah 4: Siapkan Tindakan JavaScript

Sekarang, mari tambahkan beberapa fungsi ke kotak teks kita! Kita akan menyiapkan tindakan JavaScript yang akan dipicu pada peristiwa tertentu. 

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

Inilah yang terjadi:
- OnModifyCharacter: Fungsi JavaScript ini menentukan bagaimana bidang tersebut harus berperilaku saat karakter diubah. Dalam hal ini, fungsi ini memperbolehkan dua titik desimal setelah angka tanpa pemisah.
- OnFormat: Ini memastikan bahwa saat pengguna memformat angka, ia mematuhi aturan yang sama.

Dengan menyiapkan tindakan ini, pada dasarnya kita memberi kotak teks kita sebuah kepribadian—seperti mengajarinya gerakan tarian!

## Langkah 5: Inisialisasi Nilai Bidang

Berikutnya, mari berikan kotak teks kita titik awal dengan menetapkan nilai awal. 

```csharp
field.Value = "123";
```

Baris ini menetapkan "123" sebagai nilai yang telah diisi sebelumnya di kotak teks. Ini seperti mempersiapkan panggung untuk pertunjukan.

## Langkah 6: Simpan PDF yang Dimodifikasi

Terakhir, kita perlu menyimpan dokumen kita setelah membuat semua perubahan ini.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
doc.Save(dataDir);
```

 Ini memperbarui file asli dengan perubahan Anda dan menyimpannya sebagai`Restricted_out.pdf`Anggap saja ini sebagai penentu nasib PDF kita—setelah disimpan, PDF tersebut siap untuk dipublikasikan!

## Langkah 7: Konfirmasikan Keberhasilan

Terakhir, mari kita periksa apakah semuanya berjalan lancar. 

```csharp
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

Menjalankan pesan ini akan meyakinkan Anda bahwa operasi telah berhasil diselesaikan, seperti menerima tepuk tangan dari penonton setelah pertunjukan yang hebat.

## Kesimpulan

Selamat! Anda telah berhasil menyiapkan JavaScript untuk kolom formulir dalam PDF menggunakan Aspose.PDF untuk .NET. Tutorial ini tidak hanya memberi Anda alat untuk meningkatkan interaksi pengguna tetapi juga memberdayakan Anda untuk mempersonalisasi dokumen Anda seperti seorang profesional. Baik Anda bekerja dengan formulir dalam faktur, survei, atau PDF interaktif lainnya, kemungkinannya benar-benar tidak terbatas.

### Pertanyaan yang Sering Diajukan

### Apa itu Aspose.PDF untuk .NET?  
Aspose.PDF adalah pustaka yang dirancang untuk membuat, mengedit, dan memanipulasi berkas PDF dalam aplikasi .NET, menyediakan fungsionalitas PDF yang hebat.

### Apakah saya memerlukan lisensi untuk menggunakan Aspose.PDF?  
 Meskipun uji coba gratis tersedia, lisensi diperlukan untuk penggunaan penuh tanpa batasan. Anda dapat membeli lisensi[Di Sini](https://purchase.aspose.com/buy).

### Bisakah saya mengatur JavaScript pada jenis kolom formulir lainnya?  
Tentu saja! Aspose.PDF memungkinkan tindakan JavaScript pada berbagai bidang formulir seperti kotak centang, tombol radio, dan dropdown.

### Bagaimana saya bisa mendapatkan dukungan untuk masalah Aspose.PDF?  
 Anda dapat mengakses dukungan melalui mereka[forum](https://forum.aspose.com/c/pdf/10) untuk pertanyaan atau masalah apa pun.

### Apakah ada cara untuk menguji Aspose.PDF tanpa membeli?  
Ya! Aspose menyediakan[uji coba gratis](https://releases.aspose.com/) untuk menguji fitur perpustakaan sebelum melakukan pembelian.