---
title: Tetapkan Tanggal Kedaluwarsa Dalam File PDF
linktitle: Tetapkan Tanggal Kedaluwarsa Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menetapkan tanggal kedaluwarsa dalam berkas PDF menggunakan Aspose.PDF untuk .NET dengan panduan langkah demi langkah ini.
type: docs
weight: 300
url: /id/net/programming-with-document/setexpirydate/
---
Aspose.PDF untuk .NET adalah pustaka canggih yang menyediakan berbagai fitur untuk bekerja dengan berkas PDF. Salah satu fitur tersebut adalah kemampuan untuk menetapkan tanggal kedaluwarsa untuk dokumen PDF. Dalam tutorial ini, kami akan memandu Anda melalui proses pengaturan tanggal kedaluwarsa untuk dokumen PDF menggunakan Aspose.PDF untuk .NET. 

## Langkah 1: Tetapkan jalur ke direktori dokumen

Sebelum memulai, kita perlu mengatur jalur ke direktori tempat dokumen PDF kita berada. Kita akan menyimpan jalur ini dalam variabel yang disebut "dataDir".

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Membuat dokumen PDF baru

 Untuk membuat dokumen PDF baru, kita perlu membuat instance baru`Aspose.Pdf.Document` objek. Kita dapat melakukannya dengan menggunakan kode berikut:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Langkah 3: Menambahkan halaman baru ke dokumen PDF

Setelah kita membuat dokumen PDF, kita dapat menambahkan halaman baru ke dalamnya. Kita dapat melakukannya dengan menggunakan kode berikut:

```csharp
doc.Pages.Add();
```

## Langkah 4: Menambahkan Teks ke Dokumen PDF

 Setelah menambahkan halaman ke dokumen PDF, kita dapat menambahkan teks ke dalamnya menggunakan`Paragraphs` koleksi. Kita dapat melakukannya dengan menggunakan kode berikut:

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

## Langkah 5: Mengatur tanggal kedaluwarsa PDF menggunakan JavaScript

Untuk mengatur tanggal kedaluwarsa PDF, kita perlu membuat objek JavaScript. Kita dapat melakukannya menggunakan kode berikut:

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");

// Tetapkan JavaScript sebagai tindakan buka PDF
doc.OpenAction = javaScript;
```

Dalam kode ini, kami menetapkan tanggal kedaluwarsa pada Mei 2017.

## Langkah 6: Simpan File PDF

 Setelah Anda menetapkan tanggal kedaluwarsa, Anda perlu menyimpan file PDF. Untuk melakukan ini, Anda dapat menggunakan`Save` metode dari`Document` objek dan berikan jalur ke tempat Anda ingin menyimpan berkas PDF yang diperbarui.

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
// Simpan Dokumen PDF
doc.Save(dataDir);
```

### Contoh kode sumber untuk Mengatur Tanggal Kedaluwarsa menggunakan Aspose.PDF untuk .NET

Berikut contoh kode sumber lengkap untuk menetapkan tanggal kedaluwarsa menggunakan Aspose.PDF untuk .NET:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Membuat instance objek Dokumen
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Tambahkan halaman ke koleksi halaman file PDF
doc.Pages.Add();
// Tambahkan fragmen teks ke koleksi paragraf objek halaman
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
// Buat objek JavaScript untuk mengatur tanggal kedaluwarsa PDF
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
// Tetapkan JavaScript sebagai tindakan buka PDF
doc.OpenAction = javaScript;

dataDir = dataDir + "SetExpiryDate_out.pdf";
// Simpan Dokumen PDF
doc.Save(dataDir);
```

## Kesimpulan

Menetapkan tanggal kedaluwarsa untuk dokumen PDF menggunakan Aspose.PDF for .NET merupakan fitur yang berguna untuk memastikan bahwa dokumen tersebut hanya berlaku untuk jangka waktu tertentu. Dengan mengikuti panduan langkah demi langkah dan menggunakan kode sumber C# yang disediakan, pengembang dapat dengan mudah menetapkan tanggal kedaluwarsa dan membuat PDF dengan masa berlaku terbatas. Fitur ini dapat sangat membantu untuk dokumen yang perlu diakses atau didistribusikan untuk jangka waktu terbatas.

### FAQ untuk mengatur tanggal kedaluwarsa dalam file PDF

#### T: Dapatkah saya menetapkan tanggal kedaluwarsa yang berbeda untuk dokumen PDF?

 A: Ya, Anda dapat mengatur tanggal kedaluwarsa yang berbeda untuk dokumen PDF dengan mengubah kode JavaScript di Langkah 5. Dalam contoh yang diberikan, tanggal kedaluwarsa ditetapkan pada Mei 2017. Untuk mengatur tanggal kedaluwarsa yang berbeda, Anda perlu mengubah kode JavaScript di Langkah 5.`year` Dan`month` variabel dalam kode JavaScript ke tahun dan bulan yang diinginkan.

#### T: Apa yang terjadi jika dokumen PDF telah kedaluwarsa?

A: Bila dokumen PDF telah kedaluwarsa, sebagaimana ditentukan dalam kode JavaScript, penampil akan menampilkan pesan peringatan yang menunjukkan bahwa berkas tersebut telah kedaluwarsa dan pengguna memerlukan berkas baru. Pesan peringatan ini akan ditampilkan saat PDF dibuka.

#### T: Dapatkah saya menggunakan waktu tertentu untuk tanggal kedaluwarsa, bukan hanya tanggal saja?

 A: Ya, Anda dapat mengatur waktu tertentu untuk tanggal kedaluwarsa dalam kode JavaScript. Dengan memodifikasi`expiry` variabel dalam kode JavaScript untuk menyertakan waktu yang diinginkan, Anda dapat mengatur waktu tertentu untuk tanggal kedaluwarsa.