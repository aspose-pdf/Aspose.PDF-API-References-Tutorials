---
title: Tambahkan Java Script ke File PDF
linktitle: Tambahkan File PDF Java Script
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menambahkan JavaScript ke berkas PDF menggunakan Aspose.PDF untuk .NET. Panduan langkah demi langkah dengan tutorial kode untuk penulisan skrip pada tingkat dokumen dan halaman.
type: docs
weight: 10
url: /id/net/programming-with-document/addjavascripttopage/
---
## Perkenalan

Pernahkah Anda bertanya-tanya bagaimana cara menyempurnakan PDF Anda dengan elemen interaktif seperti peringatan pop-up atau fungsi cetak otomatis? Nah, kabar baiknya—Anda bisa! Dengan menggunakan Aspose.PDF untuk .NET, Anda dapat menambahkan JavaScript ke dokumen PDF Anda dengan mudah. Baik Anda mengotomatiskan tugas atau menciptakan pengalaman pengguna yang dinamis, menyematkan JavaScript dalam PDF akan memberikan fungsionalitas ekstra pada file Anda.

## Prasyarat

Sebelum kita masuk ke bagian pengkodean, ada beberapa hal yang perlu Anda siapkan:

-  Aspose.PDF untuk .NET: Unduh pustaka dari[Rilis Aspose](https://releases.aspose.com/pdf/net/) atau dapatkan[uji coba gratis](https://releases.aspose.com/).
- Lingkungan Pengembangan: Setiap IDE yang kompatibel dengan .NET seperti Visual Studio.
- Pengetahuan Dasar C#: Panduan ini mengasumsikan Anda familier dengan sintaksis dasar C#.
-  Lisensi Sementara (Opsional): Anda bisa mendapatkannya[lisensi sementara](https://purchase.aspose.com/temporary-license/) jika Anda ingin menghindari keterbatasan selama pengembangan Anda.

## Paket Impor

Sebelum Anda mulai menulis kode, Anda perlu mengimpor namespace yang diperlukan dari pustaka Aspose.PDF. Namespace ini akan memungkinkan Anda untuk memanipulasi PDF dan menambahkan tindakan JavaScript dengan mudah.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

Sekarang, setelah Anda mengimpor namespace yang tepat, Anda siap untuk memulai pengkodean.

## Langkah 1: Muat PDF yang Ada

Hal pertama yang harus dilakukan adalah memuat dokumen PDF yang ingin Anda tambahkan JavaScript. Langkah ini menjadi dasar untuk semua modifikasi selanjutnya. Bayangkan Anda memiliki PDF yang ingin Anda tingkatkan dengan fungsionalitas dinamis, seperti mencetak dokumen secara otomatis saat dibuka.

Berikut cara Anda dapat memuat berkas PDF tersebut:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Memuat file PDF yang ada
Document doc = new Document(dataDir + "input.pdf");
```

 Dalam potongan kode ini, kami menggunakan`Document` kelas untuk memuat file PDF yang ada dari direktori yang ditentukan. Pastikan untuk mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke berkas PDF Anda.

## Langkah 2: Tambahkan JavaScript di Tingkat Dokumen

Sekarang, mari tambahkan beberapa JavaScript yang akan aktif saat dokumen dibuka. Dalam contoh ini, kita akan menulis skrip yang membuka dialog cetak segera setelah pengguna membuka PDF.

JavaScript tingkat dokumen sangat cocok untuk tindakan yang ingin Anda terapkan ke seluruh PDF. Anggap saja seperti menyiapkan aturan global untuk dokumen Anda.

Berikut kodenya:

```csharp
// Menambahkan JavaScript di Tingkat Dokumen
// Buat JavascriptAction dengan pernyataan JavaScript yang diinginkan
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Tetapkan objek JavascriptAction ke OpenAction Dokumen
doc.OpenAction = javaScript;
```

 Pada langkah ini, kita membuat`JavascriptAction` objek yang mendefinisikan fungsi JavaScript untuk membuka dialog cetak saat dokumen dibuka.`doc.OpenAction` properti kemudian diberi tindakan JavaScript ini.

## Langkah 3: Tambahkan JavaScript di Tingkat Halaman

Tidak semua tindakan harus memengaruhi seluruh dokumen. Terkadang, Anda ingin tindakan tertentu terjadi saat halaman tertentu dibuka atau ditutup. Di sini, kami akan menyiapkan tindakan JavaScript saat halaman tertentu (misalnya halaman 2) dibuka dan ditutup.

JavaScript tingkat halaman berguna untuk interaksi yang ditargetkan. Bisa berupa apa saja, mulai dari menampilkan pesan saat pengguna membuka halaman, hingga tindakan khusus seperti mengisi kolom formulir secara otomatis.

Berikut cara melakukannya:

```csharp
// Menambahkan JavaScript di Tingkat Halaman
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('Page 2 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('Page 2 closed')");
```

Dalam potongan kode ini, kami menambahkan dua tindakan JavaScript:
1. Tindakan OnOpen: Menampilkan peringatan yang mengatakan “Halaman 2 dibuka” saat pengguna membuka halaman 2.
2. Tindakan OnClose: Menampilkan peringatan yang mengatakan “Halaman 2 ditutup” saat pengguna menavigasi keluar dari halaman 2.

Ini menambahkan lapisan interaktivitas ke PDF Anda. Bayangkan memandu pengguna melalui serangkaian langkah di halaman yang berbeda, dengan peringatan yang muncul saat mereka masuk atau meninggalkan halaman.

## Langkah 4: Simpan Dokumen PDF

Anda kini telah menambahkan JavaScript ke dokumen dan halaman tertentu. Langkah terakhir adalah menyimpan PDF yang dimodifikasi ke lokasi yang Anda inginkan. Bagian ini sederhana tetapi penting—jangan lupa untuk menyimpan pekerjaan Anda!

Berikut kodenya:

```csharp
// Tentukan jalur file keluaran
dataDir = dataDir + "JavaScript-Added_out.pdf";

// Simpan dokumen PDF yang diperbarui
doc.Save(dataDir);

Console.WriteLine("\nJavaScript added successfully to the PDF.\nFile saved at " + dataDir);
```

 Dalam potongan kode ini, kami menyimpan dokumen yang diperbarui dengan JavaScript yang ditambahkan ke file baru bernama`"JavaScript-Added_out.pdf"`Ini memastikan Anda tidak menimpa berkas asli, dan memberi Anda cadangan untuk digunakan.

## Kesimpulan

Menambahkan JavaScript ke file PDF menggunakan Aspose.PDF untuk .NET merupakan cara yang ampuh untuk membuat PDF yang interaktif dan dinamis. Baik Anda mengotomatiskan tugas seperti mencetak atau membuat peringatan khusus, kemampuan untuk menyematkan JavaScript ke dalam PDF membuat dokumen Anda lebih menarik dan fungsional.

## Pertanyaan yang Sering Diajukan

### Bisakah saya menambahkan beberapa tindakan JavaScript ke halaman berbeda dalam PDF?
Ya, Anda dapat menetapkan tindakan JavaScript yang berbeda untuk halaman individual atau keseluruhan dokumen.

### Apakah mungkin untuk menghapus JavaScript dari PDF setelah menambahkannya?
Ya, Anda dapat menghapus atau mengubah tindakan JavaScript yang ada dengan menghapus`Actions` properti dokumen atau halaman.

### Fungsi JavaScript apa saja yang dapat saya gunakan dalam PDF?
Anda dapat menggunakan JavaScript apa pun yang didukung oleh mesin JavaScript Adobe Acrobat, seperti pencetakan, peringatan, dan manipulasi formulir.

### Apakah JavaScript berfungsi di semua penampil PDF?
Sebagian besar tindakan JavaScript akan berfungsi di penampil PDF yang mendukung PDF interaktif, seperti Adobe Acrobat. Namun, beberapa pembaca PDF dasar mungkin tidak mendukung JavaScript.

### Bisakah saya memicu tindakan JavaScript berdasarkan masukan pengguna dalam PDF?
Ya, Anda dapat mengikat JavaScript ke kolom formulir untuk memicu tindakan berdasarkan masukan pengguna.