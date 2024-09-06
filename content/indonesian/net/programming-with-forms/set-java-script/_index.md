---
title: Mengatur Java Script
linktitle: Mengatur Java Script
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menggunakan Aspose.PDF untuk .NET untuk mengatur JavaScript di kolom formulir di file PDF.
type: docs
weight: 270
url: /id/net/programming-with-forms/set-java-script/
---
Dalam panduan ini, kami akan menjelaskan langkah demi langkah cara menggunakan pustaka Aspose.PDF untuk .NET guna menentukan JavaScript dalam kolom formulir dokumen PDF. Kami akan menunjukkan cara mengonfigurasi tindakan JavaScript untuk melakukan operasi tertentu pada kolom teks.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Lingkungan pengembangan .NET yang terinstal pada sistem Anda.
- Pustaka Aspose.PDF untuk .NET. Anda dapat mengunduhnya dari situs web resmi Aspose.

## Langkah 1: Mengonfigurasi direktori dokumen

 Langkah pertama adalah mengonfigurasi direktori dokumen tempat file PDF yang ingin Anda kerjakan berada. Anda dapat menggunakan`dataDir` variabel untuk menentukan jalur direktori.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Pastikan untuk mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 2: Memuat file PDF masukan

 Pada langkah ini, kita akan memuat file PDF input menggunakan`Document` kelas Aspose.PDF.

```csharp
// Muat file PDF masukan
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

Pastikan berkas PDF masukan ada di direktori dokumen yang ditentukan.

## Langkah 3: Mengakses bidang TextBox

 Untuk menerapkan JavaScript ke bidang teks tertentu, pertama-tama kita perlu mengakses bidang tersebut. Dalam contoh ini, kita asumsikan bidang teks tersebut disebut "textbox1". Gunakan`doc.Form["textbox1"]` metode untuk mendapatkan yang sesuai`TextBoxField` obyek.

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

Pastikan bidang teks yang ditentukan ada dalam berkas PDF masukan.

## Langkah 4: Konfigurasikan tindakan JavaScript

 Sekarang setelah kita mengakses kolom teks, kita dapat mengonfigurasi tindakan JavaScript yang terkait dengan kolom ini. Dalam contoh ini, kita akan menggunakan dua tindakan:`OnModifyCharacter` Dan`OnFormat` Tindakan ini akan didefinisikan menggunakan`JavascriptAction` objek.

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

Pastikan untuk menyesuaikan tindakan JavaScript sesuai dengan kebutuhan Anda.

## Langkah 5: Mengatur nilai bidang awal

Sebelum menyimpan PDF yang dihasilkan, kita dapat menetapkan nilai awal untuk kolom teks. Dalam contoh ini, kita akan menetapkan nilai "123" untuk kolom tersebut.

```csharp
field.Value = "123";
```

Sesuaikan nilai ini menurut kebutuhan Anda.

## Langkah 6: Menyimpan PDF yang Dihasilkan

 Sekarang setelah kita selesai mengatur bidang teks dan tindakan JavaScript, kita dapat menyimpan PDF yang dihasilkan menggunakan`Save` metode dari`Document` kelas.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
// Simpan hasil PDF
doc.Save(dataDir);
```

Pastikan untuk menentukan jalur lengkap dan nama file untuk PDF yang dihasilkan.


### Contoh kode sumber untuk Set Java Script menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Muat file PDF masukan
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
// 2 digit setelah titik
// Tidak ada pemisah
// Gaya Negatif = minus
// Tidak ada mata uang
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
// Tetapkan nilai bidang awal
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
// Simpan hasil PDF
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## Kesimpulan

Dalam panduan ini, kita mempelajari cara menggunakan pustaka Aspose.PDF untuk .NET guna mengatur JavaScript dalam kolom formulir dokumen PDF. Dengan mengikuti langkah-langkah yang diuraikan, Anda dapat menyesuaikan tindakan JavaScript untuk melakukan berbagai operasi pada kolom teks. Jangan ragu untuk menjelajahi lebih lanjut fitur-fitur Aspose.PDF untuk .NET guna memperluas kemungkinan dalam memanipulasi file PDF.


### Pertanyaan yang Sering Diajukan

#### T: Dapatkah saya menggunakan Aspose.PDF untuk .NET untuk menambahkan JavaScript ke elemen formulir lainnya, seperti kotak centang dan tombol radio?

 A: Ya, Aspose.PDF untuk .NET memungkinkan Anda menambahkan JavaScript ke berbagai elemen formulir, termasuk kotak centang, tombol radio, dan daftar dropdown. Anda dapat menggunakan`JavascriptAction` kelas untuk menentukan tindakan JavaScript untuk berbagai elemen formulir.

#### T: Apakah mungkin untuk memvalidasi masukan pengguna menggunakan JavaScript di kolom formulir?

 A: Ya, Anda dapat menggunakan JavaScript untuk memvalidasi masukan pengguna di kolom formulir. Dengan mendefinisikan tindakan JavaScript seperti`OnBlur` atau`OnKeystroke` untuk bidang formulir, Anda dapat memvalidasi data yang dimasukkan dan menampilkan pesan kesalahan jika perlu.

#### T: Dapatkah saya menjalankan fungsi JavaScript yang kompleks menggunakan Aspose.PDF untuk .NET?

 A: Ya, Anda dapat menjalankan fungsi JavaScript yang kompleks menggunakan Aspose.PDF untuk .NET. Anda memiliki fleksibilitas untuk menentukan fungsi JavaScript khusus dan memanggilnya dalam`JavascriptAction`.

#### T: Apakah Aspose.PDF untuk .NET mendukung peristiwa JavaScript selain yang disebutkan dalam tutorial ini?

 A: Ya, Aspose.PDF untuk .NET mendukung berbagai acara JavaScript, termasuk`OnMouseEnter`, `OnMouseExit`, `OnMouseDown` , Dan`OnMouseUp`, antara lain. Anda dapat menggunakan peristiwa ini untuk memicu tindakan JavaScript berdasarkan interaksi pengguna.

#### T: Dapatkah saya menggunakan Aspose.PDF untuk .NET untuk mengekstrak kode JavaScript dari dokumen PDF yang ada?

 A: Aspose.PDF untuk .NET menyediakan kemampuan untuk mengekstrak kode JavaScript dari dokumen PDF yang ada. Anda dapat menggunakan`JavascriptAction` kelas dan metode relevan lainnya untuk mengakses dan menganalisis tindakan JavaScript dalam bentuk PDF.