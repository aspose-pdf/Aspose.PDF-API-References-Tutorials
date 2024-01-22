---
title: Blok Teks Tersembunyi Dalam File PDF
linktitle: Blok Teks Tersembunyi Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara membuat blok teks tersembunyi di file PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 230
url: /id/net/programming-with-text/hidden-text-block/
---
Dalam tutorial ini, kami akan menjelaskan cara membuat blok teks tersembunyi di file PDF menggunakan perpustakaan Aspose.PDF untuk .NET. Blok teks tersembunyi adalah teks mengambang yang terlihat saat kursor mouse melayang di atas area tertentu. Kami akan melalui proses langkah demi langkah untuk membuat blok teks tersembunyi menggunakan kode sumber C# yang disediakan.

## Persyaratan

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Pustaka Aspose.PDF untuk .NET diinstal.
- Pemahaman dasar tentang pemrograman C#.

## Langkah 1: Siapkan Direktori Dokumen

 Pertama, Anda perlu mengatur jalur ke direktori tempat Anda ingin menyimpan file PDF yang dihasilkan. Mengganti`"YOUR DOCUMENT DIRECTORY"` dalam`dataDir`variabel dengan jalur ke direktori yang Anda inginkan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Buat Contoh Dokumen

Pada langkah ini, kami membuat contoh dokumen PDF dan menambahkan fragmen teks ke dalamnya. Fragmen teks akan berfungsi sebagai pemicu untuk menampilkan blok teks tersembunyi.

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## Langkah 3: Buka Dokumen

 Sekarang, kita buka dokumen yang dibuat sebelumnya menggunakan`Document` kelas.

```csharp
Document document = new Document(outputFile);
```

## Langkah 4: Temukan Fragmen Teks

 Kami menggunakan a`TextFragmentAbsorber` objek untuk menemukan fragmen teks yang akan memicu tampilan blok teks tersembunyi. Dalam hal ini, kami mencari teks yang tepat "Gerakkan kursor mouse ke sini untuk menampilkan teks mengambang".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## Langkah 5: Buat Bidang Teks Tersembunyi

 Kami membuat`TextBoxField` objek untuk mewakili bidang teks tersembunyi. Bidang ini akan berisi teks yang akan terlihat ketika kursor mouse berada di atas teks pemicu.

```csharp
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
floatingField.Value = "This is the \"floating text field\".";
floatingField. ReadOnly = true;
floatingField.Flags |= AnnotationFlags.Hidden;
floatingField.PartialName = "FloatingField_1";
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField. Multiline = true;
```

## Langkah 6: Tambahkan Bidang Teks Tersembunyi ke Dokumen

Kami menambahkan bidang teks tersembunyi ke koleksi formulir dokumen.

```csharp
document.Form.Add(floatingField);
```

## Langkah 7: Buat Tombol Tak Terlihat

Kami membuat bidang tombol tak terlihat yang akan ditempatkan di atas fragmen teks pemicu. Bidang tombol ini akan memiliki tindakan yang terkait dengan peristiwa masuk dan keluar mouse.

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## Langkah 8: Simpan Dokumen

Terakhir, kami menyimpan dokumen yang dimodifikasi dengan blok teks tersembunyi.

```csharp
document. Save(outputFile);
```

### Contoh kode sumber untuk Blok Teks Tersembunyi menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
// Buat contoh dokumen dengan teks
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
// Buka dokumen dengan teks
Document document = new Document(outputFile);
// Buat objek TextAbsorber untuk menemukan semua frasa yang cocok dengan ekspresi reguler
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// Terima penyerap untuk halaman dokumen
document.Pages.Accept(absorber);
// Dapatkan fragmen teks pertama yang diekstraksi
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
// Buat bidang teks tersembunyi untuk teks mengambang di persegi panjang halaman tertentu
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// Atur teks untuk ditampilkan sebagai nilai bidang
floatingField.Value = "This is the \"floating text field\".";
// Kami merekomendasikan untuk membuat bidang 'hanya baca' untuk skenario ini
floatingField.ReadOnly = true;
// Setel tanda 'tersembunyi' untuk membuat bidang tidak terlihat pada pembukaan dokumen
floatingField.Flags |= AnnotationFlags.Hidden;
// Menetapkan nama bidang unik tidak diperlukan tetapi diperbolehkan
floatingField.PartialName = "FloatingField_1";
// Mengatur karakteristik tampilan lapangan tidak diperlukan tetapi membuatnya lebih baik
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
// Tambahkan bidang teks ke dokumen
document.Form.Add(floatingField);
// Buat tombol tak terlihat pada posisi fragmen teks
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
// Buat tindakan sembunyikan baru untuk bidang tertentu (anotasi) dan bendera tembus pandang.
//(Anda juga dapat merujuk bidang mengambang dengan namanya jika Anda menentukannya di atas.)
// Tambahkan tindakan saat masuk/keluar mouse di bidang tombol tak terlihat
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// Tambahkan bidang tombol ke dokumen
document.Form.Add(buttonField);
// Simpan dokumen
document.Save(outputFile);
```

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara membuat blok teks tersembunyi menggunakan pustaka Aspose.PDF untuk .NET. Dengan mengikuti panduan langkah demi langkah, Anda dapat membuat dokumen PDF dengan bidang teks tersembunyi yang terlihat saat kursor mouse diarahkan ke area tertentu. Anda dapat menyesuaikan tampilan dan perilaku blok teks tersembunyi sesuai dengan kebutuhan Anda.

### FAQ

#### Q: Apa tujuan dari tutorial "Blok Teks Tersembunyi Dalam File PDF"?

A: Tutorial "Blok Teks Tersembunyi Dalam File PDF" menjelaskan cara membuat blok teks tersembunyi dalam file PDF menggunakan perpustakaan Aspose.PDF untuk .NET. Blok teks tersembunyi adalah teks mengambang yang terlihat saat kursor mouse melayang di atas area tertentu. Tutorial ini memberikan panduan langkah demi langkah menggunakan kode sumber C#.

#### T: Mengapa saya ingin membuat blok teks tersembunyi di file PDF?

J: Membuat blok teks tersembunyi dapat berguna untuk dokumen PDF interaktif di mana Anda ingin memberikan informasi atau konteks tambahan yang hanya terlihat saat pengguna mengarahkan kursor mouse ke area yang ditentukan.

#### T: Bagaimana cara mengatur direktori dokumen?

A: Untuk mengatur direktori dokumen:

1.  Mengganti`"YOUR DOCUMENT DIRECTORY"` dalam`dataDir` variabel dengan jalur ke direktori tempat Anda ingin menyimpan file PDF yang dihasilkan.

#### T: Bagaimana cara membuat contoh dokumen dan menambahkan fragmen teks ke dalamnya?

A: Dalam tutorial, Anda menggunakan`Document` kelas untuk membuat contoh dokumen PDF dan menambahkan fragmen teks. Fragmen teks ini berfungsi sebagai pemicu untuk menampilkan blok teks tersembunyi.

#### T: Bagaimana cara menemukan fragmen teks yang memicu blok teks tersembunyi?

 A: Tutorial ini menunjukkan cara menggunakan a`TextFragmentAbsorber` objek untuk menemukan fragmen teks yang memicu tampilan blok teks tersembunyi. Ini mencari string teks tertentu dalam dokumen PDF.

#### T: Bagaimana cara membuat dan menyesuaikan bidang teks tersembunyi?

 J: Anda membuat a`TextBoxField` objek untuk mewakili bidang teks tersembunyi. Tutorial ini menyediakan kode untuk mengatur berbagai properti seperti posisi, nilai, tampilan, dan perilaku bidang teks tersembunyi.

#### T: Bagaimana cara membuat tombol tak terlihat yang terkait dengan blok teks tersembunyi?

 J: Bidang tombol tak kasat mata dibuat menggunakan`ButtonField` kelas. Bidang tombol ini diposisikan di atas fragmen teks pemicu dan memiliki tindakan yang terkait dengan peristiwa masuk dan keluar mouse. Tindakan ini mengontrol visibilitas blok teks tersembunyi.

#### T: Dapatkah saya menyesuaikan tampilan blok teks tersembunyi dan area pemicu?

J: Ya, Anda dapat menyesuaikan berbagai properti bidang teks tersembunyi dan tombol tak terlihat, termasuk font, warna, ukuran, dan posisi.

#### T: Bagaimana cara menyimpan dokumen yang dimodifikasi dengan blok teks tersembunyi?

 A: Tutorial ini menunjukkan cara menyimpan dokumen yang dimodifikasi menggunakan`Save` metode`Document` kelas.