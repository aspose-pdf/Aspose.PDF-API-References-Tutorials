---
title: Hapus Tindakan Terbuka
linktitle: Hapus Tindakan Terbuka
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menghapus tindakan terbuka dari PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 80
url: /id/net/programming-with-links-and-actions/remove-open-action/
---
Pelajari cara menghapus tindakan terbuka dari file PDF menggunakan Aspose.PDF untuk .NET dengan panduan langkah demi langkah ini.

## Langkah 1: Menyiapkan lingkungan

Pastikan Anda telah menyiapkan lingkungan pengembangan dengan proyek C# dan referensi Aspose.PDF yang sesuai.

## Langkah 2: Memuat file PDF

Tetapkan jalur direktori dokumen Anda dan unggah file PDF menggunakan kode berikut:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Buka dokumennya
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
```

## Langkah 3: Menghapus tindakan terbuka

 Hapus tindakan terbuka dari dokumen dengan mengatur`OpenAction` properti menjadi nol:

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

Tampilkan pesan yang menunjukkan bahwa tindakan terbuka berhasil dihapus dan tentukan lokasi file yang disimpan:

```csharp
Console.WriteLine("\nOpen action deleted successfully.\nFile saved to location: " + dataDir);
```

### Contoh kode sumber untuk Hapus Tindakan Terbuka menggunakan Aspose.PDF untuk .NET 
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

Selamat! Sekarang Anda tahu cara menghapus tindakan terbuka dari PDF menggunakan Aspose.PDF untuk .NET. Gunakan pengetahuan ini untuk menyesuaikan properti dan perilaku file PDF di proyek Anda.

Sekarang setelah Anda menyelesaikan panduan ini, Anda dapat menerapkan konsep ini ke proyek Anda sendiri dan menjelajahi lebih jauh fitur yang ditawarkan oleh Aspose.PDF untuk .NET.

### FAQ 

#### T: Apa yang dimaksud dengan "tindakan terbuka" dalam file PDF?

J: "Tindakan terbuka" dalam file PDF adalah instruksi yang menentukan apa yang harus terjadi ketika PDF dibuka. Ini dapat mencakup tindakan seperti menavigasi ke halaman atau lokasi tertentu dalam dokumen, meluncurkan aplikasi eksternal, atau menampilkan tampilan tertentu.

#### T: Mengapa saya ingin menghapus tindakan terbuka dari file PDF?

J: Menghapus tindakan terbuka dapat meningkatkan keamanan, pengalaman pengguna, dan kontrol terhadap cara PDF disajikan saat dibuka. Misalnya, Anda mungkin ingin mencegah navigasi otomatis atau menonaktifkan tindakan tertentu saat membuka dokumen.

#### T: Bagaimana Aspose.PDF untuk .NET membantu menghilangkan tindakan terbuka?

J: Aspose.PDF untuk .NET menyediakan API untuk memanipulasi berbagai aspek file PDF. Tutorial ini menunjukkan cara menghapus tindakan terbuka menggunakan kode C#.

#### T: Apakah ada potensi risiko atau pertimbangan ketika menghapus tindakan terbuka?

J: Menghapus tindakan terbuka dapat mengubah perilaku default PDF, jadi pastikan tindakan tersebut selaras dengan pengalaman pengguna yang diinginkan. Uji PDF yang dimodifikasi secara menyeluruh untuk memastikan bahwa penghapusan tidak memengaruhi fungsi lainnya.

#### T: Bisakah saya menyesuaikan tindakan terbuka untuk melakukan tindakan lain?

J: Ya, Aspose.PDF untuk .NET memungkinkan Anda menyesuaikan tindakan terbuka dengan mengaturnya ke berbagai jenis tindakan, seperti menavigasi ke halaman tertentu atau menjalankan JavaScript.

#### T: Dapatkah saya menghapus tindakan terbuka dari PDF yang dilindungi kata sandi?
J: Ya, Anda dapat menghapus tindakan terbuka dari PDF yang dilindungi kata sandi selama Anda memberikan kredensial yang sesuai untuk mengakses dan memodifikasi dokumen tersebut.

#### T: Apakah penghapusan tindakan terbuka dapat dibatalkan?

J: Tidak, setelah tindakan terbuka dihapus dan PDF disimpan, tindakan terbuka asli tidak dapat dipulihkan dari PDF yang dimodifikasi.

#### T: Bagaimana cara memverifikasi bahwa tindakan terbuka berhasil dihapus?

J: Setelah menghapus tindakan terbuka menggunakan kode yang disediakan, buka PDF yang dimodifikasi dan konfirmasikan bahwa tidak ada tindakan spesifik yang terjadi saat pembukaan.

#### T: Dapatkah saya menghapus tindakan terbuka dari beberapa file PDF secara bersamaan?

J: Ya, Anda dapat menggunakan pendekatan yang sama untuk menghapus tindakan terbuka dari beberapa file PDF dalam skenario pemrosesan batch.