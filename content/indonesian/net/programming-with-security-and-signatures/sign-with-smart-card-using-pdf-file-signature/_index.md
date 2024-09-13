---
title: Tanda Tangan Dengan Kartu Pintar Menggunakan Tanda Tangan File PDF
linktitle: Tanda Tangan Dengan Kartu Pintar Menggunakan Tanda Tangan File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menandatangani file PDF menggunakan kartu pintar dengan Aspose.PDF untuk .NET. Ikuti panduan langkah demi langkah ini untuk mendapatkan tanda tangan digital yang aman.
type: docs
weight: 110
url: /id/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
## Perkenalan

Di era digital, pengamanan dokumen menjadi lebih penting dari sebelumnya. Baik itu kontrak, perjanjian, atau informasi sensitif apa pun, memastikan bahwa dokumen tersebut asli dan belum dirusak adalah yang terpenting. Gunakan tanda tangan digital! Hari ini, kita akan membahas cara menandatangani file PDF menggunakan kartu pintar dengan Aspose.PDF untuk .NET. Pustaka canggih ini memungkinkan pengembang untuk memanipulasi dan membuat dokumen PDF secara efisien, termasuk menambahkan tanda tangan digital yang aman. Jadi, ambil kartu pintar Anda, dan mari kita mulai!

## Prasyarat

Sebelum kita masuk ke inti proses penandatanganan file PDF, mari pastikan Anda memiliki semua yang dibutuhkan. Berikut ini daftar periksa untuk membantu Anda mempersiapkan diri:

1.  Aspose.PDF untuk .NET: Pastikan Anda telah menginstal pustaka Aspose.PDF. Anda dapat mengunduhnya dari[lokasi](https://releases.aspose.com/pdf/net/).
2. Visual Studio: Lingkungan pengembangan tempat Anda dapat menulis dan menjalankan kode .NET Anda.
3. Kartu Pintar: Anda memerlukan kartu pintar dengan sertifikat digital valid yang terpasang.
4. Pemahaman Dasar tentang C#: Keakraban dengan pemrograman C# akan bermanfaat karena kita akan menulis potongan kode dalam bahasa ini.
5. Dokumen PDF: Contoh file PDF (seperti`blank.pdf`) untuk menguji proses penandatanganan kami.

Jika prasyarat ini terpenuhi, Anda siap untuk mulai mempelajari kodenya!

## Paket Impor

Pertama-tama, mari impor paket-paket yang diperlukan. Anda perlu menambahkan referensi ke pustaka Aspose.PDF di proyek Anda. Berikut cara melakukannya:

1. Buka Visual Studio.
2. Buat proyek baru atau buka proyek yang sudah ada.
3.  Klik kanan pada proyek Anda di Solution Explorer dan pilih`Manage NuGet Packages`.
4.  Pencarian untuk`Aspose.PDF` dan instal versi terbaru.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Sekarang setelah paket-paket yang diperlukan telah diimpor, mari kita uraikan kodenya langkah demi langkah.

## Langkah 1: Siapkan Dokumen Anda

Langkah pertama dalam proses ini adalah menyiapkan dokumen PDF yang ingin ditandatangani. Berikut cara melakukannya:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
```
 Dalam potongan kode ini, kami menentukan jalur ke direktori dokumen kami dan membuat contoh`Document` kelas menggunakan contoh file PDF bernama`blank.pdf` Pastikan untuk mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan jalur sebenarnya tempat PDF Anda berada.

## Langkah 2: Inisialisasi PdfFileSignature

 Selanjutnya, kita akan menginisialisasi`PdfFileSignature` kelas yang bertanggung jawab untuk menangani proses penandatanganan.

```csharp
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
    pdfSign.BindPdf(doc);
```
Di sini, kita membuat sebuah instance dari`PdfFileSignature`dan mengikatnya ke dokumen PDF kita. Ini mempersiapkan dokumen untuk ditandatangani.

## Langkah 3: Akses Sertifikat Kartu Pintar

Sekarang tibalah bagian yang krusial—mengakses sertifikat digital yang tersimpan di kartu pintar Anda. Berikut cara melakukannya:

### Buka Toko Sertifikat

```csharp
System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
```
Kami membuka penyimpanan sertifikat yang terletak di profil pengguna saat ini. Ini memungkinkan kami untuk mengakses sertifikat yang terpasang di komputer Anda, termasuk sertifikat yang ada di kartu pintar Anda.

### Pilih Sertifikat

```csharp
System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel =
    System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(
        store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
```
Kode ini meminta pengguna untuk memilih sertifikat dari koleksi. Antarmuka pengguna akan menampilkan semua sertifikat yang tersedia, sehingga Anda dapat memilih sertifikat yang terkait dengan kartu pintar Anda.

## Langkah 4: Buat Tanda Tangan Eksternal

Setelah Anda memilih sertifikat, langkah berikutnya adalah membuat tanda tangan eksternal menggunakan sertifikat yang dipilih.

```csharp
Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
```
Di sini, kita membuat sebuah instance dari`ExternalSignature` menggunakan sertifikat yang dipilih. Objek ini akan digunakan untuk menandatangani dokumen PDF.

## Langkah 5: Mengatur Tampilan Tanda Tangan

Sekarang, mari kita atur tampilan tanda tangan kita. Di sinilah Anda dapat menyesuaikan tampilan tanda tangan Anda pada dokumen.

```csharp
pdfSign.SignatureAppearance = dataDir + "demo.png";
```
 Dalam cuplikan ini, kami menentukan tampilan tanda tangan dengan memberikan jalur ke file gambar (seperti logo atau grafik tanda tangan). Pastikan untuk mengganti`"demo.png"` dengan gambar sebenarnya yang ingin Anda gunakan.

## Langkah 6: Tanda tangani PDF

Setelah semuanya disiapkan, waktunya menandatangani dokumen PDF!

```csharp
pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
pdfSign.Save(dataDir + "externalSignature2.pdf");
```
Pada langkah ini, kita memanggil`Sign` metode pada kami`pdfSign` objek. Berikut ini arti setiap parameter:
- `1`: Nomor halaman tempat tanda tangan akan muncul.
- `"Reason"`: Alasan penandatanganan dokumen.
- `"Contact"`: Informasi kontak untuk penandatangan.
- `"Location"`: Lokasi penandatangan.
- `true`: Menunjukkan apakah akan membuat tanda tangan yang terlihat.
- `new System.Drawing.Rectangle(100, 100, 200, 200)`: Posisi dan ukuran tanda tangan pada PDF.
- `externalSignature`: Objek tanda tangan yang kita buat sebelumnya.

 Terakhir, kami menyimpan dokumen yang ditandatangani sebagai`externalSignature2.pdf`.

## Langkah 7: Verifikasi Tanda Tangan

Setelah menandatangani dokumen, penting untuk memverifikasi bahwa tanda tangan tersebut valid. Berikut cara melakukannya:

### Inisialisasi Proses Verifikasi

```csharp
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
    IList<string> sigNames = pdfSign.GetSignNames();
```
 Kami membuat contoh baru dari`PdfFileSignature` untuk dokumen yang ditandatangani. Kami kemudian mengambil nama semua tanda tangan yang ada dalam dokumen tersebut.

### Periksa Validitas Tanda Tangan

```csharp
for (int index = 0; index <= sigNames.Count - 1; index++)
{
    if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
    {
        throw new ApplicationException("Not verified");
    }
}
```
Kami mengulang setiap nama tanda tangan dan memverifikasi keabsahannya. Jika ada tanda tangan yang gagal diverifikasi, pengecualian akan muncul, yang menunjukkan bahwa tanda tangan tersebut tidak valid.

## Kesimpulan

Nah, itu dia! Anda telah berhasil menandatangani dokumen PDF menggunakan kartu pintar dengan Aspose.PDF untuk .NET. Proses ini tidak hanya mengamankan dokumen Anda, tetapi juga menambahkan lapisan keaslian yang sangat penting dalam dunia digital saat ini. Baik Anda berurusan dengan kontrak, dokumen hukum, atau informasi sensitif apa pun, mengetahui cara menerapkan tanda tangan digital adalah keterampilan yang berharga. 

## Pertanyaan yang Sering Diajukan

### Apa itu Aspose.PDF untuk .NET?
Aspose.PDF untuk .NET adalah pustaka hebat yang memungkinkan pengembang untuk membuat, memanipulasi, dan mengonversi dokumen PDF dalam aplikasi .NET.

### Apakah saya memerlukan kartu pintar untuk menandatangani PDF?
Meskipun kartu pintar tidak wajib, namun sangat disarankan untuk tanda tangan digital yang aman, karena menyediakan lapisan keamanan tambahan.

### Bisakah saya menggunakan file PDF apa pun untuk menandatangani?
Ya, Anda dapat menggunakan berkas PDF apa pun, tetapi pastikan berkas tersebut tidak dilindungi kata sandi. Jika dilindungi kata sandi, Anda harus membukanya terlebih dahulu.

### Bagaimana jika saya tidak memiliki sertifikat digital?
Anda dapat memperoleh sertifikat digital dari otoritas sertifikat (CA) tepercaya atau menggunakan sertifikat yang ditandatangani sendiri untuk tujuan pengujian.

### Apakah ada versi uji coba Aspose.PDF yang tersedia?
 Ya, Anda dapat mengunduh versi uji coba gratis dari[Situs web Aspose](https://releases.aspose.com/).