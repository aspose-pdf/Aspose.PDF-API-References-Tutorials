---
title: Sisipkan Page Break dalam File PDF
linktitle: Sisipkan Page Break dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menyisipkan hentian halaman dalam file PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 110
url: /id/net/programming-with-tables/insert-page-break/
---
Dalam tutorial ini, kita akan mempelajari cara menyisipkan hentian halaman dalam file PDF menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber dalam C# langkah demi langkah. Di akhir tutorial ini, Anda akan mengetahui cara menambahkan hentian halaman setelah sejumlah baris tertentu dalam tabel dokumen PDF. Ayo mulai!

## Langkah 1: Menyiapkan lingkungan
Pastikan Anda telah mengonfigurasi lingkungan pengembangan C# Anda dengan Aspose.PDF untuk .NET. Tambahkan referensi ke perpustakaan dan impor namespace yang diperlukan.

## Langkah 2: Membuat Dokumen dan Tabel
Kami membuat instance Dokumen baru dan menambahkan halaman ke dokumen ini. Selanjutnya, kita membuat instance Tabel untuk mewakili tabel kita di dokumen PDF. Kami juga menentukan gaya batas untuk tabel.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## Langkah 3: Tambahkan baris ke tabel
Kami menggunakan loop untuk menambahkan 200 baris ke array. Untuk setiap baris, kami membuat instance Row dan menambahkan dua sel dengan konten teks.

```csharp
for (int counter = 0; counter <= 200; counter++)
{
     Aspose.Pdf.Row row = new Aspose.Pdf.Row();
     tab. Rows. Add(row);
    
     Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
     cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
     row. Cells. Add(cell1);
    
     Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
     cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
     row. Cells. Add(cell2);
    
     // Ketika 10 baris ditambahkan, kami menyisipkan hentian halaman baru
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## Langkah 4: Menambahkan tabel ke dokumen
Kami menambahkan tabel ke kumpulan paragraf di halaman dokumen.

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## Langkah 5: Simpan dokumen
Kami menyimpan dokumen PDF dengan page break dimasukkan.

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### Contoh kode sumber untuk Sisipkan Page Break menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat instance Dokumen
Document doc = new Document();
// Tambahkan halaman ke halaman koleksi file PDF
doc.Pages.Add();
// Buat contoh tabel
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// Tetapkan gaya batas untuk tabel
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Tetapkan gaya batas default untuk tabel dengan warna batas sebagai Merah
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Tentukan lebar kolom tabel
tab.ColumnWidths = "100 100";
// Buat loop untuk menambahkan 200 baris untuk tabel
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// Saat 10 baris ditambahkan, render baris baru di halaman baru
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
// Tambahkan tabel ke kumpulan paragraf file PDF
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
// Simpan dokumen PDF
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara menyisipkan hentian halaman dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Anda dapat menggunakan panduan langkah demi langkah ini untuk menambahkan hentian halaman setelah sejumlah baris tertentu dalam tabel dalam dokumen PDF menggunakan C#.

### FAQ untuk menyisipkan hentian halaman dalam file PDF

#### T: Bagaimana cara mengubah ukuran halaman untuk halaman baru yang dibuat setelah hentian halaman?

 J: Untuk mengubah ukuran halaman pada halaman baru yang dibuat setelah hentian halaman, Anda dapat mengaturnya`PageSize` properti dari`Page` obyek. Misalnya, Anda dapat menggunakan kode berikut untuk mengatur ukuran halaman menjadi A4:

```csharp
// Atur ukuran halaman menjadi A4
doc.Pages[1].SetPageSize(PageSize.A4);
```

#### T: Bisakah saya mengontrol margin halaman untuk halaman baru setelah hentian halaman?

 J: Ya, Anda dapat mengontrol margin halaman untuk halaman baru setelah hentian halaman. Menggunakan`Margin` properti dari`Page` objek untuk mengatur margin halaman. Misalnya, untuk mengatur semua margin menjadi 10 poin, Anda dapat menggunakan kode berikut:

```csharp
// Tetapkan semua margin menjadi 10 poin
doc.Pages[1].Margin = new MarginInfo(10, 10, 10, 10);
```

#### T: Apakah mungkin untuk menambahkan header dan footer ke halaman baru setelah hentian halaman?

 J: Ya, Anda dapat menambahkan header dan footer ke halaman baru setelah hentian halaman. Menggunakan`Page.Header` Dan`Page.Footer` properti untuk menambahkan konten ke bagian header dan footer halaman. Misalnya:

```csharp
// Tambahkan header ke halaman baru
doc.Pages[1].Header = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Header content") }
};

// Tambahkan footer ke halaman baru
doc.Pages[1].Footer = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Footer content") }
};
```

#### T: Dapatkah saya menyisipkan hentian halaman di lokasi tertentu selain setelah sejumlah baris tertentu?

 J: Ya, Anda dapat menyisipkan hentian halaman di lokasi tertentu selain setelah sejumlah baris tertentu. Anda dapat mengatur`IsInNewPage` properti baris ke`true` untuk memaksa tabel memulai halaman baru setelah baris itu.

#### T: Bagaimana cara menyesuaikan perilaku hentian halaman berdasarkan tinggi konten?

J: Anda dapat menggunakan`IsBroken` properti tabel untuk mengaktifkan atau menonaktifkan pemecahan baris otomatis di seluruh halaman. Saat diatur ke`true`, ini memungkinkan baris untuk dipecah menjadi beberapa halaman berdasarkan tinggi konten.