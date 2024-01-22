---
title: Tambahkan Gambar Dengan Isi Gradien
linktitle: Tambahkan Gambar Dengan Isi Gradien
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menambahkan gambar dengan isian gradien dengan Aspose.PDF untuk .NET. Tutorial langkah demi langkah untuk membuat dokumen PDF yang menarik.
type: docs
weight: 20
url: /id/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# berikut langkah demi langkah untuk menambahkan gambar dengan isian gradien ke pemrograman dengan grafik menggunakan Aspose.PDF untuk .NET.

Pastikan Anda telah menginstal perpustakaan Aspose.PDF dan mengatur lingkungan pengembangan Anda sebelum memulai. Juga memiliki pengetahuan dasar tentang pemrograman C#.

## Langkah 1: Pengaturan Direktori Dokumen

Dalam kode sumber yang disediakan, Anda perlu menentukan direktori tempat Anda ingin menyimpan file PDF yang dihasilkan. Ubah variabel "dataDir" ke direktori yang diinginkan.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Membuat Instansi Objek Dokumen dan Menambahkan Halaman

Kami membuat instance kelas Dokumen dan menambahkan halaman ke dokumen ini.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Langkah 3: Membuat Objek Grafik dan Menambahkannya ke Halaman

Kami membuat objek Grafik dengan dimensi tertentu dan menambahkannya ke koleksi paragraf halaman.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
```

## Langkah 4: Buat Objek Persegi Panjang dan Tambahkan ke Bagan

Kita membuat objek Rectangle dengan dimensi tertentu dan menambahkannya ke koleksi bentuk grafik.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```

## Langkah 5: Mengonfigurasi Isian Gradien

Kami mengonfigurasi pengisian gradien untuk persegi panjang menggunakan kelas GradientAxialShading.

```csharp
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
{
Start = new Point(0, 0),
End = new Point(300, 300)
}
};
```

Ini menciptakan isian gradien dari merah ke biru, dari titik (0, 0) ke titik (300, 300).

## Langkah 6: Menyimpan File PDF

Terakhir, kami menyimpan file PDF yang dihasilkan dengan nama "AddDrawingWithGradientFill_out.pdf" di direktori yang ditentukan.

```csharp
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");
```

### Contoh kode sumber untuk Menambahkan Gambar Dengan Isi Gradien menggunakan Aspose.PDF untuk .NET 

```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
	PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
	{
		Start = new Point(0, 0),
		End = new Point(300, 300)
	}
};
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");

```
## Kesimpulan

Dalam tutorial ini, kami telah menjelaskan langkah demi langkah cara menambahkan gambar dengan isian gradien ke pemrograman grafis menggunakan Aspose.PDF untuk .NET. Sekarang Anda dapat menggunakan pengetahuan ini untuk membuat dokumen PDF yang menarik dengan desain khusus dan isian gradien.

### FAQ

#### T: Apa tujuan dari tutorial ini?

J: Tutorial ini bertujuan untuk memandu Anda melalui proses menambahkan gambar dengan isian gradien ke pemrograman dengan grafik menggunakan Aspose.PDF untuk .NET.

#### Q: Prasyarat apa saja yang diperlukan sebelum memulai?

J: Sebelum memulai, pastikan Anda telah menginstal pustaka Aspose.PDF dan menyiapkan lingkungan pengembangan Anda. Selain itu, disarankan untuk memiliki pemahaman dasar tentang pemrograman C#.

#### Q: Bagaimana cara menentukan direktori untuk menyimpan file PDF?

J: Dalam kode sumber yang disediakan, Anda dapat mengubah nilai variabel "dataDir" untuk menunjukkan direktori tempat Anda ingin menyimpan file PDF yang dihasilkan.

#### Q: Apa tujuan dari objek Graph?

A: Objek Graph berfungsi sebagai wadah untuk elemen gambar. Itu dibuat dengan dimensi tertentu dan ditambahkan ke koleksi paragraf halaman.

#### T: Bagaimana cara mengonfigurasi pengisian gradien untuk suatu bentuk?

J: Untuk mengonfigurasi pengisian gradien, Anda dapat mengatur properti FillColor dari GraphInfo bentuk menggunakan kelas GradientAxialShading. Ini memungkinkan Anda menentukan titik awal dan akhir gradien serta warna transisinya.

#### T: Dapatkah saya menyesuaikan warna dan arah pengisian gradien?

A: Ya, Anda dapat menyesuaikan warna dan arah isian gradien dengan menyesuaikan objek Warna dan menentukan titik awal dan akhir GradientAxialShading.

#### Q: Apa langkah terakhir dari tutorial ini?

J: Langkah terakhir adalah menyimpan file PDF yang dihasilkan dengan nama "AddDrawingWithGradientFill_out.pdf" di direktori yang ditentukan.

#### T: Apakah ada contoh kode sumber yang tersedia?

A: Ya, tutorial menyediakan contoh kode sumber yang dapat Anda gunakan sebagai referensi untuk mengimplementasikan langkah-langkah yang dijelaskan.

#### T: Bisakah saya menerapkan isian gradien ke bentuk lain selain persegi panjang?

J: Ya, Anda juga bisa menerapkan pengisian gradien ke bentuk lainnya. Prosesnya melibatkan konfigurasi properti FillColor dari GraphInfo bentuk menggunakan kelas GradientAxialShading.