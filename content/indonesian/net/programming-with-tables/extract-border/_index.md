---
title: Ekstrak Batas Dalam File PDF
linktitle: Ekstrak Batas Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mengekstrak batas dalam berkas PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 80
url: /id/net/programming-with-tables/extract-border/
---
Dalam tutorial ini, kita akan mempelajari cara mengekstrak border dalam file PDF menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber dalam C# langkah demi langkah. Di akhir tutorial ini, Anda akan mengetahui cara mengekstrak border dari dokumen PDF dan menyimpannya sebagai gambar. Mari kita mulai!

## Langkah 1: Menyiapkan lingkungan
Pertama, pastikan Anda telah menyiapkan lingkungan pengembangan C# dengan Aspose.PDF untuk .NET. Tambahkan referensi ke pustaka dan impor namespace yang diperlukan.

## Langkah 2: Memuat Dokumen PDF
Pada langkah ini, kami memuat dokumen PDF dari berkas yang ditentukan.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan direktori sebenarnya tempat berkas PDF Anda berada.

## Langkah 3: Ekstraksi Tepi
Kita akan mengekstrak batas dari dokumen PDF dengan mengulangi operasi yang terdapat dalam dokumen.

```csharp
Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
     // Memproses semua operasi konten
     foreach(Operator op in doc.Pages[1].Contents)
     {
         // Periksa jenis operasinya
         // ...
         // Tambahkan kode untuk memproses setiap operasi
     }
}
```

 Kami menciptakan sebuah`graphicsState` tumpukan untuk menyimpan status grafik, gambar bitmap untuk menangkap perbatasan yang diekstraksi,`GraphicsPath` objek untuk menyimpan jalur gambar, dan variabel lain untuk melacak status dan warna.

## Langkah 4: Pemrosesan Transaksi
Pada langkah ini, kami memproses setiap operasi dokumen untuk mengekstraksi batas.

```csharp
// Periksa jenis operasinya
if (opSaveState != null)
{
     // Simpan status sebelumnya dan pindahkan status saat ini ke bagian atas tumpukan
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opRestoreState != null)
{
     // Hapus status saat ini dan pulihkan status sebelumnya
     graphicsState. Pop();
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opCtm != null)
{
     // Ambil matriks transformasi saat ini
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
         (float)opCtm.Matrix.A,
         (float)opCtm.Matrix.B,
         (float)opCtm.Matrix.C,
         (float)opCtm.Matrix.D,
         (float)opCtm.Matrix.E,
         (float)opCtm.Matrix.F);

     // Kalikan matriks saat ini dengan matriks status
     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opMoveTo != null)
{
     // Perbarui titik gambar terakhir
     lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
     // Proses menggambar garis
     // ...
     // Tambahkan kode untuk menangani penggambaran garis
}
// ...
// Tambahkan blok else if untuk operasi lainnya
```

Kami memeriksa jenis operasi menggunakan kondisi dan menjalankan kode yang sesuai untuk setiap operasi.

## Langkah 5: Cadangkan Gambar
Terakhir, kita simpan gambar bitmap berisi batas yang diekstrak ke berkas yang ditentukan.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

Pastikan untuk menentukan direktori dan nama file yang benar untuk menyimpan gambar keluaran.

### Contoh kode sumber untuk Ekstraksi Batas menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "input.pdf");

Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
// Nilai matriks ctm default adalah 1,0,0,1,0,0
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
//Sistem koordinat gambar berbasis kiri atas, sedangkan sistem koordinat pdf berbasis kiri bawah, jadi kita harus menerapkan matriks inversi
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
	gr.SmoothingMode = SmoothingMode.HighQuality;
	graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));

	// Memproses semua perintah konten
	foreach (Operator op in doc.Pages[1].Contents)
	{
		Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
		Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
		Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
		Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
		Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
		Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;
		Aspose.Pdf.Operators.EndPath opEndPath = op as Aspose.Pdf.Operators.EndPath;
		Aspose.Pdf.Operators.Stroke opStroke = op as Aspose.Pdf.Operators.Stroke;
		Aspose.Pdf.Operators.Fill opFill = op as Aspose.Pdf.Operators.Fill;
		Aspose.Pdf.Operators.EOFill opEOFill = op as Aspose.Pdf.Operators.EOFill;
		Aspose.Pdf.Operators.SetRGBColor opRGBFillColor = op as Aspose.Pdf.Operators.SetRGBColor;
		Aspose.Pdf.Operators.SetRGBColorStroke opRGBStrokeColor = op as Aspose.Pdf.Operators.SetRGBColorStroke;

		if (opSaveState != null)
		{
			// Simpan status sebelumnya dan pindahkan status saat ini ke bagian atas tumpukan
			graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opRestoreState != null)
		{
			// Buang status saat ini dan pulihkan status sebelumnya
			graphicsState.Pop();
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
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
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opMoveTo != null)
		{
			lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
		}
		else if (opLineTo != null)
		{
			System.Drawing.PointF linePoint = new System.Drawing.PointF((float)opLineTo.X, (float)opLineTo.Y);
			graphicsPath.AddLine(lastPoint, linePoint);

			lastPoint = linePoint;
		}
		else if (opRe != null)
		{
			System.Drawing.RectangleF re = new System.Drawing.RectangleF((float)opRe.X, (float)opRe.Y, (float)opRe.Width, (float)opRe.Height);
			graphicsPath.AddRectangle(re);
		}
		else if (opEndPath != null)
		{
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opRGBFillColor != null)
		{
			fillColor = opRGBFillColor.getColor();
		}
		else if (opRGBStrokeColor != null)
		{
			strokeColor = opRGBStrokeColor.getColor();
		}
		else if (opStroke != null)
		{
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opFill != null)
		{
			graphicsPath.FillMode = FillMode.Winding;
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.FillPath(new System.Drawing.SolidBrush(fillColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opEOFill != null)
		{
			graphicsPath.FillMode = FillMode.Alternate;
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.FillPath(new System.Drawing.SolidBrush(fillColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
	}
}
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);

Console.WriteLine("\nBorder extracted successfully as image.\nFile saved at " + dataDir);
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara mengekstrak border dari dokumen PDF menggunakan Aspose.PDF for .NET. Anda dapat menggunakan panduan langkah demi langkah ini untuk mengekstrak border dari dokumen PDF lainnya.

### FAQ untuk mengekstrak batas dalam file PDF

#### T: Apa tujuan mengekstrak batas dari berkas PDF?

A: Mengekstrak border dari file PDF dapat berguna untuk berbagai keperluan. Hal ini memungkinkan Anda untuk mengisolasi dan menganalisis elemen struktural dokumen, seperti tabel, diagram, atau elemen grafis. Anda dapat menggunakan border yang diekstrak untuk mengidentifikasi tata letak, dimensi, dan posisi konten dalam dokumen PDF.

#### T: Dapatkah saya mengekstrak batas dari halaman atau area tertentu dalam dokumen PDF?

 A: Ya, Anda dapat memodifikasi kode sumber C# yang disediakan untuk mengekstrak batas dari halaman atau wilayah tertentu dalam dokumen PDF. Dengan memanipulasi`doc.Pages` koleksi dan menentukan kriteria khusus, Anda dapat memilih untuk mengekstrak batas dari halaman atau area minat tertentu.

#### T: Bagaimana saya dapat menyesuaikan format dan kualitas gambar keluaran?

 A: Dalam kode C# yang diberikan, border yang diekstrak disimpan sebagai gambar PNG. Jika Anda ingin mengubah format gambar output, Anda dapat memodifikasi`ImageFormat.Png` parameternya di dalam`bitmap.Save` metode ini ke format gambar lain yang didukung, seperti JPEG, BMP, atau GIF. Selain itu, Anda dapat menyesuaikan kualitas gambar atau pengaturan kompresi berdasarkan kebutuhan Anda.

#### T: Operasi apa lagi yang dapat saya lakukan pada perbatasan yang diekstraksi?

J: Setelah Anda mengekstraksi border sebagai gambar, Anda dapat memprosesnya lebih lanjut menggunakan pustaka atau algoritma pemrosesan gambar. Anda dapat menganalisis gambar, menerapkan filter gambar, mendeteksi pola, atau menjalankan OCR (Optical Character Recognition) untuk mengekstraksi teks dari gambar jika diperlukan.

#### T: Apakah ada batasan atau pertimbangan saat mengekstrak batas dari dokumen PDF yang kompleks?

A: Proses ekstraksi dapat bervariasi tergantung pada kompleksitas dokumen PDF. PDF yang kompleks dengan beberapa lapisan, transparansi, atau grafik canggih mungkin memerlukan pemrosesan atau penyesuaian tambahan untuk mengekstraksi batas secara akurat. Sangat penting untuk menguji proses ekstraksi secara menyeluruh pada berbagai dokumen PDF guna memastikan hasil yang dapat diandalkan.