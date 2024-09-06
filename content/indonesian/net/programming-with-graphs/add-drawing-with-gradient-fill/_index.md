---
title: Tambahkan Gambar Dengan Isian Gradien
linktitle: Tambahkan Gambar Dengan Isian Gradien
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menambahkan gambar dengan isian gradien dengan Aspose.PDF untuk .NET. Tutorial langkah demi langkah untuk membuat dokumen PDF yang menarik.
type: docs
weight: 20
url: /id/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# berikut langkah demi langkah untuk menambahkan gambar dengan isian gradien ke pemrograman dengan grafik menggunakan Aspose.PDF untuk .NET.

Pastikan Anda telah menginstal pustaka Aspose.PDF dan menyiapkan lingkungan pengembangan sebelum memulai. Anda juga harus memiliki pengetahuan dasar tentang pemrograman C#.

## Langkah 1: Pengaturan Direktori Dokumen

Dalam kode sumber yang diberikan, Anda perlu menentukan direktori tempat Anda ingin menyimpan file PDF yang dihasilkan. Ubah variabel "dataDir" ke direktori yang diinginkan.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Membuat Instansi Objek Dokumen dan Menambahkan Halaman

Kami membuat contoh kelas Dokumen dan menambahkan halaman ke dokumen ini.

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

Kita membuat objek Persegi Panjang dengan dimensi tertentu dan menambahkannya ke koleksi bentuk bagan.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```

## Langkah 5: Mengonfigurasi Isian Gradien

Kami mengonfigurasikan isian gradien untuk persegi panjang menggunakan kelas GradientAxialShading.

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

### Contoh kode sumber untuk Menambahkan Gambar dengan Isian Gradien menggunakan Aspose.PDF untuk .NET 

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

Dalam tutorial ini, kami telah menjelaskan langkah demi langkah cara menambahkan gambar dengan isian gradien ke pemrograman dengan grafis menggunakan Aspose.PDF untuk .NET. Sekarang Anda dapat menggunakan pengetahuan ini untuk membuat dokumen PDF yang menarik dengan desain khusus dan isian gradien.

### Pertanyaan yang Sering Diajukan

#### T: Apa tujuan dari tutorial ini?

A: Tutorial ini bertujuan untuk memandu Anda melalui proses penambahan gambar dengan isian gradien ke pemrograman dengan grafik menggunakan Aspose.PDF untuk .NET.

#### T: Prasyarat apa yang diperlukan sebelum memulai?

J: Sebelum memulai, pastikan Anda telah menginstal pustaka Aspose.PDF dan menyiapkan lingkungan pengembangan Anda. Selain itu, Anda disarankan untuk memiliki pemahaman dasar tentang pemrograman C#.

#### T: Bagaimana cara menentukan direktori untuk menyimpan berkas PDF?

A: Dalam kode sumber yang disediakan, Anda dapat mengubah nilai variabel "dataDir" untuk menunjukkan direktori tempat Anda ingin menyimpan file PDF yang dihasilkan.

#### T: Apa tujuan dari objek Grafik?

A: Objek Graph berfungsi sebagai wadah untuk elemen gambar. Objek ini dibuat dengan dimensi tertentu dan ditambahkan ke koleksi paragraf halaman.

#### T: Bagaimana cara mengonfigurasikan isian gradien untuk suatu bentuk?

A: Untuk mengonfigurasikan isian gradien, Anda dapat mengatur properti FillColor dari GraphInfo suatu bentuk menggunakan kelas GradientAxialShading. Ini memungkinkan Anda untuk menentukan titik awal dan akhir gradien dan warna untuk transisi di antaranya.

#### T: Dapatkah saya menyesuaikan warna dan arah isian gradien?

A: Ya, Anda dapat menyesuaikan warna dan arah isian gradien dengan menyesuaikan objek Warna dan menentukan titik awal dan akhir GradientAxialShading.

#### T: Apa langkah terakhir dari tutorial ini?

A: Langkah terakhir melibatkan penyimpanan file PDF yang dihasilkan dengan nama "AddDrawingWithGradientFill_out.pdf" di direktori yang ditentukan.

#### T: Apakah ada contoh kode sumber yang tersedia?

A: Ya, tutorial menyediakan contoh kode sumber yang dapat Anda gunakan sebagai referensi untuk menerapkan langkah-langkah yang dijelaskan.

#### T: Dapatkah saya menerapkan isian gradien ke bentuk lain selain persegi panjang?

A: Ya, Anda juga dapat menerapkan isian gradien ke bentuk lain. Prosesnya melibatkan konfigurasi properti FillColor dari GraphInfo bentuk tersebut menggunakan kelas GradientAxialShading.