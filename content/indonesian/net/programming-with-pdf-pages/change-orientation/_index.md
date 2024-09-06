---
title: Ubah Orientasi
linktitle: Ubah Orientasi
second_title: Referensi API Aspose.PDF untuk .NET
description: Panduan langkah demi langkah untuk mengubah orientasi halaman PDF dengan Aspose.PDF untuk .NET. Mudah diikuti dan diterapkan dalam proyek Anda.
type: docs
weight: 10
url: /id/net/programming-with-pdf-pages/change-orientation/
---
Dalam tutorial ini, kami akan memandu Anda melalui proses langkah demi langkah untuk mengubah orientasi halaman dokumen PDF menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber C# yang disertakan dan memberi Anda panduan komprehensif untuk membantu Anda memahami dan menerapkan fitur ini dalam proyek Anda sendiri. Di akhir tutorial ini, Anda akan mengetahui cara mengubah orientasi halaman dokumen PDF Anda menggunakan Aspose.PDF untuk .NET.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki hal berikut:

- Pengetahuan dasar tentang bahasa pemrograman C#
- Aspose.PDF untuk .NET terinstal di lingkungan pengembangan Anda

## Langkah 1: Tentukan direktori dokumen
Pertama, Anda perlu mengatur jalur ke direktori dokumen Anda. Ini adalah lokasi tempat berkas PDF masukan Anda berada dan tempat Anda ingin menyimpan berkas PDF keluaran yang telah dimodifikasi. Ganti "DIREKTORI DOKUMEN ANDA" dengan jalur yang sesuai.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Muat dokumen PDF
 Kemudian Anda dapat memuat dokumen PDF dari file input menggunakan`Document` kelas Aspose.PDF. Pastikan untuk menentukan jalur yang benar ke berkas PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Langkah 3: Ubah orientasi halaman
Sekarang kita akan menelusuri setiap halaman dokumen dan mengubah orientasinya. Untuk setiap halaman, kita mengubah dimensi kotak media (`MediaBox`) dengan menukar lebar dan tinggi, lalu kita sesuaikan koordinat kotak media untuk mempertahankan posisi halaman. Terakhir, kita atur rotasi halaman ke 90 derajat.

```csharp
foreach(Page page in doc.Pages)
{
Aspose.Pdf.Rectangle r = page.MediaBox;
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page. Rotate = Rotate. on90;
}
```

## Langkah 4: Simpan dokumen PDF yang dimodifikasi
 Terakhir, Anda dapat menyimpan dokumen PDF yang dimodifikasi ke file keluaran menggunakan`Save()` metode dari`Document`kelas. Pastikan untuk menentukan jalur dan nama file yang benar.

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
```

### Contoh kode sumber untuk Mengubah Orientasi menggunakan Aspose.PDF untuk .NET 

```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Aspose.Pdf.Rectangle r = page.MediaBox;
	double newHeight = r.Width;
	double newWidth = r.Height;
	double newLLX = r.LLX;
	// Kita harus memindahkan halaman ke atas untuk mengimbangi perubahan ukuran halaman
	// (tepi bawah halaman adalah 0,0 dan informasi biasanya ditempatkan dari
	// Atas halaman. Itulah sebabnya kami memindahkan tepi kekasih ke atas pada perbedaan antara
	// Ketinggian lama dan baru.
	double newLLY = r.LLY + (r.Height - newHeight);
	page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Terkadang kita juga perlu mengatur CropBox (jika sudah diatur di file asli)
	page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Mengatur sudut rotasi halaman
	page.Rotate = Rotation.on90;
}
dataDir = dataDir + "ChangeOrientation_out.pdf";
// Simpan file keluaran
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);

```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara mengubah orientasi halaman dokumen PDF menggunakan Aspose.PDF untuk .NET. Dengan mengikuti langkah-langkah yang diuraikan di atas, Anda dapat dengan mudah menerapkan fungsi ini dalam proyek Anda sendiri. Jangan ragu untuk menjelajahi dokumentasi Aspose.PDF lebih lanjut untuk menemukan fitur-fitur bermanfaat lainnya untuk bekerja dengan file PDF.

### Pertanyaan yang Sering Diajukan

#### T: Apa tujuan mengubah orientasi halaman dalam dokumen PDF?

A: Mengubah orientasi halaman dalam dokumen PDF memungkinkan Anda memutar konten halaman hingga 90 derajat. Ini dapat berguna dalam skenario saat konten asli perlu ditampilkan atau dicetak dalam orientasi berbeda, seperti beralih dari mode potret ke lanskap atau sebaliknya.

#### T: Dapatkah saya mengubah orientasi halaman tertentu dalam dokumen PDF?

 A: Ya, Anda dapat mengubah orientasi halaman tertentu dalam dokumen PDF. Dalam kode sumber C# yang disediakan,`foreach` loop digunakan untuk menelusuri setiap halaman dokumen dan mengubah orientasinya. Jika Anda hanya ingin mengubah orientasi halaman tertentu, Anda dapat mengubah loop untuk menargetkan halaman tersebut berdasarkan nomor halaman atau kriteria lainnya.

#### T: Apakah mengubah orientasi halaman memengaruhi tata letak konten pada halaman?

A: Ya, mengubah orientasi halaman akan memengaruhi tata letak konten pada halaman. Konten akan diputar 90 derajat, dan lebar serta tinggi halaman akan tertukar. Akibatnya, penempatan dan perataan konten pada halaman dapat berubah.

#### T: Dapatkah saya memutar halaman pada sudut selain 90 derajat?

 A: Dalam kode sumber C# yang disediakan, rotasi halaman diatur ke 90 derajat menggunakan`page.Rotate = Rotate.on90;` . Namun, Anda dapat mengubah sudut rotasi ke nilai lain jika diperlukan. Misalnya, Anda dapat menggunakan`Rotate.on180` untuk memutar halaman sebesar 180 derajat atau`Rotate.on270` untuk memutarnya sebesar 270 derajat.

#### T: Bagaimana cara menangani konten halaman yang meluap setelah orientasi diubah?

A: Saat mengubah orientasi halaman, dimensi halaman dapat berubah, yang dapat mengakibatkan konten meluap. Untuk mengatasinya, Anda mungkin perlu menyesuaikan tata letak dan format konten pada halaman. Anda dapat menggunakan fitur yang disediakan oleh Aspose.PDF untuk .NET, seperti mengubah ukuran elemen, menyesuaikan margin, atau mengatur ulang konten, untuk memastikan bahwa konten halaman pas setelah perubahan orientasi.