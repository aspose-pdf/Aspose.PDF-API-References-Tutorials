---
title: Tetapkan Font Default Dalam File PDF
linktitle: Tetapkan Font Default Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara mengatur font default dalam file PDF menggunakan Aspose.PDF untuk .NET dengan panduan langkah demi langkah ini.
type: docs
weight: 280
url: /id/net/programming-with-document/setdefaultfont/
---
Jika Anda bekerja dengan dokumen PDF di .NET, Anda mungkin mengalami masalah ketika font yang digunakan dalam PDF tidak tersedia di sistem tempat font tersebut dilihat atau dicetak. Hal ini dapat mengakibatkan teks muncul secara tidak benar atau tidak muncul sama sekali. Aspose.PDF untuk .NET memberikan solusi untuk masalah ini dengan memungkinkan Anda mengatur font default untuk dokumen. Dalam contoh ini, cara mengatur font default menggunakan Aspose.PDF untuk .NET.

## Langkah 1: Tetapkan jalur ke direktori dokumen

kita perlu mengatur jalur ke direktori tempat dokumen PDF kita berada. Kami akan menyimpan jalur ini dalam variabel bernama "dataDir".

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Muat dokumen PDF

 Kami akan mulai dengan memuat dokumen PDF yang ada yang fontnya hilang. Dalam contoh ini, kita berasumsi bahwa dokumen PDF terletak di direktori yang ditentukan oleh`dataDir` variabel.

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    // kode masuk ke sini
}
```

## Langkah 3: Atur font default

 Selanjutnya, kita akan mengatur font default untuk dokumen PDF menggunakan`PdfSaveOptions` kelas. Dalam contoh ini, kami akan menyetel font default ke "Arial".

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## Langkah 4: Simpan dokumen yang diperbarui

Terakhir, kami akan menyimpan dokumen yang diperbarui ke file baru. Dalam contoh ini, kami akan menyimpan dokumen yang diperbarui ke file bernama "output_out.pdf" di direktori yang sama dengan file input.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### Contoh Kode Sumber untuk Mengatur Font Default menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Muat dokumen PDF yang ada dengan font yang hilang
string documentName = dataDir + "input.pdf";
string newName = "Arial";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
	PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
	// Tentukan Nama Font Default
	pdfSaveOptions.DefaultFontName = newName;
	document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
}
```

## Kesimpulan

Mengatur font default dalam dokumen PDF menggunakan Aspose.PDF untuk .NET adalah cara sederhana dan efektif untuk memastikan bahwa teks ditampilkan dengan benar, meskipun font asli tidak tersedia. Dengan mengikuti panduan langkah demi langkah dan menggunakan kode sumber C# yang disediakan, pengembang dapat dengan mudah mengatur font default dan membuat PDF yang menawarkan pengalaman menonton yang konsisten dan andal di berbagai lingkungan. Fitur ini sangat berguna dalam skenario di mana PDF akan dilihat atau dicetak pada berbagai sistem yang mungkin memiliki kumpulan font berbeda yang diinstal.

### FAQ untuk mengatur font default dalam file PDF

#### T: Mengapa pengaturan font default penting dalam dokumen PDF?

J: Mengatur font default dalam dokumen PDF penting karena memastikan teks akan ditampilkan dengan benar meskipun font asli tidak tersedia di sistem tempat PDF dilihat atau dicetak. Ini membantu mencegah masalah seperti teks hilang atau kacau, memastikan pengalaman menonton yang konsisten dan andal.

#### T: Dapatkah saya memilih font apa pun sebagai font default menggunakan Aspose.PDF untuk .NET?

 A: Ya, Anda dapat memilih font apa pun yang tersedia di sistem sebagai font default menggunakan Aspose.PDF untuk .NET. Cukup tentukan nama font di`DefaultFontName` properti dari`PdfSaveOptions` kelas.

#### T: Apa yang terjadi jika font default yang ditentukan tidak tersedia di sistem?

J: Jika font default yang ditentukan tidak tersedia di sistem, penampil PDF akan menggunakan font cadangan untuk menampilkan teks. Dianjurkan untuk memilih font yang umum tersedia seperti Arial atau Times New Roman untuk memastikan kompatibilitas di berbagai sistem.