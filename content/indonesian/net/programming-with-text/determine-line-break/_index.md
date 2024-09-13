---
title: Menentukan Pemutusan Baris dalam File PDF
linktitle: Menentukan Pemutusan Baris dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menentukan jeda baris dalam berkas PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 130
url: /id/net/programming-with-text/determine-line-break/
---
Tutorial ini akan memandu Anda melalui proses penentuan jeda baris dalam file PDF menggunakan Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan.

## Persyaratan
Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau kompiler C# lainnya terinstal di komputer Anda.
- Aspose.PDF untuk pustaka .NET. Anda dapat mengunduhnya dari situs web resmi Aspose atau menggunakan pengelola paket seperti NuGet untuk menginstalnya.

## Langkah 1: Siapkan proyek
1. Buat proyek C# baru di lingkungan pengembangan pilihan Anda.
2. Tambahkan referensi ke pustaka Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan
Dalam berkas kode tempat Anda ingin menentukan jeda baris, tambahkan perintah penggunaan berikut di bagian atas berkas:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Langkah 3: Mengatur direktori dokumen
 Dalam kode, temukan baris yang bertuliskan`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur ke direktori tempat dokumen Anda disimpan.

## Langkah 4: Buat contoh Dokumen baru
 Membuat instance baru`Document` objek dengan menambahkan baris kode berikut:

```csharp
Document doc = new Document();
```

## Langkah 5: Tambahkan halaman ke dokumen
 Tambahkan halaman baru ke dokumen menggunakan`Add` metode dari`Pages` koleksi. Dalam kode yang diberikan, halaman baru ditetapkan ke variabel`page`.

```csharp
Page page = doc.Pages.Add();
```

## Langkah 6: Tambahkan fragmen teks dengan jeda baris
Buat loop untuk menambahkan beberapa fragmen teks ke halaman, masing-masing berisi paragraf dengan jeda baris.

```csharp
for (int i = 0; i < 4; i++)
{
     TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
     text.TextState.FontSize = 20;
     page.Paragraphs.Add(text);
}
```

## Langkah 7: Simpan dokumen PDF dan ekstrak informasi jeda baris
 Simpan dokumen PDF menggunakan`Save` metode dari`Document` objek. Kemudian, ekstrak informasi jeda baris menggunakan`GetNotifications` metode halaman yang diinginkan.

```csharp
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

### Contoh kode sumber untuk Menentukan Jeda Baris menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.");
	text.TextState.FontSize = 20;
	page.Paragraphs.Add(text);
}
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

## Kesimpulan
Anda telah berhasil menentukan jeda baris dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Informasi jeda baris telah diekstrak dan disimpan ke dalam berkas teks.

### Pertanyaan yang Sering Diajukan

#### T: Apa fokus utama tutorial ini?

J: Tutorial ini difokuskan untuk memandu Anda melalui proses penentuan jeda baris dalam file PDF menggunakan pustaka Aspose.PDF for .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan untuk mencapainya.

#### T: Namespace mana yang harus saya impor untuk tutorial ini?

A: Pada berkas kode tempat Anda ingin menentukan jeda baris, impor namespace berikut di awal berkas:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### T: Bagaimana cara menentukan direktori dokumen?

 A: Pada kode tersebut, temukan baris`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

#### T: Bagaimana cara membuat contoh Dokumen baru?

 A: Pada Langkah 4, Anda akan membuat instance baru`Document` objek menggunakan kode yang disediakan.

#### T: Bagaimana cara menambahkan halaman ke dokumen?

 A: Pada Langkah 5, Anda akan menambahkan halaman baru ke dokumen menggunakan`Add` metode dari`Pages` koleksi.

#### T: Bagaimana cara menambahkan fragmen teks dengan jeda baris?

A: Pada Langkah 6, Anda akan membuat putaran untuk menambahkan beberapa fragmen teks ke halaman, masing-masing berisi paragraf dengan jeda baris.

#### T: Bagaimana cara menyimpan dokumen PDF dan mengekstrak informasi jeda baris?

 A: Pada Langkah 7, Anda akan menyimpan dokumen PDF menggunakan`Save` metode dari`Document` objek. Kemudian, Anda akan mengekstrak informasi jeda baris menggunakan`GetNotifications` metode halaman yang diinginkan dan menyimpannya ke berkas teks.

#### T: Apa tujuan dari informasi jeda baris yang diekstraksi?

A: Informasi jeda baris yang diekstrak memberikan detail tentang jeda baris dan pemberitahuan yang ada dalam dokumen PDF. Ini dapat berguna untuk menganalisis dan memahami bagaimana teks dan paragraf disusun dalam dokumen.

#### T: Apa hasil utama dari tutorial ini?

A: Dengan mengikuti tutorial ini, Anda telah mempelajari cara menentukan jeda baris dalam dokumen PDF menggunakan Aspose.PDF for .NET. Anda dapat menggunakan pengetahuan ini untuk mengekstrak dan menganalisis informasi jeda baris dari file PDF secara terprogram.