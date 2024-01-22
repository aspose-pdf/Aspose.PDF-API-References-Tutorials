---
title: Tentukan Line Break Dalam File PDF
linktitle: Tentukan Line Break Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menentukan jeda baris dalam file PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 130
url: /id/net/programming-with-text/determine-line-break/
---
Tutorial ini akan memandu Anda melalui proses menentukan jeda baris dalam file PDF menggunakan Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan.

## Persyaratan
Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau kompiler C# lainnya yang diinstal pada mesin Anda.
- Aspose.PDF untuk perpustakaan .NET. Anda dapat mendownloadnya dari situs resmi Aspose atau menggunakan manajer paket seperti NuGet untuk menginstalnya.

## Langkah 1: Siapkan proyek
1. Buat proyek C# baru di lingkungan pengembangan pilihan Anda.
2. Tambahkan referensi ke perpustakaan Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan
Dalam file kode di mana Anda ingin menentukan jeda baris, tambahkan arahan penggunaan berikut di bagian atas file:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Langkah 3: Atur direktori dokumen
 Dalam kode, temukan baris yang bertuliskan`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur ke direktori tempat dokumen Anda disimpan.

## Langkah 4: Buat instance Dokumen baru
 Buat instance yang baru`Document` objek dengan menambahkan baris kode berikut:

```csharp
Document doc = new Document();
```

## Langkah 5: Tambahkan halaman ke dokumen
 Tambahkan halaman baru ke dokumen menggunakan`Add` metode`Pages`koleksi. Dalam kode yang disediakan, halaman baru ditugaskan ke variabel`page`.

```csharp
Page page = doc.Pages.Add();
```

## Langkah 6: Tambahkan fragmen teks dengan jeda baris
Buat lingkaran untuk menambahkan beberapa fragmen teks ke halaman, masing-masing berisi paragraf dengan jeda baris.

```csharp
for (int i = 0; i < 4; i++)
{
     TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
     text.TextState.FontSize = 20;
     page.Paragraphs.Add(text);
}
```

## Langkah 7: Simpan dokumen PDF dan ekstrak informasi jeda baris
 Simpan dokumen PDF menggunakan`Save` metode`Document` obyek. Kemudian, ekstrak informasi jeda baris menggunakan`GetNotifications` metode halaman yang diinginkan.

```csharp
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

### Contoh kode sumber untuk Menentukan Line Break menggunakan Aspose.PDF untuk .NET 
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
Anda telah berhasil menentukan jeda baris dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Informasi jeda baris telah diekstraksi dan disimpan ke file teks.

### FAQ

#### Q: Apa fokus utama tutorial ini?

J: Tutorial ini difokuskan untuk memandu Anda melalui proses menentukan jeda baris dalam file PDF menggunakan pustaka Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan untuk mencapai hal ini.

#### T: Namespace manakah yang harus saya impor untuk tutorial ini?

J: Dalam file kode tempat Anda ingin menentukan jeda baris, impor namespace berikut di awal file:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### T: Bagaimana cara menentukan direktori dokumen?

 A: Di dalam kode, temukan barisnya`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

#### T: Bagaimana cara membuat instance Dokumen baru?

 J: Pada Langkah 4, Anda akan membuat instance yang baru`Document` objek menggunakan kode yang disediakan.

#### T: Bagaimana cara menambahkan halaman ke dokumen?

 J: Pada Langkah 5, Anda akan menambahkan halaman baru ke dokumen menggunakan`Add` metode`Pages` koleksi.

#### T: Bagaimana cara menambahkan fragmen teks dengan jeda baris?

J: Pada Langkah 6, Anda akan membuat lingkaran untuk menambahkan beberapa fragmen teks ke halaman, masing-masing berisi paragraf dengan jeda baris.

#### T: Bagaimana cara menyimpan dokumen PDF dan mengekstrak informasi jeda baris?

 J: Pada Langkah 7, Anda akan menyimpan dokumen PDF menggunakan`Save` metode`Document` obyek. Kemudian, Anda akan mengekstrak informasi jeda baris menggunakan`GetNotifications` metode halaman yang diinginkan dan simpan ke file teks.

#### T: Apa tujuan dari informasi jeda baris yang diekstraksi?

J: Informasi jeda baris yang diekstraksi memberikan detail tentang jeda baris dan pemberitahuan yang ada dalam dokumen PDF. Ini dapat berguna untuk menganalisis dan memahami bagaimana teks dan paragraf disusun dalam dokumen.

#### T: Apa manfaat utama dari tutorial ini?

J: Dengan mengikuti tutorial ini, Anda telah mempelajari cara menentukan jeda baris dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Anda dapat menggunakan pengetahuan ini untuk mengekstrak dan menganalisis informasi jeda baris dari file PDF secara terprogram.