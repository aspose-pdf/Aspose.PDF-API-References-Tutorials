---
title: Setel Properti Callout Dalam File PDF
linktitle: Setel Properti Callout Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara mengatur Properti Callout di File PDF menggunakan Aspose.PDF untuk .NET. Sesuaikan anotasi dengan baris info, warna teks, dan gaya akhir.
type: docs
weight: 130
url: /id/net/annotations/setcalloutproperty/
---
 Aspose.PDF untuk .NET adalah perpustakaan yang kuat untuk membuat, memanipulasi, dan mengonversi dokumen PDF di C#. Salah satu fitur yang disediakan oleh perpustakaan ini adalah kemampuan untuk mengatur properti info untuk anotasi teks gratis dalam dokumen PDF. Ini dapat dilakukan dengan menggunakan`FreeTextAnnotation` kelas, yang memungkinkan Anda membuat anotasi dengan info.

Dalam tutorial ini, kami akan memandu Anda melalui proses pengaturan properti info untuk anotasi teks gratis menggunakan Aspose.PDF untuk .NET di C#. Ikuti langkah-langkah di bawah ini untuk memulai.

## Instal Aspose.PDF untuk .NET

 Jika Anda belum melakukannya, Anda perlu melakukannya[unduh](https://releases.aspose.com/pdf/net/) dan instal Aspose.PDF untuk .NET dari Aspose Releases atau melalui manajer paket NuGet.

## Langkah 1: Buat dokumen PDF baru

 Buat dokumen PDF baru menggunakan`Document`kelas yang disediakan oleh Aspose.PDF untuk .NET.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Langkah 2: Tambahkan halaman baru ke dokumen

 Tambahkan halaman baru ke dokumen menggunakan`Pages` koleksi`Document` kelas.

```csharp
Page page = doc.Pages.Add();
```

## Langkah 3: Tetapkan tampilan default

 Atur tampilan default untuk anotasi teks bebas dengan membuat yang baru`DefaultAppearance` objek dan mengatur propertinya seperti`TextColor` Dan`FontSize`.

```csharp
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```

## Langkah 4: Buat anotasi teks gratis dengan info

 Buat anotasi teks gratis baru dengan info menggunakan`FreeTextAnnotation` kelas. Mengatur`Intent` properti ke`FreeTextIntent.FreeTextCallout` untuk menentukan bahwa ini adalah anotasi info. Mengatur`EndingStyle` properti ke`LineEnding.OpenArrow` untuk menentukan gaya panah di akhir info. Mengatur`Callout` properti ke array`Point` objek yang mewakili titik-titik pada halaman di mana garis info harus digambar.

```csharp
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
    new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
```

## Langkah 5: Tambahkan anotasi teks bebas ke halaman

 Tambahkan anotasi teks bebas ke halaman dengan menggunakan`Annotations` koleksi`Page` kelas.

```csharp
page.Annotations.Add(fta);
```

## Langkah 6: Tambahkan teks ke anotasi

 Tambahkan teks ke anotasi dengan mengatur`RichText`properti ke string XML yang diformat. Dalam tutorial ini, kita mengatur warna teks menjadi merah dan ukuran font menjadi 9.

```csharp
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"warna:#FF
```

## Langkah 7: simpan dokumen

Sekarang simpan dokumen dengan menggunakan kode berikut:

```csharp
doc.Save(dataDir + "SetCalloutProperty.pdf")
```

### Contoh kode sumber untuk Mengatur Properti Callout menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
	new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
page.Annotations.Add(fta);
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"> <span style=\"font-size:9.0pt;font-family:Helvetica\">Ini adalah contoh</span></p></body>";
doc.Save(dataDir + "SetCalloutProperty.pdf");
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara mengatur properti info untuk anotasi teks bebas dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Anotasi info berguna untuk memberikan informasi atau penjelasan tambahan terkait area tertentu dalam suatu dokumen. Aspose.PDF untuk .NET menyediakan berbagai fitur dan kemampuan untuk bekerja dengan file PDF, termasuk membuat dan menyesuaikan anotasi, seperti info. Dengan mengikuti panduan langkah demi langkah dan menggunakan kode sumber C# yang disediakan, pengembang dapat dengan mudah menerapkan anotasi info dalam dokumen PDF mereka, sehingga meningkatkan kegunaan dan kejelasan dokumen mereka. Aspose.PDF untuk .NET adalah perpustakaan serbaguna dan andal untuk pengoperasian PDF di aplikasi .NET, menawarkan alat canggih untuk menangani berbagai tugas terkait PDF secara efisien.

### FAQ untuk menyetel properti info dalam file PDF

#### T: Apa yang dimaksud dengan anotasi info dalam dokumen PDF?

J: Anotasi info dalam dokumen PDF adalah jenis anotasi yang memungkinkan Anda membuat kotak teks dengan garis pemandu yang menunjuk ke area tertentu dalam dokumen. Biasanya digunakan untuk memberikan informasi atau komentar tambahan terkait bagian atau elemen tertentu dalam dokumen.

#### T: Dapatkah saya menyesuaikan tampilan anotasi info menggunakan Aspose.PDF untuk .NET?

J: Ya, Anda dapat menyesuaikan berbagai properti anotasi info, seperti warna, ukuran font, perataan teks, gaya garis, gaya panah, dan banyak lagi.

#### T: Bagaimana cara menambahkan teks ke anotasi info?

 J: Untuk menambahkan teks ke anotasi info, Anda dapat mengatur`RichText` properti dari`FreeTextAnnotation` obyek. Itu`RichText` Properti mengambil string XML berformat yang mewakili teks yang akan ditampilkan dalam anotasi info.

#### T: Bisakah saya menambahkan beberapa anotasi info ke dokumen PDF menggunakan Aspose.PDF untuk .NET?

 J: Ya, Anda dapat membuat beberapa anotasi info dalam dokumen PDF dengan membuat beberapa contoh`FreeTextAnnotation`objek dan menambahkannya ke halaman atau lokasi berbeda dalam dokumen.