---
title: Tambahkan Teks Transparan Dalam File PDF
linktitle: Tambahkan Teks Transparan Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menambahkan teks transparan dalam berkas PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 100
url: /id/net/programming-with-text/add-transparent-text/
---
Tutorial ini akan memandu Anda melalui proses penambahan teks transparan ke dokumen PDF menggunakan Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan.

## Persyaratan
Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau kompiler C# lainnya terinstal di komputer Anda.
- Aspose.PDF untuk pustaka .NET. Anda dapat mengunduhnya dari situs web resmi Aspose atau menggunakan pengelola paket seperti NuGet untuk menginstalnya.

## Langkah 1: Siapkan proyek
1. Buat proyek C# baru di lingkungan pengembangan pilihan Anda.
2. Tambahkan referensi ke pustaka Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan
Pada berkas kode tempat Anda ingin menambahkan teks transparan, tambahkan perintah penggunaan berikut di bagian atas berkas:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## Langkah 3: Mengatur direktori dokumen
 Dalam kode, temukan baris yang bertuliskan`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur ke direktori tempat dokumen Anda disimpan.

## Langkah 4: Buat contoh Dokumen baru
 Membuat instance baru`Document` objek dengan menambahkan baris kode berikut:

```csharp
Document doc = new Document();
```

## Langkah 5: Tambahkan halaman ke dokumen
 Tambahkan halaman baru ke dokumen dengan menggunakan`Add` metode dari`Pages` koleksi. Dalam kode yang diberikan, halaman baru ditetapkan ke variabel`page`.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Langkah 6: Buat objek Grafik
 Buat yang baru`Graph` objek dengan lebar dan tinggi tertentu.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
```

## Langkah 7: Buat persegi panjang dengan transparansi
 Buat persegi panjang dengan dimensi tertentu dan atur warna isiannya menjadi warna transparan menggunakan`Color.FromRgb` metode.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
canvas.Shapes.Add(rect);
```

## Langkah 8: Tambahkan objek Grafik ke halaman
 Tambahkan`Graph` keberatan terhadap kumpulan paragraf pada halaman tersebut.

```csharp
page.Paragraphs.Add(canvas);
```

## Langkah 9: Atur posisi untuk objek Grafik
 Mengatur`IsChangePosition` milik`Graph` keberatan terhadap`false` untuk mencegahnya berubah posisi.

```csharp
canvas. IsChangePosition = false;
```

## Langkah 10: Buat TextFragment dengan transparansi
 Membuat sebuah`TextFragment` objek dan mengatur isinya ke teks yang diinginkan. Mengatur`ForegroundColor` milik`TextState` ke warna dengan transparansi menggunakan`Color.FromArgb` metode.

```csharp
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
text.TextState.ForegroundColor = color;
page.Paragraphs.Add(text);
```

## Langkah 11: Simpan dokumen PDF
 Simpan dokumen PDF menggunakan`Save` metode dari`Document` obyek.

```csharp
doc.Save(dataDir + "AddTransparentText_out.pdf");
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```

### Contoh kode sumber untuk Menambahkan Teks Transparan menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buat contoh Dokumen
Document doc = new Document();
// Buat koleksi halaman ke halaman dari file PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Buat objek Grafik
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Buat contoh persegi panjang dengan dimensi tertentu
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
// Buat objek warna dari saluran warna Alpha
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Tambahkan persegi panjang ke koleksi bentuk objek Grafik
canvas.Shapes.Add(rect);
// Tambahkan objek grafik ke kumpulan paragraf objek halaman
page.Paragraphs.Add(canvas);
// Tetapkan nilai untuk tidak mengubah posisi objek grafik
canvas.IsChangePosition = false;
// Buat instance TextFragment dengan nilai sampel
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
// Buat objek warna dari saluran Alpha
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
// Tetapkan informasi warna untuk contoh teks
text.TextState.ForegroundColor = color;
// Tambahkan teks ke koleksi paragraf dari contoh halaman
page.Paragraphs.Add(text);
dataDir = dataDir + "AddTransparentText_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```


## Kesimpulan
Anda telah berhasil menambahkan teks transparan ke dokumen PDF Anda menggunakan Aspose.PDF untuk .NET. File PDF yang dihasilkan kini dapat ditemukan di jalur file keluaran yang ditentukan.

### Pertanyaan yang Sering Diajukan

#### T: Apa fokus dari tutorial ini?

J: Tutorial ini berfokus pada penambahan teks transparan ke dokumen PDF menggunakan pustaka Aspose.PDF for .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan untuk mencapai efek ini.

#### T: Namespace mana yang perlu diimpor untuk tutorial ini?

A: Pada berkas kode tempat Anda ingin menambahkan teks transparan, impor namespace berikut di awal berkas:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### T: Bagaimana cara menentukan direktori dokumen?

 A: Pada kode tersebut, temukan baris`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

#### T: Bagaimana cara membuat contoh Dokumen baru?

 A: Pada Langkah 4, Anda akan membuat instance baru`Document` objek menggunakan kode yang disediakan.

#### T: Bagaimana cara menambahkan halaman ke dokumen?

 A: Pada Langkah 5, Anda akan menambahkan halaman baru ke dokumen menggunakan`Add` metode dari`Pages` koleksi.

#### T: Bagaimana cara membuat objek Grafik?

 A: Pada Langkah 6, Anda akan membuat yang baru`Graph` objek dengan lebar dan tinggi tertentu.

#### T: Bagaimana cara membuat persegi panjang dengan transparansi?

 A: Pada Langkah 7, Anda akan membuat persegi panjang dengan dimensi tertentu dan mengatur warna isiannya menjadi warna transparan menggunakan`Color.FromRgb` metode.

#### T: Bagaimana cara menambahkan objek Grafik ke halaman?

 A: Pada Langkah 8, Anda akan menambahkan`Graph` keberatan terhadap kumpulan paragraf pada halaman tersebut.

#### T: Bagaimana cara mengatur posisi untuk objek Grafik?

 A: Pada Langkah 9, Anda akan mengatur`IsChangePosition` milik`Graph` keberatan terhadap`false` untuk mencegahnya berubah posisi.

#### T: Bagaimana cara membuat TextFragment dengan transparansi?

A: Pada Langkah 10, Anda akan membuat`TextFragment` objek dan mengatur kontennya dan`ForegroundColor` properti untuk mendapatkan teks transparan.

#### T: Bagaimana cara menyimpan dokumen PDF?

 A: Pada Langkah 11, Anda akan menyimpan dokumen PDF menggunakan`Save` metode dari`Document` obyek.

#### T: Apa hasil utama dari tutorial ini?

J: Dengan mengikuti tutorial ini, Anda telah mempelajari cara menambahkan teks transparan ke dokumen PDF menggunakan Aspose.PDF for .NET. Ini dapat berguna untuk membuat dokumen PDF yang menarik secara visual dan kreatif.