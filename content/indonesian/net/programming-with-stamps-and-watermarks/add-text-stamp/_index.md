---
title: Tambahkan Stempel Teks Dalam File PDF
linktitle: Tambahkan Stempel Teks Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara mudah menambahkan stempel teks dalam file PDF dengan Aspose.PDF untuk .NET.
type: docs
weight: 50
url: /id/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
Dalam tutorial ini, kami akan memandu Anda langkah demi langkah tentang cara menambahkan stempel teks di file PDF menggunakan Aspose.PDF untuk .NET. Kami akan menunjukkan cara menggunakan kode sumber C# yang disediakan untuk menambahkan stempel teks khusus ke halaman tertentu pada file PDF.

## Langkah 1: Menyiapkan lingkungan

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Lingkungan pengembangan .NET yang terinstal.
- Pustaka Aspose.PDF untuk .NET diunduh dan direferensikan dalam proyek Anda.

## Langkah 2: Memuat dokumen PDF

Langkah pertama adalah memuat dokumen PDF yang ada ke dalam proyek Anda. Begini caranya:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Buka dokumennya
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori tempat dokumen PDF Anda berada.

## Langkah 3: Membuat buffer teks

Sekarang setelah Anda mengunggah dokumen PDF, Anda dapat membuat stempel teks untuk ditambahkan. Berikut cara melakukannya:

```csharp
// Buat buffer teks
TextStamp textStamp = new TextStamp("Example Stamp");
```

Kode di atas membuat buffer teks baru yang berisi teks tertentu.

## Langkah 4: Mengonfigurasi Properti Stempel Teks

Sebelum menambahkan stempel teks ke dokumen PDF, Anda dapat mengonfigurasi berbagai properti stempel, seperti latar belakang, posisi, rotasi, font, ukuran, dll. Begini caranya:

```csharp
// Konfigurasikan properti buffer teks
textStamp. Background = true;
textStamp. XIndent = 100;
textStamp. YIndent = 100;
textStamp.Rotate = Rotate.on90;
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);
```

Anda dapat menyesuaikan properti ini sesuai dengan kebutuhan Anda.

## Langkah 5: Tambahkan Stempel Teks ke PDF

Sekarang stempel teks sudah siap, Anda dapat menambahkannya ke halaman tertentu di dokumen PDF. Begini caranya:

```csharp
//Tambahkan buffer teks ke halaman tertentu
pdfDocument.Pages[1].AddStamp(textStamp);
```

Kode di atas menambahkan stempel teks ke halaman pertama dokumen PDF. Anda dapat menentukan halaman lain jika diperlukan.

## Langkah 6: Simpan dokumen keluaran

Setelah Anda menambahkan stempel teks, Anda dapat menyimpan dokumen PDF yang telah diedit. Begini caranya:

```csharp
// Simpan dokumen keluaran
pdfDocument.Save(dataDir);
```

Kode di atas menyimpan dokumen PDF yang dimodifikasi di direktori yang ditentukan.

### Contoh kode sumber untuk Menambahkan Stempel Teks menggunakan Aspose.PDF untuk .NET 
```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buka dokumen
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

// Buat stempel teks
TextStamp textStamp = new TextStamp("Sample Stamp");

// Setel apakah stempel adalah latar belakang
textStamp.Background = true;

// Tetapkan asal
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Putar stempel
textStamp.Rotate = Rotation.on90;

// Atur properti teks
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold;
textStamp.TextState.FontStyle = FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);

// Tambahkan stempel ke halaman tertentu
pdfDocument.Pages[1].AddStamp(textStamp);
dataDir = dataDir + "AddTextStamp_out.pdf";

// Simpan dokumen keluaran
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);            

```

## Kesimpulan

Selamat! Anda telah mempelajari cara menambahkan stempel teks menggunakan Aspose.PDF untuk .NET. Sekarang Anda dapat menerapkan pengetahuan ini pada proyek Anda sendiri untuk menambahkan stempel teks khusus ke dokumen PDF.

### FAQ untuk menambahkan stempel teks dalam file PDF

#### T: Apa tujuan menambahkan stempel teks dalam file PDF menggunakan Aspose.PDF untuk .NET?

J: Menambahkan stempel teks memungkinkan Anda menempatkan teks khusus pada halaman tertentu dokumen PDF. Fitur ini berguna untuk menambahkan label, komentar, tanda air, atau informasi tekstual lainnya untuk menyempurnakan konten dokumen dan memberikan konteks tambahan.

#### T: Dapatkah saya menyesuaikan tampilan stempel teks, seperti font, ukuran, warna, dan rotasi?

 J: Ya, Anda dapat sepenuhnya menyesuaikan tampilan stempel teks. Kode sumber C# yang disediakan menunjukkan cara mengatur berbagai properti`TextStamp` objek, termasuk font, ukuran font, gaya font, warna teks, warna latar belakang, dan rotasi.

#### T: Apakah mungkin untuk menambahkan beberapa stempel teks ke halaman berbeda pada dokumen PDF yang sama?

J: Tentu saja, Anda dapat menambahkan beberapa stempel teks ke halaman berbeda pada dokumen PDF yang sama. Kode yang disediakan tutorial memungkinkan Anda menentukan halaman target untuk menambahkan stempel teks, menjadikannya serbaguna untuk halaman berbeda dalam dokumen.

#### Q: Bagaimana cara menentukan posisi stempel teks dalam dokumen PDF?

 J: Anda dapat menyesuaikan posisi stempel teks dengan memodifikasi`XIndent` Dan`YIndent` properti dari`TextStamp` obyek. Properti ini menentukan koordinat sudut kiri atas prangko relatif terhadap asal halaman.

#### T: Dapatkah saya menerapkan metode ini pada dokumen PDF yang sudah ada untuk menambahkan stempel teks?

A: Ya, Anda dapat menerapkan metode ini pada dokumen PDF yang ada untuk menambahkan stempel teks. Kode yang disediakan tutorial menunjukkan cara memuat dokumen PDF yang ada dan menambahkan stempel teks ke halaman tertentu.

#### T: Dapatkah saya menambahkan warna latar belakang dan latar depan pada stempel teks?

 J: Ya, Anda dapat menambahkan warna latar belakang dan latar depan pada stempel teks. Dengan mengatur`Background` properti ke`true` , Anda dapat memberikan latar belakang berwarna untuk stempel teks. Selain itu, Anda dapat mengatur`TextState.ForegroundColor` properti untuk menentukan warna teks itu sendiri.

#### T: Bagaimana cara memastikan bahwa stempel teks tidak mengaburkan konten dasar dokumen PDF?

 J: Saat menambahkan stempel teks, perhatikan penempatannya untuk memastikan bahwa stempel tersebut tidak menghalangi informasi penting atau berdampak buruk pada keterbacaan dokumen. Anda dapat menyesuaikannya`XIndent` Dan`YIndent` properti untuk memposisikan stempel teks dengan tepat.

#### Q: Dapatkah saya menggunakan metode ini untuk menambahkan stempel selain teks, seperti gambar atau logo?

J: Tutorial khusus ini berfokus pada penambahan stempel teks, namun Anda juga dapat menambahkan jenis stempel lainnya, seperti gambar atau logo, menggunakan Aspose.PDF untuk .NET. Prosesnya melibatkan pembuatan objek stempel yang sesuai dan mengonfigurasi propertinya.

#### T: Bagaimana cara mengotomatiskan proses penambahan stempel teks ke beberapa dokumen PDF?

J: Anda dapat mengotomatiskan proses penambahan stempel teks ke beberapa dokumen PDF dengan membuat skrip atau program yang melakukan iterasi melalui daftar dokumen dan menerapkan proses stempel teks yang sama ke masing-masing dokumen.