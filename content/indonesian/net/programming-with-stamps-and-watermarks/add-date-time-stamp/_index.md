---
title: Tambahkan Cap Tanggal Waktu Dalam File PDF
linktitle: Tambahkan Cap Tanggal Waktu Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mudah menambahkan cap tanggal dan waktu dalam berkas PDF dengan Aspose.PDF untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
Dalam artikel ini, kami akan memandu Anda langkah demi langkah tentang cara menambahkan cap tanggal dan waktu dalam berkas PDF menggunakan Aspose.PDF untuk .NET. Kami akan menunjukkan cara menggunakan kode sumber C# yang disediakan untuk menambahkan cap tanggal dan waktu ke berkas PDF yang sudah ada.

## Persyaratan

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Lingkungan pengembangan .NET yang terinstal.
- Pustaka Aspose.PDF untuk .NET diunduh dan dirujuk dalam proyek Anda.

## Langkah 1: Menyiapkan lingkungan

Sebelum Anda dapat menambahkan tanggal dan stempel waktu ke dokumen PDF, Anda perlu menyiapkan lingkungan pengembangan Anda. Berikut ini langkah-langkah yang harus diikuti:

1. Buka IDE (Integrated Development Environment) favorit Anda.
2. Buat proyek C# baru.
3. Pastikan Anda telah menambahkan referensi ke pustaka Aspose.PDF untuk .NET.

## Langkah 2: Menambahkan pustaka Aspose.PDF

Pustaka Aspose.PDF untuk .NET diperlukan untuk bekerja dengan dokumen PDF di proyek Anda.

## Langkah 3: Memuat dokumen PDF

Langkah pertama untuk menambahkan cap tanggal dan waktu adalah memuat dokumen PDF yang ada ke dalam proyek Anda. Berikut caranya:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Buka dokumennya
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori tempat dokumen PDF Anda berada.

## Langkah 4: Membuat cap tanggal dan waktu

Sekarang setelah Anda mengunggah dokumen

  PDF, Anda dapat membuat stempel tanggal dan waktu untuk ditambahkan. Berikut cara melakukannya:

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

// Membuat buffer teks
TextStamp textStamp = new TextStamp(annotationText);
```

Kode di atas membuat buffer teks baru yang berisi tanggal dan waktu saat ini.

## Langkah 5: Mengonfigurasi Properti Prangko

Sebelum menambahkan stempel ke dokumen PDF, Anda dapat mengonfigurasi berbagai properti stempel, seperti margin, perataan horizontal dan vertikal, dll. Berikut caranya:

```csharp
// Mengatur properti buffer
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

Anda dapat menyesuaikan properti ini menurut kebutuhan Anda.

## Langkah 6: Tambahkan Stempel ke PDF

Setelah tanggal dan waktu sudah siap, Anda dapat menambahkannya ke halaman tertentu pada dokumen PDF. Berikut caranya:

```csharp
// Tambahkan prangko ke koleksi prangko halaman
pdfDocument.Pages[1].AddStamp(textStamp);
```

Kode di atas menambahkan stempel pada halaman pertama dokumen PDF. Anda dapat menentukan halaman lain jika diperlukan.

## Langkah 7: Simpan dokumen keluaran

Setelah Anda menambahkan tanggal dan stempel waktu, Anda dapat menyimpan dokumen PDF yang telah dimodifikasi. Berikut caranya:

```csharp
// Simpan dokumen keluaran
pdfDocument.Save(dataDir);
```

Kode di atas menyimpan dokumen PDF yang telah diedit ke direktori yang ditentukan.

### Contoh kode sumber untuk Menambahkan Cap Tanggal Waktu menggunakan Aspose.PDF untuk .NET 
```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buka dokumen
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

// Buat stempel teks
TextStamp textStamp = new TextStamp(annotationText);

// Mengatur properti prangko
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Menambahkan prangko pada koleksi prangko
pdfDocument.Pages[1].AddStamp(textStamp);
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;

Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddDateTimeStamp_out.pdf";

// Simpan dokumen keluaran
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);  
          
```

## Kesimpulan

Selamat! Anda telah mempelajari cara menambahkan cap tanggal dan waktu menggunakan Aspose.PDF untuk .NET. Sekarang Anda dapat menerapkan pengetahuan ini ke proyek Anda sendiri untuk menambahkan cap tanggal dan waktu ke dokumen PDF.

### FAQ untuk menambahkan cap tanggal waktu dalam file PDF

#### T: Apa tujuan menambahkan cap tanggal dan waktu ke dokumen PDF menggunakan Aspose.PDF untuk .NET?

J: Menambahkan cap tanggal dan waktu ke dokumen PDF akan meningkatkan nilai informasinya dengan menunjukkan kapan dokumen tersebut dimodifikasi atau dibuat. Fitur ini berguna untuk melacak perubahan dokumen dan menyediakan titik referensi untuk riwayat dokumen.

#### T: Dapatkah saya menyesuaikan format cap tanggal dan waktu agar sesuai dengan persyaratan tertentu?

 A: Ya, Anda dapat menyesuaikan format tanggal dan stempel waktu sesuai dengan preferensi Anda. Kode sumber C# yang disediakan menggunakan`DateTime.Now.ToString()` metode untuk menghasilkan stempel waktu dalam format tertentu. Anda dapat mengubah kode ini untuk memformat stempel waktu sesuai kebutuhan.

#### T: Apakah mungkin untuk menambahkan cap tanggal dan waktu ke lokasi tertentu pada halaman PDF?

 A: Tentu saja, Anda dapat menyesuaikan penempatan cap tanggal dan waktu pada halaman PDF dengan mengubah properti`TextStamp` objek. Kode yang diberikan dalam tutorial ini menunjukkan cara mengatur properti seperti margin, perataan, dan posisi vertikal.

#### T: Dapatkah saya menambahkan beberapa cap tanggal dan waktu ke halaman berbeda dalam dokumen PDF yang sama?

 A: Ya, Anda dapat menambahkan beberapa cap tanggal dan waktu ke halaman yang berbeda dari dokumen PDF yang sama. Cukup ulangi proses pembuatannya`TextStamp` objek dan mengonfigurasi propertinya untuk setiap halaman yang diinginkan.

#### T: Bagaimana cara mengubah font, ukuran, atau warna teks cap tanggal dan waktu?

 A: Untuk mengubah font, ukuran, atau warna teks cap tanggal dan waktu, Anda dapat menyesuaikan properti`DefaultAppearance` objek yang digunakan untuk membuat`TextStamp`Sesuaikan nama font, ukuran, dan nilai warna untuk mendapatkan tampilan yang diinginkan.

#### T: Apakah mungkin untuk menambahkan jenis anotasi atau stempel lain ke dokumen PDF menggunakan Aspose.PDF untuk .NET?

J: Ya, Aspose.PDF untuk .NET menyediakan berbagai jenis anotasi yang dapat Anda tambahkan ke dokumen PDF, termasuk anotasi teks, stempel, garis, bentuk, dan banyak lagi. Anda dapat menjelajahi dokumentasi Aspose.PDF untuk detail lebih lanjut tentang cara menggunakan anotasi.

#### T: Apakah ada batasan atau pertimbangan saat menambahkan cap tanggal dan waktu ke dokumen PDF?

J: Meskipun menambahkan cap tanggal dan waktu mudah dilakukan, pertimbangkan faktor-faktor seperti tata letak dokumen dan konten yang ada. Pastikan penempatan cap tidak mengaburkan informasi penting atau memengaruhi keterbacaan dokumen.

#### T: Bagaimana saya dapat mengintegrasikan metode ini ke dalam proyek saya sendiri untuk menambahkan cap tanggal dan waktu ke dokumen PDF?

J: Untuk mengintegrasikan metode ini, ikuti langkah-langkah yang diberikan dan sesuaikan kode agar sesuai dengan struktur proyek Anda. Anda dapat menambahkan cap tanggal dan waktu ke dokumen PDF yang ada untuk meningkatkan kegunaannya dan memberikan garis waktu perubahan yang jelas.

#### T: Dapatkah saya mengotomatiskan proses penambahan cap tanggal dan waktu ke beberapa dokumen PDF?

A: Ya, Anda dapat mengotomatiskan proses penambahan cap tanggal dan waktu ke beberapa dokumen PDF dengan membuat skrip atau program yang mengulangi daftar dokumen dan menerapkan proses pemberian cap yang sama untuk setiap dokumen.