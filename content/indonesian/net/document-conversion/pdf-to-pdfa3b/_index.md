---
title: PDF Ke PDFA3b
linktitle: PDF Ke PDFA3b
second_title: Aspose.PDF untuk Referensi .NET API
description: Panduan langkah demi langkah untuk mengonversi PDF ke PDF/A-3b menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 150
url: /id/net/document-conversion/pdf-to-pdfa3b/
---
Dalam tutorial ini, kami akan memandu Anda melalui proses mengonversi file PDF ke format PDF/A-3b menggunakan Aspose.PDF untuk .NET. PDF/A-3b adalah standar ISO untuk menyematkan file dan data dalam dokumen PDF. Dengan mengikuti langkah-langkah di bawah ini, Anda akan dapat mengonversi file PDF ke format PDF/A-3b.

## Prasyarat
Sebelum memulai, pastikan Anda memenuhi prasyarat berikut:

- Pengetahuan dasar tentang bahasa pemrograman C#.
- Pustaka Aspose.PDF untuk .NET diinstal di sistem Anda.
- Lingkungan pengembangan seperti Visual Studio.

## Langkah 1: Membuka dokumen PDF sumber
Pada langkah ini, kita akan membuka file PDF sumber menggunakan Aspose.PDF untuk .NET. Ikuti kode di bawah ini:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Buka dokumen PDF sumber
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Pastikan untuk mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan direktori sebenarnya tempat file PDF Anda berada.

## Langkah 2: Konversikan ke PDF/A-3b
Setelah membuka file PDF, kita dapat melanjutkan dengan konversi ke format PDF/A-3b. Gunakan kode berikut:

```csharp
// Konversikan ke format PDF/A-3b
pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);
```

Kode di atas mengonversi file PDF ke format PDF/A-3b dan menghilangkan kesalahan konversi apa pun.

## Langkah 3: Menyimpan file PDF/A-3b yang dihasilkan
Setelah konversi selesai, kita perlu menyimpan file PDF/A-3b yang dihasilkan. Inilah langkah terakhir:

```csharp
dataDir = dataDir + "PDFToPDFA3b_out.pdf";
// Simpan dokumen keluaran
pdfDocument.Save(dataDir);
```

 Mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan direktori yang diinginkan tempat Anda ingin menyimpan file PDF/A-3b keluaran.

### Contoh kode sumber untuk PDF ke PDFA3b menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buka dokumen
Document pdfDocument = new Document(dataDir + "input.pdf");            

pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);

dataDir = dataDir + "PDFToPDFA3b_out.pdf";
// Simpan dokumen keluaran
pdfDocument.Save(dataDir);

Console.WriteLine("\nPDF file converted to PDF/A-3B format.\nFile saved at " + dataDir);
```

## Kesimpulan
Dalam tutorial ini, kami membahas proses langkah demi langkah mengonversi file PDF ke format PDF/A-3b menggunakan Aspose.PDF untuk .NET. Dengan mengikuti petunjuk yang diuraikan di atas, Anda sekarang dapat mengonversi file PDF ke format PDF/A-3b. Fitur ini berguna ketika Anda ingin menyematkan file dan data tambahan ke dalam dokumen PDF yang sesuai dengan standar PDF/A-3b.

### FAQ

#### T: Apa itu PDF/A-3b, dan apa bedanya dengan standar PDF/A lainnya?

J: PDF/A-3b adalah standar ISO yang memungkinkan untuk menyematkan file dan data ke dalam dokumen PDF, menjadikannya mandiri dan memastikan pelestarian jangka panjang. Tidak seperti standar PDF/A lainnya, seperti PDF/A-1 dan PDF/A-2, PDF/A-3b memungkinkan penyertaan file dan data tambahan dalam dokumen PDF. Fitur ini membuatnya cocok untuk pengarsipan dan pertukaran dokumen yang kompleks dan interaktif.

#### T: Bisakah saya menyertakan banyak file dan data dalam dokumen PDF/A-3b?

J: Ya, salah satu keunggulan utama PDF/A-3b adalah kemampuannya untuk memasukkan banyak file dan data ke dalam dokumen PDF. Anda dapat menyematkan berbagai jenis file, seperti XML, spreadsheet, gambar, atau file PDF lainnya, beserta konten PDF utama. Hasilnya, dokumen PDF/A-3b menjadi paket mandiri yang berisi semua elemen yang diperlukan.

#### Q: Apa yang terjadi jika terjadi kesalahan pada proses konversi PDF ke PDF/A-3b?

 J: Saat mengonversi PDF ke format PDF/A-3b menggunakan Aspose.PDF untuk .NET, Anda memiliki kendali atas cara penanganan kesalahan. Itu`Convert` metode`ConvertErrorAction` parameter menentukan tindakan yang harus diambil ketika mengalami kesalahan. Dalam contoh kode yang diberikan,`ConvertErrorAction.Delete` parameter digunakan, yang berarti kesalahan apa pun yang terjadi selama konversi akan mengakibatkan penghapusan halaman yang memiliki kesalahan.

#### T: Apakah PDF/A-3b cocok untuk pelestarian dokumen jangka panjang?

J: Ya, PDF/A-3b dirancang khusus untuk penyimpanan dokumen elektronik dalam jangka panjang. Dengan menyematkan file dan data tambahan, ini memastikan bahwa semua komponen yang diperlukan disertakan dalam dokumen PDF itu sendiri, sehingga mengurangi risiko kehilangan informasi atau ketergantungan eksternal seiring waktu. Fitur ini membuatnya cocok untuk pengarsipan dokumen dengan cara yang menjamin aksesibilitas dan konsistensi jangka panjang.