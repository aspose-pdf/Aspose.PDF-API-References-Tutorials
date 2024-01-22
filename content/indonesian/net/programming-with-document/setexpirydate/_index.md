---
title: Tetapkan Tanggal Kedaluwarsa Dalam File PDF
linktitle: Tetapkan Tanggal Kedaluwarsa Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara mengatur tanggal kedaluwarsa dalam file PDF menggunakan Aspose.PDF untuk .NET dengan panduan langkah demi langkah ini.
type: docs
weight: 300
url: /id/net/programming-with-document/setexpirydate/
---
Aspose.PDF untuk .NET adalah perpustakaan canggih yang menyediakan berbagai fitur untuk bekerja dengan file PDF. Salah satu fitur tersebut adalah kemampuan untuk mengatur tanggal kedaluwarsa untuk dokumen PDF. Dalam tutorial ini, kami akan memandu Anda melalui proses pengaturan tanggal kedaluwarsa untuk dokumen PDF menggunakan Aspose.PDF untuk .NET. 

## Langkah 1: Tetapkan jalur ke direktori dokumen

Sebelum kita mulai, kita perlu mengatur path ke direktori dimana dokumen PDF kita berada. Kami akan menyimpan jalur ini dalam variabel bernama "dataDir".

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Membuat dokumen PDF baru

 Untuk membuat dokumen PDF baru, kita perlu membuat instance dokumen baru`Aspose.Pdf.Document` obyek. Kita dapat melakukan ini menggunakan kode berikut:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Langkah 3: Menambahkan halaman baru ke dokumen PDF

Setelah kami membuat dokumen PDF, kami dapat menambahkan halaman baru ke dalamnya. Kita dapat melakukan ini menggunakan kode berikut:

```csharp
doc.Pages.Add();
```

## Langkah 4: Menambahkan Teks ke Dokumen PDF

Setelah menambahkan halaman ke dokumen PDF, kita dapat menambahkan teks ke dalamnya menggunakan`Paragraphs` koleksi. Kita dapat melakukan ini menggunakan kode berikut:

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

## Langkah 5: Menetapkan tanggal kedaluwarsa PDF menggunakan JavaScript

Untuk mengatur tanggal kedaluwarsa PDF, kita perlu membuat objek JavaScript. Kita dapat melakukan ini menggunakan kode berikut:

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");

// Tetapkan JavaScript sebagai tindakan terbuka PDF
doc.OpenAction = javaScript;
```

Dalam kode ini, kami menetapkan tanggal kedaluwarsa hingga Mei 2017.

## Langkah 6: Simpan File PDF

 Setelah Anda menetapkan tanggal kedaluwarsa, Anda perlu menyimpan file PDF. Untuk melakukan ini, Anda dapat menggunakan`Save` metode`Document` objek dan berikan jalur ke tempat Anda ingin menyimpan file PDF yang diperbarui.

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
// Simpan Dokumen PDF
doc.Save(dataDir);
```

### Contoh kode sumber untuk Menetapkan Tanggal Kedaluwarsa menggunakan Aspose.PDF untuk .NET

Berikut contoh lengkap source code pengaturan tanggal kadaluwarsa menggunakan Aspose.PDF untuk .NET:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat instance objek Dokumen
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Tambahkan halaman ke halaman koleksi file PDF
doc.Pages.Add();
// Tambahkan fragmen teks ke kumpulan paragraf objek halaman
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
// Buat objek JavaScript untuk mengatur tanggal kedaluwarsa PDF
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
// Tetapkan JavaScript sebagai tindakan terbuka PDF
doc.OpenAction = javaScript;

dataDir = dataDir + "SetExpiryDate_out.pdf";
// Simpan Dokumen PDF
doc.Save(dataDir);
```

## Kesimpulan

Menetapkan tanggal kedaluwarsa untuk dokumen PDF menggunakan Aspose.PDF untuk .NET adalah fitur yang berguna untuk memastikan bahwa dokumen tersebut hanya valid untuk jangka waktu tertentu. Dengan mengikuti panduan langkah demi langkah dan menggunakan kode sumber C# yang disediakan, pengembang dapat dengan mudah mengatur tanggal kedaluwarsa dan membuat PDF dengan validitas terbatas waktu. Fitur ini khususnya berguna untuk dokumen yang perlu diakses atau didistribusikan dalam jangka waktu terbatas.

### FAQ untuk menetapkan tanggal kedaluwarsa dalam file PDF

#### T: Dapatkah saya menetapkan tanggal kedaluwarsa yang berbeda untuk dokumen PDF?

 J: Ya, Anda dapat menetapkan tanggal kedaluwarsa yang berbeda untuk dokumen PDF dengan memodifikasi kode JavaScript pada Langkah 5. Dalam contoh yang diberikan, tanggal kedaluwarsa diatur ke Mei 2017. Untuk menetapkan tanggal kedaluwarsa yang berbeda, Anda perlu mengubah`year` Dan`month` variabel dalam kode JavaScript ke tahun dan bulan yang diinginkan.

#### Q: Apa yang terjadi bila dokumen PDF sudah habis masa berlakunya?

J: Ketika dokumen PDF telah kedaluwarsa, seperti yang ditentukan dalam kode JavaScript, pemirsa akan menampilkan pesan peringatan yang menunjukkan bahwa file tersebut telah kedaluwarsa dan pengguna memerlukan yang baru. Pesan peringatan ini akan ditampilkan ketika PDF dibuka.

#### T: Dapatkah saya menggunakan waktu tertentu untuk tanggal kedaluwarsa, bukan hanya tanggal saja?

 A: Ya, Anda dapat mengatur waktu tertentu untuk tanggal kedaluwarsa dalam kode JavaScript. Dengan memodifikasi`expiry` variabel dalam kode JavaScript untuk memasukkan waktu yang diinginkan, Anda dapat mengatur waktu tertentu untuk tanggal kedaluwarsa.