---
title: Tambahkan Skrip Java ke File PDF
linktitle: Tambahkan File PDF Skrip Java
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menambahkan JavaScript ke file PDF menggunakan Aspose.PDF untuk .NET. Panduan langkah demi langkah dengan tutorial kode untuk pembuatan skrip tingkat dokumen dan halaman.
type: docs
weight: 10
url: /id/net/programming-with-document/addjavascripttopage/
---
Untuk menambahkan JavaScript ke file PDF, kami akan menggunakan Aspose.PDF untuk .NET. Perpustakaan ini menyediakan cara sederhana dan efisien untuk bekerja dengan file PDF di aplikasi .NET. Langkah-langkah berikut akan memandu Anda melalui proses menambahkan JavaScript ke file PDF menggunakan Aspose.PDF untuk .NET.

## Langkah 1: Muat File PDF

 Langkah pertama adalah memuat file PDF yang ingin Anda tambahkan JavaScript. Anda dapat melakukan ini menggunakan`Document` kelas yang disediakan oleh Aspose.PDF untuk .NET. Itu`Document` kelas menyediakan metode untuk memuat, menyimpan, dan memanipulasi file PDF.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Muat file PDF yang ada
Document doc = new Document(dataDir + "input.pdf");
```

## Langkah 2: Tambahkan JavaScript di Tingkat Dokumen

Untuk menambahkan JavaScript pada tingkat dokumen, kita akan menggunakan`JavascriptAction` kelas yang disediakan oleh Aspose.PDF untuk .NET. Kelas ini memungkinkan Anda menentukan pernyataan JavaScript yang ingin Anda tambahkan ke file PDF.

```csharp
// Menambahkan JavaScript di Tingkat Dokumen
// Buat instance JavascriptAction dengan pernyataan JavaScript yang diinginkan
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Tetapkan objek JavascriptAction ke tindakan Dokumen yang diinginkan
doc.OpenAction = javaScript;
```

Dalam tutorial ini, kami menambahkan pernyataan JavaScript yang akan mencetak file PDF dengan opsi yang ditentukan saat dokumen dibuka.

## Langkah 3: Tambahkan JavaScript di Tingkat Halaman

 Untuk menambahkan JavaScript di tingkat halaman, kita akan menggunakan`JavascriptAction` kelas dan`Actions` properti yang disediakan oleh Aspose.PDF untuk .NET. Properti ini memungkinkan Anda menentukan pernyataan JavaScript yang akan dieksekusi saat halaman dibuka atau ditutup.

```csharp
// Menambahkan JavaScript di Tingkat Halaman
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");
```

Dalam tutorial ini, kami menambahkan pernyataan JavaScript yang akan menampilkan pesan peringatan ketika halaman dibuka atau ditutup.

## Langkah 4: Simpan File PDF

Setelah Anda menambahkan JavaScript ke file PDF, Anda perlu menyimpan file yang dimodifikasi. Anda dapat melakukan ini menggunakan`Save` metode yang disediakan oleh`Document` kelas.

```csharp
dataDir = dataDir + "JavaScript-Added_out.pdf";
// Simpan Dokumen PDF
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);
```

Kode ini akan menyimpan file PDF yang dimodifikasi ke direktori yang ditentukan.

### Contoh kode sumber untuk Menambahkan Java Script Ke Halaman menggunakan Aspose.PDF untuk .NET

```csharp
            
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Muat file PDF yang ada
Document doc = new Document(dataDir + "input.pdf");

// Menambahkan JavaScript di Tingkat Dokumen
// Buat instance JavascriptAction dengan pernyataan JavaScript yang diinginkan
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Tetapkan objek JavascriptAction ke tindakan Dokumen yang diinginkan
doc.OpenAction = javaScript;

// Menambahkan JavaScript di Tingkat Halaman
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");

dataDir = dataDir + "JavaScript-Added_out.pdf";
// Simpan Dokumen PDF
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);     
```

## Kesimpulan

Pada artikel ini, kami telah menjelaskan cara menambahkan JavaScript ke file PDF di tingkat dokumen dan tingkat halaman menggunakan Aspose.PDF untuk .NET. Kami telah memberikan petunjuk langkah demi langkah dan menyertakan kode sumber lengkap untuk setiap contoh. Dengan pengetahuan ini, Anda dapat menambahkan JavaScript ke file PDF Anda dan menyesuaikan perilakunya sesuai kebutuhan Anda.


### FAQ untuk menambahkan skrip java ke file PDF

#### T: Apa itu Aspose.PDF untuk .NET?

J: Aspose.PDF untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang bekerja dengan file PDF di aplikasi .NET. Ini menyediakan berbagai fitur untuk membuat, memodifikasi, dan memanipulasi dokumen PDF.

#### T: Dapatkah saya menambahkan JavaScript ke dokumen PDF menggunakan Aspose.PDF untuk .NET?

J: Ya, Aspose.PDF untuk .NET memungkinkan Anda menambahkan JavaScript ke tingkat dokumen dan tingkat halaman file PDF, sehingga memungkinkan Anda membuat dokumen PDF yang dinamis dan interaktif.

#### T: Bagaimana cara memuat file PDF yang sudah ada menggunakan Aspose.PDF untuk .NET?

 J: Anda dapat memuat file PDF yang sudah ada menggunakan`Document` kelas dan metodenya, seperti yang ditunjukkan dalam panduan langkah demi langkah.

#### T: Jenis tindakan JavaScript apa yang dapat saya tambahkan ke dokumen PDF?

J: Dengan Aspose.PDF untuk .NET, Anda dapat menambahkan beragam tindakan JavaScript, seperti pencetakan, pesan peringatan, manipulasi bidang formulir, dan banyak lagi.

#### T: Apakah Aspose.PDF untuk .NET cocok untuk proyek komersial?

J: Ya, Aspose.PDF untuk .NET adalah pustaka yang andal dan tangguh yang biasa digunakan dalam proyek komersial untuk manipulasi dan tugas pembuatan PDF.

