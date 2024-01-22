---
title: Dapatkan Lampiran Individu Dalam File PDF
linktitle: Dapatkan Lampiran Individu Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara mendapatkan lampiran individual dalam file PDF dengan Aspose.PDF untuk .NET.
type: docs
weight: 60
url: /id/net/programming-with-attachments/get-individual-attachment/
---
Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# berikut langkah demi langkah untuk mendapatkan lampiran individual file PDF menggunakan Aspose.PDF untuk .NET.

Pastikan Anda telah menginstal perpustakaan Aspose.PDF dan mengatur lingkungan pengembangan Anda sebelum memulai. Juga memiliki pengetahuan dasar tentang pemrograman C#.

### Langkah 1: Pengaturan Direktori Dokumen

Dalam kode sumber yang disediakan, Anda perlu menentukan direktori tempat file PDF berada tempat Anda ingin mendapatkan lampiran individual. Ubah variabel "dataDir" ke direktori yang diinginkan.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Langkah 2: Buka dokumen PDF yang ada

Kami membuka dokumen PDF yang ada menggunakan jalur yang ditentukan.

```csharp
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
```

### Langkah 3: Mendapatkan Lampiran Tertentu

Kami mengambil lampiran tertentu dari koleksi lampiran dokumen. Dalam contoh ini, kita mendapatkan lampiran pertama menggunakan indeks 1.

```csharp
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
```

### Langkah 4: Dapatkan Properti File

Kami menampilkan properti lampiran seperti nama, deskripsi, tipe MIME, hash kontrol, tanggal dibuat, tanggal diubah, dan ukuran.

```csharp
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// Periksa apakah parameter objek berisi informasi tambahan
if (fileSpecification.Params != null)
{
Console.WriteLine("Check Hash: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}
```

### Langkah 5: Ambil lampiran dan simpan ke file

Kami mengambil konten lampiran dan menyimpannya ke file teks. Dalam contoh ini, file disimpan dengan nama "test_out.txt".

```csharp
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();
```

### Contoh kode sumber untuk Dapatkan Lampiran Individu menggunakan Aspose.PDF untuk .NET 

```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
// Dapatkan file tertanam tertentu
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
// Dapatkan properti file
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
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
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

```

## Kesimpulan

Dalam tutorial ini, kami menjelaskan cara mendapatkan lampiran individual dari file PDF menggunakan Aspose.PDF untuk .NET. Anda sekarang dapat menggunakan pengetahuan ini untuk mengekstrak dan menyimpan lampiran dari file PDF Anda.

### FAQ untuk mendapatkan lampiran individual dalam file PDF

#### T: Apa tujuan mendapatkan lampiran individual dari dokumen PDF?

J: Mendapatkan lampiran individual memungkinkan Anda mengekstrak dan menyimpan file tertentu yang tertanam dalam PDF, yang dapat berguna untuk analisis atau manipulasi lebih lanjut.

#### T: Apa manfaat tutorial ini dalam tugas terkait PDF saya?

J: Tutorial ini memberikan petunjuk langkah demi langkah dan kode sumber C# untuk mengambil dan menyimpan lampiran tertentu dari dokumen PDF menggunakan Aspose.PDF untuk .NET.

#### T: Properti lampiran apa yang dapat saya akses menggunakan tutorial ini?

J: Anda dapat mengakses properti lampiran seperti nama, deskripsi, tipe MIME, hash kontrol, tanggal pembuatan, tanggal modifikasi, dan ukuran lampiran tertentu.

#### T: Bisakah saya mengubah kode untuk mendapatkan lampiran selain lampiran pertama?

 J: Tentu saja, Anda dapat menyesuaikan indeksnya (misalnya,`pdfDocument.EmbeddedFiles[1]`) untuk mengambil lampiran pada indeks berbeda dalam PDF.

#### T: Bagaimana cara menyimpan lampiran yang diambil ke file?

A: Tutorial ini menyediakan kode untuk mengambil konten lampiran dan menyimpannya ke file teks dengan nama tertentu.

#### T: Apa pentingnya properti "Periksa Hash" dalam informasi lampiran?

J: Properti "Periksa Hash" mewakili nilai hash kontrol lampiran, yang dapat digunakan untuk memverifikasi integritas lampiran.

#### T: Dapatkah saya memperluas pengetahuan ini untuk mengekstrak lampiran dengan kriteria tertentu, seperti jenis file?

J: Ya, Anda dapat menyempurnakan kode untuk memfilter lampiran berdasarkan kriteria tertentu seperti jenis file atau properti lainnya.

#### T: Bagaimana Aspose.PDF untuk .NET menyederhanakan proses mengekstraksi lampiran individual?

J: Aspose.PDF untuk .NET menyediakan API ramah pengguna yang memfasilitasi ekstraksi dan manipulasi lampiran dalam dokumen PDF.

#### T: Apakah tutorial ini juga relevan untuk file PDF yang dilindungi kata sandi?

J: Ya, Anda dapat mengadaptasi teknik serupa untuk mengambil lampiran individual dari file PDF yang dilindungi kata sandi menggunakan Aspose.PDF untuk .NET.
