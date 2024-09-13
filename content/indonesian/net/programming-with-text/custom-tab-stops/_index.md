---
title: Penghentian Tab Kustom Dalam File PDF
linktitle: Penghentian Tab Kustom Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara membuat penghentian tab khusus dalam berkas PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 120
url: /id/net/programming-with-text/custom-tab-stops/
---

Tutorial ini akan memandu Anda melalui proses pembuatan tab stop khusus dalam file PDF menggunakan Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan.

## Persyaratan
Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau kompiler C# lainnya terinstal di komputer Anda.
- Aspose.PDF untuk pustaka .NET. Anda dapat mengunduhnya dari situs web resmi Aspose atau menggunakan pengelola paket seperti NuGet untuk menginstalnya.

## Langkah 1: Siapkan proyek
1. Buat proyek C# baru di lingkungan pengembangan pilihan Anda.
2. Tambahkan referensi ke pustaka Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan
Pada berkas kode tempat Anda ingin membuat penghentian tab khusus, tambahkan perintah penggunaan berikut di bagian atas berkas:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Langkah 3: Mengatur direktori dokumen
 Dalam kode, temukan baris yang bertuliskan`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur ke direktori tempat dokumen Anda disimpan.

## Langkah 4: Buat contoh Dokumen baru
 Membuat instance baru`Document` objek dengan menambahkan baris kode berikut:

```csharp
Document _pdfdocument = new Document();
```

## Langkah 5: Tambahkan halaman ke dokumen
 Tambahkan halaman baru ke dokumen menggunakan`Add` metode dari`Pages` koleksi. Dalam kode yang diberikan, halaman baru ditetapkan ke variabel`page`.

```csharp
Page page = _pdfdocument.Pages.Add();
```

## Langkah 6: Buat penghentian tab khusus
 Membuat sebuah`TabStops` objek dan tambahkan tab stop khusus ke dalamnya. Tetapkan jenis penyelarasan dan jenis penunjuk untuk setiap tab stop.

```csharp
TabStops ts = new TabStops();
TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;

TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;

TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
```

## Langkah 7: Buat fragmen teks dengan tab stop
 Membuat`TextFragment` objek dan berikan tab stop kustom kepada objek tersebut. Gunakan karakter khusus`#$TAB` untuk menunjukkan perhentian tab dalam teks.

```csharp
TextFragment header = new TextFragment("This is an example of forming a table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));

page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
```

## Langkah 8: Simpan dokumen PDF
 Simpan dokumen PDF menggunakan`Save` metode dari`Document` obyek.

```csharp
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

### Contoh kode sumber untuk Penghentian Tab Kustom menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document _pdfdocument = new Document();
Page page = _pdfdocument.Pages.Add();
Aspose.Pdf.Text.TabStops ts = new Aspose.Pdf.Text.TabStops();
Aspose.Pdf.Text.TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;
Aspose.Pdf.Text.TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;
Aspose.Pdf.Text.TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
TextFragment header = new TextFragment("This is a example of forming table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));
page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
dataDir = dataDir + "CustomTabStops_out.pdf";
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

## Kesimpulan
Anda telah berhasil membuat dokumen PDF dengan tab stop khusus menggunakan Aspose.PDF untuk .NET. File PDF yang dihasilkan kini dapat ditemukan di jalur file output yang ditentukan.

### Pertanyaan yang Sering Diajukan

#### T: Apa fokus dari tutorial ini?

J: Tutorial ini difokuskan untuk memandu Anda melalui proses pembuatan tab stop kustom dalam file PDF menggunakan pustaka Aspose.PDF for .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan untuk mencapainya.

#### T: Namespace mana yang harus saya impor untuk tutorial ini?

A: Pada berkas kode tempat Anda ingin membuat penghentian tab khusus, impor namespace berikut di awal berkas:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### T: Bagaimana cara menentukan direktori dokumen?

 A: Pada kode tersebut, temukan baris`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

#### T: Bagaimana cara membuat contoh Dokumen baru?

 A: Pada Langkah 4, Anda akan membuat instance baru`Document` objek menggunakan kode yang disediakan.

#### T: Bagaimana cara menambahkan halaman ke dokumen?

 A: Pada Langkah 5, Anda akan menambahkan halaman baru ke dokumen menggunakan`Add` metode dari`Pages` koleksi.

#### T: Bagaimana cara membuat penghentian tab khusus?

 A: Pada Langkah 6, Anda akan membuat`TabStops` objek dan menambahkan tab stop khusus ke dalamnya. Anda juga akan mengatur jenis perataan dan penunjuk arah untuk setiap tab stop.

#### T: Bagaimana cara membuat fragmen teks dengan tab stop?

 A: Pada Langkah 7, Anda akan membuat`TextFragment` objek dan meneruskan tab stop kustom kepada mereka. Anda akan menggunakan karakter khusus`#$TAB` untuk menunjukkan perhentian tab dalam teks.

#### T: Bagaimana cara menyimpan dokumen PDF?

 A: Pada Langkah 8, Anda akan menyimpan dokumen PDF menggunakan`Save` metode dari`Document` obyek.

#### T: Apa hasil utama dari tutorial ini?

A: Dengan mengikuti tutorial ini, Anda telah mempelajari cara membuat dokumen PDF dengan tab stop khusus menggunakan Aspose.PDF for .NET. Ini dapat berguna untuk mengatur dan menyelaraskan teks secara terstruktur.