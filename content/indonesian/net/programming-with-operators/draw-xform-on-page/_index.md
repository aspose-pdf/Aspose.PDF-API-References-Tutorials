---
title: Gambar XForm Di Halaman
linktitle: Gambar XForm Di Halaman
second_title: Aspose.PDF untuk Referensi .NET API
description: Panduan langkah demi langkah menggambar formulir XForm pada halaman PDF menggunakan Aspose.PDF untuk .NET. Tambahkan dan posisikan formulir di halaman.
type: docs
weight: 10
url: /id/net/programming-with-operators/draw-xform-on-page/
---
Dalam tutorial ini, kami akan memberi Anda panduan langkah demi langkah tentang cara menggambar XForm pada halaman menggunakan Aspose.PDF untuk .NET. Aspose.PDF adalah perpustakaan canggih yang memungkinkan Anda membuat, memanipulasi, dan mengonversi dokumen PDF secara terprogram. Menggunakan operator yang disediakan oleh Aspose.PDF, Anda dapat menambahkan dan memposisikan formulir XForm pada halaman PDF yang ada.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki prasyarat berikut:

1. Visual Studio diinstal dengan kerangka .NET.
2. Pustaka Aspose.PDF untuk .NET.

## Langkah 1: Pengaturan Proyek

Untuk memulai, buat proyek baru di Visual Studio dan tambahkan referensi ke perpustakaan Aspose.PDF untuk .NET. Anda dapat mengunduh perpustakaan dari situs resmi Aspose dan menginstalnya di mesin Anda.

## Langkah 2: Impor namespace yang diperlukan

Dalam file kode C# Anda, impor namespace yang diperlukan untuk mengakses kelas dan metode yang disediakan oleh Aspose.PDF:

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

Pastikan untuk menentukan jalur file sebenarnya di mesin Anda.

## Langkah 4: Memuat file PDF masukan

Gunakan kode berikut untuk memuat file PDF masukan:

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
// Kode berikut menggunakan operator GSave/GRestore
// Kode ini menggunakan operator ContatenateMatrix untuk memposisikan XForm
// Kode tersebut menggunakan operator Do untuk menggambar XForm pada halaman
// Operator GSave/GRestore membungkus konten yang ada
// hal ini dilakukan untuk mendapatkan keadaan grafik awal di akhir konten yang ada
// jika tidak, mungkin akan terjadi transformasi yang tidak diinginkan pada akhir rantai operator yang ada
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// Tambahkan operator GSave untuk mengatur ulang status grafis dengan benar setelah perintah baru
pageContents. Add(new GSave());

// Buat XForm
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// Atur lebar dan tinggi gambar
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// Muat gambar ke dalam aliran
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// Tambahkan gambar ke koleksi gambar sumber daya XForm
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// Menggunakan operator Do: operator ini menggambar gambar
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
//Posisikan XForm pada koordinat x=100 dan y=500
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// Gambar XForm dengan operator Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// Posisikan XForm pada koordinat x=100 dan y=300
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// Gambar XForm dengan operator Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// Pulihkan status grafis dengan GRestore setelah GSave
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

Pastikan untuk menentukan jalur file sebenarnya dan sesuaikan nomor halaman dan posisi XForm sesuai kebutuhan.

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
	// Penggunaan operator ContatateMatrix ke posisi xForm
	// Lakukan penggunaan operator untuk menggambar xForm di halaman
	// Bungkus konten yang ada dengan pasangan operator GSave/GRestore
	// ini untuk mendapatkan status grafis awal pada dan konten yang ada
	// jika tidak, mungkin masih ada beberapa transformasi yang tidak diinginkan pada akhir rantai operator yang ada
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Tambahkan operator simpan status grafis untuk menghapus status grafis dengan benar setelah perintah baru
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
	//Tambahkan gambar ke koleksi Gambar Sumber Daya XForm
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// Menggunakan operator Do: operator ini menggambar gambar
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Tempatkan formulir pada koordinat x=100 y=500
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// Menggambar formulir dengan operator Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Tempatkan formulir pada koordinat x=100 y=300
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// Menggambar formulir dengan operator Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Pulihkan status grafis dengan GRestore setelah GSave
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## Kesimpulan

Dalam tutorial ini, Anda mempelajari cara menggambar formulir XForm pada halaman PDF menggunakan Aspose.PDF untuk .NET. Dengan mengikuti langkah-langkah yang dijelaskan, Anda akan dapat menambahkan dan memposisikan formulir XForm pada halaman yang sudah ada, sehingga memberikan lebih banyak fleksibilitas pada dokumen PDF Anda.

### FAQ untuk menggambar XForm di halaman

#### T: Apa itu XForm di Aspose.PDF?

J: XForm adalah objek grafis yang dapat digunakan kembali dalam dokumen PDF. Ini memungkinkan Anda untuk menentukan dan menggambar grafik, gambar, atau teks kompleks yang dapat digunakan kembali beberapa kali di halaman berbeda.

#### T: Bagaimana cara mengimpor namespace yang diperlukan untuk Aspose.PDF?

 A: Dalam file kode C# Anda, gunakan`using` arahan untuk mengimpor namespace yang diperlukan untuk mengakses kelas dan metode yang disediakan oleh Aspose.PDF:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### Q: Apa tujuan dari operator GSave dan GRestore?

 J: Itu`GSave` Dan`GRestore`operator di Aspose.PDF digunakan untuk menyimpan dan memulihkan keadaan grafik. Mereka membantu memastikan bahwa transformasi dan pengaturan yang diterapkan pada satu bagian konten tidak mempengaruhi bagian berikutnya.

#### T: Bagaimana cara mendefinisikan XForm menggunakan Aspose.PDF?

 J: Untuk membuat XForm, gunakan`XForm.CreateNewForm` metode dan menambahkannya ke`Resources.Forms` kumpulan halaman tertentu. Anda kemudian dapat menambahkan konten ke XForm`Contents` Properti.

#### T: Bagaimana cara menggambar gambar dalam XForm?

 J: Muat gambar ke dalam aliran dan tambahkan ke`Resources.Images` koleksi XForm. Menggunakan`Do` operator dalam XForm`Contents` untuk menggambar gambar.

#### T: Bagaimana cara memposisikan XForm pada halaman PDF?

 J: Untuk memposisikan XForm pada halaman, gunakan`ConcatenateMatrix` operator di dalam halaman`Contents`. Sesuaikan parameter matriks untuk menentukan terjemahan (posisi) dan penskalaan XForm.

#### T: Bisakah saya menggambar beberapa XForm di halaman yang sama?

 A: Ya, Anda dapat menggambar beberapa XForm pada halaman yang sama dengan menyesuaikannya`ConcatenateMatrix`parameter untuk memposisikan setiap XForm pada koordinat yang berbeda.

#### T: Bisakah saya mengubah konten XForm setelah dibuat?

 J: Ya, Anda dapat memodifikasi konten XForm setelah pembuatan dengan menambahkan operator tambahan ke dalamnya`Contents` Properti.

#### T: Apa yang terjadi jika saya menghilangkan operator GSave dan GRestore?

J: Menghilangkan operator GSave dan GRestore dapat menyebabkan transformasi atau setelan yang tidak diinginkan diterapkan pada konten berikutnya. Menggunakannya membantu menjaga kondisi grafis tetap bersih.

#### T: Bisakah saya menggunakan kembali XForms di berbagai halaman dokumen PDF?

 J: Ya, Anda dapat menggunakan kembali XForm di beberapa halaman dengan menambahkan XForm yang sama ke dalamnya`Resources.Forms` kumpulan halaman yang berbeda.

#### Q: Apakah ada batasan jumlah XForm yang bisa saya buat?

J: Meskipun tidak ada batasan ketat mengenai jumlah XForm yang dapat Anda buat, perlu diingat bahwa terlalu banyak XForm dapat memengaruhi kinerja dan penggunaan memori. Gunakan dengan bijaksana.

#### T: Dapatkah saya memutar XForm atau menerapkan transformasi lainnya?

 A: Ya, Anda dapat menggunakan`ConcatenateMatrix`operator untuk menerapkan transformasi seperti rotasi, penskalaan, dan terjemahan ke XForm.
