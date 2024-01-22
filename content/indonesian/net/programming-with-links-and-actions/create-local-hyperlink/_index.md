---
title: Buat Hyperlink Lokal Dalam File PDF
linktitle: Buat Hyperlink Lokal Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Buat hyperlink lokal dengan mudah dalam file PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 40
url: /id/net/programming-with-links-and-actions/create-local-hyperlink/
---
Membuat hyperlink lokal dalam file PDF memungkinkan Anda membuat link yang dapat diklik yang membawa pengguna ke halaman lain dalam dokumen PDF yang sama. Dengan Aspose.PDF untuk .NET, Anda dapat dengan mudah membuat tautan tersebut dengan mengikuti kode sumber berikut:

## Langkah 1: Impor Perpustakaan yang Diperlukan

Sebelum memulai, Anda perlu mengimpor perpustakaan yang diperlukan untuk proyek C# Anda. Berikut adalah arahan impor yang diperlukan:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.InteractiveFeatures;
```

## Langkah 2: Tetapkan jalur ke folder dokumen

 Pada langkah ini, Anda perlu menentukan jalur ke folder tempat Anda ingin menyimpan file PDF yang dihasilkan. Mengganti`"YOUR DOCUMENT DIRECTORY"`dalam kode berikut dengan jalur sebenarnya ke folder dokumen Anda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 3: Buat sebuah instance dari Dokumen

 Kami akan membuat sebuah instance dari`Document` kelas untuk mewakili dokumen PDF kami. Ini kode yang sesuai:

```csharp
Document doc = new Document();
```

## Langkah 4: Tambahkan halaman dan teks dengan hyperlink

Pada langkah ini, kita akan menambahkan halaman ke dokumen PDF kita dan menambahkan beberapa teks yang berisi hyperlink lokal. Kami akan menentukan halaman target untuk setiap link. Ini kode yang sesuai:

```csharp
Page page = doc.Pages.Add();

TextFragment text = new TextFragment("Link to page 7");
LocalHyperlink link = new LocalHyperlink();
link.TargetPageNumber = 7;
text. Hyperlink = link;
page.Paragraphs.Add(text);

text = new TextFragment("Link to page 1");
text. IsInNewPage = true;
link = new LocalHyperlink();
link.TargetPageNumber = 1;
text. Hyperlink = link;
page.Paragraphs.Add(text);
```

## Langkah 5: Simpan dokumen yang diperbarui

 Sekarang mari simpan file PDF yang diperbarui menggunakan`Save` metode`doc` obyek. Ini kode yang sesuai:

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
doc.Save(dataDir);
```

### Contoh kode sumber untuk Membuat Hyperlink Lokal menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buat contoh Dokumen
Document doc = new Document();
// Tambahkan halaman ke halaman koleksi file PDF
Page page = doc.Pages.Add();
// Buat instance Fragmen Teks
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
// Buat contoh hyperlink lokal
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink();
// Tetapkan halaman target untuk contoh tautan
link.TargetPageNumber = 7;
// Setel hyperlink TextFragment
text.Hyperlink = link;
//Tambahkan teks ke kumpulan paragraf Halaman
page.Paragraphs.Add(text);
// Buat instance TextFragment baru
text = new TextFragment("link page number test to page 1");
// TextFragment harus ditambahkan di halaman baru
text.IsInNewPage = true;
// Buat contoh hyperlink lokal lainnya
link = new LocalHyperlink();
// Tetapkan halaman Target untuk hyperlink kedua
link.TargetPageNumber = 1;
// Setel tautan untuk TextFragment kedua
text.Hyperlink = link;
// Tambahkan teks ke kumpulan paragraf objek halaman
page.Paragraphs.Add(text);    
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
// Simpan dokumen yang diperbarui
doc.Save(dataDir);
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);            
```

## Kesimpulan

Selamat! Sekarang Anda memiliki panduan langkah demi langkah untuk membuat hyperlink lokal di PDF menggunakan Aspose.PDF untuk .NET. Anda dapat menggunakan kode ini untuk membuat link yang dapat diklik yang mengarahkan pengguna ke halaman lain di dokumen yang sama.

Pastikan untuk memeriksa dokumentasi resmi Aspose.PDF untuk informasi lebih lanjut tentang fitur hyperlink tingkat lanjut.

### FAQ untuk membuat hyperlink lokal dalam file PDF

#### T: Apa yang dimaksud dengan hyperlink lokal dalam file PDF?

J: Hyperlink lokal dalam file PDF adalah link yang dapat diklik yang mengarahkan pengguna ke halaman berbeda dalam dokumen yang sama. Tautan ini meningkatkan navigasi dan memungkinkan pembaca mengakses bagian relevan dengan cepat.

#### T: Apa manfaat hyperlink lokal terhadap dokumen PDF saya?

J: Hyperlink lokal menyediakan cara efisien untuk menghubungkan konten terkait dalam dokumen PDF yang sama. Mereka meningkatkan pengalaman pengguna dengan memungkinkan pembaca melompat ke bagian tertentu dengan cepat tanpa menggulir seluruh dokumen.

#### T: Bagaimana Aspose.PDF untuk .NET mendukung pembuatan hyperlink lokal?
J: Aspose.PDF untuk .NET menawarkan dukungan komprehensif untuk membuat hyperlink lokal. Tutorial langkah demi langkah yang disediakan dalam panduan ini menunjukkan cara menambahkan hyperlink lokal ke dokumen PDF Anda menggunakan C#.

#### T: Dapatkah saya menyesuaikan tampilan hyperlink lokal?

J: Ya, Anda dapat menyesuaikan tampilan hyperlink lokal, termasuk warna dan gaya teks, untuk memastikannya cocok dengan desain dokumen Anda dan memberikan pengalaman visual yang konsisten.

#### T: Apakah mungkin membuat beberapa hyperlink lokal dalam satu halaman PDF?

J: Tentu saja! Anda dapat membuat beberapa hyperlink lokal dalam satu halaman PDF, memungkinkan pembaca untuk melompat ke berbagai bagian atau halaman sesuai kebutuhan. Setiap hyperlink lokal dapat disesuaikan dengan targetnya masing-masing.

#### T: Bisakah saya menautkan ke bagian halaman tertentu menggunakan hyperlink lokal?

J: Meskipun hyperlink lokal biasanya menavigasi ke seluruh halaman, Anda dapat membuat jangkar atau penanda dalam dokumen PDF Anda untuk mencapai tautan yang ditargetkan. Aspose.PDF untuk .NET mendukung berbagai opsi hyperlink.

#### T: Bagaimana cara memverifikasi bahwa hyperlink lokal saya berfungsi dengan benar?

J: Dengan mengikuti tutorial dan contoh kode yang disediakan, Anda dapat dengan percaya diri membuat hyperlink lokal yang berfungsi. Anda dapat menguji tautan dengan membuka dokumen PDF yang dihasilkan dan mengeklik teks hyperlink.

#### T: Apakah ada batasan saat menggunakan hyperlink lokal?

J: Hyperlink lokal adalah cara efektif untuk meningkatkan navigasi dokumen, namun penting untuk memastikan bahwa struktur dokumen tetap jelas dan intuitif. Hyperlink dan jangkar yang diberi label dengan benar berkontribusi pada pengalaman pengguna yang positif.

#### T: Bisakah saya membuat hyperlink lokal di dalam tabel atau gambar?

J: Ya, Anda dapat membuat hyperlink lokal dalam berbagai elemen dokumen PDF Anda, termasuk tabel, gambar, dan teks. Aspose.PDF untuk .NET menawarkan fleksibilitas dalam menambahkan hyperlink ke berbagai jenis konten.