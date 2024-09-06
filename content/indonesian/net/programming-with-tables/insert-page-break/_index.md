---
title: Sisipkan Hentian Halaman dalam File PDF
linktitle: Sisipkan Hentian Halaman dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menyisipkan jeda halaman dalam berkas PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 110
url: /id/net/programming-with-tables/insert-page-break/
---
Dalam tutorial ini, kita akan mempelajari cara menyisipkan pemisah halaman dalam berkas PDF menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber dalam C# langkah demi langkah. Di akhir tutorial ini, Anda akan mengetahui cara menambahkan pemisah halaman setelah sejumlah baris tertentu dalam tabel dokumen PDF. Mari kita mulai!

## Langkah 1: Menyiapkan lingkungan
Pastikan Anda telah mengonfigurasi lingkungan pengembangan C# dengan Aspose.PDF untuk .NET. Tambahkan referensi ke pustaka dan impor namespace yang diperlukan.

## Langkah 2: Membuat Dokumen dan Tabel
Kita buat contoh Dokumen baru dan tambahkan halaman ke dokumen ini. Selanjutnya, kita buat contoh Tabel untuk mewakili tabel kita dalam dokumen PDF. Kita juga tentukan gaya batas untuk tabel tersebut.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## Langkah 3: Tambahkan baris ke tabel
Kami menggunakan loop untuk menambahkan 200 baris ke array. Untuk setiap baris, kami membuat contoh Baris dan menambahkan dua sel dengan konten teks.

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
    
     // Ketika 10 baris ditambahkan, kami memasukkan jeda halaman baru
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## Langkah 4: Menambahkan tabel ke dokumen
Kami menambahkan tabel ke koleksi paragraf di halaman dokumen.

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## Langkah 5: Simpan dokumen
Kami menyimpan dokumen PDF dengan memasukkan pemisah halaman.

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### Contoh kode sumber untuk Sisipkan Hentian Halaman menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Membuat contoh dokumen
Document doc = new Document();
// Tambahkan halaman ke koleksi halaman file PDF
doc.Pages.Add();
// Buat contoh tabel
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// Mengatur gaya batas untuk tabel
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
	// Ketika 10 baris ditambahkan, render baris baru di halaman baru
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
Dalam tutorial ini, kita mempelajari cara menyisipkan pemisah halaman dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Anda dapat menggunakan panduan langkah demi langkah ini untuk menambahkan pemisah halaman setelah sejumlah baris tertentu dalam tabel dalam dokumen PDF menggunakan C#.

### FAQ untuk menyisipkan pemisah halaman dalam file PDF

#### T: Bagaimana cara mengubah ukuran halaman untuk halaman baru yang dibuat setelah hentian halaman?

 A: Untuk mengubah ukuran halaman untuk halaman baru yang dibuat setelah hentian halaman, Anda dapat mengatur`PageSize` milik`Page` objek. Misalnya, Anda dapat menggunakan kode berikut untuk mengatur ukuran halaman ke A4:

```csharp
// Atur ukuran halaman ke A4
doc.Pages[1].SetPageSize(PageSize.A4);
```

#### T: Dapatkah saya mengontrol margin halaman untuk halaman baru setelah jeda halaman?

 A: Ya, Anda dapat mengontrol margin halaman untuk halaman baru setelah jeda halaman. Gunakan`Margin` milik`Page` objek untuk mengatur margin halaman. Misalnya, untuk mengatur semua margin menjadi 10 poin, Anda dapat menggunakan kode berikut:

```csharp
// Atur semua margin menjadi 10 poin
doc.Pages[1].Margin = new MarginInfo(10, 10, 10, 10);
```

#### T: Apakah mungkin untuk menambahkan header dan footer ke halaman baru setelah hentian halaman?

 A: Ya, Anda dapat menambahkan header dan footer ke halaman baru setelah jeda halaman. Gunakan`Page.Header` Dan`Page.Footer` properti untuk menambahkan konten ke bagian header dan footer halaman. Misalnya:

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

#### T: Dapatkah saya menyisipkan jeda halaman di lokasi tertentu selain setelah sejumlah baris tertentu?

 A: Ya, Anda dapat menyisipkan pemisah halaman di lokasi tertentu selain setelah sejumlah baris tertentu. Anda dapat mengatur`IsInNewPage` properti baris ke`true` untuk memaksa tabel memulai halaman baru setelah baris tersebut.

#### T: Bagaimana cara menyesuaikan perilaku hentian halaman berdasarkan tinggi konten?

 A: Kamu bisa menggunakan`IsBroken` properti tabel untuk mengaktifkan atau menonaktifkan pemisahan baris otomatis di seluruh halaman. Saat diatur ke`true`, ini memungkinkan baris dipecah di beberapa halaman berdasarkan tinggi konten.