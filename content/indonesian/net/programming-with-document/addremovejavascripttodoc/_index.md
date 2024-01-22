---
title: Tambahkan Hapus Javascript Ke Dokumen PDF
linktitle: Tambahkan Hapus Javascript Ke Dokumen
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menambah dan menghapus JavaScript ke dokumen PDF menggunakan Aspose.PDF untuk .NET. Panduan langkah demi langkah dengan tutorial kode untuk pembuatan skrip tingkat dokumen.
type: docs
weight: 30
url: /id/net/programming-with-document/addremovejavascripttodoc/
---
Untuk menambah dan menghapus JavaScript ke dokumen PDF, kami akan menggunakan perpustakaan Aspose.PDF untuk .NET. Pustaka yang kuat ini memungkinkan kita memanipulasi file PDF dalam aplikasi .NET. Ikuti petunjuk langkah demi langkah di bawah ini untuk menambah dan menghapus JavaScript menggunakan Aspose.PDF untuk .NET.

## Langkah 1: Buat Dokumen PDF Baru

 Mulailah dengan membuat instance baru dari`Document` kelas yang disediakan oleh Aspose.PDF untuk .NET. Ini akan berfungsi sebagai dokumen PDF tempat kita akan menambahkan JavaScript.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
```

## Langkah 2: Tambahkan JavaScript di Tingkat Dokumen

 Untuk menambahkan JavaScript di tingkat dokumen, gunakan`JavaScript` properti dari`Document` kelas. Tetapkan fungsi JavaScript ke kunci dalam kamus JavaScript.

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");
```

 Dalam tutorial ini, kami telah menambahkan dua fungsi JavaScript,`func1` Dan`func2`, ke dokumen PDF.

## Langkah 3: Hapus JavaScript Tingkat Dokumen

 Untuk menghapus JavaScript di tingkat dokumen, muat dokumen PDF dan akses`JavaScript`kamus. Ulangi tombol dan hapus fungsi JavaScript yang diinginkan.

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;

foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed");
```

 Dalam tutorial ini, kami menghapus`func1` Fungsi JavaScript dari dokumen PDF.

## Langkah 4: Simpan dan Verifikasi Perubahan

Simpan dokumen PDF yang dimodifikasi dan verifikasi perubahannya.

```csharp
Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

Kode ini akan menyimpan dokumen PDF yang dimodifikasi dan menampilkan pesan sukses.

### Contoh kode sumber untuk Tambah Hapus Javascript dari dokumen PDF menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");

// Hapus JavaScript tingkat Dokumen
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
	Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
Console.WriteLine("=============================== ");

Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

## Kesimpulan

Pada artikel ini, kami telah menyediakan panduan langkah demi langkah untuk menambahkan dan menghapus JavaScript dari dokumen PDF menggunakan Aspose.PDF untuk .NET. Dengan mengikuti petunjuk dan memanfaatkan tutorial kode yang disediakan, Anda dapat dengan mudah memasukkan JavaScript ke dalam dokumen PDF Anda dan menghapusnya bila diperlukan. JavaScript memungkinkan fungsionalitas dinamis dan interaktivitas dalam file PDF Anda, sehingga meningkatkan pengalaman pengguna.


### FAQ untuk menambahkan menghapus javascript ke dokumen PDF

#### T: Apa itu Aspose.PDF untuk .NET?

J: Aspose.PDF untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang memanipulasi file PDF dalam aplikasi .NET secara efektif. Ini menyediakan fitur ekstensif untuk bekerja dengan dokumen PDF secara terprogram.

#### T: Bagaimana cara menambahkan JavaScript ke dokumen PDF menggunakan Aspose.PDF untuk .NET?

 J: Anda dapat menambahkan JavaScript pada tingkat dokumen menggunakan`JavaScript` properti dari`Document` kelas. Cukup tetapkan fungsi JavaScript ke kunci di kamus JavaScript.

#### T: Bisakah saya menghapus JavaScript dari dokumen PDF menggunakan Aspose.PDF untuk .NET?

 J: Ya, Anda dapat menghapus JavaScript dari dokumen PDF dengan mengakses`JavaScript` kamus dan menghapus fungsi JavaScript yang diinginkan.

#### T: Apakah Aspose.PDF untuk .NET cocok untuk proyek profesional?

J: Tentu saja, Aspose.PDF untuk .NET banyak digunakan dalam proyek profesional untuk manipulasi PDF dan tugas pembuatan. Ia menawarkan kinerja tinggi dan fungsionalitas yang andal.

#### T: Apa manfaat menambahkan JavaScript ke dokumen PDF?

J: Menambahkan JavaScript ke dokumen PDF memungkinkan Anda membuat file PDF yang interaktif dan dinamis. Anda dapat menerapkan validasi formulir, melakukan penghitungan, dan menambahkan berbagai fitur interaktivitas untuk meningkatkan pengalaman pengguna.