---
title: Dapatkan Tanda Air Dari File PDF
linktitle: Dapatkan Tanda Air Dari File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara mengekstrak tanda air dari file PDF dengan Aspose.PDF untuk .NET.
type: docs
weight: 100
url: /id/net/programming-with-stamps-and-watermarks/get-watermark/
---
Dalam tutorial ini, kami akan memandu Anda langkah demi langkah tentang cara mendapatkan watermark dari file PDF menggunakan Aspose.PDF untuk .NET. Kami akan menunjukkan kepada Anda cara menggunakan kode sumber C# yang disediakan untuk melakukan iterasi melalui artefak halaman tertentu dan mendapatkan jenis tanda air, teks, dan lokasi.

## Langkah 1: Menyiapkan lingkungan

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Lingkungan pengembangan .NET yang terinstal.
- Pustaka Aspose.PDF untuk .NET diunduh dan direferensikan dalam proyek Anda.

## Langkah 2: Memuat dokumen PDF

Langkah pertama adalah memuat dokumen PDF yang ada ke dalam proyek Anda. Begini caranya:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Buka dokumen PDF
Document pdfDocument = new Document(dataDir + "watermark.pdf");
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori tempat dokumen PDF Anda berada.

## Langkah 3: Mendapatkan tanda air

Sekarang setelah Anda memuat dokumen PDF, Anda dapat mengulangi artefak halaman tertentu untuk mendapatkan informasi tanda air. Begini caranya:

```csharp
// Jelajahi artefak dan dapatkan subtipe tanda air, teks, dan lokasi
foreach(Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
     Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}
```

Kode di atas menelusuri semua artefak di halaman pertama dokumen PDF dan menampilkan subtipe, teks, dan persegi panjang (lokasi) dari setiap tanda air yang ditemukan.

### Contoh kode sumber untuk Mendapatkan Tanda Air menggunakan Aspose.PDF untuk .NET 
```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buka dokumen
Document pdfDocument = new Document( dataDir +  "watermark.pdf");

// Ulangi dan dapatkan tipe bak, teks, dan lokasi artefak
foreach (Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
	Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}

```

## Kesimpulan

Selamat! Anda telah mempelajari cara mendapatkan informasi tanda air dari dokumen PDF menggunakan Aspose.PDF untuk .NET. Sekarang Anda dapat menggunakan pengetahuan ini untuk menganalisis dan memproses tanda air di dokumen PDF Anda.

### FAQ untuk mendapatkan tanda air dari file PDF

#### T: Apa yang dimaksud dengan tanda air pada dokumen PDF, dan mengapa saya perlu mengekstrak informasinya?

J: Tanda air dalam dokumen PDF adalah gambar atau teks yang dapat dikenali dan ditempelkan pada konten dokumen, sering kali untuk menunjukkan status, kepemilikan, atau sifat rahasianya. Ekstraksi informasi watermark dapat berguna untuk menganalisis keaslian dokumen, mengidentifikasi sumber dokumen, atau memproses dokumen berdasarkan keberadaan watermark.

#### T: Bagaimana kode sumber C# yang disediakan membantu mengekstrak informasi tanda air dari file PDF?

 J: Kode yang diberikan menunjukkan cara memuat dokumen PDF yang ada, melakukan iterasi melalui artefak halaman tertentu, dan mengekstrak informasi tentang tanda air. Hal ini dilakukan dengan mengakses`Subtype`, `Text` , Dan`Rectangle` properti masing-masing artefak.

####  T: Apa yang dimaksud dengan`Subtype` property of an artifact represent?

 J: Itu`Subtype` properti artefak mewakili jenis artefak. Untuk watermark menandakan bahwa artefak tersebut merupakan watermark.

#### Q: Bagaimana cara kode menentukan letak (persegi panjang) watermark pada halaman?

 A: Kode menggunakan`Rectangle` properti artefak untuk menentukan lokasi tanda air. Itu`Rectangle` properti mewakili persegi panjang pembatas artefak di halaman.

#### T: Dapatkah saya memodifikasi kode untuk mengekstrak informasi tambahan tentang tanda air, seperti tampilan atau warnanya?

J: Ya, Anda dapat memodifikasi kode untuk mengakses properti artefak lainnya, seperti tampilan atau warnanya, jika informasi tersebut tersedia dan relevan dengan kasus penggunaan Anda.

#### T: Dapatkah saya mengekstrak informasi tanda air dari beberapa halaman dokumen PDF menggunakan kode ini?

J: Ya, Anda dapat memodifikasi kode untuk mengulangi artefak di beberapa halaman dengan mengubah indeks halaman dalam loop untuk mengakses artefak dari halaman berbeda.

#### T: Apa yang terjadi jika tidak ada tanda air pada halaman yang ditentukan?

J: Jika tidak ada tanda air pada halaman yang ditentukan, perulangan tidak akan dijalankan, dan tidak ada informasi tanda air yang akan ditampilkan.

#### T: Bagaimana cara menggunakan informasi tanda air yang diekstraksi untuk diproses lebih lanjut?

J: Informasi tanda air yang diekstraksi dapat digunakan untuk berbagai tujuan, seperti pencatatan, analisis, pelaporan, atau otomatisasi tindakan tertentu berdasarkan keberadaan atau properti tanda air.

#### T: Dapatkah saya mengubah kode ini untuk mengekstrak informasi tentang jenis artefak lain dalam dokumen PDF?

J: Ya, Anda dapat memodifikasi kode untuk mengekstrak informasi tentang jenis artefak lain dengan mengakses propertinya menggunakan pendekatan serupa.

#### T: Bagaimana cara mengakses tanda air yang bukan artefak namun merupakan bagian dari konten PDF?

J: Tanda air yang bukan merupakan artefak mungkin merupakan bagian dari konten PDF itu sendiri, seperti gambar atau teks. Untuk mengekstrak informasi tentang jenis tanda air ini, Anda mungkin perlu menganalisis konten PDF dan mengidentifikasi elemen tertentu yang mewakili tanda air tersebut.