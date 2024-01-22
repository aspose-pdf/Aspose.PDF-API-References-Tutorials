---
title: Tambahkan HTML Menggunakan DOM dan Timpa PDF
linktitle: Tambahkan HTML Menggunakan DOM Dan Timpa
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menambahkan konten HTML menggunakan penimpaan DOM dan PDF di Aspose.PDF untuk .NET.
type: docs
weight: 50
url: /id/net/programming-with-text/add-html-using-dom-and-overwrite/
---
Tutorial ini akan memandu Anda melalui proses menambahkan konten HTML menggunakan DOM (Document Object Model) di Aspose.PDF untuk .NET. Selain itu, Anda akan mempelajari cara menimpa gaya untuk konten HTML. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan.

## Persyaratan
Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau kompiler C# lainnya yang diinstal pada mesin Anda.
- Aspose.PDF untuk perpustakaan .NET. Anda dapat mendownloadnya dari situs resmi Aspose atau menggunakan manajer paket seperti NuGet untuk menginstalnya.

## Langkah 1: Siapkan proyek
1. Buat proyek C# baru di lingkungan pengembangan pilihan Anda.
2. Tambahkan referensi ke perpustakaan Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan
Dalam file kode tempat Anda ingin menambahkan konten HTML, tambahkan arahan penggunaan berikut di bagian atas file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Langkah 3: Atur direktori dokumen dan jalur file keluaran
 Dalam kode, temukan baris yang bertuliskan`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur ke direktori tempat dokumen Anda disimpan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 4: Buat objek Dokumen baru
 Buat instance yang baru`Document` objek dengan menambahkan baris kode berikut:

```csharp
Document doc = new Document();
```

## Langkah 5: Tambahkan halaman ke dokumen
 Tambahkan halaman baru ke dokumen dengan menggunakan`Add` metode`Pages`koleksi. Dalam kode yang disediakan, halaman baru ditugaskan ke variabel`page`.

```csharp
Page page = doc.Pages.Add();
```

## Langkah 6: Buat HtmlFragment dengan konten HTML
 Buat contoh sebuah`HtmlFragment` objek dan berikan konten HTML yang diinginkan. Dalam kode yang disediakan, konten HTML ditugaskan ke variabel`title`. Anda dapat memodifikasi konten HTML sesuai kebutuhan.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## Langkah 7: Timpa gaya untuk konten HTML
 Untuk menimpa gaya konten HTML, Anda dapat memodifikasi`TextState` properti dari`HtmlFragment` obyek. Dalam kode yang disediakan, jenis font diubah menjadi "Arial" dan ukuran font diatur menjadi 20.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## Langkah 8: Tetapkan informasi margin
Sesuaikan margin bawah dan atas fragmen HTML jika perlu. Dalam kode yang diberikan, margin bawah diatur ke 10 dan margin atas diatur ke 400.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## Langkah 9: Tambahkan HtmlFragment ke halaman
 Tambahkan`HtmlFragment` keberatan dengan kumpulan paragraf halaman.

```csharp
page.Paragraphs.Add(title);
```

## Langkah 10: Simpan dokumen PDF
 Simpan dokumen PDF menggunakan`Save` metode`Document` obyek. Tentukan jalur file keluaran yang Anda atur di Langkah 3.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### Contoh kode sumber untuk Menambahkan HTMLMenggunakan DOMDan Timpa menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buat instance objek Dokumen
Document doc = new Document();
// Tambahkan halaman ke halaman koleksi file PDF
Page page = doc.Pages.Add();
// Buat instance HtmlFragment dengan konten HTML
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//Keluarga font dari 'Verdana' akan disetel ulang ke 'Arial'
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// Tetapkan informasi margin bawah
title.Margin.Bottom = 10;
// Tetapkan informasi margin atas
title.Margin.Top = 400;
// Tambahkan Fragmen HTML ke kumpulan paragraf halaman
page.Paragraphs.Add(title);
// Simpan berkas PDF
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// Simpan berkas PDF
doc.Save(dataDir);
```

## Kesimpulan
Anda telah berhasil menambahkan konten HTML menggunakan DOM di Aspose.PDF untuk .NET dan menimpa gaya untuk konten HTML. File PDF yang dihasilkan sekarang dapat ditemukan di jalur file keluaran yang ditentukan.

### FAQ

#### Q: Apa fokus dari tutorial ini?

J: Tutorial ini dirancang untuk memandu Anda melalui proses menambahkan konten HTML ke dokumen PDF menggunakan Document Object Model (DOM) di Aspose.PDF untuk .NET. Selain itu, Anda akan mempelajari cara menimpa gaya untuk konten HTML, memungkinkan Anda menyesuaikan tampilannya. Tutorial ini menyediakan cuplikan kode sumber C# untuk mendemonstrasikan langkah-langkah yang diperlukan.

#### T: Namespace manakah yang perlu saya impor untuk tutorial ini?

J: Dalam file kode tempat Anda ingin menambahkan konten HTML, impor namespace berikut di awal file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### T: Bagaimana cara menentukan direktori dokumen dan jalur file keluaran?

 A: Di dalam kode, temukan barisnya`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

#### T: Bagaimana cara membuat objek Dokumen?

 J: Pada Langkah 4, Anda akan membuat instance yang baru`Document` objek menggunakan baris kode berikut:

```csharp
Document doc = new Document();
```

#### T: Bagaimana cara menambahkan halaman ke dokumen?

 J: Pada Langkah 5, Anda akan menambahkan halaman baru ke dokumen menggunakan`Add` metode`Pages` koleksi:

```csharp
Page page = doc.Pages.Add();
```

#### T: Bagaimana cara menyetel konten HTML menggunakan DOM?

 J: Pada Langkah 6, Anda akan membuat`HtmlFragment` objek dan tetapkan konten HTML yang Anda inginkan ke dalamnya. Konten HTML ditugaskan ke variabel`title`:

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### T: Bagaimana cara menimpa gaya konten HTML?

 J: Pada Langkah 7, Anda akan menimpa gaya konten HTML dengan memodifikasi`TextState` properti dari`HtmlFragment` obyek. Misalnya, Anda dapat mengubah jenis font menjadi "Arial" dan mengatur ukuran font menjadi 20:

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### T: Dapatkah saya menyesuaikan margin konten HTML?

J: Ya, pada Langkah 8, Anda dapat menyesuaikan margin bawah dan atas fragmen HTML sesuai kebutuhan:

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### T: Bagaimana cara menambahkan HtmlFragment ke dokumen PDF?

 J: Pada Langkah 9, Anda akan menambahkan`HtmlFragment` objek (`title`) ke kumpulan paragraf halaman:

```csharp
page.Paragraphs.Add(title);
```

#### Q: Bagaimana cara menyimpan dokumen PDF yang dihasilkan?

 J: Setelah menambahkan konten HTML dan menyesuaikan gayanya, gunakan`Save` metode`Document` keberatan untuk menyimpan dokumen PDF:

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### T: Apa inti dari tutorial ini?

J: Dengan mengikuti tutorial ini, Anda telah berhasil mempelajari cara memasukkan konten HTML menggunakan Document Object Model (DOM) di Aspose.PDF untuk .NET. Selain itu, Anda memperoleh kemampuan untuk menimpa gaya untuk menyesuaikan tampilan konten HTML dalam dokumen PDF yang dihasilkan.