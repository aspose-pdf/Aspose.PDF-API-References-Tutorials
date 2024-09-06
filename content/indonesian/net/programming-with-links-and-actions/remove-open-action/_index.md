---
title: Hapus Tindakan Terbuka
linktitle: Hapus Tindakan Terbuka
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menghapus tindakan terbuka dari PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 80
url: /id/net/programming-with-links-and-actions/remove-open-action/
---
Pelajari cara menghapus tindakan terbuka dari berkas PDF menggunakan Aspose.PDF untuk .NET dengan panduan langkah demi langkah ini.

## Langkah 1: Menyiapkan lingkungan

Pastikan Anda telah menyiapkan lingkungan pengembangan Anda dengan proyek C# dan referensi Aspose.PDF yang sesuai.

## Langkah 2: Memuat file PDF

Tetapkan jalur direktori dokumen Anda dan unggah file PDF menggunakan kode berikut:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Buka dokumennya
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
```

## Langkah 3: Menghapus tindakan terbuka

 Hapus tindakan terbuka dari dokumen dengan mengatur`OpenAction` properti menjadi null:

```csharp
document. OpenAction = null;
```

## Langkah 4: Simpan dokumen yang diperbarui

 Simpan dokumen yang diperbarui menggunakan`Save` metode:

```csharp
dataDir = dataDir + "RemoveOpenAction_out.pdf";
document. Save(dataDir);
```

## Langkah 5: Menampilkan hasilnya

Menampilkan pesan yang menunjukkan bahwa tindakan terbuka berhasil dihapus dan menentukan lokasi file yang disimpan:

```csharp
Console.WriteLine("\nOpen action deleted successfully.\nFile saved to location: " + dataDir);
```

### Contoh kode sumber untuk Remove Open Action menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
// Hapus tindakan buka dokumen
document.OpenAction = null;
dataDir = dataDir + "RemoveOpenAction_out.pdf";
// Simpan dokumen yang diperbarui
document.Save(dataDir);
Console.WriteLine("\nOpen action removed successfully.\nFile saved at " + dataDir); 
```

## Kesimpulan

Selamat! Sekarang Anda tahu cara menghapus tindakan terbuka dari PDF menggunakan Aspose.PDF untuk .NET. Gunakan pengetahuan ini untuk menyesuaikan properti dan perilaku file PDF dalam proyek Anda.

Sekarang setelah Anda menyelesaikan panduan ini, Anda dapat menerapkan konsep-konsep ini ke proyek Anda sendiri dan mengeksplorasi lebih lanjut fitur-fitur yang ditawarkan oleh Aspose.PDF untuk .NET.

### Pertanyaan yang Sering Diajukan 

#### T: Apa yang dimaksud dengan "tindakan terbuka" dalam berkas PDF?

J: "Tindakan buka" dalam file PDF adalah instruksi yang menentukan apa yang harus terjadi saat PDF dibuka. Tindakan ini dapat mencakup tindakan seperti menavigasi ke halaman atau lokasi tertentu dalam dokumen, meluncurkan aplikasi eksternal, atau menampilkan tampilan tertentu.

#### T: Mengapa saya ingin menghapus tindakan terbuka dari berkas PDF?

J: Menghapus tindakan buka dapat meningkatkan keamanan, pengalaman pengguna, dan kontrol atas cara PDF ditampilkan saat dibuka. Misalnya, Anda mungkin ingin mencegah navigasi otomatis atau menonaktifkan tindakan tertentu saat membuka dokumen.

#### T: Bagaimana Aspose.PDF untuk .NET membantu menghapus tindakan terbuka?

A: Aspose.PDF untuk .NET menyediakan API untuk memanipulasi berbagai aspek file PDF. Tutorial ini menunjukkan cara menghapus tindakan buka menggunakan kode C#.

#### T: Apakah ada risiko atau pertimbangan potensial saat melepas tindakan terbuka?

J: Menghapus tindakan buka dapat mengubah perilaku default PDF, jadi pastikan tindakan tersebut sesuai dengan pengalaman pengguna yang diinginkan. Uji PDF yang dimodifikasi secara menyeluruh untuk memastikan bahwa penghapusan tersebut tidak memengaruhi fungsi lainnya.

#### T: Dapatkah saya menyesuaikan tindakan terbuka untuk melakukan tindakan lain?

A: Ya, Aspose.PDF untuk .NET memungkinkan Anda menyesuaikan tindakan terbuka dengan mengaturnya ke berbagai jenis tindakan, seperti menavigasi ke halaman tertentu atau menjalankan JavaScript.

#### T: Dapatkah saya menghapus tindakan terbuka dari PDF yang dilindungi kata sandi?
A: Ya, Anda dapat menghapus tindakan terbuka dari PDF yang dilindungi kata sandi selama Anda memberikan kredensial yang sesuai untuk mengakses dan mengubah dokumen tersebut.

#### T: Apakah tindakan pelepasan terbuka dapat dibatalkan?

A: Tidak, setelah tindakan terbuka dihapus dan PDF disimpan, tindakan terbuka asli tidak dapat dipulihkan dari PDF yang dimodifikasi.

#### T: Bagaimana cara memverifikasi bahwa tindakan terbuka telah berhasil dihapus?

A: Setelah menghapus tindakan terbuka menggunakan kode yang disediakan, buka PDF yang dimodifikasi dan konfirmasikan bahwa tidak ada tindakan tertentu yang terjadi saat dibuka.

#### T: Dapatkah saya menghapus tindakan terbuka dari beberapa file PDF secara bersamaan?

A: Ya, Anda dapat menggunakan pendekatan yang sama untuk menghapus tindakan terbuka dari beberapa file PDF dalam skenario pemrosesan batch.