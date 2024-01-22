---
title: Tentukan Halaman Saat Melihat
linktitle: Tentukan Halaman Saat Melihat
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menentukan halaman saat melihat PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 110
url: /id/net/programming-with-links-and-actions/specify-page-when-viewing/
---
Pelajari cara menentukan halaman saat melihat file PDF menggunakan Aspose.PDF untuk .NET dengan panduan langkah demi langkah ini.

## Langkah 1: Menyiapkan lingkungan

Pastikan Anda telah menyiapkan lingkungan pengembangan dengan proyek C# dan referensi Aspose.PDF yang sesuai.

## Langkah 2: Memuat file PDF

Tetapkan jalur direktori dokumen Anda dan unggah file PDF menggunakan kode berikut:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Muat file PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

## Langkah 3: Menentukan halaman target

Dapatkan contoh halaman target menggunakan kode berikut:

```csharp
Page page2 = doc.Pages[2];
```

 Anda dapat menyesuaikan indeks`[2]` untuk memilih halaman yang diinginkan.

## Langkah 4: Mengonfigurasi pengaturan zoom

Buat variabel untuk mengatur faktor pembesaran halaman target:

```csharp
double zoom = 1;
```

Anda dapat mengatur nilai zoom sesuai kebutuhan Anda.

## Langkah 5: Buat tindakan navigasi

Buat instance tindakan navigasi menggunakan halaman target yang ditentukan:

```csharp
GoToAction action = new GoToAction(doc.Pages[2]);
```

## Langkah 6: Menetapkan tujuan

Tetapkan tujuan untuk menuju halaman target menggunakan koordinat dan zoom:

```csharp
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

## Langkah 7: Mengonfigurasi Tindakan Buka Dokumen

Atur tindakan buka dokumen dengan tindakan navigasi yang dibuat:

```csharp
doc. OpenAction = action;
```

## Langkah 8: Simpan dokumen yang diperbarui

 Simpan dokumen yang diperbarui menggunakan`Save` metode:

```csharp
doc.Save(dataDir + "goto2page_out.pdf");
```

### Contoh kode sumber untuk Tentukan Halaman Saat Melihat menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Muat file PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
// Dapatkan contoh halaman kedua dokumen
Page page2 = doc.Pages[2];
// Buat variabel untuk mengatur faktor zoom halaman target
double zoom = 1;
// Buat instance GoToAction
GoToAction action = new GoToAction(doc.Pages[2]);
// Pergi ke halaman 2
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
// Atur tindakan membuka dokumen
doc.OpenAction = action;
// Simpan dokumen yang diperbarui
doc.Save(dataDir + "goto2page_out.pdf");
```

## Kesimpulan

Selamat! Anda sekarang tahu cara menentukan halaman saat melihat PDF menggunakan Aspose.PDF untuk .NET. Gunakan pengetahuan ini untuk menyesuaikan pengalaman melihat pengguna di dokumen PDF Anda.

Sekarang setelah Anda menyelesaikan panduan ini, Anda dapat menerapkan konsep ini ke proyek Anda sendiri dan menjelajahi lebih jauh fitur yang ditawarkan oleh Aspose.PDF untuk .NET.

### FAQ 

#### T: Apa tujuan menentukan halaman target saat melihat file PDF?

J: Menentukan halaman target memungkinkan Anda mengontrol halaman dokumen PDF mana yang ditampilkan saat file dibuka. Hal ini dapat meningkatkan pengalaman pengguna dengan mengarahkan mereka ke halaman tertentu yang diminati.

#### T: Bagaimana menentukan halaman target dapat berguna dalam dokumen PDF?

J: Menentukan halaman target bermanfaat ketika Anda ingin memandu pengguna ke bagian atau konten tertentu dalam dokumen PDF tanpa mengharuskan mereka menavigasi halaman secara manual.

#### T: Bagaimana Aspose.PDF untuk .NET memfasilitasi penentuan halaman target untuk dilihat?

J: Aspose.PDF untuk .NET menyediakan API yang memungkinkan Anda mengatur tampilan awal dokumen PDF, termasuk halaman target, tingkat zoom, dan properti tampilan lainnya.

#### T: Dapatkah saya menentukan halaman mana saja sebagai halaman target?

J: Ya, Anda dapat menentukan halaman mana pun dalam dokumen PDF sebagai halaman target untuk dilihat. Cukup gunakan indeks yang sesuai untuk memilih halaman yang diinginkan.

#### T: Apa pentingnya faktor zoom saat menentukan halaman target?

A: Faktor zoom menentukan tingkat pembesaran yang diterapkan pada halaman target saat dokumen PDF dibuka. Ini mengontrol berapa banyak konten yang ditampilkan dalam area pandang.

#### T: Dapatkah saya menetapkan faktor zoom yang berbeda untuk halaman target yang berbeda?

J: Ya, Anda dapat mengatur faktor zoom yang berbeda untuk halaman target yang berbeda dengan membuat halaman terpisah`GoToAction` instance dan mengonfigurasi tujuannya sesuai dengan itu.

#### T: Apakah ada batasan dalam menentukan halaman target?

A: Menentukan halaman target hanya sebatas mengontrol tampilan awal saat PDF dibuka. Ini tidak mempengaruhi interaksi atau navigasi pengguna setelah PDF ditampilkan.

#### T: Dapatkah saya menggunakan fitur ini untuk membuat presentasi dalam dokumen PDF?

J: Ya, Anda dapat menggunakan fitur ini untuk menciptakan pengalaman seperti presentasi dalam dokumen PDF, memandu pengguna melalui berbagai bagian atau topik.

#### T: Dapatkah saya menyesuaikan aspek lain dari tampilan awal, seperti tata letak halaman?

J: Ya, Aspose.PDF untuk .NET menyediakan properti untuk menyesuaikan aspek lain dari tampilan awal, termasuk tata letak halaman, mode halaman, dan banyak lagi.

#### T: Bagaimana cara menguji apakah halaman target dan faktor zoom yang ditentukan berfungsi sebagaimana mestinya?

J: Setelah menerapkan kode yang disediakan untuk menentukan halaman target dan faktor zoom, buka file PDF yang dimodifikasi dan verifikasi bahwa file tersebut terbuka dengan halaman dan tingkat zoom yang benar.