---
title: Ubah Orientasi
linktitle: Ubah Orientasi
second_title: Referensi API Aspose.PDF untuk .NET
description: Panduan langkah demi langkah untuk mengubah orientasi halaman PDF dengan Aspose.PDF untuk .NET. Mudah diikuti dan diterapkan dalam proyek Anda.
type: docs
weight: 10
url: /id/net/programming-with-pdf-pages/change-orientation/
---
## Perkenalan

Pernahkah Anda mengalami kesulitan dengan file PDF yang orientasi halamannya tidak tepat? Mungkin Anda sedang menangani dokumen yang dipindai atau dibuat secara tidak benar, dan halaman-halamannya perlu diputar agar dapat dipahami. Beruntung bagi kita, Aspose.PDF untuk .NET menyediakan cara yang mudah dan canggih untuk memanipulasi file PDF dengan cara apa pun yang dapat dibayangkan—termasuk mengubah orientasi halaman Anda. Apakah Anda ingin beralih dari potret ke lanskap atau sebaliknya, panduan ini akan memandu Anda melalui proses tersebut langkah demi langkah.

Jadi, jika Anda siap untuk mulai dan memutar halaman PDF tersebut dengan mudah, mari kita mulai!

## Prasyarat

Sebelum kita membahas detail tentang mengubah orientasi halaman di PDF Anda, mari kita bahas secara singkat apa saja yang perlu Anda siapkan:

-  Aspose.PDF untuk .NET: Pastikan Anda telah menginstal pustaka Aspose.PDF untuk .NET. Jika belum, Anda dapat[unduh disini](https://releases.aspose.com/pdf/net/).
- Lingkungan Pengembangan .NET: Anda dapat menggunakan Visual Studio, JetBrains Rider, atau IDE pilihan apa pun untuk bekerja dengan .NET.
- Pengetahuan Dasar C#: Meskipun panduan ini mudah dipahami, pemahaman dasar tentang C# akan membuatnya lebih mudah diikuti.
- Berkas PDF: Contoh di bawah ini mengasumsikan Anda memiliki berkas PDF dengan beberapa halaman. Jika Anda tidak memilikinya, buat atau unduh contoh PDF untuk digunakan.

 Selain itu, jika Anda baru memulai, Anda dapat mencoba Aspose.PDF dengan[lisensi sementara gratis](https://purchase.aspose.com/temporary-license/) sebelum memutuskan untuk[beli versi lengkapnya](https://purchase.aspose.com/buy).

## Mengimpor Ruang Nama

Sebelum Anda dapat memanipulasi orientasi halaman dalam PDF, Anda perlu mengimpor namespace yang diperlukan dalam proyek C# Anda. Pastikan Anda memiliki yang berikut ini:

```csharp
using System.IO;
using Aspose.Pdf;
```

Setelah ini diimpor, mari masuk ke bagian utama tutorial.

## Langkah 1: Muat Dokumen PDF

 Hal pertama yang perlu kita lakukan adalah memuat file PDF yang ingin Anda ubah. Anda dapat menggunakan`Document` kelas dari namespace Aspose.PDF untuk membuka PDF Anda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

 Baris ini memuat PDF dari direktori yang Anda tentukan. Pastikan untuk mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke file Anda.`"input.pdf"` adalah PDF yang ingin Anda ubah orientasinya.

## Langkah 2: Ulangi Setiap Halaman

 Sekarang setelah dokumen dimuat, mari kita ulangi setiap halaman dalam PDF. Kita akan menggunakan`foreach` loop untuk menelusuri setiap halaman, sehingga memungkinkan kita menerapkan perubahan orientasi ke semuanya.

```csharp
foreach (Page page in doc.Pages)
{
    // Memanipulasi setiap halaman
}
```

Perulangan ini akan mengulangi semua halaman dalam dokumen.

## Langkah 3: Dapatkan MediaBox Halaman

 Setiap halaman dalam PDF memiliki`MediaBox` yang menentukan batas halaman. Kita perlu mengaksesnya untuk menentukan orientasi saat ini dan mengubahnya.

```csharp
Aspose.Pdf.Rectangle r = page.MediaBox;
```

 Itu`MediaBox` memberi kita dimensi halaman, seperti lebar, tinggi, dan posisinya.

## Langkah 4: Tukar Lebar dan Tinggi

Untuk mengubah orientasi halaman dari potret ke lanskap atau lanskap ke potret, kita cukup menukar nilai lebar dan tinggi. Langkah ini akan menyesuaikan dimensi halaman.

```csharp
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
```

Kode ini menukar tinggi dan lebar dan memposisikan ulang sudut kiri bawah (`LLY`) sehingga konten terpasang rapi setelah diputar.

## Langkah 5: Perbarui MediaBox dan CropBox

Sekarang setelah kita memiliki tinggi dan lebar baru, mari terapkan perubahan ke halaman`MediaBox` Dan`CropBox` . Itu`CropBox` penting jika dokumen asli memiliki satu set, memastikan seluruh halaman ditampilkan dengan benar.

```csharp
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
```

Langkah ini mengubah ukuran halaman berdasarkan dimensi baru yang baru saja kita hitung.

## Langkah 6: Putar Halaman

Terakhir, kita atur sudut rotasi halaman. Aspose.PDF membuat ini sangat mudah. Kita dapat memutar halaman 90 derajat untuk beralih dari potret ke lanskap atau sebaliknya.

```csharp
page.Rotate = Rotation.on90;
```

Kode ini memutar halaman sebesar 90 derajat, membaliknya ke orientasi yang diinginkan.

## Langkah 7: Simpan PDF Output

Setelah menerapkan perubahan orientasi pada semua halaman, kami menyimpan dokumen yang dimodifikasi ke berkas baru. 

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);
```

 Pastikan Anda memberikan nama file baru (dalam kasus ini,`ChangeOrientation_out.pdf`) untuk menyimpan output. Dengan cara ini, Anda tidak akan menimpa file asli.

### Kesimpulan

Nah, itu dia! Mengubah orientasi halaman file PDF menggunakan Aspose.PDF untuk .NET semudah memuat dokumen, mengulang halaman, menyesuaikan MediaBox, dan menyimpan file yang diperbarui. Baik Anda menangani dokumen yang dipindai dengan buruk atau perlu memutar halaman agar sesuai dengan kebutuhan pemformatan Anda, panduan langkah demi langkah ini akan membantu Anda.

## Pertanyaan yang Sering Diajukan

### Bisakah saya memutar halaman tertentu, bukan semua halaman dalam PDF?  
Ya, Anda dapat memodifikasi loop untuk menargetkan halaman-halaman tertentu menggunakan indeksnya, alih-alih melakukan loop melalui semua halaman.

###  Apakah yang`MediaBox`?  
 Itu`MediaBox` mendefinisikan ukuran dan bentuk halaman dalam berkas PDF. Di sinilah konten halaman ditempatkan.

### Apakah Aspose.PDF untuk .NET berfungsi dengan format file lain?  
Ya, Aspose.PDF dapat menangani berbagai format file seperti HTML, XML, XPS, dan banyak lagi.

### Apakah ada versi gratis Aspose.PDF untuk .NET?  
 Ya, Anda bisa memulai dengan[uji coba gratis](https://releases.aspose.com/) atau meminta[lisensi sementara](https://purchase.aspose.com/temporary-license/).

### Bisakah saya membatalkan perubahan yang sudah disimpan?  
Setelah Anda menyimpan dokumen, perubahannya bersifat permanen. Pastikan untuk mengerjakan salinan atau menyimpan cadangan berkas asli.