---
title: Tambahkan Bookmark Anak ke PDF
linktitle: Tambahkan Bookmark Anak ke PDF
second_title: API Pemrosesan PDF Java Aspose.PDF
description: Pelajari cara menyempurnakan dokumen PDF dengan penanda anak menggunakan Aspose.PDF untuk Java. Panduan langkah demi langkah dengan contoh kode untuk navigasi dan pengaturan yang lebih baik.
type: docs
weight: 11
url: /id/java/pdf-bookmarks/add-child-bookmarks-pdfs/
---

## Pengantar untuk Menambahkan Bookmark Anak ke PDF

Dalam artikel ini, kita akan membahas cara menambahkan penanda anak ke dokumen PDF menggunakan Aspose.PDF untuk Java. Penanda anak merupakan cara yang mudah untuk mengatur dan menavigasi konten dokumen PDF, sehingga memudahkan pengguna menemukan bagian atau topik tertentu dalam dokumen.

## Prasyarat

Sebelum kita mulai menerapkannya, pastikan Anda telah memenuhi prasyarat berikut:

- Lingkungan pengembangan Java terinstal pada sistem Anda.
-  Aspose.PDF untuk pustaka Java. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/pdf/java/).

## Menyiapkan Lingkungan

1. Unduh pustaka Aspose.PDF untuk Java dari tautan yang disediakan.
2. Tambahkan perpustakaan ke proyek Java Anda.

Sekarang, mari kita mulai dengan membuat dokumen PDF baru dan menambahkan penanda anak ke dalamnya selangkah demi selangkah.

## Membuat Dokumen PDF Baru

Untuk memulai, kita perlu menginisialisasi dokumen PDF dan menambahkan halaman ke dalamnya. Berikut cuplikan kode untuk memulai:

```java
// Inisialisasi dokumen PDF
Document pdfDocument = new Document();

// Tambahkan halaman ke PDF
pdfDocument.getPages().add();
pdfDocument.getPages().add();
```

Dalam contoh ini, kami telah membuat dokumen PDF baru dan menambahkan dua halaman ke dalamnya.

## Menambahkan Bookmark Induk

Penanda induk berfungsi sebagai bagian atau kategori utama dalam dokumen PDF Anda. Mari buat beberapa penanda induk:

```java
// Buat penanda induk
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);
```

Kami telah menambahkan dua penanda induk, "Penanda Induk 1" dan "Penanda Induk 2."

## Menambahkan Bookmark Anak

Sekarang, saatnya menambahkan bookmark anak ke bookmark induk yang telah kita buat sebelumnya. Bookmark anak mewakili topik atau sub-bagian tertentu dalam setiap bookmark induk. Berikut cara melakukannya:

```java
// Tambahkan penanda anak ke Penanda Induk 1
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//Tambahkan penanda anak ke Penanda Induk 2
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);
```

Kami telah menambahkan penanda anak ke "Penanda Induk 1" dan "Penanda Induk 2".

## Menyesuaikan Tampilan Bookmark

Anda dapat menyesuaikan tampilan bookmark dengan mengubah teks dan gayanya. Selain itu, Anda dapat menambahkan ikon ke bookmark untuk representasi visual yang lebih baik. Berikut ini contoh cara melakukannya:

```java
// Sesuaikan tampilan penanda buku
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());
```

Dalam contoh ini, kami membuat penanda induk miring, mengubah warna teks penanda anak menjadi hijau, dan menambahkan ikon miring ke penanda anak.

## Penanganan Peristiwa

Bookmark juga dapat memiliki tindakan yang terkait dengannya. Misalnya, Anda dapat menambahkan tindakan yang dipicu saat pengguna mengklik bookmark. Berikut cara menangani peristiwa klik bookmark:

```java
// Tambahkan tindakan ke penanda
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);
```

Dalam kode ini, kami telah menambahkan tindakan "GoTo" ke penanda anak yang akan membawa pengguna ke halaman kedua PDF saat diklik.

## Menyimpan PDF

Setelah Anda menambahkan semua penanda yang diperlukan dan menyesuaikan tampilan dan tindakannya, Anda dapat menyimpan dokumen PDF yang dimodifikasi:

```java
// Simpan dokumen PDF
pdfDocument.save("output.pdf");
```

Dokumen PDF Anda dengan penanda buku anak sekarang sudah siap.

## Kode Sumber Lengkap

Berikut kode sumber lengkap untuk menambahkan penanda anak ke dokumen PDF menggunakan Aspose.PDF untuk Java:

```java
// Inisialisasi dokumen PDF
Document pdfDocument = new Document();

// Tambahkan halaman ke PDF
pdfDocument.getPages().add();
pdfDocument.getPages().add();

// Buat penanda induk
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);

// Tambahkan penanda anak ke Penanda Induk 1
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//Tambahkan penanda anak ke Penanda Induk 2
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);

// Sesuaikan tampilan penanda buku
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());

// Tambahkan tindakan ke penanda
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);

// Simpan dokumen PDF
pdfDocument.save("output.pdf");
```

## Kesimpulan

Menambahkan bookmark anak ke PDF menggunakan Aspose.PDF untuk Java merupakan fitur hebat yang meningkatkan navigasi dan pengaturan dokumen Anda. Dengan mengikuti langkah-langkah yang diuraikan dalam artikel ini, Anda dapat membuat PDF terstruktur dengan baik dengan bookmark induk dan anak, menyesuaikan tampilannya, dan bahkan menambahkan tindakan untuk meningkatkan pengalaman pengguna.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara mengunduh Aspose.PDF untuk Java?

 Anda dapat mengunduh Aspose.PDF untuk Java dari situs web[Di Sini](https://releases.aspose.com/pdf/java/).

### Apakah penanda anak didukung di semua penampil PDF?

Ya, penanda anak didukung di sebagian besar penampil PDF modern dan memberikan pengalaman pengguna yang lebih baik untuk menavigasi dokumen PDF.

### Bisakah saya menyesuaikan tampilan bookmark lebih lanjut?

Ya, Anda dapat menyesuaikan tampilan bookmark dengan menyesuaikan gaya teks, warna, dan ikon agar sesuai dengan desain dokumen Anda.

### Tindakan apa lagi yang dapat saya tambahkan ke penanda?

Selain tindakan "GoTo", Anda dapat menambahkan tindakan seperti tindakan "URI" untuk membuka tautan web atau tindakan "JavaScript" untuk mengeksekusi skrip khusus saat bookmark diklik.

### Apakah Aspose.PDF untuk Java cocok untuk proyek komersial?

Ya, Aspose.PDF untuk Java cocok untuk proyek pribadi dan komersial, dan menawarkan berbagai fitur untuk manipulasi dan pembuatan PDF.