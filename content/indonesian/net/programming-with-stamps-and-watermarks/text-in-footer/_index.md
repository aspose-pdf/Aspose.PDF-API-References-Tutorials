---
title: Teks di Footer File PDF
linktitle: Teks di Footer File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menambahkan teks di footer file PDF dengan Aspose.PDF untuk .NET.
type: docs
weight: 180
url: /id/net/programming-with-stamps-and-watermarks/text-in-footer/
---
Dalam tutorial ini, kita akan mempelajari cara menambahkan teks di footer file PDF menggunakan Aspose.PDF untuk .NET. Ikuti langkah-langkah di bawah ini:

## Langkah 1: Persiapan proyek

Pastikan Anda telah menginstal Aspose.PDF untuk .NET dan membuat proyek C#.

## Langkah 2: Mengimpor namespace

Tambahkan namespace berikut ke file sumber C# Anda:

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

Telusuri semua halaman dokumen PDF dan tambahkan stempel teks di footer:

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

// Buat catatan kaki
TextStamp textStamp = new TextStamp("Footer Text");

// Mengatur properti stempel
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

Selamat! Anda telah mempelajari cara menambahkan teks di footer dokumen PDF menggunakan Aspose.PDF untuk .NET. Anda sekarang dapat menyesuaikan footer Anda dengan menambahkan teks tambahan ke dokumen PDF Anda.

### FAQ untuk teks di footer file PDF

#### Q: Apa tujuan menambahkan teks di footer dokumen PDF?

J: Menambahkan teks di footer dokumen PDF memungkinkan Anda memasukkan informasi penting, seperti pemberitahuan hak cipta, nomor halaman, versi dokumen, atau teks lain yang ingin Anda tampilkan secara konsisten di bagian bawah setiap halaman.

#### T: Bagaimana kode sumber C# yang disediakan dapat menambahkan teks di footer dokumen PDF?

J: Kode ini menunjukkan proses membuka dokumen PDF yang ada, membuat stempel teks dengan teks footer yang diinginkan, menyesuaikan properti teks, menambahkan stempel teks ke semua halaman, dan terakhir menyimpan dokumen PDF yang diperbarui dengan teks footer yang ditambahkan.

#### T: Dapatkah saya mengubah tampilan teks footer, seperti font, ukuran, warna, dan perataannya?

 J: Ya, Anda dapat menyesuaikan tampilan teks footer dengan memodifikasi properti`TextStamp` obyek. Contoh kode mencakup pengaturan properti seperti margin bawah, perataan horizontal, dan perataan vertikal. Anda juga dapat menyesuaikan font, ukuran, warna, dan properti terkait teks lainnya.

#### T: Apakah mungkin untuk menambahkan teks berbeda ke footer setiap halaman?

 J: Ya, Anda dapat menambahkan teks berbeda ke footer setiap halaman dengan membuatnya terpisah`TextStamp` objek dengan konten teks atau properti berbeda dan kemudian menambahkannya ke halaman tertentu sesuai kebutuhan.

#### T: Bagaimana cara memastikan teks footer muncul secara konsisten di setiap halaman dokumen PDF?

J: Dengan menggunakan loop yang mengulangi seluruh halaman dokumen PDF dan menambahkan stempel teks yang sama ke setiap halaman, Anda memastikan bahwa teks footer muncul secara konsisten di setiap halaman.

#### T: Dapatkah saya menambahkan beberapa baris teks atau memformat teks footer dengan jeda baris?

 J: Ya, Anda dapat menambahkan beberapa baris teks ke footer dengan menyertakan jeda baris dalam string teks. Misalnya, Anda dapat menggunakan urutan escape`\n` untuk menunjukkan jeda baris dalam teks.

#### T: Apa yang terjadi jika saya ingin menambahkan konten berbeda ke header dan footer dokumen PDF yang sama?

J: Untuk menambahkan konten berbeda ke bagian header dan footer, Anda dapat mengikuti langkah serupa untuk kedua bagian. Kode ini menunjukkan penambahan teks ke footer; Anda dapat menggunakan pendekatan serupa untuk menambahkan teks ke header.

#### T: Apakah mungkin menambahkan gambar atau elemen lain di samping teks footer menggunakan pendekatan ini?

J: Meskipun kode yang diberikan secara khusus menunjukkan penambahan teks ke footer, Anda dapat memperluas pendekatan untuk menambahkan elemen lain seperti gambar, garis, bentuk, atau konten lainnya ke bagian footer menggunakan pustaka Aspose.PDF.