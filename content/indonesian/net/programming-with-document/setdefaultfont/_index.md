---
title: Mengatur Font Default Dalam File PDF
linktitle: Mengatur Font Default Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mengatur font default dalam file PDF menggunakan Aspose.PDF untuk .NET dengan panduan langkah demi langkah ini.
type: docs
weight: 280
url: /id/net/programming-with-document/setdefaultfont/
---
Jika Anda bekerja dengan dokumen PDF dalam format .NET, Anda mungkin mengalami masalah ketika font yang digunakan dalam PDF tidak tersedia di sistem tempat dokumen tersebut dilihat atau dicetak. Hal ini dapat mengakibatkan teks tidak muncul dengan benar atau tidak muncul sama sekali. Aspose.PDF untuk .NET menyediakan solusi untuk masalah ini dengan memungkinkan Anda menyetel font default untuk dokumen tersebut. Dalam contoh ini, cara menyetel font default menggunakan Aspose.PDF untuk .NET.

## Langkah 1: Tetapkan jalur ke direktori dokumen

kita perlu mengatur jalur ke direktori tempat dokumen PDF kita berada. Kita akan menyimpan jalur ini dalam variabel yang disebut "dataDir".

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Muat dokumen PDF

 Kita akan mulai dengan memuat dokumen PDF yang sudah ada yang font-nya hilang. Dalam contoh ini, kita akan berasumsi bahwa dokumen PDF tersebut berada di direktori yang ditentukan oleh`dataDir` variabel.

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    // kode ada di sini
}
```

## Langkah 3: Mengatur font default

 Selanjutnya, kita akan mengatur font default untuk dokumen PDF menggunakan`PdfSaveOptions`kelas. Dalam contoh ini, kita akan menetapkan font default ke "Arial".

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## Langkah 4: Simpan dokumen yang diperbarui

Terakhir, kita akan menyimpan dokumen yang telah diperbarui ke file baru. Dalam contoh ini, kita akan menyimpan dokumen yang telah diperbarui ke file bernama "output_out.pdf" di direktori yang sama dengan file input.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### Contoh Kode Sumber untuk Mengatur Font Default menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Memuat dokumen PDF yang ada dengan font yang hilang
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

Menetapkan fon default dalam dokumen PDF menggunakan Aspose.PDF untuk .NET merupakan cara yang sederhana dan efektif untuk memastikan bahwa teks ditampilkan dengan benar, meskipun fon asli tidak tersedia. Dengan mengikuti panduan langkah demi langkah dan menggunakan kode sumber C# yang disediakan, pengembang dapat dengan mudah menetapkan fon default dan membuat PDF yang menawarkan pengalaman tampilan yang konsisten dan andal di berbagai lingkungan. Fitur ini khususnya berguna dalam skenario di mana PDF akan dilihat atau dicetak pada berbagai sistem yang mungkin memiliki set fon yang berbeda.

### FAQ untuk mengatur font default dalam file PDF

#### T: Mengapa pengaturan font default penting dalam dokumen PDF?

J: Menetapkan font default dalam dokumen PDF penting karena memastikan bahwa teks akan ditampilkan dengan benar meskipun font asli tidak tersedia pada sistem tempat PDF dilihat atau dicetak. Ini membantu mencegah masalah seperti teks yang hilang atau tidak jelas, memastikan pengalaman menonton yang konsisten dan andal.

#### T: Dapatkah saya memilih font apa pun sebagai font default menggunakan Aspose.PDF untuk .NET?

 A: Ya, Anda dapat memilih font apa pun yang tersedia di sistem sebagai font default menggunakan Aspose.PDF untuk .NET. Cukup tentukan nama font di`DefaultFontName` milik`PdfSaveOptions` kelas.

#### T: Apa yang terjadi jika font default yang ditentukan tidak tersedia pada sistem?

J: Jika font default yang ditentukan tidak tersedia di sistem, penampil PDF akan menggunakan font cadangan untuk menampilkan teks. Sebaiknya pilih font yang umum digunakan seperti Arial atau Times New Roman untuk memastikan kompatibilitas di berbagai sistem.