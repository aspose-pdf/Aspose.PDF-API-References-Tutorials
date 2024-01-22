---
title: Dapatkan Semua Lampiran Dalam File PDF
linktitle: Dapatkan Semua Lampiran Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara mendapatkan semua lampiran dalam file PDF dengan Aspose.PDF untuk .NET. Panduan langkah demi langkah untuk penanganan mudah.
type: docs
weight: 40
url: /id/net/programming-with-attachments/get-all-the-attachments/
---
Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# berikut langkah demi langkah untuk mendapatkan semua lampiran dalam file PDF menggunakan Aspose.PDF untuk .NET.

Pastikan Anda telah menginstal perpustakaan Aspose.PDF dan mengatur lingkungan pengembangan Anda sebelum memulai. Juga memiliki pengetahuan dasar tentang pemrograman C#.

### Langkah 1: Pengaturan Direktori Dokumen

Dalam kode sumber yang disediakan, Anda perlu menentukan direktori tempat file PDF berada dari mana Anda ingin mendapatkan lampirannya. Ubah variabel "dataDir" ke direktori yang diinginkan.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Langkah 2: Buka dokumen PDF yang ada

Kami membuka dokumen PDF yang ada menggunakan jalur yang ditentukan.

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### Langkah 3: Mendapatkan Koleksi Lampiran

Kami mendapatkan kumpulan lampiran dari dokumen.

```csharp
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
```

### Langkah 4: Mengambil lampiran

Kami menelusuri koleksi untuk mendapatkan semua lampiran dan menampilkan informasinya. Kami juga menyimpan lampiran dalam file individual.

```csharp
int count = 1;
foreach(FileSpecification fileSpecification in embeddedFiles)
{
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// Periksa apakah parameter objek berisi informasi tambahan
if (fileSpecification.Params != null)
{
Console.WriteLine("CheckSum: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}

// Ambil lampiran dan simpan dalam file
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

count += 1;
}
```


### Contoh kode sumber untuk Dapatkan Semua Lampiran menggunakan Aspose.PDF untuk .NET 

```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// Dapatkan koleksi file yang disematkan
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
// Dapatkan hitungan file yang disematkan
Console.WriteLine("Total files : {0}", embeddedFiles.Count);
int count = 1;
// Ulangi koleksi untuk mendapatkan semua lampiran
foreach (FileSpecification fileSpecification in embeddedFiles)
{
	Console.WriteLine("Name: {0}", fileSpecification.Name);
	Console.WriteLine("Description: {0}",
	fileSpecification.Description);
	Console.WriteLine("Mime Type: {0}", fileSpecification.MIMEType);
	//Periksa apakah objek parameter berisi parameter
	if (fileSpecification.Params != null)
	{
		Console.WriteLine("CheckSum: {0}",
		fileSpecification.Params.CheckSum);
		Console.WriteLine("Creation Date: {0}",
		fileSpecification.Params.CreationDate);
		Console.WriteLine("Modification Date: {0}",
		fileSpecification.Params.ModDate);
		Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
	}
	// Dapatkan lampiran dan tulis ke file atau streaming
	byte[] fileContent = new byte[fileSpecification.Contents.Length];
	fileSpecification.Contents.Read(fileContent, 0,
	fileContent.Length);
	FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt",
	FileMode.Create);
	fileStream.Write(fileContent, 0, fileContent.Length);
	fileStream.Close();
	count+=1;
}

```

## Kesimpulan

Dalam tutorial ini, kami menjelaskan cara mendapatkan semua lampiran dari file PDF menggunakan Aspose.PDF untuk .NET. Anda sekarang dapat menggunakan pengetahuan ini untuk mengekstrak dan memanipulasi lampiran dari file PDF Anda.

## FAQ untuk mendapatkan semua lampiran dalam file PDF

#### T: Mengapa saya perlu mengambil semua lampiran dari dokumen PDF?

J: Mengambil lampiran memungkinkan Anda mengakses dan memanipulasi file tambahan yang tertanam dalam PDF, yang dapat berguna untuk pengarsipan, berbagi, atau pemrosesan lebih lanjut.

#### T: Jenis file apa saja yang dapat dilampirkan ke dokumen PDF?

J: Dokumen PDF dapat berisi berbagai macam file lampiran, termasuk gambar, dokumen, spreadsheet, file audio, dan banyak lagi.

#### T: Bagaimana tutorial ini membantu saya mengambil lampiran dari PDF menggunakan Aspose.PDF untuk .NET?

J: Tutorial ini memberikan petunjuk langkah demi langkah dan kode sumber C# untuk mengakses dan mengambil semua lampiran dalam dokumen PDF.

#### T: Bisakah saya mengambil lampiran tertentu dan bukan semua lampiran menggunakan tutorial ini?

J: Ya, Anda dapat mengubah kode yang diberikan untuk mengambil lampiran secara selektif berdasarkan kebutuhan Anda.

#### T: Informasi apa tentang setiap lampiran yang dapat saya peroleh menggunakan tutorial ini?

J: Tutorial ini menunjukkan cara mengambil dan menampilkan detail seperti nama lampiran, deskripsi, tipe MIME, tanggal pembuatan, tanggal modifikasi, dan ukuran.

#### T: Bagaimana cara lampiran yang diambil disimpan menggunakan tutorial ini?

J: Tutorial ini memandu Anda dalam menyimpan setiap lampiran yang diambil sebagai file terpisah di direktori yang ditentukan.

#### T: Bisakah saya menggunakan pengetahuan ini untuk mengekstrak lampiran dari file PDF yang dilindungi kata sandi?

J: Ya, Anda dapat menerapkan prinsip serupa untuk mengambil lampiran dari file PDF yang dilindungi kata sandi menggunakan Aspose.PDF untuk .NET.

#### T: Bagaimana Aspose.PDF untuk .NET memfasilitasi pengambilan lampiran?

J: Aspose.PDF untuk .NET menyediakan API intuitif yang memungkinkan Anda mengakses dan memanipulasi lampiran dalam dokumen PDF dengan mudah.

#### T: Apakah ada skenario tertentu yang direkomendasikan untuk mengambil lampiran?

J: Mengambil lampiran berguna ketika Anda perlu mengakses file yang tertanam dalam PDF, seperti mengekstrak gambar, file audio, atau dokumen tambahan.