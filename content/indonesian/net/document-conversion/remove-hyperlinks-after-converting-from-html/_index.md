---
title: Hapus Hyperlink Setelah Mengonversi Dari Html
linktitle: Hapus Hyperlink Setelah Mengonversi Dari Html
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menghapus hyperlink dari dokumen HTML setelah mengonversi ke PDF menggunakan Aspose.PDF untuk .NET dalam panduan langkah demi langkah ini.
type: docs
weight: 250
url: /id/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
## Perkenalan

Di era digital, mengonversi dokumen HTML ke PDF merupakan tugas yang umum. Namun, terkadang Anda mungkin ingin menghapus hyperlink dari PDF yang dikonversi karena berbagai alasan, seperti meningkatkan keterbacaan atau mencegah navigasi yang tidak diinginkan. Dalam tutorial ini, kita akan membahas cara melakukannya menggunakan Aspose.PDF untuk .NET. 

## Prasyarat

Sebelum menyelami kode, pastikan Anda memiliki prasyarat berikut:

1. Visual Studio: Pastikan Anda telah menginstal Visual Studio di komputer Anda. Ini akan menjadi lingkungan pengembangan Anda.
2.  Aspose.PDF untuk .NET: Anda perlu memiliki pustaka Aspose.PDF. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/pdf/net/).
3. Pengetahuan Dasar C#: Keakraban dengan pemrograman C# akan membantu Anda memahami kode dengan lebih baik.

## Paket Impor

Untuk memulai, Anda perlu mengimpor paket yang diperlukan ke dalam proyek C# Anda. Berikut cara melakukannya:

1. Buka proyek Visual Studio Anda.
2. Klik kanan pada proyek Anda di Solution Explorer dan pilih "Kelola Paket NuGet."
3.  Pencarian untuk`Aspose.PDF` dan menginstalnya.

```csharp
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
using System.IO;
```

Sekarang setelah Anda menyiapkan semuanya, mari kita uraikan proses menghapus hyperlink dari berkas HTML setelah mengonversinya ke PDF.

## Langkah 1: Siapkan Direktori Dokumen

Pertama-tama, Anda perlu menentukan jalur ke direktori dokumen Anda. Di sinilah berkas HTML Anda berada dan tempat penyimpanan PDF keluaran.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya tempat berkas HTML Anda disimpan.

## Langkah 2: Muat Dokumen HTML

 Selanjutnya, Anda akan memuat dokumen HTML menggunakan`Document` kelas dari Aspose.PDF. Kelas ini memudahkan Anda untuk bekerja dengan dokumen PDF.

```csharp
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
```

 Di sini, kita memuat file HTML bernama`SampleHtmlFile.html`Pastikan berkas ini ada di direktori yang Anda tentukan.

## Langkah 3: Simpan Dokumen ke Aliran Memori

Sebelum kita mulai memproses anotasi, kita perlu menyimpan dokumen ke aliran memori. Langkah ini penting karena mempersiapkan dokumen untuk manipulasi lebih lanjut.

```csharp
doc.Save(new MemoryStream());
```

Baris ini menyimpan dokumen dalam memori, sehingga memungkinkan kita untuk bekerja dengannya tanpa harus menulisnya ke disk.

## Langkah 4: Ulangi Melalui Anotasi

Sekarang, kita akan mengulangi anotasi dalam dokumen. Anotasi adalah elemen seperti tautan, komentar, dan sorotan. Kita secara khusus tertarik pada anotasi tautan.

```csharp
foreach (Annotation a in doc.Pages[1].Annotations)
{
    if (a.AnnotationType == AnnotationType.Link)
    {
        // Memproses anotasi tautan
    }
}
```

Dalam loop ini, kami memeriksa apakah jenis anotasi adalah tautan. Jika ya, kami melanjutkan ke langkah berikutnya.

## Langkah 5: Hapus Tindakan Hyperlink

Untuk setiap anotasi tautan, kita perlu memeriksa apakah tautan tersebut memiliki tindakan hyperlink. Jika ada, kita akan menghapus hyperlink tersebut dengan menyetel URI-nya ke string kosong.

```csharp
LinkAnnotation la = (LinkAnnotation)a;
if (la.Action is GoToURIAction)
{
    GoToURIAction gta = (GoToURIAction)la.Action;
    gta.URI = "";
```

Potongan kode ini memastikan bahwa tindakan hyperlink dihapus secara efektif.

## Langkah 6: Menyerap Fragmen Teks

Selanjutnya, kita akan menyerap fragmen teks yang terkait dengan anotasi tautan. Ini memungkinkan kita untuk memanipulasi tampilan teks.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
doc.Pages[a.PageIndex].Accept(tfa);
```

 Di sini, kita membuat`TextFragmentAbsorber` dan mengatur opsi pencariannya ke persegi panjang anotasi. Ini membantu kita menemukan teks yang ditautkan.

## Langkah 7: Ubah Tampilan Teks

Setelah kita memiliki fragmen teks, kita dapat mengubah tampilannya. Dalam kasus ini, kita akan menghapus garis bawah dan mengubah warna teks menjadi hitam.

```csharp
foreach (TextFragment tf in tfa.TextFragments)
{
    tf.TextState.Underline = false;
    tf.TextState.ForegroundColor = Color.Black;
}
```

Langkah ini meningkatkan keterbacaan teks dengan menghilangkan gaya hyperlink.

## Langkah 8: Hapus Anotasi

Setelah memodifikasi teks, kita dapat menghapus anotasi tautan dari dokumen dengan aman.

```csharp
doc.Pages[a.PageIndex].Annotations.Delete(a);
}
```

Baris ini menghapus hyperlink dari PDF, memastikan bahwa hyperlink tersebut tidak lagi ada dalam hasil akhir.

## Langkah 9: Simpan Dokumen yang Dimodifikasi

Terakhir, kita perlu menyimpan dokumen yang dimodifikasi ke berkas PDF baru. Ini adalah langkah terakhir dalam proses kita.

```csharp
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 Baris ini menyimpan dokumen dengan hyperlink dihapus, membuat file PDF baru bernama`RemoveHyperlinksFromText_out.pdf`.

## Kesimpulan

Nah, itu dia! Anda telah berhasil menghapus hyperlink dari dokumen HTML setelah mengonversinya ke PDF menggunakan Aspose.PDF untuk .NET. Proses ini tidak hanya meningkatkan keterbacaan PDF Anda, tetapi juga memberi Anda kendali atas konten yang Anda sajikan. 

## Pertanyaan yang Sering Diajukan

### Bisakah saya menghapus hyperlink dari dokumen PDF mana pun?
Ya, Anda dapat menghapus hyperlink dari dokumen PDF apa pun menggunakan Aspose.PDF untuk .NET.

### Apakah Aspose.PDF gratis untuk digunakan?
 Aspose.PDF menawarkan uji coba gratis, tetapi untuk fitur lengkap, Anda perlu membeli lisensi. Periksa[halaman pembelian](https://purchase.aspose.com/buy).

### Bagaimana jika saya mengalami masalah saat menggunakan Aspose.PDF?
 Anda dapat mencari bantuan di[forum dukungan](https://forum.aspose.com/c/pdf/10).

### Bisakah saya mengonversi format file lain ke PDF menggunakan Aspose?
Ya, Aspose mendukung berbagai format file untuk konversi ke PDF.

### Di mana saya dapat mengunduh Aspose.PDF untuk .NET?
 Anda dapat mengunduhnya dari[tautan unduhan](https://releases.aspose.com/pdf/net/).