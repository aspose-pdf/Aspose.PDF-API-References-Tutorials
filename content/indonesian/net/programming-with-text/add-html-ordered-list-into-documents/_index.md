---
title: Tambahkan Daftar Urutan HTML ke dalam Dokumen
linktitle: Tambahkan Daftar Pesanan HTML ke dalam Dokumen
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menambahkan daftar urutan HTML ke dokumen menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 30
url: /id/net/programming-with-text/add-html-ordered-list-into-documents/
---
Dalam tutorial ini, Anda akan mempelajari cara menggunakan pustaka Aspose.PDF untuk .NET untuk menambahkan daftar urutan HTML ke dalam dokumen. Kode yang diberikan menunjukkan langkah-langkah yang diperlukan untuk menyelesaikan tugas ini.

## Persyaratan
Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau kompiler C# lainnya yang diinstal pada mesin Anda.
- Aspose.PDF untuk perpustakaan .NET. Anda dapat mendownloadnya dari situs resmi Aspose atau menggunakan manajer paket seperti NuGet untuk menginstalnya.

## Langkah 1: Siapkan proyek
1. Buat proyek C# baru di lingkungan pengembangan pilihan Anda.
2. Tambahkan referensi ke perpustakaan Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan
Dalam file kode tempat Anda ingin menambahkan daftar urutan HTML, tambahkan arahan penggunaan berikut di bagian atas file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Langkah 3: Atur direktori dokumen dan jalur file keluaran
 Dalam kode, temukan baris yang bertuliskan`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur ke direktori tempat dokumen Anda disimpan.

 Selanjutnya, cari baris yang bertuliskan`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` dan ganti`"AddHTMLOrderedListIntoDocuments_out.pdf"` dengan nama yang diinginkan untuk file PDF keluaran Anda.

## Langkah 4: Buat objek Dokumen baru
 Buat instance yang baru`Document` objek dengan menambahkan baris kode berikut:

```csharp
Document doc = new Document();
```

## Langkah 5: Buat objek HtmlFragment dengan konten HTML
 Buat contoh sebuah`HtmlFragment` objek dengan konten HTML yang ingin Anda tambahkan ke dokumen. Dalam kode yang disediakan, konten HTML ditugaskan ke variabel`t`. Anda dapat memodifikasi konten HTML sesuai kebutuhan.

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## Langkah 6: Tambahkan halaman ke dokumen
 Tambahkan halaman baru ke dokumen dengan menggunakan`Add` metode`Pages`koleksi. Dalam kode yang disediakan, halaman baru ditugaskan ke variabel`page`.

```csharp
Page page = doc.Pages.Add();
```

## Langkah 7: Tambahkan HtmlFragment ke halaman
 Tambahkan`HtmlFragment` objek ke halaman dengan menggunakan`Add` metode`Paragraphs` koleksi.

```csharp
page.Paragraphs.Add(t);
```

## Langkah 8: Simpan dokumen PDF
 Simpan file PDF yang dihasilkan menggunakan`Save` metode`Document` obyek. Tentukan jalur file keluaran yang Anda atur di Langkah 3.

```csharp
doc.Save(outFile);
```

### Contoh kode sumber untuk Menambahkan Daftar Pesanan HTML ke dalam Dokumen menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Jalur ke dokumen keluaran.
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// Buat instance objek Dokumen
Document doc = new Document();
// Buat instance objek HtmlFragment dengan fragmen HTML yang sesuai
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
// Tambahkan Halaman di Koleksi Halaman
Page page = doc.Pages.Add();
// Tambahkan HtmlFragment di dalam halaman
page.Paragraphs.Add(t);
// Simpan file PDF yang dihasilkan
doc.Save(outFile);
```

## Kesimpulan
Anda telah berhasil menambahkan daftar urutan HTML ke dalam dokumen menggunakan Aspose.PDF untuk .NET. File PDF yang dihasilkan sekarang dapat ditemukan di jalur file keluaran yang ditentukan.

Ingatlah untuk menyesuaikan konten HTML dan menyesuaikan kode sesuai dengan kebutuhan spesifik Anda.

### FAQ

#### T: Apa tujuan dari tutorial ini?

J: Tutorial ini bertujuan untuk memandu Anda melalui proses menambahkan daftar urutan HTML ke dalam dokumen menggunakan pustaka Aspose.PDF untuk .NET. Ini memberikan petunjuk langkah demi langkah dan cuplikan kode untuk membantu Anda mencapai tugas ini.

#### T: Namespace manakah yang perlu saya impor untuk tutorial ini?

J: Anda perlu mengimpor namespace berikut di bagian atas file kode Anda:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### T: Bagaimana cara menentukan direktori dokumen dan jalur file keluaran?

 A: Di dalam kode, temukan barisnya`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda. Temukan juga garisnya`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` dan ganti`"AddHTMLOrderedListIntoDocuments_out.pdf"` dengan nama file PDF keluaran yang Anda inginkan.

#### T: Dapatkah saya menyesuaikan konten HTML yang ditambahkan ke dokumen?

 J: Tentu saja! Pada Langkah 5, Anda akan membuat`HtmlFragment` objek bernama`t` yang menyimpan konten HTML. Anda dapat memodifikasi konten HTML di dalam backticks agar sesuai dengan kebutuhan Anda.

#### T: Bagaimana cara menambahkan daftar urutan HTML ke halaman dalam dokumen?

 J: Pada Langkah 7, Anda akan menambahkan`HtmlFragment` objek (`t` ) ke halaman menggunakan`Add` metode`Paragraphs`koleksi. Ini akan dengan mulus mengintegrasikan daftar urutan HTML ke dalam dokumen.

#### Q: Bagaimana cara menyimpan dokumen PDF yang dihasilkan?

 A: Setelah menambahkan konten HTML dan menyusunnya dalam sebuah halaman, Anda dapat menyimpan dokumen PDF menggunakan`Save` metode`Document` obyek. Pastikan untuk memberikan jalur file keluaran yang benar yang Anda atur sebelumnya.

#### T: Dapatkah Anda memberikan ringkasan contoh kode sumber untuk referensi?

J: Tentu saja! Berikut adalah versi ringkasan dari contoh kode sumber yang disediakan dalam tutorial ini:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
Document doc = new Document();
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
Page page = doc.Pages.Add();
page.Paragraphs.Add(t);
doc.Save(outFile);
```

#### T: Apa inti dari tutorial ini?

J: Dengan mengikuti tutorial ini, Anda telah berhasil mempelajari cara memanfaatkan pustaka Aspose.PDF untuk .NET untuk memasukkan daftar urutan HTML ke dalam dokumen. Pengetahuan baru ini dapat diterapkan untuk meningkatkan proses pembuatan dan manipulasi dokumen Anda.