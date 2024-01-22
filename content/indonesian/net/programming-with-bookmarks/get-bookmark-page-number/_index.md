---
title: Dapatkan Nomor Halaman Bookmark Dalam File PDF
linktitle: Dapatkan Nomor Halaman Bookmark Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Dapatkan nomor halaman bookmark dengan mudah dalam file PDF dengan Aspose.PDF untuk .NET.
type: docs
weight: 60
url: /id/net/programming-with-bookmarks/get-bookmark-page-number/
---
Mengambil nomor halaman yang terkait dengan bookmark dalam file PDF dapat berguna untuk navigasi. Dengan Aspose.PDF untuk .NET, Anda dapat dengan mudah mendapatkan nomor halaman bookmark dengan mengikuti kode sumber berikut:

## Langkah 1: Impor perpustakaan yang diperlukan

Sebelum memulai, Anda perlu mengimpor perpustakaan yang diperlukan untuk proyek C# Anda. Berikut adalah arahan impor yang diperlukan:

```csharp
using Aspose.Pdf.Facades;
```

## Langkah 2: Tetapkan jalur ke folder dokumen

 Pada langkah ini, Anda perlu menentukan jalur ke folder yang berisi file PDF yang ingin Anda ekstrak nomor halaman bookmarknya. Mengganti`"YOUR DOCUMENT DIRECTORY"`dalam kode berikut dengan jalur sebenarnya ke folder dokumen Anda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 3: Buat editor bookmark

 Sekarang kita akan membuat a`PdfBookmarkEditor` objek untuk memanipulasi bookmark dokumen. Gunakan kode berikut:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

## Langkah 4: Buka File PDF

 Pada langkah ini, kami membuka file PDF menggunakan`BindPdf` metode editor bookmark. Ini kode yang sesuai:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

## Langkah 5: Ekstrak bookmark

 Sekarang kita akan mengekstrak bookmark dari dokumen menggunakan`ExtractBookmarks` metode editor bookmark. Ini kode yang sesuai:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

## Langkah 6: Jelajahi bookmark dan dapatkan nomor halaman

 Terakhir, kita menelusuri bookmark yang diekstraksi dan mendapatkan nomor halaman yang terkait dengan setiap bookmark menggunakan a`foreach` lingkaran. Ini kode yang sesuai:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
     string strLevelSeprator = string.Empty;
     for (int i = 1; i < bookmark.Level; i++)
     {
         strLevelSeprator += "----";
     }
     Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
     Console.WriteLine("{0}Page number: {1}", strLevelSeprator, bookmark.PageNumber);
     Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

### Contoh kode sumber untuk Mendapatkan Nomor Halaman Bookmark menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buat PdfBookmarkEditor
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
// Buka berkas PDF
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
// Ekstrak bookmark
Aspose.Pdf.Facades.Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
foreach (Aspose.Pdf.Facades.Bookmark bookmark in bookmarks)
{
	string strLevelSeprator = string.Empty;
	for (int i = 1; i < bookmark.Level; i++)
	{
		strLevelSeprator += "----";
	}
	Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
	Console.WriteLine("{0}Page Number: {1}", strLevelSeprator, bookmark.PageNumber);
	Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

## Kesimpulan

Selamat! Sekarang Anda memiliki panduan langkah demi langkah untuk mendapatkan nomor halaman bookmark dengan Aspose.PDF untuk .NET. Anda dapat menggunakan kode ini untuk mengambil informasi navigasi yang terkait dengan setiap bookmark di dokumen PDF Anda.

Pastikan untuk memeriksa dokumentasi resmi Aspose.PDF untuk informasi lebih lanjut tentang fitur manipulasi bookmark tingkat lanjut.

### FAQ untuk mendapatkan nomor halaman bookmark dalam file PDF

#### T: Apa yang dimaksud dengan bookmark dalam file PDF?

J: Penanda dalam file PDF adalah alat bantu navigasi yang memungkinkan pengguna melompat ke bagian atau halaman tertentu dalam dokumen dengan cepat. Mereka meningkatkan pengalaman pengguna dengan menyediakan pintasan ke konten yang relevan.

#### T: Mengapa saya ingin mengambil nomor halaman bookmark dari file PDF?

J: Mengambil nomor halaman bookmark membantu pengguna menavigasi dokumen dengan lebih efektif, memberikan indikasi yang jelas ke mana arah setiap bookmark. Ini khususnya berguna untuk dokumen yang lebih panjang dengan banyak bagian.

#### T: Bagaimana cara mengimpor perpustakaan yang diperlukan untuk proyek C# saya?

J: Untuk mengimpor perpustakaan yang diperlukan untuk proyek C# Anda, gunakan perintah impor berikut:

```csharp
using Aspose.Pdf.Facades;
```

Arahan ini memungkinkan Anda untuk memanfaatkan kelas dan metode yang disediakan oleh Aspose.PDF untuk .NET.

#### T: Bagaimana cara menentukan jalur ke folder dokumen?

 A: Di kode sumber yang disediakan, ganti`"YOUR DOCUMENT DIRECTORY"`dengan jalur sebenarnya ke folder yang berisi file PDF tempat Anda ingin mengekstrak nomor halaman bookmark. Ini memastikan bahwa kode dapat menemukan file PDF target.

#### T: Bagaimana cara membuat editor bookmark?

A: Untuk membuat editor bookmark, gunakan kode berikut:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

#### T: Bagaimana cara membuka file PDF untuk manipulasi bookmark?

A: Untuk membuka file PDF untuk mengekstrak informasi bookmark, gunakan kode berikut:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

 Mengganti`"GetBookmarks.pdf"` dengan nama file sebenarnya.

#### T: Bagaimana cara mengekstrak bookmark dari file PDF?

 J: Untuk mengekstrak bookmark dari file PDF, gunakan`ExtractBookmarks` metode editor bookmark:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

#### T: Bagaimana cara mengambil dan menampilkan nomor halaman penanda?

 A: Ulangi bookmark yang diekstraksi menggunakan a`foreach` loop dan akses`PageNumber` properti setiap bookmark untuk mengambil dan menampilkan nomor halaman terkait:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
    Console.WriteLine("Title: " + bookmark.Title);
    Console.WriteLine("Page Number: " + bookmark.PageNumber);
    Console.WriteLine("Page Action: " + bookmark.Action);
}
```

#### T: Bisakah saya mengubah properti bookmark menggunakan pendekatan ini?

 J: Meskipun tutorial ini berfokus pada mengambil nomor halaman bookmark, Anda dapat mengubah properti bookmark lainnya menggunakan hal yang sama`Bookmark`objek dan properti terkait.

#### T: Bagaimana cara menyimpan file PDF yang diperbarui setelah mengekstrak informasi bookmark?

J: Ekstraksi bookmark tidak mengubah file PDF asli. Jika Anda ingin menyimpan perubahan apa pun, Anda dapat melakukannya menggunakan metode lain yang disediakan oleh Aspose.PDF untuk .NET.