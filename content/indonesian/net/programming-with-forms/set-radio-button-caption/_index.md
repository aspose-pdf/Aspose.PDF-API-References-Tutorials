---
title: Mengatur Judul Tombol Radio
linktitle: Mengatur Judul Tombol Radio
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menggunakan Aspose.PDF untuk .NET untuk mengatur judul tombol radio dalam formulir PDF.
type: docs
weight: 280
url: /id/net/programming-with-forms/set-radio-button-caption/
---
Dalam panduan ini, kami akan menjelaskan langkah demi langkah cara menggunakan pustaka Aspose.PDF untuk .NET guna menentukan judul tombol radio dalam bentuk PDF. Kami akan menunjukkan cara mengakses kolom tombol radio, membuat opsi tombol radio baru, dan menyesuaikan judul tombol.

## Langkah 1: Mengonfigurasi direktori dokumen

 Langkah pertama adalah mengonfigurasi direktori dokumen tempat formulir PDF yang ingin Anda kerjakan berada. Anda dapat menggunakan`dataDir` variabel untuk menentukan jalur direktori.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Pastikan untuk mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 2: Memuat formulir PDF sumber

 Pada langkah ini, kita akan memuat formulir PDF sumber menggunakan`Aspose.Pdf.Facades.Form` kelas Aspose.PDF.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

Pastikan berkas PDF yang berisi formulir ada di direktori dokumen yang ditentukan.

## Langkah 3: Mengedit judul tombol radio

Kita akan menelusuri nama-nama kolom formulir dan mencari kolom tombol radio. Jika kolom yang cocok ditemukan, kita akan membuat opsi tombol radio baru dengan judul khusus dan menambahkannya ke kolom yang sudah ada.

```csharp
foreach(var item in form1.FieldNames)
{
if (item.Contains("radio1"))
{
Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
fieldoption.OptionName = "Yes";
fieldoption.PartialName = "Yesname";
var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
updatedFragment.TextState.FontSize = 10;
updatedFragment.TextState.LineSpacing = 6.32f;
// Membuat objek TextParagraph
TextParagraph par = new TextParagraph();
// Mengatur posisi paragraf
par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
// Tentukan mode pembungkusan kata
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
// Tambahkan TextFragment baru ke paragraf
par.AppendLine(updatedFragment);
// Tambahkan TextParagraph menggunakan TextBuilder
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

Sesuaikan tombol radio teks dan pengaturan lainnya sesuai kebutuhan.

## Langkah 4: Menyimpan PDF yang Dihasilkan

 Sekarang setelah kita selesai memodifikasi judul tombol radio, kita dapat menyimpan PDF yang dihasilkan menggunakan`Save` metode dari`Document` kelas.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Pastikan untuk menentukan jalur lengkap dan nama file untuk PDF yang dihasilkan.

### Contoh kode sumber untuk Set Radio Button Caption menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Muat formulir PDF sumber
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
Document PDF_Template_PDF_HTML = new Document(dataDir + "RadioButtonField.pdf");
foreach (var item in form1.FieldNames)
{
	Console.WriteLine(item.ToString());
	Dictionary<string, string> radioOptions = form1.GetButtonOptionValues(item);
	if (item.Contains("radio1"))
	{
		Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
		Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
		fieldoption.OptionName = "Yes";
		fieldoption.PartialName = "Yesname";
		var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
		updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
		updatedFragment.TextState.FontSize = 10;
		updatedFragment.TextState.LineSpacing = 6.32f;
		// Buat objek TextParagraph
		TextParagraph par = new TextParagraph();
		// Mengatur posisi paragraf
		par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
		// Tentukan mode pembungkusan kata
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		// Tambahkan TextFragment baru ke paragraf
		par.AppendLine(updatedFragment);
		// Tambahkan TextParagraph menggunakan TextBuilder
		TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
		textBuilder.AppendParagraph(par);
		field0.DeleteOption("item1");
	}
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

## Kesimpulan

Dalam panduan ini, kita mempelajari cara menggunakan pustaka Aspose.PDF untuk .NET guna mengatur teks untuk tombol radio dalam bentuk PDF. Dengan mengikuti langkah-langkah yang dijelaskan, Anda dapat menyesuaikan opsi tombol radio dan mengubah teks sesuai kebutuhan. Jangan ragu untuk menjelajahi lebih lanjut fitur-fitur Aspose.PDF untuk .NET guna memperluas kemungkinan dalam memanipulasi file PDF.

### Pertanyaan yang Sering Diajukan

#### T: Dapatkah saya menggunakan Aspose.PDF untuk .NET untuk mengatur keterangan tombol radio dalam formulir PDF?

A: Ya, Anda dapat menggunakan Aspose.PDF for .NET untuk menetapkan teks pada tombol radio dalam bentuk PDF. Contoh kode sumber yang diberikan menunjukkan cara mengakses kolom tombol radio, membuat opsi tombol radio baru dengan teks khusus, dan memperbarui kolom yang sudah ada.

#### T: Bagaimana cara menyesuaikan tampilan judul tombol radio, seperti ukuran dan warna font?

 A: Anda dapat menyesuaikan tampilan judul tombol radio dengan menyesuaikan properti`TextFragment` digunakan untuk keterangan. Misalnya, Anda dapat mengatur jenis huruf, ukuran huruf, warna, spasi baris, dan opsi pemformatan teks lainnya.

#### T: Apakah mungkin untuk menambahkan beberapa opsi tombol radio dengan keterangan berbeda ke satu grup tombol radio?

A: Ya, Anda dapat menambahkan beberapa opsi tombol radio dengan keterangan berbeda ke satu grup tombol radio. Setiap opsi akan mewakili pilihan yang berbeda, dan pengguna hanya dapat memilih satu opsi dari grup tersebut.

#### T: Dapatkah saya menggunakan Aspose.PDF untuk .NET untuk mengubah bidang formulir lain dalam dokumen PDF?

A: Ya, Aspose.PDF untuk .NET menyediakan serangkaian fitur lengkap untuk memanipulasi berbagai bidang formulir dalam dokumen PDF, seperti bidang teks, kotak centang, daftar dropdown, dan banyak lagi. Anda dapat menggunakan pustaka untuk menetapkan nilai, mengubah tampilan, dan menambahkan interaktivitas ke bidang formulir.

#### T: Apakah Aspose.PDF untuk .NET mendukung penggunaan PDF yang dihasilkan dari sumber lain, seperti dokumen yang dipindai?

A: Ya, Aspose.PDF untuk .NET mendukung penggunaan PDF yang dihasilkan dari berbagai sumber, termasuk dokumen yang dipindai. Pustaka ini menyediakan kemampuan OCR (Pengenalan Karakter Optik) untuk mengekstrak teks dari PDF yang dipindai dan memanipulasi konten secara terprogram.