---
title: Dapatkan Faktor Zoom Dalam File PDF
linktitle: Dapatkan Faktor Zoom Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menggunakan Aspose.PDF untuk .NET untuk mendapatkan faktor zoom dalam file PDF dengan panduan langkah demi langkah ini.
type: docs
weight: 210
url: /id/net/programming-with-document/getzoomfactor/
---
Aspose.PDF for .NET adalah perpustakaan manipulasi PDF yang menyediakan banyak fitur untuk melakukan berbagai operasi pada dokumen PDF. Salah satu fitur tersebut adalah kemampuan untuk mendapatkan faktor zoom dalam file PDF. Dalam tutorial ini, kami akan menjelaskan cara menggunakan Aspose.PDF untuk .NET untuk mendapatkan faktor zoom dalam file PDF menggunakan kode sumber C#.


## Langkah 1: Buat instance objek Dokumen baru

 Langkah pertama untuk mendapatkan faktor zoom file PDF menggunakan Aspose.PDF untuk .NET adalah membuat instance yang baru`Document` obyek. Itu`Document` objek mewakili dokumen PDF yang dapat dimuat dari file atau aliran.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat instance objek Dokumen baru
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");
```

 Dalam kode di atas, kita telah membuat a`Document` objek dengan meneruskan jalur file PDF ke konstruktor`Document` kelas. Anda perlu mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya dari direktori tempat file PDF Anda berada.

## Langkah 2: Buat objek GoToAction

 Langkah selanjutnya adalah membuat a`GoToAction` obyek. A`GoToAction`objek mewakili tindakan yang menuju ke tujuan tertentu dalam dokumen PDF. Dalam kasus kami, kami ingin mendapatkan faktor zoom file PDF, jadi kami akan menggunakan`OpenAction` properti dari`Document` objek untuk mendapatkan`GoToAction` obyek.

```csharp
// Buat objek GoToAction
GoToAction action = doc.OpenAction as GoToAction;
```

 Dalam kode di atas, kita telah membuat a`GoToAction` objek dengan melemparkannya`OpenAction` properti dari`Document` objek untuk`GoToAction`.

## Langkah 3: Dapatkan faktor Zoom file PDF

 Langkah ketiga adalah mendapatkan faktor zoom file PDF. Kita bisa mendapatkan faktor zoom file PDF dengan mengakses`Destination` properti dari`GoToAction` objek dan kemudian melemparkannya ke`XYZExplicitDestination` . Itu`XYZExplicitDestination` kelas mewakili tujuan dalam dokumen PDF yang menentukan koordinat dan faktor zoom yang akan dituju.

```csharp
// Dapatkan faktor Zoom file PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Nilai pembesaran dokumen;
```

 Dalam kode di atas, kita telah mengakses`Destination` properti dari`GoToAction` objek dan kemudian melemparkannya ke`XYZExplicitDestination` . Setelah itu, kami telah mengakses`Zoom` properti dari`XYZExplicitDestination` objek untuk mendapatkan faktor zoom file PDF.

## Langkah 4: Keluarkan faktor Zoom

 Langkah terakhir adalah menampilkan faktor zoom file PDF. Kita bisa menggunakan`System.Console.WriteLine`

```csharp
// Dapatkan faktor Zoom file PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Nilai pembesaran dokumen;
```        

### Contoh Kode Sumber untuk Mendapatkan Faktor Zoom menggunakan Aspose.PDF untuk .NET

Berikut contoh lengkap kode sumber Get Zoom Factor menggunakan Aspose.PDF untuk .NET:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat instance objek Dokumen baru
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");

// Buat objek GoToAction
GoToAction action = doc.OpenAction as GoToAction;

// Dapatkan faktor Zoom file PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Nilai pembesaran dokumen;
```

## Kesimpulan

Dalam tutorial ini, kita telah menjelajahi cara menggunakan Aspose.PDF untuk .NET untuk mendapatkan faktor zoom file PDF. Faktor zoom adalah aspek penting dari dokumen PDF, karena menentukan ukuran tampilan awal saat dibuka di penampil. Dengan mengakses dan memanfaatkan faktor zoom, pengembang dapat menyesuaikan pengalaman menonton bagi pengguna akhir. Aspose.PDF untuk .NET menyediakan API sederhana dan efektif untuk mengambil faktor zoom dan informasi terkait navigasi lainnya dari dokumen PDF, memberdayakan pengembang untuk membangun aplikasi PDF yang kaya fitur dan interaktif.

### FAQ untuk mendapatkan faktor zoom dalam file PDF

#### Q: Apa faktor zoom pada file PDF?

J: Faktor zoom dalam file PDF mengacu pada tingkat pembesaran yang diterapkan pada dokumen saat dilihat. Ini menentukan ukuran tampilan awal file PDF di layar. Faktor zoom 1,0 menunjukkan ukuran sebenarnya (zoom 100%), sedangkan faktor zoom lebih besar dari 1,0 menunjukkan pembesaran, dan faktor zoom kurang dari 1,0 menunjukkan pengecilan.

#### T: Bagaimana cara menggunakan informasi faktor zoom di aplikasi saya?

J: Anda dapat menggunakan informasi faktor zoom untuk menyesuaikan ukuran tampilan awal dokumen PDF saat dibuka di penampil. Misalnya, Anda dapat mengatur faktor zoom tertentu untuk memastikan bahwa PDF ditampilkan pada ukuran tertentu atau menyesuaikan seluruh halaman dengan jendela penampil.

#### T: Bisakah saya mengubah faktor zoom dokumen PDF secara terprogram menggunakan Aspose.PDF untuk .NET?

 J: Ya, Anda dapat mengubah faktor zoom dokumen PDF secara terprogram menggunakan Aspose.PDF untuk .NET. Anda dapat mengatur faktor zoom untuk tindakan tertentu, misalnya`GoToAction` atau`GoToRemoteAction`untuk mengontrol bagaimana dokumen ditampilkan saat pengguna berinteraksi dengan tautan atau bookmark.

#### T: Apakah ada cara lain untuk menavigasi ke lokasi tertentu dalam dokumen PDF menggunakan Aspose.PDF untuk .NET?

 J: Ya, Aspose.PDF untuk .NET menyediakan berbagai fitur untuk menavigasi ke lokasi tertentu dalam dokumen PDF. Selain menggunakan`GoToAction` , Anda dapat menggunakan tindakan lain seperti`GoToURIAction` untuk membuka URL,`GoToEmbeddedAction` untuk menavigasi ke file yang disematkan, dan`GoToNamedAction` untuk pergi ke tujuan yang disebutkan dalam dokumen PDF.