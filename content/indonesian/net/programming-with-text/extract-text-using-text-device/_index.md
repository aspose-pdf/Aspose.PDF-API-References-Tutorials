---
title: Ekstrak Teks Menggunakan Perangkat Teks
linktitle: Ekstrak Teks Menggunakan Perangkat Teks
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mengekstrak teks dari dokumen PDF menggunakan Perangkat Teks di Aspose.PDF untuk .NET.
type: docs
weight: 210
url: /id/net/programming-with-text/extract-text-using-text-device/
---
Tutorial ini akan memandu Anda melalui proses mengekstraksi teks dari dokumen PDF menggunakan Text Device di Aspose.PDF for .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan.

## Persyaratan
Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau kompiler C# lainnya terinstal di komputer Anda.
- Aspose.PDF untuk pustaka .NET. Anda dapat mengunduhnya dari situs web resmi Aspose atau menggunakan pengelola paket seperti NuGet untuk menginstalnya.

## Langkah 1: Siapkan proyek
1. Buat proyek C# baru di lingkungan pengembangan pilihan Anda.
2. Tambahkan referensi ke pustaka Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan
Pada berkas kode tempat Anda ingin mengekstrak teks, tambahkan perintah penggunaan berikut di bagian atas berkas:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## Langkah 3: Mengatur direktori dokumen
 Dalam kode, temukan baris yang bertuliskan`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur ke direktori tempat dokumen Anda disimpan.

## Langkah 4: Buka dokumen PDF
 Buka dokumen PDF yang ada menggunakan`Document` konstruktor dan meneruskan jalur ke berkas PDF masukan.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Langkah 5: Ekstrak teks menggunakan Perangkat Teks
 Membuat sebuah`StringBuilder` objek untuk menampung teks yang diekstrak. Ulangi setiap halaman dokumen dan gunakan`TextDevice` untuk mengekstrak teks dari setiap halaman.

```csharp
StringBuilder builder = new StringBuilder();
string extractedText = "";
foreach(Page pdfPage in pdfDocument.Pages)
{
using (MemoryStream textStream = new MemoryStream())
{
TextDevice textDevice = new TextDevice();
TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
textDevice.ExtractionOptions = textExtOptions;
textDevice.Process(pdfPage, textStream);
textStream. Close();
extractedText = Encoding.Unicode.GetString(textStream.ToArray());
}
builder. Append(extractedText);
}
```

## Langkah 6: Simpan teks yang diekstrak
 Tentukan jalur file keluaran dan simpan teks yang diekstrak ke file teks menggunakan`File.WriteAllText` metode.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### Contoh kode sumber untuk Ekstrak Teks Menggunakan Perangkat Teks menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
//String untuk menampung teks yang diekstraksi
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		// Buat perangkat teks
		TextDevice textDevice = new TextDevice();
		// Mengatur opsi ekstraksi teks - mengatur mode ekstraksi teks (Mentah atau Murni)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// Konversi halaman tertentu dan simpan teks ke aliran
		textDevice.Process(pdfPage, textStream);
		// Konversi halaman tertentu dan simpan teks ke aliran
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// Tutup aliran memori
		textStream.Close();
		// Dapatkan teks dari aliran memori
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
// Simpan teks yang diekstrak dalam file teks
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## Kesimpulan
Anda telah berhasil mengekstrak teks dari dokumen PDF menggunakan Text Device di Aspose.PDF for .NET. Teks yang diekstrak telah disimpan ke berkas keluaran yang ditentukan.

### Pertanyaan yang Sering Diajukan

#### T: Apa tujuan dari tutorial ini?

J: Tutorial ini menyediakan panduan tentang cara mengekstrak teks dari dokumen PDF menggunakan fitur Text Device di Aspose.PDF untuk .NET. Kode sumber C# yang disertakan menunjukkan langkah-langkah yang diperlukan untuk mencapai tugas ini.

#### T: Namespace apa yang harus saya impor?

A: Pada berkas kode tempat Anda berencana mengekstrak teks, sertakan perintah penggunaan berikut di awal berkas:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### T: Bagaimana cara menentukan direktori dokumen?

 A: Dalam kode tersebut, temukan baris yang bertuliskan`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

#### T: Bagaimana cara membuka dokumen PDF yang sudah ada?

 A: Pada Langkah 4, Anda akan membuka dokumen PDF yang ada menggunakan`Document` konstruktor dan menyediakan jalur ke berkas PDF masukan.

#### T: Bagaimana cara mengekstrak teks menggunakan Perangkat Teks?

 A: Langkah 5 melibatkan pembuatan`StringBuilder` objek untuk menampung teks yang diekstrak. Anda kemudian akan mengulangi setiap halaman dokumen dan menggunakan`TextDevice` bersama dengan`TextExtractionOptions` untuk mengekstrak teks dari setiap halaman.

#### T: Bagaimana cara menyimpan teks yang diekstrak ke dalam berkas?

 A: Pada Langkah 6, Anda akan menentukan jalur file keluaran dan menggunakan`File.WriteAllText`metode untuk menyimpan teks yang diekstrak ke dalam berkas teks.

#### T: Apa inti sari dari tutorial ini?

J: Dengan mengikuti tutorial ini, Anda telah mempelajari cara memanfaatkan fitur Text Device di Aspose.PDF for .NET untuk mengekstrak teks dari dokumen PDF. Teks yang diekstrak telah disimpan ke file keluaran tertentu, sehingga Anda dapat memanipulasi dan memanfaatkan konten yang diekstrak sesuai kebutuhan.