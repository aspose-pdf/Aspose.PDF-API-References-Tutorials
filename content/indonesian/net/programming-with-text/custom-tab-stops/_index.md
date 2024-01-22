---
title: Tab Kustom Berhenti Di File PDF
linktitle: Tab Kustom Berhenti Di File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara membuat perhentian tab khusus dalam file PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 120
url: /id/net/programming-with-text/custom-tab-stops/
---

Tutorial ini akan memandu Anda melalui proses membuat perhentian tab khusus dalam file PDF menggunakan Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan.

## Persyaratan
Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau kompiler C# lainnya yang diinstal pada mesin Anda.
- Aspose.PDF untuk perpustakaan .NET. Anda dapat mendownloadnya dari situs resmi Aspose atau menggunakan manajer paket seperti NuGet untuk menginstalnya.

## Langkah 1: Siapkan proyek
1. Buat proyek C# baru di lingkungan pengembangan pilihan Anda.
2. Tambahkan referensi ke perpustakaan Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan
Dalam file kode tempat Anda ingin membuat perhentian tab khusus, tambahkan arahan penggunaan berikut di bagian atas file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Langkah 3: Atur direktori dokumen
 Dalam kode, temukan baris yang bertuliskan`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur ke direktori tempat dokumen Anda disimpan.

## Langkah 4: Buat instance Dokumen baru
 Buat instance yang baru`Document` objek dengan menambahkan baris kode berikut:

```csharp
Document _pdfdocument = new Document();
```

## Langkah 5: Tambahkan halaman ke dokumen
 Tambahkan halaman baru ke dokumen menggunakan`Add` metode`Pages`koleksi. Dalam kode yang disediakan, halaman baru ditugaskan ke variabel`page`.

```csharp
Page page = _pdfdocument.Pages.Add();
```

## Langkah 6: Buat perhentian tab khusus
 Membuat`TabStops` objek dan tambahkan perhentian tab khusus ke dalamnya. Tetapkan tipe perataan dan tipe pemimpin untuk setiap perhentian tab.

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
 Membuat`TextFragment` objek dan meneruskan perhentian tab khusus ke objek tersebut. Gunakan karakter khusus`#$TAB` untuk menunjukkan tab berhenti di dalam teks.

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
 Simpan dokumen PDF menggunakan`Save` metode`Document` obyek.

```csharp
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

### Contoh kode sumber untuk Perhentian Tab Kustom menggunakan Aspose.PDF untuk .NET 
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
Anda telah berhasil membuat dokumen PDF dengan tab stop khusus menggunakan Aspose.PDF untuk .NET. File PDF yang dihasilkan sekarang dapat ditemukan di jalur file keluaran yang ditentukan.

### FAQ

#### Q: Apa fokus dari tutorial ini?

J: Tutorial ini difokuskan untuk memandu Anda melalui proses pembuatan tab stop kustom dalam file PDF menggunakan pustaka Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan untuk mencapai hal ini.

#### T: Namespace manakah yang harus saya impor untuk tutorial ini?

J: Dalam file kode tempat Anda ingin membuat perhentian tab khusus, impor namespace berikut di awal file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### T: Bagaimana cara menentukan direktori dokumen?

 A: Di dalam kode, temukan barisnya`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

#### T: Bagaimana cara membuat instance Dokumen baru?

 J: Pada Langkah 4, Anda akan membuat instance yang baru`Document` objek menggunakan kode yang disediakan.

#### T: Bagaimana cara menambahkan halaman ke dokumen?

 J: Pada Langkah 5, Anda akan menambahkan halaman baru ke dokumen menggunakan`Add` metode`Pages` koleksi.

#### T: Bagaimana cara membuat perhentian tab khusus?

 J: Pada Langkah 6, Anda akan membuat a`TabStops` objek dan tambahkan perhentian tab khusus ke dalamnya. Anda juga akan mengatur perataan dan jenis pemimpin untuk setiap perhentian tab.

#### T: Bagaimana cara membuat fragmen teks dengan tab stop?

 J: Pada Langkah 7, Anda akan membuat`TextFragment` objek dan meneruskan perhentian tab khusus ke objek tersebut. Anda akan menggunakan karakter khusus`#$TAB` untuk menunjukkan tab berhenti di dalam teks.

#### Q: Bagaimana cara menyimpan dokumen PDF?

 J: Pada Langkah 8, Anda akan menyimpan dokumen PDF menggunakan`Save` metode`Document` obyek.

#### T: Apa manfaat utama dari tutorial ini?

J: Dengan mengikuti tutorial ini, Anda telah mempelajari cara membuat dokumen PDF dengan tab stop khusus menggunakan Aspose.PDF untuk .NET. Ini dapat berguna untuk mengatur dan menyelaraskan teks secara terstruktur.