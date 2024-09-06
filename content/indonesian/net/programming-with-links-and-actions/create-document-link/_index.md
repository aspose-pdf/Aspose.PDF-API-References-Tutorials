---
title: Buat Tautan Dokumen
linktitle: Buat Tautan Dokumen
second_title: Referensi API Aspose.PDF untuk .NET
description: Buat tautan ke dokumen PDF lain dengan mudah dengan Aspose.PDF untuk .NET.
type: docs
weight: 30
url: /id/net/programming-with-links-and-actions/create-document-link/
---
Dengan menautkan ke dokumen lain dalam file PDF, Anda dapat membuat tautan yang dapat diklik yang mengarahkan pengguna ke dokumen PDF lainnya. Dengan Aspose.PDF untuk .NET, Anda dapat dengan mudah membuat tautan tersebut dengan mengikuti kode sumber berikut:

## Langkah 1: Impor pustaka yang diperlukan

Sebelum memulai, Anda perlu mengimpor pustaka yang diperlukan untuk proyek C# Anda. Berikut ini adalah perintah impor yang diperlukan:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Langkah 2: Tetapkan jalur ke folder dokumen

 Pada langkah ini, Anda perlu menentukan jalur ke folder yang berisi file PDF yang ingin Anda tambahkan tautan ke dokumen lain. Ganti`"YOUR DOCUMENT DIRECTORY"` dalam kode berikut dengan jalur sebenarnya ke folder dokumen Anda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 3: Buka dokumen PDF

Sekarang kita akan membuka dokumen PDF yang ingin kita tambahkan tautan ke dokumen lain menggunakan kode berikut:

```csharp
Document document = new Document(dataDir + "CreateDocumentLink.pdf");
```

## Langkah 4: Buat tautan ke dokumen lain

 Pada langkah ini, kita akan membuat tautan ke dokumen lain menggunakan`LinkAnnotation` anotasi. Kami akan menentukan koordinat dan area tautan, serta tindakan navigasi ke dokumen eksternal. Berikut kode yang sesuai:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
```

## Langkah 5: Simpan file yang diperbarui

Sekarang mari simpan file PDF yang diperbarui menggunakan`Save` metode dari`document` objek. Berikut kode terkait:

```csharp
dataDir = dataDir + "CreateDocumentLink_out.pdf";
document. Save(dataDir);
```

### Contoh kode sumber untuk Membuat Tautan Dokumen menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document document = new Document(dataDir+ "CreateDocumentLink.pdf");
// Buat tautan
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
dataDir = dataDir + "CreateDocumentLink_out.pdf";
// Simpan dokumen yang diperbarui
document.Save(dataDir);
Console.WriteLine("\nDocument link created successfully.\nFile saved at " + dataDir);            
```

## Kesimpulan

Selamat! Kini Anda memiliki panduan langkah demi langkah untuk menautkan ke dokumen lain dengan Aspose.PDF untuk .NET. Anda dapat menggunakan kode ini untuk membuat tautan yang dapat diklik di berkas PDF Anda, yang akan mengarahkan pengguna ke dokumen lain.

Pastikan untuk memeriksa dokumentasi resmi Aspose.PDF untuk informasi lebih lanjut tentang fitur lanjutan tautan interaktif.

### FAQ untuk membuat tautan dokumen

#### T: Apa itu tautan dokumen dalam berkas PDF?

A: Tautan dokumen dalam file PDF adalah tautan yang dapat diklik yang mengarahkan pengguna ke dokumen PDF lainnya. Tautan ini meningkatkan navigasi dengan menyediakan cara yang efisien untuk menghubungkan konten terkait dan memfasilitasi pengalaman membaca yang lancar.

#### T: Bagaimana saya dapat memperoleh manfaat dari pembuatan tautan dokumen?

A: Membuat tautan dokumen memungkinkan Anda membuat hubungan antara berbagai bagian atau topik dalam dokumen PDF Anda. Fitur ini memungkinkan pengguna mengakses informasi tambahan atau materi terkait dengan mudah.

#### T: Bagaimana Aspose.PDF untuk .NET mendukung pembuatan tautan dokumen?

J: Aspose.PDF untuk .NET menyederhanakan proses pembuatan tautan dokumen dengan menyediakan serangkaian API yang lengkap. Tutorial langkah demi langkah yang diuraikan dalam panduan ini menunjukkan cara menambahkan tautan dokumen ke berkas PDF Anda.

#### T: Dapatkah saya menyesuaikan tampilan tautan dokumen?

A: Tentu saja! Aspose.PDF untuk .NET menawarkan opsi penyesuaian untuk tampilan tautan dokumen, termasuk warna, gaya, dan efek hover. Anda dapat menyesuaikan tampilan agar sesuai dengan desain dokumen Anda.

#### T: Apakah mungkin untuk menautkan ke bagian atau halaman tertentu dalam dokumen lain?

J: Ya, Anda dapat membuat tautan yang mengarahkan pengguna ke halaman atau bagian tertentu dalam dokumen PDF lainnya. Aspose.PDF untuk .NET menyediakan fleksibilitas untuk menentukan lokasi target dalam dokumen yang ditautkan.

#### T: Bagaimana saya dapat memastikan tautan dokumen saya berfungsi?

A: Dengan mengikuti tutorial dan contoh kode yang diberikan, Anda dapat membuat tautan dokumen yang berfungsi dengan yakin. Anda dapat menguji tautan tersebut dengan membuka dokumen PDF yang dihasilkan dan mengeklik tautan tersebut.

#### T: Dapatkah saya membuat beberapa tautan dokumen dalam satu berkas PDF?

 A: Tentu saja! Anda dapat membuat beberapa tautan dokumen dalam satu dokumen PDF menggunakan`LinkAnnotation` anotasi. Hal ini memungkinkan Anda memberi pengguna akses ke berbagai dokumen terkait dari berbagai bagian.

#### T: Apakah ada batasan saat menautkan ke dokumen eksternal?

A: Saat menautkan ke dokumen eksternal, pastikan dokumen yang ditautkan dapat diakses dan berada di jalur yang ditentukan. Penting juga untuk mempertimbangkan izin pengguna dan kompatibilitas dokumen yang ditautkan.

#### T: Dapatkah saya menautkan ke dokumen yang disimpan di web atau repositori daring?

J: Meskipun tutorial ini berfokus pada penautan ke dokumen lokal, Aspose.PDF untuk .NET juga mendukung penautan ke URL web atau repositori daring. Anda dapat mengadaptasi kode yang diberikan untuk membuat tautan dokumen berbasis web.