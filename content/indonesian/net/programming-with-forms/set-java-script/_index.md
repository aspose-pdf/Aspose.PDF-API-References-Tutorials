---
title: Atur Skrip Java
linktitle: Atur Skrip Java
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menggunakan Aspose.PDF untuk .NET untuk mengatur JavaScript di bidang formulir dalam file PDF.
type: docs
weight: 270
url: /id/net/programming-with-forms/set-java-script/
---
Dalam panduan ini, kami akan menjelaskan langkah demi langkah cara menggunakan perpustakaan Aspose.PDF untuk .NET guna mendefinisikan JavaScript di bidang formulir dokumen PDF. Kami akan menunjukkan cara mengonfigurasi tindakan JavaScript untuk melakukan operasi tertentu pada bidang teks.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Lingkungan pengembangan .NET diinstal pada sistem Anda.
- Pustaka Aspose.PDF untuk .NET. Anda dapat mendownloadnya dari situs resmi Aspose.

## Langkah 1: Mengonfigurasi direktori dokumen

 Langkah pertama adalah mengkonfigurasi direktori dokumen tempat file PDF yang ingin Anda kerjakan berada. Anda dapat menggunakan`dataDir` variabel untuk menentukan jalur direktori.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Pastikan untuk mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 2: Memuat file PDF masukan

Pada langkah ini, kita akan memuat file PDF masukan menggunakan`Document` kelas Aspose.PDF.

```csharp
// Muat file PDF masukan
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

Pastikan file PDF masukan ada di direktori dokumen yang ditentukan.

## Langkah 3: Mengakses bidang TextBox

 Untuk menerapkan JavaScript ke kolom teks tertentu, pertama-tama kita perlu mengakses kolom tersebut. Dalam contoh ini, kita menganggap kolom teks disebut "kotak teks1". Menggunakan`doc.Form["textbox1"]` metode untuk mendapatkan yang sesuai`TextBoxField` obyek.

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

Pastikan kolom teks yang ditentukan ada di file PDF masukan.

## Langkah 4: Konfigurasikan tindakan JavaScript

 Sekarang kita telah mengakses kolom teks, kita dapat mengonfigurasi tindakan JavaScript yang terkait dengan kolom ini. Dalam contoh ini, kita akan menggunakan dua tindakan:`OnModifyCharacter` Dan`OnFormat` . Tindakan ini akan ditentukan menggunakan`JavascriptAction` objek.

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

Pastikan untuk menyesuaikan tindakan JavaScript sesuai dengan kebutuhan Anda.

## Langkah 5: Menetapkan nilai bidang awal

Sebelum menyimpan PDF yang dihasilkan, kita dapat menetapkan nilai awal untuk kolom teks. Dalam contoh ini, kita akan menetapkan nilai "123" untuk bidang tersebut.

```csharp
field.Value = "123";
```

Sesuaikan nilai ini sesuai dengan kebutuhan Anda.

## Langkah 6: Menyimpan PDF yang Dihasilkan

 Sekarang kita sudah selesai menyiapkan bidang teks dan tindakan JavaScript, kita dapat menyimpan PDF yang dihasilkan menggunakan`Save` metode`Document` kelas.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
// Simpan PDF yang dihasilkan
doc.Save(dataDir);
```

Pastikan untuk menentukan jalur lengkap dan nama file untuk PDF yang dihasilkan.


### Contoh kode sumber untuk Mengatur Java Script menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Muat file PDF masukan
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
// 2 digit demi titik
// Tidak ada pemisah
// Gaya negatif = minus
// Tidak ada mata uang
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
// Tetapkan nilai bidang awal
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
// Simpan PDF yang dihasilkan
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## Kesimpulan

Dalam panduan ini, kita mempelajari cara menggunakan pustaka Aspose.PDF untuk .NET guna mengatur JavaScript di bidang formulir dokumen PDF. Dengan mengikuti langkah-langkah yang dijelaskan, Anda dapat menyesuaikan tindakan JavaScript untuk melakukan berbagai operasi pada bidang teks. Jangan ragu untuk menjelajahi lebih jauh fitur Aspose.PDF untuk .NET guna memperluas kemungkinan memanipulasi file PDF.


### FAQ

#### T: Dapatkah saya menggunakan Aspose.PDF untuk .NET untuk menambahkan JavaScript ke elemen formulir lainnya, seperti kotak centang dan tombol radio?

 J: Ya, Aspose.PDF untuk .NET memungkinkan Anda menambahkan JavaScript ke berbagai elemen formulir, termasuk kotak centang, tombol radio, dan daftar dropdown. Anda dapat menggunakan`JavascriptAction` kelas untuk mendefinisikan tindakan JavaScript untuk elemen formulir yang berbeda.

#### T: Apakah mungkin untuk memvalidasi input pengguna menggunakan JavaScript di kolom formulir?

 J: Ya, Anda dapat menggunakan JavaScript untuk memvalidasi input pengguna di kolom formulir. Dengan mendefinisikan tindakan JavaScript seperti`OnBlur` atau`OnKeystroke` untuk bidang formulir, Anda dapat memvalidasi data yang dimasukkan dan menampilkan pesan kesalahan jika perlu.

#### T: Bisakah saya menjalankan fungsi JavaScript yang kompleks menggunakan Aspose.PDF untuk .NET?

 J: Ya, Anda dapat menjalankan fungsi JavaScript yang kompleks menggunakan Aspose.PDF untuk .NET. Anda memiliki fleksibilitas untuk menentukan fungsi JavaScript khusus dan memanggilnya di dalam`JavascriptAction`.

#### T: Apakah Aspose.PDF untuk .NET mendukung peristiwa JavaScript selain yang disebutkan dalam tutorial ini?

 J: Ya, Aspose.PDF untuk .NET mendukung berbagai peristiwa JavaScript, termasuk`OnMouseEnter`, `OnMouseExit`, `OnMouseDown` , Dan`OnMouseUp`, diantara yang lain. Anda dapat menggunakan peristiwa ini untuk memicu tindakan JavaScript berdasarkan interaksi pengguna.

#### T: Dapatkah saya menggunakan Aspose.PDF untuk .NET untuk mengekstrak kode JavaScript dari dokumen PDF yang ada?

 J: Aspose.PDF untuk .NET menyediakan kemampuan untuk mengekstrak kode JavaScript dari dokumen PDF yang ada. Anda dapat menggunakan`JavascriptAction` kelas dan metode relevan lainnya untuk mengakses dan menganalisis tindakan JavaScript dalam bentuk PDF.