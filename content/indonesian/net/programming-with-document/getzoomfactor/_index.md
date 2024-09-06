---
title: Dapatkan Faktor Zoom Dalam File PDF
linktitle: Dapatkan Faktor Zoom Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menggunakan Aspose.PDF untuk .NET untuk mendapatkan faktor zoom dalam file PDF dengan panduan langkah demi langkah ini.
type: docs
weight: 210
url: /id/net/programming-with-document/getzoomfactor/
---
Aspose.PDF untuk .NET adalah pustaka manipulasi PDF yang menyediakan banyak fitur untuk melakukan berbagai operasi pada dokumen PDF. Salah satu fitur ini adalah kemampuan untuk mendapatkan faktor zoom dalam berkas PDF. Dalam tutorial ini, kami akan menjelaskan cara menggunakan Aspose.PDF untuk .NET untuk mendapatkan faktor zoom dalam berkas PDF menggunakan kode sumber C#.


## Langkah 1: Buat objek Dokumen baru

 Langkah pertama untuk mendapatkan faktor zoom file PDF menggunakan Aspose.PDF untuk .NET adalah membuat instance baru`Document` objek. Itu`Document` Objek mewakili dokumen PDF yang dapat dimuat dari berkas atau aliran.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Membuat instance objek Dokumen baru
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");
```

 Pada kode di atas, kita telah membuat sebuah`Document` objek dengan meneruskan jalur file PDF ke konstruktor`Document` kelas. Anda perlu mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya dari direktori tempat file PDF Anda berada.

## Langkah 2: Buat objek GoToAction

 Langkah selanjutnya adalah membuat`GoToAction` objek. Sebuah`GoToAction`Objek mewakili tindakan yang menuju ke tujuan tertentu dalam dokumen PDF. Dalam kasus kami, kami ingin mendapatkan faktor zoom dari file PDF, jadi kami akan menggunakan`OpenAction` milik`Document` objek untuk mendapatkan`GoToAction` obyek.

```csharp
// Buat objek GoToAction
GoToAction action = doc.OpenAction as GoToAction;
```

 Pada kode di atas, kita telah membuat sebuah`GoToAction` objek dengan pengecoran`OpenAction` milik`Document` keberatan terhadap`GoToAction`.

## Langkah 3: Dapatkan faktor Zoom file PDF

 Langkah ketiga adalah mendapatkan faktor zoom dari file PDF. Kita bisa mendapatkan faktor zoom dari file PDF dengan mengakses`Destination` milik`GoToAction` objek dan kemudian melemparkannya ke`XYZExplicitDestination` . Itu`XYZExplicitDestination` kelas mewakili tujuan dalam dokumen PDF yang menentukan koordinat dan faktor zoom yang dituju.

```csharp
// Dapatkan faktor Zoom file PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Nilai zoom dokumen;
```

 Pada kode di atas, kita telah mengakses`Destination` milik`GoToAction` objek dan kemudian melemparkannya ke`XYZExplicitDestination` Setelah itu kita sudah mengakses`Zoom` milik`XYZExplicitDestination` objek untuk mendapatkan faktor zoom berkas PDF.

## Langkah 4: Keluarkan faktor Zoom

 Langkah terakhir adalah mengeluarkan faktor zoom dari file PDF. Kita dapat menggunakan`System.Console.WriteLine`

```csharp
// Dapatkan faktor Zoom file PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Nilai zoom dokumen;
```        

### Contoh Kode Sumber untuk Mendapatkan Faktor Zoom menggunakan Aspose.PDF untuk .NET

Berikut contoh kode sumber lengkap untuk Mendapatkan Faktor Zoom menggunakan Aspose.PDF untuk .NET:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Membuat instance objek Dokumen baru
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");

// Buat objek GoToAction
GoToAction action = doc.OpenAction as GoToAction;

// Dapatkan faktor Zoom file PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Nilai zoom dokumen;
```

## Kesimpulan

Dalam tutorial ini, kami telah menjajaki cara menggunakan Aspose.PDF untuk .NET guna memperoleh faktor pembesaran berkas PDF. Faktor pembesaran merupakan aspek penting dari dokumen PDF, karena menentukan ukuran tampilan awal saat dibuka di penampil. Dengan mengakses dan memanfaatkan faktor pembesaran, pengembang dapat menyesuaikan pengalaman tampilan bagi pengguna akhir. Aspose.PDF untuk .NET menyediakan API yang sederhana dan efektif untuk memperoleh faktor pembesaran dan informasi terkait navigasi lainnya dari dokumen PDF, yang memberdayakan pengembang untuk membangun aplikasi PDF yang kaya fitur dan interaktif.

### FAQ untuk mendapatkan faktor zoom dalam file PDF

#### T: Berapa faktor zoom dalam berkas PDF?

A: Faktor zoom dalam file PDF mengacu pada tingkat pembesaran yang diterapkan pada dokumen saat dilihat. Faktor ini menentukan ukuran tampilan awal file PDF di layar. Faktor zoom 1,0 menunjukkan ukuran sebenarnya (zoom 100%), sedangkan faktor zoom lebih besar dari 1,0 menunjukkan pembesaran, dan faktor zoom kurang dari 1,0 menunjukkan pengecilan.

#### T: Bagaimana cara menggunakan informasi faktor zoom di aplikasi saya?

J: Anda dapat menggunakan informasi faktor zoom untuk menyesuaikan ukuran tampilan awal dokumen PDF saat dibuka di penampil. Misalnya, Anda dapat mengatur faktor zoom tertentu untuk memastikan bahwa PDF ditampilkan pada ukuran tertentu atau menyesuaikan seluruh halaman dengan jendela penampil.

#### T: Dapatkah saya mengubah faktor zoom dokumen PDF secara terprogram menggunakan Aspose.PDF untuk .NET?

 A: Ya, Anda dapat mengubah faktor zoom dokumen PDF secara terprogram menggunakan Aspose.PDF untuk .NET. Anda dapat mengatur faktor zoom untuk tindakan tertentu, seperti`GoToAction` atau`GoToRemoteAction`untuk mengontrol bagaimana dokumen ditampilkan saat pengguna berinteraksi dengan tautan atau penanda.

#### T: Apakah ada cara lain untuk menavigasi ke lokasi tertentu dalam dokumen PDF menggunakan Aspose.PDF untuk .NET?

 A: Ya, Aspose.PDF untuk .NET menyediakan berbagai fitur untuk menavigasi ke lokasi tertentu dalam dokumen PDF. Selain menggunakan`GoToAction` Anda dapat menggunakan tindakan lain seperti`GoToURIAction` untuk membuka URL,`GoToEmbeddedAction` untuk menavigasi ke file yang tertanam, dan`GoToNamedAction` untuk menuju ke tujuan yang disebutkan dalam dokumen PDF.