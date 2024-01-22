---
title: Ekstrak Perbatasan Dalam File PDF
linktitle: Ekstrak Perbatasan Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara mengekstrak batas dalam file PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 80
url: /id/net/programming-with-tables/extract-border/
---
Dalam tutorial ini, kita akan mempelajari cara mengekstrak perbatasan dalam file PDF menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber dalam C# langkah demi langkah. Di akhir tutorial ini, Anda akan mengetahui cara mengekstrak batas dari dokumen PDF dan menyimpannya sebagai gambar. Ayo mulai!

## Langkah 1: Menyiapkan lingkungan
Pertama, pastikan Anda telah menyiapkan lingkungan pengembangan C# dengan Aspose.PDF untuk .NET. Tambahkan referensi ke perpustakaan dan impor namespace yang diperlukan.

## Langkah 2: Memuat Dokumen PDF
Pada langkah ini, kami memuat dokumen PDF dari file yang ditentukan.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan direktori sebenarnya tempat file PDF Anda berada.

## Langkah 3: Ekstraksi Tepi
Kami akan mengekstrak batas dari dokumen PDF dengan mengulangi operasi yang terdapat dalam dokumen tersebut.

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
     // Proses semua operasi konten
     foreach(Operator op in doc.Pages[1].Contents)
     {
         // Periksa jenis operasinya
         // ...
         // Tambahkan kode untuk memproses setiap operasi
     }
}
```

 Kami membuat`graphicsState` tumpukan untuk menyimpan status grafik, gambar bitmap untuk menangkap batas yang diekstraksi, a`GraphicsPath` objek untuk menyimpan jalur gambar, dan variabel lain untuk melacak keadaan dan warna.

## Langkah 4: Pemrosesan Transaksi
Pada langkah ini, kami memproses setiap operasi dokumen untuk mengekstrak perbatasan.

```csharp
// Periksa jenis operasinya
if (opSaveState != null)
{
     // Simpan keadaan sebelumnya dan dorong keadaan saat ini ke puncak tumpukan
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opRestoreState != null)
{
     // Hapus keadaan saat ini dan pulihkan keadaan sebelumnya
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

     // Kalikan matriks saat ini dengan matriks keadaan
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
     // Tambahkan kode untuk menangani menggambar garis
}
// ...
// Tambahkan blok else if untuk operasi lainnya
```

Kami memeriksa jenis operasi menggunakan kondisi dan menjalankan kode yang sesuai untuk setiap operasi.

## Langkah 5: Cadangkan Gambar
Terakhir, kami menyimpan gambar bitmap yang berisi batas yang diekstraksi ke file tertentu.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

Pastikan untuk menentukan direktori dan nama file yang benar untuk menyimpan gambar keluaran.

### Contoh kode sumber untuk Ekstrak Perbatasan menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "input.pdf");

Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
// Nilai matriks ctm default adalah 1,0,0,1,0,0
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
//Sistem.Gambar sistem koordinat berbasis kiri atas, sedangkan sistem koordinat pdf berbasis kiri bawah, jadi kita harus menerapkan matriks inversi
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
			//Simpan status sebelumnya dan dorong status saat ini ke bagian atas tumpukan
			graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opRestoreState != null)
		{
			// Buang keadaan saat ini dan pulihkan keadaan sebelumnya
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

			// Kalikan matriks saat ini dengan matriks keadaan
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
Dalam tutorial ini, kita mempelajari cara mengekstrak batas dari dokumen PDF menggunakan Aspose.PDF untuk .NET. Anda dapat menggunakan panduan langkah demi langkah ini untuk mengekstrak batas dari dokumen PDF lainnya.

### FAQ untuk mengekstrak batas dalam file PDF

#### T: Apa tujuan mengekstraksi perbatasan dari file PDF?

A: Mengekstrak border dari file PDF dapat berguna untuk berbagai tujuan. Ini memungkinkan Anda untuk mengisolasi dan menganalisis elemen struktural dokumen, seperti tabel, diagram, atau elemen grafis. Anda dapat menggunakan batas yang diekstraksi untuk mengidentifikasi tata letak, dimensi, dan posisi konten dalam dokumen PDF.

#### T: Bisakah saya mengekstrak batas halaman atau area tertentu dalam dokumen PDF?

J: Ya, Anda dapat memodifikasi kode sumber C# yang disediakan untuk mengekstrak batas dari halaman atau wilayah tertentu dalam dokumen PDF. Dengan memanipulasi`doc.Pages` pengumpulan dan menentukan kriteria khusus, Anda dapat memilih untuk mengekstrak batas dari halaman atau bidang minat tertentu.

#### T: Bagaimana cara menyesuaikan format dan kualitas gambar keluaran?

 A: Dalam kode C# yang disediakan, batas yang diekstraksi disimpan sebagai gambar PNG. Jika Anda ingin mengubah format gambar keluaran, Anda dapat memodifikasi`ImageFormat.Png` parameter di`bitmap.Save` metode ke format gambar lain yang didukung, seperti JPEG, BMP, atau GIF. Selain itu, Anda dapat menyesuaikan pengaturan kualitas gambar atau kompresi berdasarkan kebutuhan Anda.

#### T: Operasi apa lagi yang dapat saya lakukan pada perbatasan yang diekstraksi?

J: Setelah Anda mengekstrak batas sebagai gambar, Anda dapat memprosesnya lebih lanjut menggunakan perpustakaan atau algoritma pemrosesan gambar. Anda dapat menganalisis gambar, menerapkan filter gambar, mendeteksi pola, atau melakukan OCR (Optical Character Recognition) untuk mengekstrak teks dari gambar jika diperlukan.

#### T: Apakah ada batasan atau pertimbangan saat mengekstraksi batas dari dokumen PDF yang rumit?

A: Proses ekstraksi dapat bervariasi tergantung kompleksitas dokumen PDF. PDF kompleks dengan banyak lapisan, transparansi, atau grafik tingkat lanjut mungkin memerlukan pemrosesan atau penyesuaian tambahan untuk mengekstrak batasnya secara akurat. Penting untuk menguji proses ekstraksi secara menyeluruh pada berbagai dokumen PDF untuk memastikan hasil yang dapat diandalkan.