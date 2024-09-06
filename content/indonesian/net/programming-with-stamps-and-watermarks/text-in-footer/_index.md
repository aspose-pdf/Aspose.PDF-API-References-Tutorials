---
title: Teks Di Footer File PDF
linktitle: Teks Di Footer File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menambahkan teks di footer file PDF dengan Aspose.PDF untuk .NET.
type: docs
weight: 180
url: /id/net/programming-with-stamps-and-watermarks/text-in-footer/
---
Dalam tutorial ini, kita akan mempelajari cara menambahkan teks di bagian bawah berkas PDF menggunakan Aspose.PDF untuk .NET. Ikuti langkah-langkah berikut:

## Langkah 1: Persiapan proyek

Pastikan Anda telah menginstal Aspose.PDF untuk .NET dan membuat proyek C#.

## Langkah 2: Mengimpor namespace

Tambahkan namespace berikut ke berkas sumber C# Anda:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Langkah 3: Membuka dokumen

Buka dokumen PDF yang ada menggunakan jalur yang disediakan:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document pdfDocument = new Document(dataDir + "TextinFooter.pdf");
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 4: Buat teks footer

Buat stempel teks baru dengan teks yang ingin Anda tambahkan di footer:

```csharp
TextStamp textStamp = new TextStamp("footer text");
```

Anda dapat menyesuaikan teks dengan mengubah propertinya seperti margin bawah, perataan horizontal, dan perataan vertikal.

## Langkah 5: Tambahkan teks footer ke semua halaman

Telusuri semua halaman dokumen PDF dan tambahkan stempel teks di bagian bawah:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## Langkah 6: Menyimpan Dokumen PDF

Setelah teks footer ditambahkan di semua halaman, simpan dokumen PDF yang diperbarui:

```csharp
dataDir = dataDir + "TextinFooter_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at: " + dataDir);
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori tempat Anda ingin menyimpan dokumen PDF.

### Contoh kode sumber untuk Textin Footer menggunakan Aspose.PDF untuk .NET 
```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buka dokumen
Document pdfDocument = new Document(dataDir+ "TextinFooter.pdf");

// Buat footer
TextStamp textStamp = new TextStamp("Footer Text");

// Mengatur properti prangko
textStamp.BottomMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Tambahkan footer di semua halaman
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}
dataDir = dataDir + "TextinFooter_out.pdf";

// Simpan file PDF yang diperbarui
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at " + dataDir);

```

## Kesimpulan

Selamat! Anda telah mempelajari cara menambahkan teks di bagian bawah dokumen PDF menggunakan Aspose.PDF untuk .NET. Kini Anda dapat menyesuaikan bagian bawah dengan menambahkan teks tambahan ke dokumen PDF Anda.

### FAQ untuk teks di bagian bawah file PDF

#### T: Apa tujuan menambahkan teks di footer dokumen PDF?

A: Menambahkan teks di footer dokumen PDF memungkinkan Anda menyertakan informasi penting, seperti pemberitahuan hak cipta, nomor halaman, versi dokumen, atau teks lain yang ingin Anda munculkan secara konsisten di bagian bawah setiap halaman.

#### T: Bagaimana kode sumber C# yang disediakan mencapai penambahan teks di footer dokumen PDF?

A: Kode ini menunjukkan proses membuka dokumen PDF yang sudah ada, membuat stempel teks dengan teks footer yang diinginkan, menyesuaikan properti teks, menambahkan stempel teks ke semua halaman, dan akhirnya menyimpan dokumen PDF yang diperbarui dengan teks footer yang ditambahkan.

#### T: Dapatkah saya mengubah tampilan teks footer, seperti font, ukuran, warna, dan perataannya?

 A: Ya, Anda dapat menyesuaikan tampilan teks footer dengan mengubah properti`TextStamp` objek. Contoh kode tersebut mencakup pengaturan properti seperti margin bawah, perataan horizontal, dan perataan vertikal. Anda juga dapat menyesuaikan font, ukuran, warna, dan properti terkait teks lainnya.

#### T: Apakah mungkin untuk menambahkan teks yang berbeda pada footer setiap halaman?

 A: Ya, Anda dapat menambahkan teks yang berbeda ke footer setiap halaman dengan membuat footer terpisah.`TextStamp` objek dengan konten teks atau properti yang berbeda, lalu menambahkannya ke halaman tertentu sesuai kebutuhan.

#### T: Bagaimana cara memastikan teks footer muncul secara konsisten di setiap halaman dokumen PDF?

A: Dengan menggunakan loop yang berulang melalui semua halaman dokumen PDF dan menambahkan stempel teks yang sama ke setiap halaman, Anda memastikan bahwa teks footer muncul secara konsisten di setiap halaman.

#### T: Dapatkah saya menambahkan beberapa baris teks atau memformat teks footer dengan jeda baris?

 A: Ya, Anda dapat menambahkan beberapa baris teks ke footer dengan menyertakan jeda baris dalam string teks. Misalnya, Anda dapat menggunakan escape sequence`\n` untuk menunjukkan jeda baris pada teks.

#### T: Apa yang terjadi jika saya ingin menambahkan konten yang berbeda ke header dan footer dokumen PDF yang sama?

J: Untuk menambahkan konten yang berbeda ke bagian header dan footer, Anda akan mengikuti langkah-langkah yang sama untuk kedua bagian tersebut. Kode tersebut menunjukkan cara menambahkan teks ke footer; Anda dapat menggunakan pendekatan yang sama untuk menambahkan teks ke header.

#### T: Apakah mungkin untuk menambahkan gambar atau elemen lain di samping teks footer menggunakan pendekatan ini?

A: Sementara kode yang diberikan secara khusus menunjukkan penambahan teks ke footer, Anda dapat memperluas pendekatan untuk menambahkan elemen lain seperti gambar, garis, bentuk, atau konten lainnya ke bagian footer menggunakan pustaka Aspose.PDF.