---
title: XML Ke PDFSet Jalur Gambar
linktitle: XML Ke PDFSet Jalur Gambar
second_title: Aspose.PDF untuk Referensi .NET API
description: Panduan langkah demi langkah untuk mengatur jalur gambar saat mengonversi XML ke PDF dengan Aspose.PDF untuk .NET.
type: docs
weight: 340
url: /id/net/document-conversion/xml-to-pdfset-image-path/
---
Dalam tutorial ini, kami akan memandu Anda langkah demi langkah cara mengatur jalur gambar saat mengonversi file XML ke PDF menggunakan perpustakaan Aspose.PDF untuk .NET. Kami akan merinci kode sumber C# yang disediakan dan menunjukkan cara mengimplementasikannya dalam proyek Anda sendiri. Di akhir tutorial ini, Anda dapat dengan mudah menentukan jalur gambar saat mengonversi XML ke PDF.

## Langkah 1: Tetapkan Jalur File
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string inXml = dataDir + "input.xml";
string inFile = dataDir + "aspose-logo.jpg";
string outFile = dataDir + "output_out.pdf";
```
 Tentukan jalur file XML masukan, gambar yang akan digunakan, dan file PDF keluaran. Mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan jalur tempat Anda menyimpan file Anda.

## Langkah 2: Buat instance objek Dokumen
```csharp
Document doc = new Document();
```
Buat sebuah instance dari objek Dokumen.

## Langkah 3: Tautkan file XML sumber
```csharp
doc. BindXml(inXml);
```
Tautkan file XML sumber ke dokumen.

## Langkah 4: Tetapkan Jalur Gambar
```csharp
Image image = (Image)doc.GetObjectById("testImg");
image.File = inFile;
```
Dapatkan referensi objek Gambar dari XML menggunakan ID-nya dan atur jalur gambar yang akan digunakan.

## Langkah 5: Simpan File PDF yang Dihasilkan
```csharp
doc.Save(outFile);
```
Simpan file PDF yang dihasilkan ke direktori yang ditentukan.

### Contoh kode sumber untuk XML ke PDFSet Image Path menggunakan Aspose.PDF untuk .NET

```csharp
try
{
	
	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string inXml = dataDir + "input.xml";
	string inFile = dataDir + "aspose-logo.jpg";
	string outFile = dataDir + "output_out.pdf";
	Document doc = new Document();
	doc.BindXml(inXml);
	Image image = (Image)doc.GetObjectById("testImg");
	image.File = inFile;
	doc.Save(outFile);
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara mengatur jalur gambar saat mengonversi XML ke PDF menggunakan perpustakaan Aspose.PDF untuk .NET. Dengan mengikuti langkah-langkah yang disediakan, Anda dapat dengan mudah menentukan jalur gambar dalam konversi XML ke PDF Anda sendiri.

### FAQ

#### T: Apa tujuan menyetel jalur gambar saat mengonversi XML ke PDF?

J: Saat mengonversi XML ke PDF, pengaturan jalur gambar memungkinkan Anda menentukan lokasi gambar yang direferensikan dalam XML. Ini memastikan bahwa gambar ditampilkan dengan benar dalam dokumen PDF yang dihasilkan.

#### T: Bisakah saya menggunakan gambar dari direktori berbeda?

 J: Ya, Anda dapat menggunakan gambar dari direktori berbeda dengan menyediakan jalur file yang benar untuk setiap gambar. Dalam kode yang disediakan, itu`inFile` Variabel menyimpan jalur ke file gambar, dan Anda dapat memperbaruinya agar mengarah ke gambar di direktori berbeda.

#### T: Dapatkah saya menggunakan gambar dari URL jarak jauh?

J: Ya, Anda dapat menggunakan gambar dari URL jarak jauh dengan memberikan URL, bukan jalur file lokal. Pastikan aplikasi Anda memiliki akses internet untuk mengambil gambar dari URL jarak jauh.

#### T: Format apa yang harus dimiliki file XML masukan?

J: File XML masukan harus memiliki struktur yang mereferensikan gambar menggunakan ID. Dalam kode yang disediakan, ID "testImg" digunakan untuk mereferensikan gambar.

#### T: Bisakah saya menambahkan banyak gambar ke PDF?

J: Ya, Anda dapat menambahkan banyak gambar ke PDF dengan mereferensikannya dalam file XML menggunakan ID berbeda dan mengatur jalur file yang sesuai.