---
title: Mengatur Judul Tombol Radio
linktitle: Mengatur Judul Tombol Radio
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mengatur teks tombol radio dalam PDF menggunakan Aspose.PDF untuk .NET. Panduan langkah demi langkah ini memandu Anda dalam memuat, memodifikasi, dan menyimpan formulir PDF Anda.
type: docs
weight: 280
url: /id/net/programming-with-forms/set-radio-button-caption/
---
## Perkenalan

Jika Anda ingin mencoba manipulasi PDF dengan Aspose.PDF untuk .NET, Anda akan dimanjakan! Hari ini, kami akan fokus pada fitur praktis: pengaturan teks tombol radio dalam formulir PDF Anda. Tombol radio sangat penting untuk formulir pengguna yang mengharuskan Anda memilih dari serangkaian opsi. Bayangkan tombol radio sebagai pertanyaan pilihan ganda yang hanya boleh dijawab dengan satu jawaban. Tutorial ini akan memandu Anda melalui proses pembaruan teks tombol radio dalam formulir PDF, sehingga dokumen Anda interaktif dan mudah digunakan. 

## Prasyarat

Sebelum menyelami kode, ada beberapa hal yang perlu Anda pastikan:

1. Aspose.PDF untuk .NET: Pastikan Anda telah menginstal pustaka Aspose.PDF. Pustaka ini akan membantu Anda memanipulasi file PDF secara terprogram.
2. Lingkungan Pengembangan: Anda harus menyiapkan lingkungan pengembangan .NET, seperti Visual Studio.
3. Contoh Formulir PDF: Untuk tutorial ini, Anda memerlukan contoh formulir PDF dengan tombol radio. Anda dapat menggunakan formulir PDF yang sudah ada atau membuat yang baru dengan tombol radio.
4. Pengetahuan Dasar C#: Panduan ini mengasumsikan Anda memiliki pemahaman dasar tentang konsep pemrograman C# dan .NET.

 Jika Anda belum menginstal Aspose.PDF untuk .NET atau Anda memerlukan lisensi sementara, Anda dapat[unduh disini](https://releases.aspose.com/pdf/net/) atau[dapatkan lisensi sementara](https://purchase.aspose.com/temporary-license/).

## Paket Impor

Untuk memulai, Anda perlu mengimpor paket yang diperlukan ke dalam proyek C# Anda. Berikut cara menyertakan pustaka Aspose.PDF:

```csharp
using System;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
using Aspose.Pdf.Text;
```

Pastikan Anda telah menambahkan paket-paket ini ke proyek Anda melalui NuGet atau metode pilihan Anda.

## Langkah 1: Muat Formulir PDF

 Pertama, Anda perlu memuat formulir PDF yang berisi tombol radio.`Aspose.Pdf.Facades.Form`class digunakan untuk tujuan ini. Berikut cara melakukannya:

```csharp
// Tentukan jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Muat formulir PDF sumber
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
Document PDF_Template_PDF_HTML = new Document(dataDir + "RadioButtonField.pdf");
```

Dalam potongan kode ini:
- `dataDir` menentukan jalur tempat PDF Anda berada.
- `Form` kelas digunakan untuk berinteraksi dengan kolom formulir dalam PDF.
- `Document` kelas menyediakan akses ke halaman dokumen PDF.

## Langkah 2: Ulangi Melalui Bidang Tombol Radio

Berikutnya, Anda perlu mengulangi kolom-kolom di formulir Anda untuk mengidentifikasi dan memanipulasi kolom tombol radio:

```csharp
foreach (var item in form1.FieldNames)
{
    Console.WriteLine(item.ToString());
    Dictionary<string, string> radioOptions = form1.GetButtonOptionValues(item);
```

Dalam lingkaran ini:
- `FieldNames` menyediakan daftar semua nama bidang dalam PDF.
- `GetButtonOptionValues(item)` mengambil opsi yang tersedia untuk setiap tombol radio.

## Langkah 3: Ubah Opsi Tombol Radio

 Setelah Anda mengidentifikasi bidang tombol radio, Anda dapat mengubah opsinya. Untuk ini, Anda perlu mengubah bidang ke`RadioButtonField` dan memperbarui opsinya:

```csharp
    if (item.Contains("radio1"))
    {
        Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
        Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
        fieldoption.OptionName = "Yes";
        fieldoption.PartialName = "Yesname";
```

Di Sini:
- Kami memeriksa apakah nama bidang berisi "radio1" untuk mengidentifikasi bidang tombol radio tertentu yang ingin kami ubah.
- `RadioButtonField`dilemparkan dari bidang formulir untuk membuat modifikasi tertentu.

## Langkah 4: Mengatur Judul untuk Tombol Radio

 Untuk mengatur atau memperbarui judul tombol radio, Anda perlu membuat`TextFragment` dan gunakan`TextBuilder` untuk menempatkannya di lokasi yang diinginkan:

```csharp
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
```

Pada bagian ini:
- `TextFragment` digunakan untuk mendefinisikan teks dan tampilannya.
- `TextParagraph` membantu memposisikan dan memformat teks.
- `TextBuilder` menambahkan teks ke halaman PDF yang ditentukan.

## Langkah 5: Simpan PDF yang Diperbarui

Terakhir, simpan PDF yang diperbarui ke file baru:

```csharp
        field0.DeleteOption("item1");
    }
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Ini akan memastikan bahwa:
- Perubahan diterapkan pada PDF.
- Opsi tombol radio asli dihapus seperti yang ditentukan.

## Kesimpulan

Memodifikasi teks tombol radio dalam formulir PDF menggunakan Aspose.PDF untuk .NET dapat meningkatkan interaktivitas dan kegunaan dokumen Anda secara signifikan. Dengan langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat dengan mudah memuat PDF, memperbarui opsi tombol radio, dan menyimpan perubahan Anda. Pendekatan ini berguna untuk manajemen formulir dan memastikan PDF Anda memenuhi kebutuhan pengguna Anda. Pelajari Aspose.PDF dan jelajahi kemampuannya untuk manipulasi PDF lainnya!

## Pertanyaan yang Sering Diajukan

### Bisakah saya memperbarui beberapa bidang tombol radio sekaligus?
Ya, Anda dapat mengulangi semua bidang tombol radio dan menerapkan perubahan seperlunya.

### Apakah saya memerlukan lisensi untuk menggunakan Aspose.PDF?
 Anda dapat memulai dengan uji coba gratis, tetapi lisensi diperlukan untuk penggunaan jangka panjang.[Dapatkan lisensi di sini](https://purchase.aspose.com/buy).

### Bagaimana saya dapat menguji perubahan sebelum menyimpan PDF?
Anda dapat melihat pratinjau PDF di lingkungan pengembangan Anda atau menggunakan penampil PDF untuk memeriksa modifikasi.

### Apakah Aspose.PDF kompatibel dengan semua versi .NET?
Aspose.PDF mendukung berbagai versi .NET. Pastikan Anda memeriksa kompatibilitas dengan versi .NET spesifik Anda.

### Bisakah saya memanipulasi kolom formulir lainnya dengan cara yang sama?
Ya, teknik serupa dapat diterapkan pada jenis bidang formulir lain dalam dokumen PDF.