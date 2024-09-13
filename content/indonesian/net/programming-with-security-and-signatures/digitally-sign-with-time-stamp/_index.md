---
title: Tanda Tangan Digital Dengan Cap Waktu Dalam File PDF
linktitle: Tanda Tangan Digital Dengan Cap Waktu Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menandatangani PDF secara digital dengan stempel waktu menggunakan Aspose.PDF untuk .NET. Panduan langkah demi langkah ini mencakup prasyarat, pengaturan sertifikat, pemberian stempel waktu, dan banyak lagi.
type: docs
weight: 50
url: /id/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
## Perkenalan

Pernahkah Anda perlu menandatangani PDF secara digital dan menyertakan stempel waktu untuk keamanan ekstra? Baik Anda mengerjakan dokumen hukum, kontrak, atau apa pun yang memerlukan autentikasi aman, tanda tangan digital dengan stempel waktu menambahkan lapisan kredibilitas ekstra. Dalam tutorial ini, kami akan menguraikan cara menggunakan Aspose.PDF untuk .NET guna menambahkan tanda tangan digital beserta stempel waktu ke dokumen PDF Anda. Jangan khawatir, kami akan melakukannya selangkah demi selangkah!

## Prasyarat

Sebelum kita mulai menggunakan kode, ada beberapa hal yang perlu Anda siapkan untuk mengikutinya. Berikut ini daftar periksa singkat tentang prasyarat untuk membantu Anda memulai:

-  Pustaka Aspose.PDF untuk .NET: Anda memerlukan pustaka Aspose.PDF untuk .NET yang terinstal di proyek Anda. Anda dapat[unduh versi terbaru di sini](https://releases.aspose.com/pdf/net/) atau tambahkan ke proyek Anda melalui NuGet.
- Dokumen PDF: Anda memerlukan contoh file PDF untuk digunakan. Pastikan Anda memiliki file di direktori proyek yang ingin Anda tandatangani.
-  Sertifikat Digital (file PFX): Pastikan Anda memiliki sertifikat digital (file PFX)`.pfx` file) untuk menandatangani dokumen secara digital.
- URL Penandaan Waktu: Ini adalah layanan penandaan waktu daring yang akan digunakan untuk melampirkan penandaan waktu ke tanda tangan digital. 
- Pengetahuan dasar C#: Anda tidak perlu menjadi ahli, tetapi mengetahui dasar-dasar C# akan membantu Anda memahami dan menyesuaikan kode.

Setelah Anda mencentang semua kotak ini, Anda siap untuk mulai membuat kode!

## Paket Impor

Untuk memulai, Anda perlu mengimpor namespace berikut ke dalam proyek C# Anda. Ini memastikan Anda memiliki akses ke kelas dan fungsi Aspose.PDF yang relevan.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Collections;
```

## Langkah 1: Muat Dokumen PDF

Hal pertama yang perlu kita lakukan adalah memuat dokumen PDF yang ingin kita tandatangani. Berikut cara melakukannya:

```csharp
// Tentukan jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Muat dokumen PDF
Document document = new Document(dataDir + @"DigitallySign.pdf");
```

 Langkah ini cukup mudah. Kita hanya perlu menentukan jalur ke dokumen yang ingin kita tandatangani.`Document` kelas dari Aspose.PDF menangani pemuatan berkas.

## Langkah 2: Siapkan Tanda Tangan Digital

Selanjutnya, kita akan membuat tanda tangan digital menggunakan kelas PKCS7 dan memuat berkas PFX. Berkas PFX ini berisi sertifikat dan kunci pribadi Anda, yang diperlukan untuk menandatangani dokumen.

```csharp
// Jalur ke file .pfx Anda
string pfxFile = "YOUR DOCUMENTS DIRECTORY\\certificate.pfx";

// Inisialisasi objek tanda tangan
PdfFileSignature signature = new PdfFileSignature(document);

// Muat file PFX dengan kata sandi
PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
```

 Pada titik ini, Anda memberi tahu Aspose untuk menggunakan sertifikat digital Anda untuk menandatangani dokumen.`PKCS7`objek menangani semua pekerjaan kriptografi untuk Anda, jadi Anda tidak perlu khawatir tentang detail-detail yang rumit.

## Langkah 3: Tambahkan Pengaturan Cap Waktu

Salah satu komponen utama tanda tangan digital yang kuat adalah stempel waktu. Ini memastikan bahwa tanda tangan dokumen dapat diverifikasi bahkan setelah sertifikat kedaluwarsa. Mari kita atur stempel waktu menggunakan otoritas penandaan waktu daring.

```csharp
// Tentukan pengaturan cap waktu
TimestampSettings timestampSettings = new TimestampSettings("https://url_stempel_waktu_anda", "pengguna:kata_sandi");

// Tambahkan pengaturan stempel waktu ke objek PKCS7
pkcs.TimestampSettings = timestampSettings;
```

Di sini, Anda menentukan URL untuk layanan penandaan waktu, yang secara otomatis akan memberikan waktu dan tanggal pada tanda tangan Anda. Ini dapat dilakukan dengan atau tanpa autentikasi.

## Langkah 4: Tentukan Lokasi dan Tampilan Tanda Tangan

Sekarang, kita akan menentukan di mana tanda tangan akan muncul dalam PDF dan dimensinya. Anda dapat menyesuaikan posisi kotak tanda tangan pada halaman, serta ukurannya.

```csharp
//Tentukan tampilan dan lokasi tanda tangan (halaman 1, dengan persegi panjang yang ditentukan)
System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
```

Di sini, kami mendefinisikan persegi panjang yang memposisikan tanda tangan pada koordinat (100, 100) di halaman pertama PDF, dengan lebar 200 dan tinggi 100. Anda dapat mengubah nilai ini agar sesuai dengan desain Anda.

## Langkah 5: Tanda tangani Dokumen PDF

Setelah semuanya siap, saatnya untuk benar-benar menerapkan tanda tangan digital ke PDF. Langkah ini menggabungkan sertifikat, stempel waktu, dan posisi menjadi satu perintah sederhana.

```csharp
// Tanda tangani dokumen di halaman pertama
signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
```

Inilah yang terjadi:
- 1: Ini menunjukkan bahwa tanda tangan harus diterapkan pada halaman pertama.
- "Alasan Tanda Tangan": Di sinilah Anda dapat menentukan mengapa Anda menandatangani dokumen.
- "Kontak": Masukkan informasi kontak penanda tangan.
- "Lokasi": Tentukan lokasi penanda tangan.
- benar: Nilai boolean ini menunjukkan apakah tanda tangan terlihat dalam dokumen.
- rect: Persegi panjang yang kita definisikan sebelumnya menentukan ukuran dan posisi tanda tangan.
- pkcs: Objek PKCS7 berisi sertifikat digital dan pengaturan stempel waktu.

## Langkah 6: Simpan PDF yang Ditandatangani

Setelah dokumen ditandatangani, yang perlu dilakukan hanyalah menyimpannya. Anda dapat memilih nama berkas baru untuk menyimpan versi asli dan yang sudah ditandatangani.

```csharp
// Simpan dokumen PDF yang telah ditandatangani
signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
```

PDF Anda yang baru ditandatangani dan diberi cap waktu sekarang disimpan ke direktori yang ditentukan!

## Kesimpulan

Nah, itu dia! Anda telah berhasil menandatangani PDF secara digital dengan stempel waktu menggunakan Aspose.PDF untuk .NET. Proses ini memastikan keaslian dan integritas dokumen Anda, sehingga Anda dan penerima merasa tenang. Tanda tangan digital menjadi semakin penting di dunia digital saat ini, jadi menguasai proses ini jelas merupakan keterampilan yang layak dimiliki.

## Pertanyaan yang Sering Diajukan

### Bisakah saya menggunakan format file yang berbeda untuk sertifikat?  
Ya, tetapi tutorial ini berfokus pada penggunaan berkas PFX, yang merupakan format paling umum untuk sertifikat digital.

### Apakah saya memerlukan koneksi internet untuk menerapkan stempel waktu?  
Ya, karena stempel waktu diambil dari otoritas penandaan waktu daring, Anda memerlukan akses internet.

### Bisakah saya menandatangani beberapa halaman dalam PDF?  
 Tentu saja! Anda dapat memodifikasi`signature.Sign()` metode untuk menargetkan beberapa halaman atau mengulang semua halaman.

### Apa yang terjadi jika kata sandi berkas PFX salah?  
Anda akan menerima pengecualian jika kata sandi salah, jadi pastikan kata sandi yang dimasukkan benar.

### Bisakah saya membuat tanda tangan tidak terlihat?  
 Ya, kamu bisa lulus`false` ke`Sign` parameter visibilitas metode untuk membuat tanda tangan tidak terlihat.