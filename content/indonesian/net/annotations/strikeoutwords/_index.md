---
title: Coret Kata-kata
linktitle: Coret Kata-kata
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mencoret kata-kata dalam PDF menggunakan Aspose.PDF untuk .NET dengan panduan langkah demi langkah yang komprehensif ini. Tingkatkan keterampilan mengedit dokumen Anda.
type: docs
weight: 150
url: /id/net/annotations/strikeoutwords/
---
## Perkenalan

Pernahkah Anda merasa perlu memberi penekanan pada teks tertentu dalam PDF dengan mencoretnya? Baik saat Anda meninjau dokumen, menandai teks, atau sekadar ingin menyorot bagian tertentu, mencoret kata dapat menjadi alat yang berguna. Dalam tutorial ini, kita akan membahas cara melakukannya menggunakan Aspose.PDF untuk .NET. Panduan lengkap ini akan memandu Anda melalui setiap langkah, memastikan Anda memiliki semua informasi yang diperlukan untuk menerapkan fitur ini secara efektif dalam aplikasi .NET Anda. 

## Prasyarat

Sebelum kita masuk ke kode, ada beberapa prasyarat yang harus Anda penuhi untuk mengikuti tutorial ini:

1.  Pustaka Aspose.PDF untuk .NET: Pastikan Anda telah menginstal pustaka Aspose.PDF untuk .NET. Anda dapat[unduh disini](https://releases.aspose.com/pdf/net/).

2. .NET Framework: Pastikan Anda telah menginstal .NET Framework di komputer Anda. Tutorial ini dirancang untuk aplikasi .NET.

3. Lingkungan Pengembangan: Anda memerlukan IDE seperti Visual Studio untuk menulis dan menjalankan kode Anda.

4. Dokumen PDF: Siapkan contoh file PDF yang ingin Anda gunakan. Ini akan menjadi dokumen tempat kita akan mencoret teks.

5. Pengetahuan Dasar C#: Keakraban dengan pemrograman C# diperlukan untuk memahami dan menerapkan langkah-langkah dalam tutorial ini.

## Paket Impor

Sebelum kita dapat memulai pengkodean, kita perlu mengimpor namespace yang diperlukan dalam proyek .NET kita. Ini akan memberi kita akses ke kelas dan metode yang diperlukan untuk memanipulasi file PDF menggunakan Aspose.PDF.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

Ruang nama ini penting untuk bekerja dengan dokumen PDF, menangani teks, dan menambahkan anotasi seperti coretan.

Di bagian ini, kami akan menguraikan proses mencoret kata-kata dalam dokumen PDF menjadi beberapa langkah sederhana dan mudah dilakukan. Setiap langkah akan disertai dengan penjelasan terperinci untuk memastikan Anda memahami cara kerja semuanya.

## Langkah 1: Muat Dokumen PDF

Langkah pertama adalah memuat dokumen PDF yang ingin Anda edit. Dokumen ini akan menjadi tempat Anda mencoret kata atau frasa tertentu.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buka dokumen PDF
Document document = new Document(dataDir + "input.pdf");
```

- `dataDir` : Variabel ini menyimpan jalur ke direktori dokumen Anda. Ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya tempat berkas PDF Anda berada.
- `Document` : : Itu`Document` class mewakili dokumen PDF. Dengan meneruskan jalur file ke konstruktornya, kita membuka file PDF untuk diproses.

## Langkah 2: Buat Penyerap TextFragment untuk Menemukan Teks Tertentu

 Selanjutnya, kita akan membuat sebuah instance dari`TextFragmentAbsorber` untuk mencari fragmen teks tertentu dalam dokumen PDF. Ini memungkinkan kita menemukan teks yang ingin kita coret.

```csharp
// Buat instance TextFragment Absorber untuk mencari fragmen teks tertentu
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

- `TextFragmentAbsorber`Kelas ini digunakan untuk menemukan dan mengolah fragmen teks tertentu dalam dokumen PDF. Dalam contoh ini, kita mencari kata "Estoque". Ganti "Estoque" dengan kata atau frasa yang ingin Anda temukan dalam dokumen Anda.

## Langkah 3: Ulangi Halaman Dokumen PDF

 Sekarang setelah kita memiliki`TextFragmentAbsorber`, kita perlu mengulangi setiap halaman dokumen PDF untuk menemukan teks yang ditentukan.

```csharp
// Ulangi melalui halaman dokumen PDF
for (int i = 1; i <= document.Pages.Count; i++)
{
    // Dapatkan halaman terkini dari dokumen PDF
    Page page = document.Pages[i];
    page.Accept(textFragmentAbsorber);
}
```

- `for (int i = 1; i <= document.Pages.Count; i++)`: Perulangan ini mengulangi setiap halaman dokumen PDF.
- `document.Pages[i]`: Mengambil halaman saat ini yang sedang diproses.
- `page.Accept(textFragmentAbsorber)` :Metode ini menerapkan`TextFragmentAbsorber` ke halaman saat ini, mencari teks yang ditentukan.

## Langkah 4: Kumpulkan dan Proses Fragmen Teks

Setelah memeriksa halaman-halaman, kami akan mengumpulkan fragmen teks yang ditemukan dan mempersiapkannya untuk diproses lebih lanjut.

```csharp
// Membuat koleksi fragmen teks yang diserap
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- `TextFragmentCollection`Koleksi ini menyimpan semua fragmen teks yang ditemukan dalam dokumen. Kita akan menggunakan koleksi ini pada langkah berikutnya untuk mencoret teks.

## Langkah 5: Ulangi Fragmen Teks dan Coretlah

Pada langkah ini, kita akan mengulang setiap fragmen teks dalam koleksi kita dan menerapkan anotasi coretan padanya.

```csharp
// Ulangi koleksi fragmen teks
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

    // Dapatkan dimensi persegi panjang dari objek TextFragment
    Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
        (float)textFragment.Position.XIndent,
        (float)textFragment.Position.YIndent,
        (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width,
        (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

    // Membuat contoh Anotasi StrikeOut
    StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);

    // Mengatur properti anotasi coretan
    strikeOut.Opacity = .80f;
    strikeOut.Border = new Border(strikeOut);
    strikeOut.Color = Aspose.Pdf.Color.Red;

    // Tambahkan anotasi ke koleksi anotasi halaman fragmen teks
    textFragment.Page.Annotations.Add(strikeOut);
}
```

- `TextFragment textFragment = textFragmentCollection[j]`: Baris ini mengambil fragmen teks saat ini.
- `Aspose.Pdf.Rectangle`:Kami menghitung dimensi persegi panjang dari fragmen teks untuk menentukan di mana akan menerapkan coretan.
- `StrikeOutAnnotation`: Kelas ini mewakili anotasi coretan. Kami membuat contohnya dengan persegi panjang terhitung dan halaman saat ini.
- `strikeOut.Opacity`: Properti ini mengatur opasitas garis coretan, menjadikannya 80% terlihat.
- `strikeOut.Color`Kami mengatur warna coretan menjadi merah. Anda dapat mengubahnya ke warna apa pun yang Anda inginkan.
- `textFragment.Page.Annotations.Add(strikeOut)`: Ini menambahkan anotasi coretan ke halaman.

## Langkah 6: Simpan Dokumen PDF yang Dimodifikasi

Langkah terakhir adalah menyimpan dokumen PDF yang dimodifikasi dengan tanda coretan yang diterapkan.

```csharp
// Simpan dokumen PDF yang diperbarui
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

- `dataDir + "StrikeOutWords_out.pdf"`: Ini akan membuat nama berkas baru untuk dokumen yang dimodifikasi. Berkas asli tetap tidak berubah.
- `document.Save(dataDir)`: Menyimpan dokumen PDF dengan coretan di lokasi yang ditentukan.

## Kesimpulan

Selamat! Anda telah berhasil mencoret kata-kata tertentu dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Dengan mengikuti panduan langkah demi langkah ini, kini Anda dapat menyesuaikan dokumen PDF dengan menyorot atau mencoret teks, sehingga dokumen tersebut lebih dinamis dan disesuaikan dengan kebutuhan Anda. Baik Anda membuat anotasi pada dokumen hukum, menyiapkan laporan, atau sekadar menandai teks untuk ditinjau, tutorial ini telah membekali Anda dengan keterampilan untuk melakukannya secara efisien.

## Pertanyaan yang Sering Diajukan

### Bisakah saya mengubah warna coretan?

 Ya, Anda dapat mengubah warna dengan memodifikasi`strikeOut.Color`properti. Misalnya, Anda dapat mengaturnya ke`Aspose.Pdf.Color.Blue` untuk coretan biru.

### Apakah mungkin untuk mencoret beberapa kata sekaligus?

 Tentu saja!`TextFragmentAbsorber` dapat digunakan untuk mencari kata atau frasa apa pun dalam dokumen. Anda dapat menerapkan coretan ke beberapa contoh dengan mengulangi`TextFragmentCollection`.

### Bagaimana jika saya ingin mencoret teks pada halaman tertentu saja?

 Anda dapat mengubah loop yang berulang melalui halaman untuk hanya menyertakan halaman yang ingin Anda ubah. Misalnya,`for (int i = 1; i <= 3; i++)` akan menerapkan coretan hanya pada tiga halaman pertama.

### Bagaimana cara menyesuaikan ketebalan garis coretan?

 Anda dapat menyesuaikan ketebalan garis coretan dengan memodifikasi`Border` milik`StrikeOutAnnotation`Ini memungkinkan penyesuaian tampilan coretan.

### Apakah ada cara untuk membatalkan coretan setelah menyimpan dokumen?

Setelah dokumen disimpan, coretan tersebut bersifat permanen. Jika Anda perlu mempertahankan teks asli tanpa coretan, pertimbangkan untuk menyimpan salinan cadangan dokumen asli sebelum menerapkan modifikasi apa pun.