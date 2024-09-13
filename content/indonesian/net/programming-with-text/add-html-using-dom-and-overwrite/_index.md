---
title: Tambahkan HTML Menggunakan DOM Dan Penimpaan PDF
linktitle: Tambahkan HTML Menggunakan DOM dan Timpa
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menambahkan konten HTML menggunakan DOM dan penimpaan PDF di Aspose.PDF untuk .NET.
type: docs
weight: 50
url: /id/net/programming-with-text/add-html-using-dom-and-overwrite/
---
Tutorial ini akan memandu Anda melalui proses penambahan konten HTML menggunakan DOM (Document Object Model) di Aspose.PDF untuk .NET. Selain itu, Anda akan mempelajari cara menimpa gaya untuk konten HTML. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan.

## Persyaratan
Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau kompiler C# lainnya terinstal di komputer Anda.
- Aspose.PDF untuk pustaka .NET. Anda dapat mengunduhnya dari situs web resmi Aspose atau menggunakan pengelola paket seperti NuGet untuk menginstalnya.

## Langkah 1: Siapkan proyek
1. Buat proyek C# baru di lingkungan pengembangan pilihan Anda.
2. Tambahkan referensi ke pustaka Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan
Pada berkas kode tempat Anda ingin menambahkan konten HTML, tambahkan perintah penggunaan berikut di bagian atas berkas:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Langkah 3: Tetapkan direktori dokumen dan jalur file keluaran
 Dalam kode, temukan baris yang bertuliskan`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur ke direktori tempat dokumen Anda disimpan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 4: Buat objek Dokumen baru
 Membuat instance baru`Document` objek dengan menambahkan baris kode berikut:

```csharp
Document doc = new Document();
```

## Langkah 5: Tambahkan halaman ke dokumen
 Tambahkan halaman baru ke dokumen dengan menggunakan`Add` metode dari`Pages` koleksi. Dalam kode yang diberikan, halaman baru ditetapkan ke variabel`page`.

```csharp
Page page = doc.Pages.Add();
```

## Langkah 6: Buat HtmlFragment dengan konten HTML
 Membuat contoh sebuah`HtmlFragment` objek dan menyediakan konten HTML yang diinginkan. Dalam kode yang diberikan, konten HTML ditetapkan ke variabel`title`Anda dapat mengubah konten HTML sesuai kebutuhan.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## Langkah 7: Timpa gaya untuk konten HTML
 Untuk menimpa gaya konten HTML, Anda dapat memodifikasi`TextState` properti dari`HtmlFragment` objek. Dalam kode yang diberikan, jenis font diubah menjadi "Arial" dan ukuran font ditetapkan menjadi 20.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## Langkah 8: Tetapkan informasi margin
Sesuaikan margin bawah dan atas fragmen HTML jika perlu. Dalam kode yang diberikan, margin bawah ditetapkan ke 10 dan margin atas ditetapkan ke 400.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## Langkah 9: Tambahkan HtmlFragment ke halaman
 Tambahkan`HtmlFragment` keberatan terhadap kumpulan paragraf pada halaman tersebut.

```csharp
page.Paragraphs.Add(title);
```

## Langkah 10: Simpan dokumen PDF
 Simpan dokumen PDF menggunakan`Save` metode dari`Document` objek. Tentukan jalur file keluaran yang Anda tetapkan pada Langkah 3.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### Contoh kode sumber untuk Menambahkan HTML Menggunakan DOM dan Menimpa menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Membuat instance objek Dokumen
Document doc = new Document();
// Tambahkan halaman ke kumpulan halaman file PDF
Page page = doc.Pages.Add();
// Membuat instance HtmlFragment dengan konten HTML
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//Font-family dari 'Verdana' akan direset ke 'Arial'
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// Tetapkan informasi margin bawah
title.Margin.Bottom = 10;
// Tetapkan informasi margin atas
title.Margin.Top = 400;
// Tambahkan Fragmen HTML ke kumpulan paragraf halaman
page.Paragraphs.Add(title);
// Simpan file PDF
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// Simpan file PDF
doc.Save(dataDir);
```

## Kesimpulan
Anda telah berhasil menambahkan konten HTML menggunakan DOM di Aspose.PDF untuk .NET dan mengganti gaya untuk konten HTML. File PDF yang dihasilkan sekarang dapat ditemukan di jalur file keluaran yang ditentukan.

### Pertanyaan yang Sering Diajukan

#### T: Apa fokus dari tutorial ini?

J: Tutorial ini dirancang untuk memandu Anda melalui proses penambahan konten HTML ke dokumen PDF menggunakan Document Object Model (DOM) di Aspose.PDF untuk .NET. Selain itu, Anda akan mempelajari cara menimpa gaya untuk konten HTML, yang memungkinkan Anda menyesuaikan tampilannya. Tutorial ini menyediakan potongan kode sumber C# untuk menunjukkan langkah-langkah yang diperlukan.

#### T: Namespace mana yang perlu saya impor untuk tutorial ini?

A: Pada berkas kode tempat Anda ingin menambahkan konten HTML, impor namespace berikut di awal berkas:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### T: Bagaimana cara menentukan direktori dokumen dan jalur berkas keluaran?

 A: Pada kode tersebut, temukan baris`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

#### T: Bagaimana cara membuat objek Dokumen?

 A: Pada Langkah 4, Anda akan membuat instance baru`Document` objek menggunakan baris kode berikut:

```csharp
Document doc = new Document();
```

#### T: Bagaimana cara menambahkan halaman ke dokumen?

 A: Pada Langkah 5, Anda akan menambahkan halaman baru ke dokumen menggunakan`Add` metode dari`Pages` koleksi:

```csharp
Page page = doc.Pages.Add();
```

#### T: Bagaimana cara mengatur konten HTML menggunakan DOM?

 A: Pada Langkah 6, Anda akan membuat`HtmlFragment` objek dan tetapkan konten HTML yang Anda inginkan padanya. Konten HTML ditetapkan ke variabel`title`:

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### T: Bagaimana cara menimpa gaya konten HTML?

 A: Pada Langkah 7, Anda akan menimpa gaya konten HTML dengan memodifikasi`TextState` properti dari`HtmlFragment`objek. Misalnya, Anda dapat mengubah jenis font menjadi "Arial" dan mengatur ukuran font menjadi 20:

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### T: Dapatkah saya menyesuaikan margin konten HTML?

A: Ya, pada Langkah 8, Anda dapat menyesuaikan margin bawah dan atas fragmen HTML sesuai kebutuhan:

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### T: Bagaimana cara menambahkan HtmlFragment ke dokumen PDF?

 A: Pada Langkah 9, Anda akan menambahkan`HtmlFragment` objek (`title`) ke kumpulan paragraf halaman:

```csharp
page.Paragraphs.Add(title);
```

#### T: Bagaimana cara menyimpan dokumen PDF yang dihasilkan?

 A: Setelah menambahkan konten HTML dan menyesuaikan gayanya, gunakan`Save` metode dari`Document` objek untuk menyimpan dokumen PDF:

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### T: Apa inti sari dari tutorial ini?

A: Dengan mengikuti tutorial ini, Anda telah berhasil mempelajari cara menggabungkan konten HTML menggunakan Document Object Model (DOM) di Aspose.PDF untuk .NET. Selain itu, Anda telah memperoleh kemampuan untuk menimpa gaya guna menyesuaikan tampilan konten HTML dalam dokumen PDF yang dihasilkan.