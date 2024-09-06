---
title: Tambahkan Daftar HTML yang Diurutkan ke dalam Dokumen
linktitle: Tambahkan Daftar HTMLOrdered ke dalam Dokumen
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menambahkan daftar HTML yang diurutkan ke dokumen menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 30
url: /id/net/programming-with-text/add-html-ordered-list-into-documents/
---
Dalam tutorial ini, Anda akan mempelajari cara menggunakan pustaka Aspose.PDF for .NET untuk menambahkan daftar HTML yang diurutkan ke dalam dokumen. Kode yang diberikan menunjukkan langkah-langkah yang diperlukan untuk menyelesaikan tugas ini.

## Persyaratan
Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau kompiler C# lainnya terinstal di komputer Anda.
- Aspose.PDF untuk pustaka .NET. Anda dapat mengunduhnya dari situs web resmi Aspose atau menggunakan pengelola paket seperti NuGet untuk menginstalnya.

## Langkah 1: Siapkan proyek
1. Buat proyek C# baru di lingkungan pengembangan pilihan Anda.
2. Tambahkan referensi ke pustaka Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan
Pada berkas kode tempat Anda ingin menambahkan daftar HTML yang diurutkan, tambahkan perintah penggunaan berikut di bagian atas berkas:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Langkah 3: Tetapkan direktori dokumen dan jalur file keluaran
 Dalam kode, temukan baris yang bertuliskan`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur ke direktori tempat dokumen Anda disimpan.

 Selanjutnya, cari baris yang bertuliskan`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` dan mengganti`"AddHTMLOrderedListIntoDocuments_out.pdf"` dengan nama yang diinginkan untuk berkas PDF keluaran Anda.

## Langkah 4: Buat objek Dokumen baru
 Membuat instance baru`Document` objek dengan menambahkan baris kode berikut:

```csharp
Document doc = new Document();
```

## Langkah 5: Buat objek HtmlFragment dengan konten HTML
 Membuat contoh sebuah`HtmlFragment` objek dengan konten HTML yang ingin Anda tambahkan ke dokumen. Dalam kode yang diberikan, konten HTML ditetapkan ke variabel`t`Anda dapat mengubah konten HTML sesuai kebutuhan.

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## Langkah 6: Tambahkan halaman ke dokumen
 Tambahkan halaman baru ke dokumen dengan menggunakan`Add` metode dari`Pages`koleksi. Dalam kode yang diberikan, halaman baru ditetapkan ke variabel`page`.

```csharp
Page page = doc.Pages.Add();
```

## Langkah 7: Tambahkan HtmlFragment ke halaman
 Tambahkan`HtmlFragment` menolak halaman tersebut dengan menggunakan`Add` metode dari`Paragraphs` koleksi.

```csharp
page.Paragraphs.Add(t);
```

## Langkah 8: Simpan dokumen PDF
 Simpan file PDF yang dihasilkan menggunakan`Save` metode dari`Document` objek. Tentukan jalur file keluaran yang Anda tetapkan pada Langkah 3.

```csharp
doc.Save(outFile);
```

### Contoh kode sumber untuk Menambahkan Daftar HTML yang Diurutkan ke dalam Dokumen menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Jalur ke dokumen keluaran.
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// Membuat instance objek Dokumen
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
Anda telah berhasil menambahkan daftar HTML yang diurutkan ke dalam dokumen menggunakan Aspose.PDF untuk .NET. File PDF yang dihasilkan sekarang dapat ditemukan di jalur file keluaran yang ditentukan.

Ingatlah untuk menyesuaikan konten HTML dan menyesuaikan kode menurut kebutuhan spesifik Anda.

### Pertanyaan yang Sering Diajukan

#### T: Apa tujuan dari tutorial ini?

J: Tutorial ini bertujuan untuk memandu Anda melalui proses penambahan daftar HTML yang diurutkan ke dalam dokumen menggunakan pustaka Aspose.PDF for .NET. Tutorial ini menyediakan petunjuk langkah demi langkah dan cuplikan kode untuk membantu Anda mencapai tugas ini.

#### T: Namespace mana yang perlu saya impor untuk tutorial ini?

A: Anda perlu mengimpor namespace berikut di bagian atas berkas kode Anda:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### T: Bagaimana cara menentukan direktori dokumen dan jalur berkas keluaran?

 A: Pada kode tersebut, temukan baris`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda. Temukan juga baris`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` dan mengganti`"AddHTMLOrderedListIntoDocuments_out.pdf"` dengan nama berkas PDF keluaran yang Anda inginkan.

#### T: Dapatkah saya menyesuaikan konten HTML yang ditambahkan ke dokumen?

 A: Tentu saja! Pada Langkah 5, Anda akan membuat`HtmlFragment` objek bernama`t` yang berisi konten HTML. Anda dapat mengubah konten HTML di dalam tanda kutip belakang sesuai dengan kebutuhan Anda.

#### T: Bagaimana cara menambahkan daftar HTML yang diurutkan ke suatu halaman dalam dokumen?

 A: Pada Langkah 7, Anda akan menambahkan`HtmlFragment` objek (`t` ) ke halaman menggunakan`Add` metode dari`Paragraphs`koleksi. Ini akan mengintegrasikan daftar HTML yang diurutkan ke dalam dokumen dengan lancar.

#### T: Bagaimana cara menyimpan dokumen PDF yang dihasilkan?

 A: Setelah menambahkan konten HTML dan mengaturnya di halaman, Anda dapat menyimpan dokumen PDF menggunakan`Save` metode dari`Document` objek. Pastikan untuk memberikan jalur file keluaran yang benar yang Anda tetapkan sebelumnya.

#### T: Dapatkah Anda memberikan ringkasan contoh kode sumber untuk referensi?

A: Tentu saja! Berikut ini adalah versi ringkasan dari contoh kode sumber yang disediakan dalam tutorial ini:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
Document doc = new Document();
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
Page page = doc.Pages.Add();
page.Paragraphs.Add(t);
doc.Save(outFile);
```

#### T: Apa inti sari dari tutorial ini?

J: Dengan mengikuti tutorial ini, Anda telah berhasil mempelajari cara memanfaatkan pustaka Aspose.PDF for .NET untuk memasukkan daftar HTML yang diurutkan ke dalam dokumen. Pengetahuan baru ini dapat diterapkan untuk meningkatkan proses pembuatan dan manipulasi dokumen Anda.