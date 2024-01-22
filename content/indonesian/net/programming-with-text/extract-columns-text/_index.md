---
title: Ekstrak Teks Kolom Dalam File PDF
linktitle: Ekstrak Teks Kolom Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara mengekstrak teks kolom dalam file PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 150
url: /id/net/programming-with-text/extract-columns-text/
---
Tutorial ini akan memandu Anda melalui proses mengekstraksi teks kolom dalam file PDF menggunakan Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan.

## Persyaratan
Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau kompiler C# lainnya yang diinstal pada mesin Anda.
- Aspose.PDF untuk perpustakaan .NET. Anda dapat mendownloadnya dari situs resmi Aspose atau menggunakan manajer paket seperti NuGet untuk menginstalnya.

## Langkah 1: Siapkan proyek
1. Buat proyek C# baru di lingkungan pengembangan pilihan Anda.
2. Tambahkan referensi ke perpustakaan Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan
Dalam file kode tempat Anda ingin mengekstrak teks kolom, tambahkan arahan penggunaan berikut di bagian atas file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## Langkah 3: Atur direktori dokumen
 Dalam kode, temukan baris yang bertuliskan`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur ke direktori tempat dokumen Anda disimpan.

## Langkah 4: Buka dokumen PDF
 Buka dokumen PDF yang ada menggunakan`Document`konstruktor dan meneruskan jalur ke file PDF masukan.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Langkah 5: Sesuaikan ukuran font
Kurangi ukuran font fragmen teks sebanyak 0,7 kali untuk meningkatkan keterbacaan dan representasi teks kolom dengan lebih baik.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach(TextFragment tf in tfc)
{
     tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

## Langkah 6: Ekstrak teks dari kolom
 Simpan dokumen PDF yang dimodifikasi ke aliran memori dan muat ulang sebagai dokumen baru. Kemudian, gunakan`TextAbsorber` kelas untuk mengekstrak teks dari kolom.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument);
```

## Langkah 7: Simpan teks yang diekstraksi
Simpan teks yang diekstraksi ke file teks di jalur file keluaran yang ditentukan.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

### Contoh kode sumber untuk Ekstrak Teks Kolom menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");                
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach (TextFragment tf in tfc)
{
	// Perlu mengurangi ukuran font setidaknya 70%
	tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument); 
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);           
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## Kesimpulan
Anda telah berhasil mengekstrak teks kolom dari dokumen PDF menggunakan Aspose.PDF untuk .NET. Teks yang diekstraksi telah disimpan ke file keluaran yang ditentukan.

### FAQ

#### T: Apa tujuan dari tutorial ini?

J: Tutorial ini menawarkan panduan langkah demi langkah dalam mengekstraksi kolom teks dari file PDF menggunakan Aspose.PDF untuk .NET. Kode sumber C# yang menyertainya memberikan demonstrasi praktis tentang prosedur yang diperlukan.

#### T: Namespace apa yang harus saya impor?

J: Dalam file kode tempat Anda ingin mengekstrak kolom teks, sertakan arahan penggunaan berikut di awal file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### T: Bagaimana cara menentukan direktori dokumen?

 A: Temukan garisnya`string dataDir = "YOUR DOCUMENT DIRECTORY";` dalam kode dan ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

#### T: Bagaimana cara membuka dokumen PDF yang sudah ada?

 J: Pada Langkah 4, Anda akan membuka dokumen PDF yang ada menggunakan`Document` konstruktor dan menyediakan jalur ke file PDF masukan.

#### Q: Mengapa ukuran font disesuaikan?

J: Langkah 5 melibatkan pengurangan ukuran font fragmen teks sebanyak 0,7 kali. Penyesuaian ini meningkatkan keterbacaan dan merepresentasikan teks kolom dengan lebih akurat.

#### T: Bagaimana cara mengekstrak teks dari kolom?

 J: Langkah 6 terdiri dari menyimpan dokumen PDF yang dimodifikasi ke aliran memori, memuatnya kembali sebagai dokumen baru, dan kemudian menggunakan`TextAbsorber` kelas untuk mengekstrak teks dari kolom.

#### Q: Apa tujuan menyimpan teks yang diekstraksi?

J: Pada Langkah 7, Anda akan menyimpan teks yang diekstrak ke file teks di jalur file keluaran yang ditentukan.

#### T: Mengapa mengurangi ukuran font sebelum ekstraksi?

J: Mengurangi ukuran font membantu memastikan bahwa teks yang diekstraksi sejajar dengan kolom, memberikan representasi tata letak asli yang lebih akurat.

#### T: Apa inti dari tutorial ini?

J: Dengan mengikuti tutorial ini, Anda memperoleh pengetahuan dan keterampilan yang diperlukan untuk mengekstrak kolom teks dari dokumen PDF menggunakan Aspose.PDF untuk .NET. Teks yang dihasilkan telah disimpan ke file keluaran yang ditentukan.