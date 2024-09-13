---
title: Panjang Garis
linktitle: Panjang Garis
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menyesuaikan pola garis putus-putus dalam PDF menggunakan Aspose.PDF untuk .NET dengan panduan langkah demi langkah kami. Sempurna untuk menambahkan gaya ke dokumen Anda.
type: docs
weight: 70
url: /id/net/programming-with-graphs/dash-length/
---
## Perkenalan

Apakah Anda ingin menambahkan sentuhan kreativitas pada dokumen PDF Anda dengan menyesuaikan garis dengan berbagai pola garis putus-putus? Dengan Aspose.PDF for .NET, Anda dapat dengan mudah mengubah gaya garis agar sesuai dengan kebutuhan dokumen Anda. Dalam tutorial ini, kita akan membahas cara menyesuaikan panjang garis putus-putus pada dokumen PDF menggunakan Aspose.PDF for .NET. Baik Anda menginginkan garis putus-putus atau pola titik-titik, panduan ini akan menyediakan alat dan langkah-langkah yang diperlukan untuk mencapai hasil yang Anda inginkan.

## Prasyarat

Sebelum memulai tutorial, ada beberapa hal yang Anda perlukan:

1. Aspose.PDF untuk .NET: Pastikan Anda telah menginstal Aspose.PDF untuk .NET. Jika Anda belum menginstalnya, Anda dapat mengunduhnya dari[Aspose.PDF untuk .NET](https://releases.aspose.com/pdf/net/).
2. Pengetahuan Dasar tentang C#: Tutorial ini mengasumsikan Anda memiliki pemahaman dasar tentang pemrograman C#. Jika Anda baru mengenal C#, sebaiknya Anda memoles dasar-dasarnya terlebih dahulu.
3. Visual Studio: Meskipun Anda dapat menggunakan IDE apa pun, panduan ini mengasumsikan Anda menggunakan Visual Studio untuk menulis dan menjalankan kode C# Anda.
4.  Akun Aspose: Untuk sumber daya dan dukungan tambahan, pastikan Anda memiliki akun di Aspose. Anda dapat mendaftar untuk[uji coba gratis](https://releases.aspose.com/) atau membeli lisensi[Di Sini](https://purchase.aspose.com/buy).

## Paket Impor

Untuk mulai bekerja dengan Aspose.PDF untuk .NET, Anda perlu mengimpor namespace yang relevan. Berikut cara melakukannya:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Ruang nama ini mencakup kelas dan metode yang dibutuhkan untuk bekerja dengan dokumen PDF, gambar, dan garis.

## Langkah 1: Siapkan Proyek Anda

Sebelum Anda mulai membuat kode, siapkan proyek C# baru di Visual Studio. Tambahkan pustaka Aspose.PDF for .NET ke proyek Anda melalui NuGet atau dengan merujuk DLL secara manual. 

## Langkah 2: Inisialisasi Dokumen

Mulailah dengan membuat dokumen PDF baru dan menambahkan halaman ke dalamnya. Ini adalah kanvas tempat Anda akan menggambar garis.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Membuat contoh dokumen
Document doc = new Document();

// Tambahkan halaman ke koleksi halaman objek Dokumen
Page page = doc.Pages.Add();
```

 Di sini, kita membuat`Document` objek dan tambahkan yang baru`Page` Ini menjadi dasar untuk menggambar garis Anda.

## Langkah 3: Buat Objek Gambar

 Selanjutnya, buatlah`Graph` objek yang mewakili area tempat Anda akan menggambar. Tentukan dimensinya sesuai dengan kebutuhan Anda.

```csharp
// Membuat objek Gambar dengan dimensi tertentu
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100.0, 400.0);

// Tambahkan objek gambar ke koleksi paragraf dari contoh halaman
page.Paragraphs.Add(canvas);
```

 Itu`Graph` Objek berfungsi sebagai wadah untuk elemen gambar Anda. Di sini, objek diatur ke lebar 100 unit dan tinggi 400 unit.

## Langkah 4: Tentukan Garisnya

 Sekarang saatnya untuk membuat`Line`objek. Tentukan titik awal dan akhir garis dan sesuaikan gayanya.

```csharp
// Buat objek Garis
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
```

Garis ini dimulai pada koordinat (100, 100) dan berakhir pada (200, 100). Anda dapat menyesuaikan koordinat ini agar sesuai dengan kebutuhan spesifik Anda.

## Langkah 5: Sesuaikan Gaya Garis

Atur warna dan pola garis putus-putus. Di sinilah Anda dapat membuat garis Anda menonjol.

```csharp
// Mengatur warna untuk objek Garis
line.GraphInfo.Color = Aspose.Pdf.Color.Red;

// Tentukan larik tanda hubung untuk objek garis
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };

// Mengatur fase tanda hubung untuk instance Garis
line.GraphInfo.DashPhase = 1;
```

- `line.GraphInfo.Color`: Mengatur warna garis. Dalam hal ini, warnanya merah.
- `line.GraphInfo.DashArray` : Menentukan pola tanda hubung. Di sini,`{ 0, 1, 0 }` menunjukkan pola putus-putus.
- `line.GraphInfo.DashPhase`: Menyesuaikan titik awal pola garis putus-putus.

## Langkah 6: Tambahkan Garis ke Gambar

 Dengan garis yang sudah ditata, tambahkan ke`Graph` obyek.

```csharp
// Tambahkan garis ke koleksi bentuk objek gambar
canvas.Shapes.Add(line);
```

Ini mengintegrasikan garis ke kanvas gambar Anda.

## Langkah 7: Simpan Dokumen

Terakhir, simpan dokumen Anda di jalur yang ditentukan. Di sinilah berkas PDF akan dibuat.

```csharp
dataDir = dataDir + "DashLength_out.pdf";

// Simpan dokumen PDF
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);
```

Baris kode ini menyimpan dokumen PDF dan memberikan pesan konfirmasi yang menunjukkan lokasi penyimpanan berkas.

## Kesimpulan

Menyesuaikan gaya garis dalam dokumen PDF dapat menambahkan sentuhan profesional pada laporan, presentasi, dan dokumen lainnya. Dengan mengikuti tutorial ini, Anda telah mempelajari cara menyesuaikan panjang garis putus-putus menggunakan Aspose.PDF untuk .NET. Baik Anda membuat garis putus-putus sederhana atau pola yang lebih rumit, Aspose.PDF menyediakan fleksibilitas yang Anda butuhkan untuk membuat dokumen Anda menonjol. Bereksperimenlah dengan berbagai pola dan warna garis putus-putus untuk menemukan gaya yang paling sesuai dengan kebutuhan Anda.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara menginstal Aspose.PDF untuk .NET?
 Anda dapat menginstalnya melalui NuGet di Visual Studio atau mengunduhnya dari[Situs web Aspose](https://releases.aspose.com/pdf/net/).

### Dapatkah saya menggunakan Aspose.PDF untuk .NET secara gratis?
 Ya, Aspose menawarkan[uji coba gratis](https://releases.aspose.com/) sehingga Anda dapat menguji fitur-fiturnya sebelum membeli lisensi.

### Kustomisasi apa lagi yang dapat saya buat pada baris dalam PDF?
 Anda dapat menyesuaikan ketebalan garis, warna, dan pola garis putus-putus. Lihat[dokumentasi](https://reference.aspose.com/pdf/net/) untuk lebih jelasnya.

### Bagaimana saya bisa mendapatkan dukungan jika saya mengalami masalah?
 Anda dapat mengakses dukungan melalui[Forum Aspose](https://forum.aspose.com/c/pdf/10).

### Di mana saya dapat membeli lisensi Aspose.PDF untuk .NET?
Anda dapat membeli lisensi[Di Sini](https://purchase.aspose.com/buy).