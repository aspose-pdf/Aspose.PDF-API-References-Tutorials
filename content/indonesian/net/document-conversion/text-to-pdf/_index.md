---
title: Teks Ke PDF
linktitle: Teks Ke PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Konversi file teks ke PDF yang sederhana dan efisien menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 300
url: /id/net/document-conversion/text-to-pdf/
---
Tutorial ini akan memandu Anda melalui langkah-langkah untuk mengonversi file teks ke file PDF menggunakan Aspose.PDF untuk .NET. Aspose.PDF menawarkan solusi sederhana dan efektif untuk mengonversi teks biasa ke PDF sambil mempertahankan format dan presentasi teks. Ikuti langkah-langkah di bawah ini untuk melakukan konversi ini.

## Prasyarat
Sebelum memulai, pastikan Anda memenuhi prasyarat berikut:

- Pengetahuan dasar tentang bahasa pemrograman C#.
- Pustaka Aspose.PDF untuk .NET diinstal di sistem Anda.
- Lingkungan pengembangan seperti Visual Studio.

## Langkah 1: Membaca file teks
 Langkah pertama adalah membaca isi file teks menggunakan`StreamReader` kelas. Gunakan kode berikut:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Baca file teks
TextReader tr = new StreamReader(dataDir + "log.txt");
```

 Pastikan untuk mengganti`"YOUR DOCUMENTS DIRECTORY"`dengan direktori sebenarnya tempat file teks Anda berada.

## Langkah 2: Membuat dokumen PDF
 Langkah kedua adalah membuat a`Document` objek yang akan mewakili dokumen PDF akhir. Gunakan kode berikut:

```csharp
// Buat objek Dokumen
Document doc = new Document();
```

## Langkah 3: Tambahkan teks ke dokumen
Langkah ketiga adalah menambahkan teks yang sudah dibaca ke halaman dokumen PDF. Gunakan kode berikut:

```csharp
//Tambahkan halaman baru ke dokumen
Page page = doc.Pages.Add();

// Buat objek TextFragment dan teruskan teks yang sudah dibaca sebagai argumen
TextFragment text = new TextFragment(tr.ReadToEnd());

// Tambahkan paragraf teks ke halaman
page.Paragraphs.Add(text);
```

## Langkah 4: Menyimpan file PDF
Terakhir, simpan file PDF yang dihasilkan dengan menentukan jalur dan nama file yang diinginkan. Gunakan kode berikut:

```csharp
// Simpan file PDF yang dihasilkan
doc.Save(dataDir + "TexttoPDF_out.pdf");
```

Pastikan untuk menentukan jalur dan nama file yang diinginkan untuk file PDF yang dihasilkan.

### Contoh kode sumber untuk Teks ke PDF menggunakan Aspose.PDF untuk .NET

```csharp
try
{
	
	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Baca file teks sumber
	TextReader tr = new StreamReader(dataDir + "log.txt");

	// Buat instance objek Dokumen dengan memanggil konstruktor kosongnya
	Document doc = new Document();

	// Tambahkan halaman baru di koleksi Halaman Dokumen
	Page page = doc.Pages.Add();

	// Buat instance TextFragmet dan teruskan teks dari objek pembaca ke konstruktornya sebagai argumen
	TextFragment text = new TextFragment(tr.ReadToEnd());
	//Teks.TextState.Font = FontRepository.FindFont("Arial Unicode MS");

	// Tambahkan paragraf teks baru dalam kumpulan paragraf dan teruskan objek TextFragment
	page.Paragraphs.Add(text);

	// Simpan file PDF yang dihasilkan
	doc.Save(dataDir + "TexttoPDF_out.pdf"); 
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara mengonversi file teks ke file PDF menggunakan Aspose.PDF untuk .NET. Dengan mengikuti langkah-langkah yang diberikan di atas, Anda dapat dengan mudah melakukan konversi ini. Gunakan metode ini untuk mengonversi file teks Anda ke PDF dan nikmati fleksibilitas dan kualitas Aspose.PDF.

### FAQ

#### T: Apa itu Aspose.PDF untuk .NET?

J: Aspose.PDF untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang bekerja dengan dokumen PDF dalam aplikasi C#. Ini menawarkan berbagai fungsi, termasuk mengkonversi teks biasa ke PDF.

#### T: Mengapa saya ingin mengonversi file teks ke PDF?

J: Mengonversi file teks ke format PDF memungkinkan pengelolaan, pembagian, dan distribusi dokumen yang lebih baik. File PDF menawarkan pemformatan yang konsisten di berbagai perangkat dan sistem operasi.

#### T: Bagaimana cara memuat file teks dan mengonversinya menjadi PDF menggunakan Aspose.PDF untuk .NET?

A: Untuk memuat file teks, Anda dapat menggunakan`StreamReader` kelas untuk membaca isi file. Kemudian, buat a`Document` objek untuk mewakili dokumen PDF. Tambahkan halaman baru dan a`TextFragment` berisi teks dari file teks. Terakhir, simpan PDF yang dihasilkan menggunakan`Save` metode`Document` obyek.

#### T: Bisakah saya menyesuaikan tampilan teks di PDF?

A: Ya, Aspose.PDF untuk .NET menyediakan berbagai opsi untuk menyesuaikan tampilan teks dalam PDF yang dihasilkan, seperti gaya font, ukuran, warna, dan perataan.

#### T: Apakah format teks dipertahankan dalam PDF yang dihasilkan?

J: Ya, Aspose.PDF untuk .NET mempertahankan format dan tata letak teks selama konversi teks ke PDF, memastikan representasi akurat dari konten asli.