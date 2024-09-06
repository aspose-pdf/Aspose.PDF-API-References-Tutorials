---
title: Tambahkan Stempel Teks Dalam File PDF
linktitle: Tambahkan Stempel Teks Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mudah menambahkan stempel teks dalam berkas PDF dengan Aspose.PDF untuk .NET.
type: docs
weight: 50
url: /id/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
Dalam tutorial ini, kami akan memandu Anda langkah demi langkah tentang cara menambahkan stempel teks dalam berkas PDF menggunakan Aspose.PDF untuk .NET. Kami akan menunjukkan kepada Anda cara menggunakan kode sumber C# yang disediakan untuk menambahkan stempel teks khusus ke halaman tertentu dalam berkas PDF.

## Langkah 1: Menyiapkan lingkungan

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Lingkungan pengembangan .NET yang terinstal.
- Pustaka Aspose.PDF untuk .NET diunduh dan dirujuk dalam proyek Anda.

## Langkah 2: Memuat dokumen PDF

Langkah pertama adalah memuat dokumen PDF yang ada ke dalam proyek Anda. Berikut caranya:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Buka dokumennya
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori tempat dokumen PDF Anda berada.

## Langkah 3: Membuat buffer teks

Setelah Anda mengunggah dokumen PDF, Anda dapat membuat stempel teks untuk ditambahkan. Berikut cara melakukannya:

```csharp
// Buat buffer teks
TextStamp textStamp = new TextStamp("Example Stamp");
```

Kode di atas membuat buffer teks baru yang berisi teks yang ditentukan.

## Langkah 4: Mengonfigurasi Properti Cap Teks

Sebelum menambahkan stempel teks ke dokumen PDF, Anda dapat mengonfigurasi berbagai properti stempel, seperti latar belakang, posisi, rotasi, font, ukuran, dll. Berikut caranya:

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

Anda dapat menyesuaikan properti ini menurut kebutuhan Anda.

## Langkah 5: Tambahkan Stempel Teks ke PDF

Setelah stempel teks siap, Anda dapat menambahkannya ke halaman tertentu dalam dokumen PDF. Berikut caranya:

```csharp
//Tambahkan buffer teks ke halaman tertentu
pdfDocument.Pages[1].AddStamp(textStamp);
```

Kode di atas menambahkan stempel teks ke halaman pertama dokumen PDF. Anda dapat menentukan halaman lain jika diperlukan.

## Langkah 6: Simpan dokumen keluaran

Setelah Anda menambahkan stempel teks, Anda dapat menyimpan dokumen PDF yang telah diedit. Berikut caranya:

```csharp
// Simpan dokumen keluaran
pdfDocument.Save(dataDir);
```

Kode di atas menyimpan dokumen PDF yang dimodifikasi dalam direktori yang ditentukan.

### Contoh kode sumber untuk Menambahkan Stempel Teks menggunakan Aspose.PDF untuk .NET 
```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buka dokumen
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

// Buat stempel teks
TextStamp textStamp = new TextStamp("Sample Stamp");

// Atur apakah stempel adalah latar belakang
textStamp.Background = true;

// Tetapkan asal
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Putar prangko
textStamp.Rotate = Rotation.on90;

// Mengatur properti teks
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold;
textStamp.TextState.FontStyle = FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);

// Tambahkan prangko ke halaman tertentu
pdfDocument.Pages[1].AddStamp(textStamp);
dataDir = dataDir + "AddTextStamp_out.pdf";

// Simpan dokumen keluaran
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);            

```

## Kesimpulan

Selamat! Anda telah mempelajari cara menambahkan stempel teks menggunakan Aspose.PDF untuk .NET. Sekarang Anda dapat menerapkan pengetahuan ini ke proyek Anda sendiri untuk menambahkan stempel teks khusus ke dokumen PDF.

### FAQ untuk menambahkan stempel teks dalam file PDF

#### T: Apa tujuan menambahkan stempel teks dalam berkas PDF menggunakan Aspose.PDF untuk .NET?

A: Menambahkan stempel teks memungkinkan Anda untuk menempatkan teks khusus pada halaman tertentu dari dokumen PDF. Fitur ini berguna untuk menambahkan label, komentar, tanda air, atau informasi tekstual lainnya untuk menyempurnakan konten dokumen dan memberikan konteks tambahan.

#### T: Dapatkah saya menyesuaikan tampilan stempel teks, seperti font, ukuran, warna, dan rotasi?

 A: Ya, Anda dapat sepenuhnya menyesuaikan tampilan stempel teks. Kode sumber C# yang disediakan menunjukkan cara mengatur berbagai properti`TextStamp` objek, termasuk font, ukuran font, gaya font, warna teks, warna latar belakang, dan rotasi.

#### T: Apakah mungkin untuk menambahkan beberapa stempel teks ke halaman berbeda dalam dokumen PDF yang sama?

J: Tentu saja, Anda dapat menambahkan beberapa stempel teks ke halaman yang berbeda dalam dokumen PDF yang sama. Kode yang disediakan dalam tutorial memungkinkan Anda menentukan halaman target untuk menambahkan stempel teks, sehingga dapat digunakan di berbagai halaman dalam dokumen.

#### T: Bagaimana cara menentukan posisi stempel teks dalam dokumen PDF?

 A: Anda dapat menyesuaikan posisi stempel teks dengan memodifikasi`XIndent` Dan`YIndent` properti dari`TextStamp` objek. Properti ini menentukan koordinat sudut kiri atas prangko relatif terhadap asal halaman.

#### T: Dapatkah saya menerapkan metode ini ke dokumen PDF yang ada untuk menambahkan stempel teks?

A: Ya, Anda dapat menerapkan metode ini ke dokumen PDF yang sudah ada untuk menambahkan stempel teks. Kode yang diberikan dalam tutorial menunjukkan cara memuat dokumen PDF yang sudah ada dan menambahkan stempel teks ke halaman tertentu.

#### T: Dapatkah saya menambahkan warna latar belakang dan latar depan pada stempel teks?

 A: Ya, Anda dapat menambahkan warna latar belakang dan latar depan ke stempel teks. Dengan menyetel`Background` properti untuk`true` , Anda dapat memberikan latar belakang berwarna untuk stempel teks. Selain itu, Anda dapat mengatur`TextState.ForegroundColor` properti untuk menentukan warna teks itu sendiri.

#### T: Bagaimana saya dapat memastikan bahwa cap teks tidak mengaburkan konten dasar dokumen PDF?

A: Saat menambahkan stempel teks, perhatikan penempatannya untuk memastikan bahwa stempel tersebut tidak menghalangi informasi penting atau memengaruhi keterbacaan dokumen secara negatif. Anda dapat menyesuaikan`XIndent` Dan`YIndent` properti untuk memposisikan stempel teks dengan tepat.

#### T: Dapatkah saya menggunakan metode ini untuk menambahkan prangko selain teks, seperti gambar atau logo?

J: Tutorial khusus ini berfokus pada penambahan stempel teks, tetapi Anda juga dapat menambahkan jenis stempel lain, seperti gambar atau logo, menggunakan Aspose.PDF untuk .NET. Prosesnya melibatkan pembuatan objek stempel yang sesuai dan mengonfigurasi propertinya.

#### T: Bagaimana saya dapat mengotomatiskan proses penambahan stempel teks ke beberapa dokumen PDF?

A: Anda dapat mengotomatiskan proses penambahan stempel teks ke beberapa dokumen PDF dengan membuat skrip atau program yang mengulangi daftar dokumen dan menerapkan proses pemberian stempel teks yang sama ke setiap dokumen.