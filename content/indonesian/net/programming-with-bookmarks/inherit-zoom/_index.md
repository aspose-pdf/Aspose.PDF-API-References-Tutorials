---
title: Mewarisi Zoom Dalam File PDF
linktitle: Mewarisi Zoom Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Mewarisi zoom bookmark dalam file PDF dengan mudah dengan Aspose.PDF untuk .NET.
type: docs
weight: 90
url: /id/net/programming-with-bookmarks/inherit-zoom/
---
Warisan zoom dalam file PDF memungkinkan Anda menentukan tingkat zoom default untuk bookmark. Dengan Aspose.PDF untuk .NET, Anda dapat dengan mudah mewarisi zoom dengan mengikuti kode sumber berikut:

## Langkah 1: Impor perpustakaan yang diperlukan

Sebelum memulai, Anda perlu mengimpor perpustakaan yang diperlukan untuk proyek C# Anda. Berikut adalah arahan impor yang diperlukan:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Langkah 2: Tetapkan jalur ke folder dokumen

 Pada langkah ini, Anda perlu menentukan jalur ke folder yang berisi file PDF yang ingin Anda warisi zoomnya. Mengganti`"YOUR DOCUMENT DIRECTORY"`dalam kode berikut dengan jalur sebenarnya ke folder dokumen Anda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 3: Buka dokumen PDF

Sekarang kita akan membuka dokumen PDF yang ingin kita warisi zoomnya menggunakan kode berikut:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Langkah 4: Dapatkan Koleksi Bookmark

 Pada langkah ini, kita akan mendapatkan kumpulan bookmark atau landmark dari dokumen tersebut menggunakan`Outlines` properti dari`doc` obyek. Ini kode yang sesuai:

```csharp
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
```

## Langkah 5: Atur Tingkat Zoom

 Sekarang kita akan mengatur tingkat zoom dengan membuat`XYZExplicitDestination` objek dengan koordinat x, y dan z yang ditentukan. Disini kita menggunakan koordinat (100, 100, 0) dengan zoom 2. Berikut kode yang sesuai:

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

## Langkah 6: Tambahkan Tingkat Zoom ke Bookmark

 Pada langkah ini, kami menambahkan`XYZExplicitDestination` objek sebagai tindakan terhadap bookmark`item` koleksi. Ini kode yang sesuai:

```csharp
item. Action = new GoToAction(dest);
```

## Langkah 7: Tambahkan bookmark yang diperbarui ke dokumen

 Terakhir, kami menambahkan bookmark yang diperbarui ke koleksi bookmark dokumen menggunakan`Add` metode`doc.Outlines` obyek. Ini kode yang sesuai:

```csharp
doc. Outlines. Add(item);
```

## Langkah 8: Simpan file yang diperbarui

 Sekarang mari simpan file PDF yang diperbarui menggunakan`Save` metode`doc` obyek. Ini kode yang sesuai:

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

### Contoh kode sumber untuk Inherit Zoom menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document doc = new Document(dataDir + "input.pdf");
// Dapatkan koleksi outline/bookmark file PDF
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
// Atur tingkat zoom ke 0
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
// Tambahkan XYZExplicitDestination sebagai tindakan untuk menguraikan koleksi PDF
item.Action = new GoToAction(dest);
// Tambahkan item ke kumpulan garis besar file PDF
doc.Outlines.Add(item);
dataDir = dataDir + "InheritZoom_out.pdf";
// Simpan keluaran
doc.Save(dataDir);
Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```

## Kesimpulan

Selamat! Sekarang Anda memiliki panduan langkah demi langkah untuk Mewarisi Zoom dengan Aspose.PDF untuk .NET. Anda dapat menggunakan kode ini untuk menentukan tingkat zoom default untuk bookmark di dokumen PDF Anda.

Pastikan untuk memeriksa dokumentasi resmi Aspose.PDF untuk informasi lebih lanjut tentang fitur manipulasi bookmark tingkat lanjut.

### FAQ untuk mewarisi zoom dalam file PDF

#### T: Apa yang dimaksud dengan warisan zoom dalam file PDF?

J: Warisan zoom mengacu pada kemampuan untuk menentukan tingkat zoom default untuk bookmark dalam dokumen PDF. Hal ini memungkinkan navigasi yang konsisten dan ramah pengguna saat pengguna berinteraksi dengan bookmark.

#### T: Mengapa saya ingin mewarisi tingkat zoom untuk bookmark?

J: Mewarisi tingkat zoom memastikan pengguna memiliki pengalaman menonton yang konsisten saat menavigasi penanda dalam dokumen PDF. Ini bisa sangat berguna ketika Anda ingin memberikan tampilan spesifik untuk berbagai bagian dokumen.

#### T: Bagaimana cara mengimpor perpustakaan yang diperlukan untuk proyek C# saya?

J: Untuk mengimpor pustaka yang diperlukan untuk proyek C# Anda, sertakan arahan impor berikut:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Arahan ini memungkinkan Anda mengakses kelas dan metode yang diperlukan untuk bekerja dengan dokumen dan bookmark PDF.

#### T: Bagaimana cara menentukan jalur ke folder dokumen?

 A: Di kode sumber yang disediakan, ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke folder yang berisi file PDF yang ingin Anda warisi tingkat zoomnya.

#### T: Bagaimana cara membuka dokumen PDF untuk mewarisi tingkat zoom?

J: Untuk membuka dokumen PDF untuk mewarisi tingkat zoom, gunakan kode berikut:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 Mengganti`"input.pdf"` dengan nama file sebenarnya.

#### T: Bagaimana cara mengatur tingkat zoom untuk bookmark?

 A: Untuk mengatur tingkat zoom, buatlah`XYZExplicitDestination` objek dengan koordinat dan faktor zoom yang diinginkan. Berikut ini contohnya:

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

Ini mengatur tingkat zoom ke 2 pada koordinat (100, 100).

#### T: Bagaimana cara menambahkan tingkat zoom ke bookmark?

 J: Tambahkan`XYZExplicitDestination` objek sebagai tindakan terhadap koleksi bookmark:

```csharp
item.Action = new GoToAction(dest);
```

 Di mana`item` adalah`OutlineItemCollection` mewakili penanda.

#### T: Bagaimana cara menyimpan file PDF yang diperbarui?

 A: Simpan file PDF yang diperbarui menggunakan`Save` metode`doc` obyek:

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

#### T: Dapatkah saya menyesuaikan tingkat zoom untuk berbagai bookmark?

 J: Ya, Anda dapat menyesuaikan tingkat zoom untuk berbagai penanda dengan membuat beberapa penanda`XYZExplicitDestination` objek dengan koordinat dan faktor zoom yang berbeda.

#### T: Apakah ada batasan jumlah bookmark yang dapat saya gunakan untuk menerapkan warisan zoom?

J: Biasanya tidak ada batasan ketat mengenai jumlah bookmark yang dapat Anda gunakan untuk menerapkan warisan zoom. Namun, dokumen yang sangat besar dengan jumlah penanda yang berlebihan mungkin memerlukan manajemen memori yang efisien.

#### T: Bagaimana cara mengonfirmasi bahwa pewarisan zoom telah diterapkan?

J: Buka file PDF yang dihasilkan untuk memverifikasi bahwa tingkat zoom yang ditentukan telah diwarisi oleh bookmark.