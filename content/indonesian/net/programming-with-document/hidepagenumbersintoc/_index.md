---
title: Sembunyikan Nomor Halaman Di Daftar Isi
linktitle: Sembunyikan Nomor Halaman Di Daftar Isi
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menyembunyikan nomor halaman di Daftar Isi menggunakan Aspose.PDF untuk .NET. Ikuti panduan terperinci ini dengan contoh kode untuk membuat PDF profesional.
type: docs
weight: 220
url: /id/net/programming-with-document/hidepagenumbersintoc/
---
## Perkenalan

Saat Anda bekerja dengan PDF, terkadang Anda mungkin ingin membuat Daftar Isi (TOC) tetapi tetap rapi dengan menyembunyikan nomor halaman. Mungkin dokumen akan lebih baik tanpa nomor halaman, atau mungkin itu adalah pilihan estetika. Apa pun alasan Anda, jika Anda bekerja dengan Aspose.PDF untuk .NET, tutorial ini akan menunjukkan kepada Anda cara menyembunyikan nomor halaman di TOC Anda.

## Prasyarat

Sebelum kita mulai, ada beberapa hal yang perlu Anda persiapkan. Berikut daftar periksa singkatnya:

- Visual Studio Terpasang: Anda memerlukan versi Visual Studio yang berfungsi untuk membuat kode.
- Pustaka Aspose.PDF untuk .NET: Pastikan Anda telah menginstal pustaka Aspose.PDF untuk .NET.
  -  Tautan unduhan:[Aspose.PDF untuk .NET](https://releases.aspose.com/pdf/net/)
- Lisensi Sementara: Jika Anda menguji fitur-fiturnya, ada baiknya Anda memiliki lisensi sementara.
  -  Lisensi sementara:[Dapatkan di sini](https://purchase.aspose.com/temporary-license/)

## Paket Impor

Sebelum memulai kode, pastikan Anda mengimpor namespace berikut ke dalam proyek C# Anda. Namespace ini akan menyediakan kelas dan metode yang diperlukan untuk bekerja dengan dokumen PDF dan membuat Daftar Isi (TOC).

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Sekarang lingkungan Anda sudah siap dan paket-paket telah diimpor, mari kita bahas setiap langkah dari proses tersebut. Kami akan membahas setiap bagian dari kode untuk memastikan kejelasan, sehingga Anda dapat mengikutinya dengan mudah.

## Langkah 1: Inisialisasi Dokumen PDF Anda

Hal pertama yang perlu kita lakukan adalah membuat dokumen PDF baru dan menambahkan halaman untuk Daftar Isi (TOC).


```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
```

- dataDir: Ini adalah direktori tempat file keluaran Anda akan disimpan.
- Document(): Menginisialisasi dokumen PDF baru.
- Pages.Add(): Menambahkan halaman kosong baru ke dokumen, yang nantinya akan memuat TOC Anda.

## Langkah 2: Siapkan Info Daftar Isi dan Judul

Berikutnya, kita akan menentukan informasi TOC, termasuk mengatur judul yang akan muncul di bagian atas TOC.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

- TocInfo: Objek ini menyimpan semua informasi tentang TOC.
- TextFragment: Mewakili teks judul TOC, di sini kita mengaturnya sebagai "Daftar Isi."
- FontStyle: Kami memberi gaya pada judul TOC dengan mengatur ukurannya menjadi 20 dan membuatnya tebal.
- tocPage.TocInfo: Kami menetapkan info TOC ke halaman yang akan menampilkan TOC.

## Langkah 3: Sembunyikan Nomor Halaman di Daftar Isi

Sekarang saatnya bagian yang menyenangkan! Di sinilah kita mengonfigurasi TOC untuk menyembunyikan nomor halaman.

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
```

-  IsShowPageNumbers: Ini adalah tombol ajaib yang menyembunyikan nomor halaman. Atur ke`false`, dan nomor halaman tidak akan muncul di Daftar Isi.
- FormatArrayLength: Kami menetapkan ini ke 4, yang menunjukkan bahwa kami ingin menentukan pemformatan untuk empat tingkat judul TOC.

## Langkah 4: Sesuaikan Pemformatan Daftar Isi

Untuk menambahkan lebih banyak gaya ke Daftar Isi Anda, sekarang kita akan menentukan pemformatan untuk berbagai tingkat judul.

```csharp
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
```

- FormatArray: Array ini mengontrol pemformatan entri TOC. Setiap indeks mewakili tingkat judul yang berbeda.
- Margin dan TextStyle: Kami mengatur margin dan menerapkan gaya font seperti tebal, miring, dan garis bawah untuk setiap tingkat judul.

## Langkah 5: Tambahkan Judul ke Dokumen

Terakhir, mari tambahkan judul sebenarnya yang akan menjadi bagian Daftar Isi.

```csharp
Page page = doc.Pages.Add();
for (int Level = 1; Level != 5; Level++)
{ 
    Heading heading2 = new Heading(Level); 
    TextSegment segment2 = new TextSegment(); 
    heading2.TocPage = tocPage; 
    heading2.Segments.Add(segment2); 
    heading2.IsAutoSequence = true; 
    segment2.Text = "this is heading of level " + Level; 
    heading2.IsInList = true; 
    page.Paragraphs.Add(heading2); 
}
```

- Heading dan TextSegment: Ini merupakan judul yang akan muncul di TOC Anda. Setiap level memiliki judulnya sendiri.
- IsAutoSequence: Secara otomatis memberi nomor pada judul.
- IsInList: Memastikan bahwa setiap judul muncul di TOC.

## Langkah 6: Simpan Dokumen

Setelah semuanya diatur, simpan dokumen PDF ke berkas keluaran yang Anda tentukan.

```csharp
doc.Save(outFile);
```

Selesai! Anda telah berhasil membuat PDF dengan Daftar Isi, dan nomor halamannya disembunyikan!

## Kesimpulan

Membuat Daftar Isi dalam PDF dan menyembunyikan nomor halaman mungkin tampak rumit, tetapi dengan Aspose.PDF untuk .NET, semuanya menjadi mudah. Dengan mengikuti panduan langkah demi langkah ini, Anda telah mempelajari cara menyesuaikan format TOC, menyembunyikan nomor halaman, dan menerapkan berbagai gaya pada judul. Kini Anda dapat membuat PDF profesional yang disesuaikan dengan kebutuhan Anda.

## Pertanyaan yang Sering Diajukan

### Dapatkah saya menampilkan nomor halaman untuk judul tertentu di Daftar Isi?
Tidak, Aspose.PDF menyembunyikan atau menampilkan nomor halaman untuk seluruh TOC. Anda tidak dapat menyembunyikannya secara selektif untuk entri tertentu.

### Apakah mungkin untuk menambahkan lebih banyak level ke Daftar Isi?
 Ya, Anda dapat meningkatkannya`FormatArrayLength` untuk menentukan lebih banyak tingkatan judul TOC.

### Bagaimana cara mengubah font untuk semua entri TOC?
 Anda dapat mengubah font dengan memodifikasi`TextState.Font` properti untuk setiap level di`FormatArray`.

### Bisakah saya menyisipkan hyperlink di Daftar Isi?
 Ya, Anda dapat menautkan setiap entri TOC ke bagian tertentu dalam dokumen menggunakan`Heading.TocPage` milik.

### Apakah saya memerlukan lisensi untuk Aspose.PDF?
Ya, lisensi yang valid diperlukan untuk penggunaan produksi. Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/) untuk menguji fitur-fiturnya.