---
title: Tanda Tangan Dengan Kartu Pintar Menggunakan Kolom Tanda Tangan
linktitle: Tanda Tangan Dengan Kartu Pintar Menggunakan Kolom Tanda Tangan
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menandatangani PDF dengan aman menggunakan kartu pintar dengan Aspose.PDF untuk .NET. Ikuti panduan langkah demi langkah kami untuk penerapan yang mudah.
type: docs
weight: 120
url: /id/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
## Perkenalan

Di dunia digital saat ini, pengamanan dokumen menjadi lebih penting dari sebelumnya. Baik Anda seorang pengembang, pemilik bisnis, atau hanya seseorang yang menangani informasi sensitif, mengetahui cara menandatangani PDF secara elektronik dapat menghemat waktu Anda dan memastikan dokumen Anda diautentikasi. Dalam panduan ini, kami akan memandu Anda melalui proses penandatanganan PDF menggunakan kartu pintar dan kolom tanda tangan dengan Aspose.PDF untuk .NET. 

## Prasyarat

Sebelum kita menyelami seluk-beluk proses penandatanganan, mari pastikan Anda memiliki semua yang dibutuhkan untuk memulai. Berikut ini adalah daftar prasyarat:

1. Aspose.PDF untuk .NET: Pastikan Anda telah menginstal pustaka Aspose.PDF di lingkungan .NET Anda. Anda dapat mengunduhnya dari[lokasi](https://releases.aspose.com/pdf/net/).

2. Visual Studio: Anda memerlukan IDE untuk menulis dan menjalankan kode .NET. Visual Studio Community Edition adalah pilihan gratis yang bagus.

3. Kartu Pintar: Ini penting untuk menandatangani PDF Anda. Pastikan Anda memiliki pembaca kartu pintar dan sertifikat yang diperlukan terpasang di mesin Anda.

4. Pengetahuan Dasar C#: Keakraban dengan pemrograman C# akan membantu Anda memahami potongan kode yang akan kita gunakan.

5. Contoh Dokumen PDF: Siapkan contoh dokumen PDF untuk pengujian. Anda dapat membuat PDF kosong atau menggunakan PDF yang sudah ada.

## Paket Impor

Sebelum kita mulai membuat kode, mari impor paket-paket yang diperlukan. Anda perlu menyertakan namespace berikut dalam berkas C# Anda:

```csharp
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

Ruang nama ini akan memberi Anda akses ke kelas dan metode yang diperlukan untuk bekerja dengan PDF dan menangani tanda tangan digital.

## Panduan Langkah demi Langkah untuk Menandatangani PDF dengan Kartu Pintar

Setelah semua prasyarat terpenuhi, mari kita bagi proses penandatanganan menjadi beberapa langkah yang mudah dikelola. Kita akan membahas setiap langkah secara terperinci, untuk memastikan Anda memahami apa yang terjadi di balik layar.

### Langkah 1: Siapkan Direktori Dokumen Anda

Yang Harus Dilakukan: Tentukan jalur ke direktori dokumen Anda.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Penjelasan: Ganti`"YOUR DOCUMENTS DIRECTORY"` dengan jalur sebenarnya tempat file PDF Anda berada. Di sinilah kita akan membaca PDF kosong dan menyimpan dokumen yang ditandatangani.

### Langkah 2: Salin PDF Kosong

Yang Harus Dilakukan: Buat salinan PDF kosong Anda untuk digunakan.

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
```

 Penjelasan: Baris ini menyalin`blank.pdf`file ke file baru bernama`externalSignature1.pdf` . Itu`true` parameter memperbolehkan penimpaan jika berkas sudah ada.

### Langkah 3: Buka Dokumen PDF

Yang Harus Dilakukan: Buka PDF yang disalin untuk membaca dan menulis.

```csharp
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
    using (Document doc = new Document(fs))
    {
        // Langkah selanjutnya akan dilakukan di sini
    }
}
```

 Penjelasan: Kami menggunakan`FileStream` untuk membuka file PDF kami.`Document` kelas dari Aspose.PDF memungkinkan kita untuk memanipulasi konten PDF.

### Langkah 4: Buat Kolom Tanda Tangan

Yang Harus Dilakukan: Tentukan bidang tanda tangan di PDF tempat tanda tangan akan ditempatkan.

```csharp
SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
```

 Penjelasan: Di sini kita membuat`SignatureField` pada halaman kedua (indeks halaman dimulai dari 1) PDF.`Rectangle` mendefinisikan posisi dan ukuran bidang tanda tangan.

### Langkah 5: Akses Penyimpanan Sertifikat Kartu Pintar

Yang Harus Dilakukan: Buka penyimpanan sertifikat untuk memilih sertifikat kartu pintar Anda.

```csharp
X509Store store = new X509Store(StoreLocation.CurrentUser);
store.Open(OpenFlags.ReadOnly);
```

Penjelasan: Kami mengakses penyimpanan sertifikat untuk pengguna saat ini. Di sinilah sertifikat kartu pintar Anda disimpan.

### Langkah 6: Pilih Sertifikat

Apa yang Harus Dilakukan: Meminta pengguna untuk memilih sertifikat dari toko.

```csharp
X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
```

Penjelasan: Baris ini membuka dialog untuk Anda memilih sertifikat. Anda dapat memilih sertifikat yang terkait dengan kartu pintar Anda.

### Langkah 7: Buat Tanda Tangan Eksternal

 Apa yang Harus Dilakukan: Buat contoh`ExternalSignature` menggunakan sertifikat yang dipilih.

```csharp
Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0])
{
    Authority = "Me",
    Reason = "Reason",
    ContactInfo = "Contact"
};
```

 Penjelasan: Kami menginisialisasi`ExternalSignature` dengan sertifikat yang dipilih. Anda juga dapat mengatur kewenangan, alasan penandatanganan, dan informasi kontak.

### Langkah 8: Tambahkan Bidang Tanda Tangan ke Dokumen

Apa yang Harus Dilakukan: Tambahkan kolom tanda tangan ke dokumen.

```csharp
field1.PartialName = "sig1";
doc.Form.Add(field1, 1);
```

Penjelasan: Kami memberi nama pada kolom tanda tangan dan menambahkannya ke halaman pertama dokumen. Ini mempersiapkan PDF untuk ditandatangani.

### Langkah 9: Tandatangani Dokumen

Apa yang Harus Dilakukan: Gunakan tanda tangan eksternal untuk menandatangani PDF.

```csharp
field1.Sign(externalSignature);
doc.Save();
```

Penjelasan: Baris ini menandatangani dokumen menggunakan tanda tangan eksternal dan menyimpan perubahan pada PDF. Dokumen Anda kini telah ditandatangani!

### Langkah 10: Verifikasi Tanda Tangan

Yang Harus Dilakukan: Periksa apakah tanda tangan valid.

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
{
    IList<string> sigNames = pdfSign.GetSignNames();
    for (int index = 0; index <= sigNames.Count - 1; index++)
    {
        if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
        {
            throw new ApplicationException("Not verified");
        }
    }
}
```

Penjelasan: Kami membuat sebuah instance dari`PdfFileSignature` untuk memverifikasi tanda tangan dalam dokumen. Jika tanda tangan tidak valid, pengecualian akan dikeluarkan.

## Kesimpulan

Selamat! Anda baru saja mempelajari cara menandatangani dokumen PDF menggunakan kartu pintar dan kolom tanda tangan dengan Aspose.PDF untuk .NET. Proses ini tidak hanya mengamankan dokumen Anda tetapi juga memastikan keasliannya, sehingga menjadikannya keterampilan penting dalam lanskap digital saat ini. Baik Anda menandatangani kontrak, faktur, atau dokumen penting lainnya, mengetahui cara menerapkan tanda tangan digital dapat menghemat waktu dan memberikan ketenangan pikiran.

## Pertanyaan yang Sering Diajukan

### Apa itu Aspose.PDF untuk .NET?
Aspose.PDF untuk .NET adalah pustaka hebat yang memungkinkan pengembang untuk membuat, memanipulasi, dan mengonversi dokumen PDF dalam aplikasi .NET.

### Apakah saya memerlukan kartu pintar untuk menandatangani PDF?
Ya, kartu pintar diperlukan untuk menandatangani PDF secara aman dengan sertifikat digital.

### Dapatkah saya menggunakan Aspose.PDF secara gratis?
 Aspose.PDF menawarkan uji coba gratis, yang dapat Anda unduh[Di Sini](https://releases.aspose.com/).

### Bagaimana cara memverifikasi PDF yang sudah ditandatangani?
 Anda dapat menggunakan`PdfFileSignature` kelas di Aspose.PDF untuk memverifikasi tanda tangan di dokumen PDF Anda.

### Di mana saya dapat menemukan dokumentasi lebih lanjut tentang Aspose.PDF?
 Anda dapat memeriksa[Dokumentasi Aspose.PDF](https://reference.aspose.com/pdf/net/) untuk rincian dan contoh lebih lanjut.