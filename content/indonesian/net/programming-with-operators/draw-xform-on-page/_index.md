---
title: Menggambar XForm Di Halaman
linktitle: Menggambar XForm Di Halaman
second_title: Referensi API Aspose.PDF untuk .NET
description: Panduan langkah demi langkah untuk menggambar formulir XForm pada halaman PDF menggunakan Aspose.PDF untuk .NET. Tambahkan dan posisikan formulir pada halaman.
type: docs
weight: 10
url: /id/net/programming-with-operators/draw-xform-on-page/
---
Dalam tutorial ini, kami akan memberikan panduan langkah demi langkah tentang cara menggambar XForm pada halaman menggunakan Aspose.PDF untuk .NET. Aspose.PDF adalah pustaka canggih yang memungkinkan Anda membuat, memanipulasi, dan mengonversi dokumen PDF secara terprogram. Dengan menggunakan operator yang disediakan oleh Aspose.PDF, Anda dapat menambahkan dan memposisikan formulir XForm pada halaman PDF yang sudah ada.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki prasyarat berikut:

1. Visual Studio terinstal dengan kerangka kerja .NET.
2. Pustaka Aspose.PDF untuk .NET.

## Langkah 1: Pengaturan Proyek

Untuk memulai, buat proyek baru di Visual Studio dan tambahkan referensi ke pustaka Aspose.PDF untuk .NET. Anda dapat mengunduh pustaka tersebut dari situs web resmi Aspose dan menginstalnya di komputer Anda.

## Langkah 2: Impor namespace yang diperlukan

Dalam berkas kode C# Anda, impor namespace yang diperlukan untuk mengakses kelas dan metode yang disediakan oleh Aspose.PDF:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## Langkah 3: Mengatur jalur file

Tentukan jalur file untuk gambar latar belakang, file PDF masukan, dan file PDF keluaran:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

Pastikan untuk menentukan jalur berkas sesungguhnya pada mesin Anda.

## Langkah 4: Memuat file PDF masukan

Gunakan kode berikut untuk memuat berkas PDF masukan:

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
// Kode berikut menggunakan operator GSave/GRestore
// Kode ini menggunakan operator ContatatenateMatrix untuk memposisikan XForm
// Kode ini menggunakan operator Do untuk menggambar XForm di halaman
// Operator GSave/GRestore membungkus konten yang ada
//ini dilakukan untuk mendapatkan keadaan grafis awal di akhir konten yang ada
// jika tidak, mungkin ada transformasi yang tidak diinginkan yang tertinggal di akhir rantai operator yang ada
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// Tambahkan operator GSave untuk mengatur ulang status grafis dengan benar setelah perintah baru
pageContents. Add(new GSave());

// Buat XForm
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// Mengatur lebar dan tinggi gambar
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// Memuat gambar ke dalam aliran
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// Tambahkan gambar ke koleksi gambar sumber daya XForm
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// Menggunakan operator Do: operator ini menggambar gambar
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
// Posisikan XForm pada koordinat x=100 dan y=500
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// Menggambar XForm dengan operator Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// Posisikan XForm pada koordinat x=100 dan y=300
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// Menggambar XForm dengan operator Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// Pulihkan status grafis dengan GRestore setelah GSave
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

Pastikan untuk menentukan jalur berkas sebenarnya dan menyesuaikan nomor halaman dan posisi XForm sesuai kebutuhan.

### Contoh kode sumber untuk Draw XForm On Page menggunakan Aspose.PDF untuk .NET
 
```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imageFile = dataDir+ "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
using (Document doc = new Document(inFile))
{
	OperatorCollection pageContents = doc.Pages[1].Contents;
	// Sampel menunjukkan
	// Penggunaan operator GSave/GRestore
	// Penggunaan operator ContatatenateMatrix untuk memposisikan xForm
	//Apakah penggunaan operator untuk menggambar xForm di halaman?
	// Bungkus konten yang ada dengan pasangan operator GSave/GRestore
	// ini untuk mendapatkan status grafis awal di akhir konten yang ada
	// jika tidak, mungkin akan tetap ada beberapa transformasi yang tidak diinginkan pada akhir rantai operator yang ada
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Tambahkan operator simpan status grafik untuk menghapus status grafik dengan benar setelah perintah baru
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// Buat xForm
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	// Tentukan lebar dan tinggi gambar
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	// Muat gambar ke dalam aliran
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	// Tambahkan gambar ke koleksi Gambar Sumber Daya XForm
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// Menggunakan operator Do: operator ini menggambar gambar
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Tempatkan formulir ke koordinat x=100 y=500
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// Menggambar bentuk dengan operator Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Tempatkan formulir ke koordinat x=100 y=300
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// Menggambar bentuk dengan operator Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Pulihkan status grafik dengan GRestore setelah GSave
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## Kesimpulan

Dalam tutorial ini, Anda mempelajari cara menggambar formulir XForm pada halaman PDF menggunakan Aspose.PDF untuk .NET. Dengan mengikuti langkah-langkah yang dijelaskan, Anda akan dapat menambahkan dan memposisikan formulir XForm pada halaman yang sudah ada, sehingga memberikan lebih banyak fleksibilitas pada dokumen PDF Anda.

### FAQ untuk menggambar XForm di halaman

#### T: Apa itu XForm di Aspose.PDF?

J: XForm adalah objek grafis yang dapat digunakan kembali dalam dokumen PDF. Objek ini memungkinkan Anda untuk menentukan dan menggambar grafik, gambar, atau teks kompleks yang dapat digunakan kembali beberapa kali pada halaman yang berbeda.

#### T: Bagaimana cara mengimpor namespace yang diperlukan untuk Aspose.PDF?

 A: Dalam file kode C# Anda, gunakan`using` direktif untuk mengimpor namespace yang diperlukan untuk mengakses kelas dan metode yang disediakan oleh Aspose.PDF:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### T: Apa tujuan operator GSave dan GRestore?

 Sebuah:`GSave` Dan`GRestore` Operator dalam Aspose.PDF digunakan untuk menyimpan dan memulihkan status grafik. Operator ini membantu memastikan bahwa transformasi dan pengaturan yang diterapkan pada satu bagian konten tidak memengaruhi bagian berikutnya.

#### T: Bagaimana cara mendefinisikan XForm menggunakan Aspose.PDF?

 A: Untuk membuat XForm, gunakan`XForm.CreateNewForm` metode dan menambahkannya ke`Resources.Forms` kumpulan halaman tertentu. Anda kemudian dapat menambahkan konten ke XForm`Contents` milik.

#### T: Bagaimana cara menggambar gambar dalam XForm?

A: Muat gambar ke dalam aliran dan tambahkan ke`Resources.Images` koleksi XForm. Gunakan`Do` operator dalam XForm`Contents` untuk menggambar gambar.

#### T: Bagaimana cara memposisikan XForm pada halaman PDF?

 A: Untuk memposisikan XForm pada halaman, gunakan`ConcatenateMatrix` operator di dalam halaman`Contents`Sesuaikan parameter matriks untuk menentukan translasi (posisi) dan penskalaan XForm.

#### T: Bisakah saya menggambar beberapa XForm di halaman yang sama?

 A: Ya, Anda dapat menggambar beberapa XForms pada halaman yang sama dengan menyesuaikan`ConcatenateMatrix` parameter untuk memposisikan setiap XForm pada koordinat yang berbeda.

#### T: Dapatkah saya mengubah konten XForm setelah dibuat?

 A: Ya, Anda dapat mengubah konten XForm setelah pembuatan dengan menambahkan operator tambahan ke dalamnya`Contents` milik.

#### T: Apa yang terjadi jika saya menghilangkan operator GSave dan GRestore?

J: Mengabaikan operator GSave dan GRestore dapat menyebabkan transformasi atau pengaturan yang tidak diinginkan diterapkan ke konten berikutnya. Penggunaannya membantu menjaga kondisi grafis tetap bersih.

#### T: Dapatkah saya menggunakan kembali XForms di berbagai halaman dokumen PDF?

 A: Ya, Anda dapat menggunakan kembali XForms di beberapa halaman dengan menambahkan XForm yang sama ke`Resources.Forms` kumpulan halaman yang berbeda.

#### T: Apakah ada batasan jumlah XForm yang dapat saya buat?

J: Meskipun tidak ada batasan ketat untuk jumlah XForm yang dapat Anda buat, perlu diingat bahwa terlalu banyak XForm dapat memengaruhi kinerja dan penggunaan memori. Gunakan dengan bijaksana.

#### T: Dapatkah saya memutar XForm atau menerapkan transformasi lainnya?

 A: Ya, Anda bisa menggunakan`ConcatenateMatrix` operator untuk menerapkan transformasi seperti rotasi, penskalaan, dan translasi ke XForm.
