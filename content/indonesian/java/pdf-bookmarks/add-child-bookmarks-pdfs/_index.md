---
title: Tambahkan Bookmark Anak ke PDF
linktitle: Tambahkan Bookmark Anak ke PDF
second_title: Aspose.PDF API Pemrosesan PDF Java
description: Pelajari cara menyempurnakan dokumen PDF dengan bookmark anak menggunakan Aspose.PDF untuk Java. Panduan langkah demi langkah dengan contoh kode untuk meningkatkan navigasi dan pengorganisasian.
type: docs
weight: 11
url: /id/java/pdf-bookmarks/add-child-bookmarks-pdfs/
---

## Pengantar Menambahkan Bookmark Anak ke PDF

Pada artikel ini, kita akan mempelajari cara menambahkan bookmark anak ke dokumen PDF menggunakan Aspose.PDF untuk Java. Bookmark anak adalah cara mudah untuk mengatur dan menavigasi konten dokumen PDF, sehingga memudahkan pengguna menemukan bagian atau topik tertentu dalam dokumen.

## Prasyarat

Sebelum kita mendalami penerapannya, pastikan Anda memiliki prasyarat berikut:

- Lingkungan pengembangan Java diinstal pada sistem Anda.
-  Aspose.PDF untuk perpustakaan Java. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/pdf/java/).

## Menyiapkan Lingkungan

1. Unduh perpustakaan Aspose.PDF untuk Java dari tautan yang disediakan.
2. Tambahkan perpustakaan ke proyek Java Anda.

Sekarang, mari kita mulai dengan membuat dokumen PDF baru dan menambahkan bookmark anak ke dalamnya langkah demi langkah.

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

Bookmark induk berfungsi sebagai bagian atau kategori utama dalam dokumen PDF Anda. Mari buat beberapa bookmark induk:

```java
// Buat bookmark orang tua
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);
```

Kami telah menambahkan dua bookmark induk, "Bookmark Induk 1" dan "Bookmark Induk 2".

## Menambahkan Bookmark Anak

Sekarang saatnya menambahkan bookmark anak ke bookmark induk yang kita buat sebelumnya. Bookmark anak mewakili topik atau subbagian tertentu dalam setiap bookmark induk. Inilah cara Anda melakukannya:

```java
// Tambahkan bookmark anak ke Bookmark Induk 1
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//Tambahkan bookmark anak ke Bookmark Induk 2
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);
```

Kami telah menambahkan bookmark anak ke "Bookmark Induk 1" dan "Bookmark Induk 2".

## Menyesuaikan Tampilan Bookmark

Anda dapat menyesuaikan tampilan bookmark dengan mengubah teks dan gayanya. Selain itu, Anda dapat menambahkan ikon ke bookmark untuk representasi visual yang lebih baik. Berikut ini contoh cara melakukannya:

```java
// Sesuaikan tampilan penanda
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());
```

Dalam contoh ini, kami telah membuat penanda induk menjadi miring, mengubah warna teks penanda anak menjadi hijau, dan menambahkan ikon miring ke penanda anak.

## Menangani Acara

Bookmark juga dapat memiliki tindakan yang terkait dengannya. Misalnya, Anda dapat menambahkan tindakan yang terpicu saat pengguna mengklik bookmark. Inilah cara Anda menangani peristiwa klik bookmark:

```java
// Tambahkan tindakan ke bookmark
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);
```

Dalam kode ini, kami telah menambahkan tindakan "GoTo" ke bookmark anak yang akan membawa pengguna ke halaman kedua PDF ketika diklik.

## Menyimpan PDF

Setelah Anda menambahkan semua bookmark yang diperlukan dan menyesuaikan tampilan serta tindakannya, Anda dapat menyimpan dokumen PDF yang dimodifikasi:

```java
// Simpan dokumen PDF
pdfDocument.save("output.pdf");
```

Dokumen PDF Anda dengan penanda anak sekarang sudah siap.

## Kode Sumber Lengkap

Berikut source code lengkap untuk menambahkan child bookmark pada dokumen PDF menggunakan Aspose.PDF for Java:

```java
// Inisialisasi dokumen PDF
Document pdfDocument = new Document();

// Tambahkan halaman ke PDF
pdfDocument.getPages().add();
pdfDocument.getPages().add();

// Buat bookmark orang tua
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);

// Tambahkan bookmark anak ke Bookmark Induk 1
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//Tambahkan bookmark anak ke Bookmark Induk 2
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);

// Sesuaikan tampilan penanda
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());

// Tambahkan tindakan ke bookmark
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);

// Simpan dokumen PDF
pdfDocument.save("output.pdf");
```

## Kesimpulan

Menambahkan bookmark anak ke PDF menggunakan Aspose.PDF untuk Java adalah fitur canggih yang meningkatkan navigasi dan pengorganisasian dokumen Anda. Dengan mengikuti langkah-langkah yang dijelaskan dalam artikel ini, Anda dapat membuat PDF terstruktur dengan baik dengan bookmark induk dan anak, menyesuaikan tampilannya, dan bahkan menambahkan tindakan untuk meningkatkan pengalaman pengguna.

## FAQ

### Bagaimana cara mengunduh Aspose.PDF untuk Java?

 Anda dapat mengunduh Aspose.PDF untuk Java dari situs web[Di Sini](https://releases.aspose.com/pdf/java/).

### Apakah bookmark anak didukung di semua penampil PDF?

Ya, penanda anak didukung di sebagian besar penampil PDF modern dan memberikan pengalaman pengguna yang lebih baik untuk menavigasi dokumen PDF.

### Bisakah saya menyesuaikan tampilan bookmark lebih lanjut?

Ya, Anda dapat menyesuaikan tampilan penanda dengan menyesuaikan gaya teks, warna, dan ikon agar sesuai dengan desain dokumen Anda.

### Tindakan apa lagi yang dapat saya tambahkan ke bookmark?

Selain tindakan "GoTo", Anda dapat menambahkan tindakan seperti tindakan "URI" untuk membuka tautan web atau tindakan "JavaScript" untuk menjalankan skrip khusus saat bookmark diklik.

### Apakah Aspose.PDF untuk Java cocok untuk proyek komersial?

Ya, Aspose.PDF untuk Java cocok untuk proyek pribadi dan komersial, dan menawarkan berbagai fitur untuk manipulasi dan pembuatan PDF.