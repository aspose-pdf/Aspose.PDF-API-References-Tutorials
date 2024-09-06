---
title: Informasi Gambar Dalam File PDF
linktitle: Informasi Gambar Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Ekstrak informasi gambar dalam berkas PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 160
url: /id/net/programming-with-images/image-information/
---
Panduan ini akan memandu Anda langkah demi langkah cara mengekstrak informasi tentang gambar dalam file PDF menggunakan Aspose.PDF untuk .NET. Pastikan Anda telah menyiapkan lingkungan Anda dan ikuti langkah-langkah di bawah ini:

## Langkah 1: Tentukan direktori dokumen

 Pastikan untuk mengatur direktori dokumen yang benar. Ganti`"YOUR DOCUMENT DIRECTORY"` dalam kode dengan jalur ke direktori tempat dokumen PDF Anda berada.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Muat file PDF sumber

 Pada langkah ini, kita akan memuat file PDF sumber menggunakan`Document` kelas Aspose.PDF. Gunakan`Document` konstruktor dan meneruskan jalur ke dokumen PDF.

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## Langkah 3: Tetapkan resolusi default

Pada langkah ini, kita akan mengatur resolusi default untuk gambar. Dalam contoh ini, resolusi default ditetapkan pada 72.

```csharp
int defaultResolution = 72;
```

## Langkah 4: Inisialisasi objek dan penghitung

Pada langkah ini, kita akan menginisialisasi objek dan penghitung yang diperlukan untuk mengambil informasi gambar.

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## Langkah 5: Berputar melalui operator pada halaman pertama dokumen

Pada langkah ini, kita akan menelusuri operator di halaman pertama dokumen untuk mengidentifikasi operasi terkait gambar.

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## Langkah 6: Kelola operator dan ekstrak informasi gambar

Pada langkah ini, kami akan mengelola berbagai jenis operator dan mengekstrak informasi tentang gambar.

```csharp
Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;

//Menangani operasi GSave dan GRestore untuk transformasi
if (opSaveState != null)
{
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
}
else if (opRestoreState != null)
{
     graphicsState. Pop();
}
// Menangani operasi ConcatenateMatrix untuk transformasi
else if (opCtm != null)
{
     // Terapkan matriks transformasi
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
        (float)opCtm.Matrix.A,
        (float)opCtm.Matrix.B,
        (float)opCtm.Matrix.C,
        (float)opCtm.Matrix.D,
        (float)opCtm.Matrix.E,
        (float)opCtm.Matrix.F);


     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     keep on going;
}
// Menangani operasi Do untuk gambar
else if (opDo != null)
{
     if (imageNames.Contains(opDo.Name))
     {
         // Ambil gambarnya
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         // Ambil dimensi gambar
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         // Hitung resolusi berdasarkan informasi di atas
         double resHorizontal = originalWidth * defaultResolution / scaledWidth;
         double resVertical = originalHeight * defaultResolution / scaledHeight;
         // Menampilkan informasi gambar
         Console.Out.WriteLine(
                 string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
     }
}
```

### Contoh kode sumber untuk Informasi Gambar menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Muat file PDF sumber
Document doc = new Document(dataDir+ "ImageInformation.pdf");
// Tentukan resolusi default untuk gambar
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// Tentukan objek daftar array yang akan menampung nama gambar
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
// Masukkan objek untuk ditumpuk
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// Dapatkan semua operator di halaman pertama dokumen
foreach (Operator op in doc.Pages[1].Contents)
{
	// Gunakan operator GSave/GRestore untuk mengembalikan transformasi ke set sebelumnya
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// Buat instance objek ConcatenateMatrix sebagaimana objek tersebut mendefinisikan matriks transformasi saat ini.
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	// Buat operator Do yang menggambar objek dari sumber daya. Operator ini menggambar objek Form dan objek Image
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//Simpan status sebelumnya dan pindahkan status saat ini ke bagian atas tumpukan
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		// Buang status saat ini dan pulihkan status sebelumnya
		graphicsState.Pop();
	}
	else if (opCtm != null)
	{
		System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
		   (float)opCtm.Matrix.A,
		   (float)opCtm.Matrix.B,
		   (float)opCtm.Matrix.C,
		   (float)opCtm.Matrix.D,
		   (float)opCtm.Matrix.E,
		   (float)opCtm.Matrix.F);
		// Kalikan matriks saat ini dengan matriks status
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		// Jika ini adalah operator gambar gambar
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			// Buat objek XImage untuk menampung gambar halaman pdf pertama
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			// Dapatkan dimensi gambar
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			// Dapatkan informasi Tinggi dan Lebar gambar
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			// Hitung resolusi berdasarkan informasi di atas
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			// Menampilkan informasi Dimensi dan Resolusi setiap gambar
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## Kesimpulan

Selamat! Anda kini telah mempelajari cara mengekstrak informasi gambar dalam file PDF menggunakan Aspose.PDF for .NET. Anda dapat menggunakan informasi ini untuk berbagai tugas pemrosesan gambar dalam aplikasi Anda.

### FAQ untuk informasi gambar dalam file PDF

#### T: Apa tujuan mengekstrak informasi gambar dari dokumen PDF menggunakan Aspose.PDF untuk .NET?

A: Mengekstrak informasi gambar dari dokumen PDF memberikan wawasan tentang dimensi, resolusi, dan atribut gambar lainnya dalam dokumen. Informasi ini dapat digunakan untuk tugas pemrosesan, analisis, atau pengoptimalan gambar.

#### T: Bagaimana Aspose.PDF untuk .NET membantu mengekstrak informasi gambar dari dokumen PDF?

A: Aspose.PDF untuk .NET menyediakan alat untuk mengakses dan menganalisis konten dokumen PDF, termasuk gambarnya. Kode yang diberikan menunjukkan cara mengekstrak dan menampilkan informasi gambar menggunakan berbagai operator.

#### T: Informasi gambar apa saja yang dapat diekstraksi menggunakan metode ini?

A: Metode ini memungkinkan Anda mengekstrak dan menampilkan informasi seperti dimensi skala, resolusi, dan nama gambar untuk gambar dalam dokumen PDF.

#### T: Bagaimana kode mengidentifikasi dan memproses operator terkait gambar dalam dokumen PDF?

A: Kode tersebut mengulangi operator pada halaman tertentu dari dokumen PDF. Kode tersebut mengidentifikasi dan memproses operator yang terkait dengan operasi gambar, transformasi, dan rendering.

#### T: Apa pentingnya resolusi default, dan bagaimana ia digunakan dalam kode?

A: Resolusi default digunakan sebagai titik acuan untuk menghitung resolusi gambar yang sebenarnya. Kode menghitung resolusi setiap gambar berdasarkan dimensinya dan pengaturan resolusi default.

#### T: Bagaimana informasi gambar yang diekstraksi dapat digunakan dalam skenario dunia nyata?

A: Informasi gambar yang diekstraksi dapat digunakan untuk tugas-tugas seperti penilaian kualitas gambar, pengoptimalan gambar, pembuatan gambar mini, dan memfasilitasi proses pengambilan keputusan terkait gambar.

#### T: Dapatkah saya mengubah kode untuk mengekstrak atribut tambahan terkait gambar?

A: Ya, Anda dapat menyesuaikan kode untuk mengekstrak atribut tambahan gambar, seperti ruang warna, kedalaman piksel, atau jenis gambar.

#### T: Apakah proses ekstraksi informasi gambar membutuhkan banyak sumber daya atau memakan waktu?

A: Proses ekstraksi informasi gambar efisien dan dioptimalkan untuk kinerja, memastikan dampak minimal pada penggunaan sumber daya dan waktu pemrosesan.

#### T: Bagaimana pengembang dapat memperoleh manfaat dari mengidentifikasi dan mengekstrak informasi gambar dari dokumen PDF?

J: Pengembang dapat memperoleh wawasan tentang karakteristik gambar dalam dokumen PDF, sehingga memungkinkan mereka membuat keputusan yang tepat terkait manipulasi, pemrosesan, dan pengoptimalan gambar.

#### T: Dapatkah metode ini digunakan untuk pemrosesan batch dokumen PDF yang berisi gambar?

A: Ya, metode ini dapat diperluas untuk pemrosesan batch dengan mengulangi beberapa halaman atau dokumen, mengekstrak informasi gambar, dan melakukan tugas terkait gambar.