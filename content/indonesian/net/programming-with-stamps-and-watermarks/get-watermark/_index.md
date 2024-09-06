---
title: Dapatkan Tanda Air Dari File PDF
linktitle: Dapatkan Tanda Air Dari File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mengekstrak tanda air dari berkas PDF dengan Aspose.PDF untuk .NET.
type: docs
weight: 100
url: /id/net/programming-with-stamps-and-watermarks/get-watermark/
---
Dalam tutorial ini, kami akan memandu Anda langkah demi langkah tentang cara mendapatkan tanda air dari berkas PDF menggunakan Aspose.PDF untuk .NET. Kami akan menunjukkan kepada Anda cara menggunakan kode sumber C# yang disediakan untuk menelusuri artefak halaman tertentu dan mendapatkan jenis, teks, dan lokasi tanda air.

## Langkah 1: Menyiapkan lingkungan

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Lingkungan pengembangan .NET yang terinstal.
- Pustaka Aspose.PDF untuk .NET diunduh dan dirujuk dalam proyek Anda.

## Langkah 2: Memuat dokumen PDF

Langkah pertama adalah memuat dokumen PDF yang ada ke dalam proyek Anda. Berikut caranya:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Buka dokumen PDF
Document pdfDocument = new Document(dataDir + "watermark.pdf");
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori tempat dokumen PDF Anda berada.

## Langkah 3: Mendapatkan tanda air

Setelah Anda memuat dokumen PDF, Anda dapat menelusuri artefak halaman tertentu untuk mendapatkan informasi tanda air. Berikut caranya:

```csharp
// Telusuri artefak dan dapatkan subtipe tanda air, teks, dan lokasi
foreach(Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
     Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}
```

Kode di atas mengulang semua artefak di halaman pertama dokumen PDF dan menampilkan subtipe, teks, dan persegi panjang (lokasi) setiap tanda air yang ditemukan.

### Contoh kode sumber untuk Mendapatkan Tanda Air menggunakan Aspose.PDF untuk .NET 
```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buka dokumen
Document pdfDocument = new Document( dataDir +  "watermark.pdf");

// Ulangi dan dapatkan jenis bak, teks, dan lokasi artefak
foreach (Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
	Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}

```

## Kesimpulan

Selamat! Anda telah mempelajari cara mendapatkan informasi tanda air dari dokumen PDF menggunakan Aspose.PDF untuk .NET. Sekarang Anda dapat menggunakan pengetahuan ini untuk menganalisis dan memproses tanda air dalam dokumen PDF Anda.

### FAQ untuk mendapatkan tanda air dari file PDF

#### T: Apa itu tanda air dalam dokumen PDF, dan mengapa saya perlu mengekstrak informasinya?

J: Tanda air dalam dokumen PDF adalah gambar atau teks yang dapat dikenali yang ditumpangkan pada konten dokumen, sering kali untuk menunjukkan status, kepemilikan, atau sifat kerahasiaannya. Mengekstrak informasi tanda air dapat berguna untuk menganalisis keaslian dokumen, mengidentifikasi sumber dokumen, atau memproses dokumen berdasarkan keberadaan tanda air.

#### T: Bagaimana kode sumber C# yang disediakan membantu dalam mengekstrak informasi tanda air dari berkas PDF?

 A: Kode yang diberikan menunjukkan cara memuat dokumen PDF yang ada, mengulangi artefak halaman tertentu, dan mengekstrak informasi tentang tanda air. Kode ini melakukannya dengan mengakses`Subtype`, `Text` , Dan`Rectangle` properti masing-masing artefak.

####  T: Apa yang dimaksud dengan`Subtype` property of an artifact represent?

 Sebuah:`Subtype` properti dari artefak menunjukkan jenis artefak. Untuk tanda air, ini menunjukkan bahwa artefak tersebut adalah tanda air.

#### T: Bagaimana kode menentukan lokasi (persegi panjang) tanda air di halaman?

 A: Kode tersebut menggunakan`Rectangle` properti artifak untuk menentukan lokasi tanda air.`Rectangle` Properti mewakili persegi panjang pembatas artefak pada halaman.

#### T: Dapatkah saya mengubah kode untuk mengekstrak informasi tambahan tentang tanda air, seperti tampilan atau warnanya?

A: Ya, Anda dapat mengubah kode untuk mengakses properti artefak lainnya, seperti tampilan atau warnanya, jika informasi tersebut tersedia dan relevan dengan kasus penggunaan Anda.

#### T: Dapatkah saya mengekstrak informasi tanda air dari beberapa halaman dokumen PDF menggunakan kode ini?

A: Ya, Anda dapat mengubah kode untuk mengulang artefak di beberapa halaman dengan mengubah indeks halaman dalam loop untuk mengakses artefak dari halaman berbeda.

#### T: Apa yang terjadi jika tidak ada tanda air pada halaman yang ditentukan?

A: Jika tidak ada tanda air di halaman yang ditentukan, loop tidak akan dijalankan, dan tidak ada informasi tanda air yang akan ditampilkan.

#### T: Bagaimana saya dapat menggunakan informasi tanda air yang diekstrak untuk pemrosesan lebih lanjut?

A: Informasi tanda air yang diekstraksi dapat digunakan untuk berbagai tujuan, seperti pencatatan, analisis, pelaporan, atau otomatisasi tindakan tertentu berdasarkan keberadaan atau sifat tanda air.

#### T: Dapatkah saya mengubah kode ini untuk mengekstrak informasi tentang jenis artefak lain dalam dokumen PDF?

A: Ya, Anda dapat mengubah kode untuk mengekstrak informasi tentang jenis artefak lain dengan mengakses propertinya menggunakan pendekatan serupa.

#### T: Bagaimana cara mengakses tanda air yang bukan artefak tetapi merupakan bagian dari konten PDF?

J: Tanda air yang bukan artefak mungkin merupakan bagian dari konten PDF itu sendiri, seperti gambar atau teks. Untuk mengekstrak informasi tentang jenis tanda air ini, Anda mungkin perlu menganalisis konten PDF dan mengidentifikasi elemen tertentu yang mewakili tanda air tersebut.