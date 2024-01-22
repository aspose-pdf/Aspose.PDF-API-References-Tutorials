---
title: Tambahkan Stempel Tanggal Waktu Dalam File PDF
linktitle: Tambahkan Stempel Tanggal Waktu Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara mudah menambahkan cap tanggal dan waktu dalam file PDF dengan Aspose.PDF untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
Pada artikel ini, kami akan memandu Anda langkah demi langkah tentang cara menambahkan cap tanggal dan waktu di file PDF menggunakan Aspose.PDF untuk .NET. Kami akan menunjukkan cara menggunakan kode sumber C# yang disediakan untuk menambahkan cap tanggal dan waktu ke file PDF yang ada.

## Persyaratan

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Lingkungan pengembangan .NET yang terinstal.
- Pustaka Aspose.PDF untuk .NET diunduh dan direferensikan dalam proyek Anda.

## Langkah 1: Menyiapkan lingkungan

Sebelum Anda dapat menambahkan cap tanggal dan waktu ke dokumen PDF, Anda perlu menyiapkan lingkungan pengembangan Anda. Berikut langkah-langkah yang harus diikuti:

1. Buka IDE (Lingkungan Pengembangan Terpadu) favorit Anda.
2. Buat proyek C# baru.
3. Pastikan Anda telah menambahkan referensi ke perpustakaan Aspose.PDF untuk .NET.

## Langkah 2: Menambahkan perpustakaan Aspose.PDF

Pustaka Aspose.PDF untuk .NET diperlukan untuk bekerja dengan dokumen PDF di proyek Anda.

## Langkah 3: Memuat dokumen PDF

Langkah pertama untuk menambahkan cap tanggal dan waktu adalah memuat dokumen PDF yang ada ke dalam proyek Anda. Begini caranya:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Buka dokumennya
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori tempat dokumen PDF Anda berada.

## Langkah 4: Membuat stempel tanggal dan waktu

Sekarang Anda telah mengunggah dokumennya

  PDF, Anda dapat membuat cap tanggal dan waktu untuk ditambahkan. Berikut cara melakukannya:

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

// Buat buffer teks
TextStamp textStamp = new TextStamp(annotationText);
```

Kode di atas membuat buffer teks baru yang berisi tanggal dan waktu saat ini.

## Langkah 5: Mengonfigurasi Properti Stempel

Sebelum menambahkan stempel ke dokumen PDF, Anda dapat mengonfigurasi berbagai properti stempel, seperti margin, perataan horizontal dan vertikal, dll. Begini caranya:

```csharp
// Atur properti penyangga
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

Anda dapat menyesuaikan properti ini sesuai dengan kebutuhan Anda.

## Langkah 6: Tambahkan Stempel ke PDF

Sekarang stempel tanggal dan waktu sudah siap, Anda dapat menambahkannya ke halaman tertentu di dokumen PDF. Begini caranya:

```csharp
// Tambahkan prangko ke koleksi prangko halaman
pdfDocument.Pages[1].AddStamp(textStamp);
```

Kode di atas menambahkan cap pada halaman pertama dokumen PDF. Anda dapat menentukan halaman lain jika diperlukan.

## Langkah 7: Simpan dokumen keluaran

Setelah Anda menambahkan cap tanggal dan waktu, Anda dapat menyimpan dokumen PDF yang dimodifikasi. Begini caranya:

```csharp
// Simpan dokumen keluaran
pdfDocument.Save(dataDir);
```

Kode di atas menyimpan dokumen PDF yang diedit ke direktori yang ditentukan.

### Contoh kode sumber untuk Menambahkan Stempel Tanggal Waktu menggunakan Aspose.PDF untuk .NET 
```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buka dokumen
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

// Buat stempel teks
TextStamp textStamp = new TextStamp(annotationText);

// Mengatur properti stempel
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Menambah prangko pada koleksi prangko
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

Selamat! Anda telah mempelajari cara menambahkan cap tanggal dan waktu menggunakan Aspose.PDF untuk .NET. Sekarang Anda dapat menerapkan pengetahuan ini pada proyek Anda sendiri untuk menambahkan stempel tanggal dan waktu ke dokumen PDF.

### FAQ untuk menambahkan stempel tanggal dan waktu dalam file PDF

#### T: Apa tujuan menambahkan cap tanggal dan waktu ke dokumen PDF menggunakan Aspose.PDF untuk .NET?

J: Menambahkan stempel tanggal dan waktu ke dokumen PDF akan meningkatkan nilai informasinya dengan menunjukkan kapan dokumen tersebut dimodifikasi atau dibuat. Fitur ini berguna untuk melacak perubahan dokumen dan memberikan titik referensi riwayat dokumen.

#### T: Dapatkah saya menyesuaikan format stempel tanggal dan waktu agar sesuai dengan kebutuhan spesifik?

 A: Ya, Anda dapat menyesuaikan format stempel tanggal dan waktu sesuai preferensi Anda. Kode sumber C# yang disediakan menggunakan`DateTime.Now.ToString()` metode untuk menghasilkan stempel waktu dalam format tertentu. Anda dapat mengubah kode ini untuk memformat stempel waktu sesuai kebutuhan.

#### T: Apakah mungkin untuk menambahkan cap tanggal dan waktu ke lokasi tertentu pada halaman PDF?

 J: Tentu saja, Anda dapat menyesuaikan penempatan cap tanggal dan waktu pada halaman PDF dengan memodifikasi properti dari`TextStamp` obyek. Kode yang disediakan dalam tutorial menunjukkan cara mengatur properti seperti margin, perataan, dan pemosisian vertikal.

#### T: Dapatkah saya menambahkan beberapa stempel tanggal dan waktu ke halaman berbeda pada dokumen PDF yang sama?

 J: Ya, Anda dapat menambahkan beberapa stempel tanggal dan waktu ke halaman berbeda pada dokumen PDF yang sama. Cukup ulangi proses pembuatan a`TextStamp` objek dan mengonfigurasi propertinya untuk setiap halaman yang diinginkan.

#### T: Bagaimana cara mengubah font, ukuran, atau warna teks stempel tanggal dan waktu?

 J: Untuk mengubah font, ukuran, atau warna teks stempel tanggal dan waktu, Anda dapat menyesuaikan propertinya`DefaultAppearance` objek yang digunakan untuk membuat`TextStamp`. Sesuaikan nama font, ukuran, dan nilai warna untuk mencapai tampilan yang diinginkan.

#### T: Apakah mungkin untuk menambahkan jenis anotasi atau stempel lain ke dokumen PDF menggunakan Aspose.PDF untuk .NET?

J: Ya, Aspose.PDF untuk .NET menyediakan berbagai jenis anotasi yang dapat Anda tambahkan ke dokumen PDF, termasuk anotasi teks, stempel, garis, bentuk, dan banyak lagi. Anda dapat menjelajahi dokumentasi Aspose.PDF untuk detail lebih lanjut tentang bekerja dengan anotasi.

#### T: Apakah ada batasan atau pertimbangan saat menambahkan stempel tanggal dan waktu ke dokumen PDF?

J: Meskipun menambahkan stempel tanggal dan waktu sangatlah mudah, pertimbangkan faktor-faktor seperti tata letak dokumen dan konten yang ada. Pastikan penempatan stempel tidak mengaburkan informasi penting atau mempengaruhi keterbacaan dokumen.

#### T: Bagaimana cara mengintegrasikan metode ini ke dalam proyek saya sendiri untuk menambahkan stempel tanggal dan waktu ke dokumen PDF?

J: Untuk mengintegrasikan metode ini, ikuti langkah-langkah yang disediakan dan sesuaikan kode agar sesuai dengan struktur proyek Anda. Anda dapat menambahkan stempel tanggal dan waktu ke dokumen PDF yang ada untuk meningkatkan kegunaannya dan memberikan garis waktu perubahan yang jelas.

#### T: Dapatkah saya mengotomatiskan proses penambahan stempel tanggal dan waktu ke beberapa dokumen PDF?

J: Ya, Anda dapat mengotomatiskan proses penambahan stempel tanggal dan waktu ke beberapa dokumen PDF dengan membuat skrip atau program yang melakukan iterasi melalui daftar dokumen dan menerapkan proses stempel yang sama pada masing-masing dokumen.