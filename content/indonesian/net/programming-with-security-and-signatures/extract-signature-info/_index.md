---
title: Ekstrak Info Tanda Tangan
linktitle: Ekstrak Info Tanda Tangan
second_title: Referensi API Aspose.PDF untuk .NET
description: Mengekstrak informasi tanda tangan menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 80
url: /id/net/programming-with-security-and-signatures/extract-signature-info/
---
Proses mengekstraksi informasi tanda tangan dari dokumen PDF dapat sangat berguna dalam berbagai skenario. Baik Anda perlu memvalidasi keaslian dokumen yang ditandatangani atau menganalisis sertifikat yang digunakan untuk tanda tangan, pustaka Aspose.PDF untuk .NET menyediakan solusi yang praktis. Dalam tutorial ini, kami akan memandu Anda melalui proses langkah demi langkah untuk mengekstraksi informasi tanda tangan menggunakan kode sumber C# yang disediakan.

## Persyaratan

Sebelum kita memulai, pastikan Anda memiliki prasyarat berikut:

1. Pengetahuan dasar tentang bahasa pemrograman C#.
2. Aspose.PDF untuk pustaka .NET yang terinstal di sistem Anda.
3. Dokumen PDF yang valid dengan satu atau lebih bidang tanda tangan.

Sekarang, mari kita masuk ke detail implementasinya.

## Langkah 1: Mengimpor Pustaka yang Diperlukan

 Untuk memulai, Anda perlu mengimpor pustaka yang diperlukan ke dalam proyek C# Anda. Dalam kasus ini, kita perlu mengimpor`Aspose.Pdf` Dan`System.IO` namespace. Hal ini dapat dilakukan dengan menambahkan kode berikut di awal berkas C# Anda:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Langkah 2: Mengatur Jalur Dokumen

Selanjutnya, Anda perlu mengatur jalur ke dokumen PDF tempat Anda ingin mengekstrak informasi tanda tangan. Ganti`"YOUR DOCUMENTS DIRECTORY"` dalam potongan kode berikut dengan jalur sebenarnya ke dokumen Anda:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

## Langkah 3: Mengekstrak Informasi Tanda Tangan

Sekarang, mari kita lanjutkan ke bagian utama kode tempat kita mengekstrak informasi tanda tangan dari dokumen PDF. Kita ulangi setiap kolom dalam formulir dokumen dan periksa apakah itu kolom tanda tangan. Jika kolom tanda tangan ditemukan, kita lanjutkan dengan mengekstrak sertifikat. Tambahkan cuplikan kode berikut:

```csharp
using (Document pdfDocument = new Document(input))
{
     foreach(Field field in pdfDocument.Form)
     {
         SignatureField sf = field as SignatureField;
         if (sf != null)
         {
             // Ekstrak sertifikatnya
             Stream cerStream = sf.ExtractCertificate();
             if (cerStream != null)
             {
                 using (cerStream)
                 {
                     byte[] bytes = new byte[cerStream.Length];
                     using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
                     {
                         cerStream.Read(bytes, 0, bytes.Length);
                         fs.Write(bytes, 0, bytes.Length);
                     }
                 }
             }
         }
     }
}
```

## Langkah 4: Mengekstrak Sertifikat

Pada langkah ini, kami mengekstrak sertifikat dari kolom tanda tangan dan menyimpannya sebagai file. Sertifikat yang diekstrak dapat dianalisis lebih lanjut atau digunakan untuk tujuan validasi. Cuplikan kode di bawah ini menunjukkan proses ekstraksi dan penyimpanan:

```csharp
Stream cerStream = sf.ExtractCertificate();
if (cerStream != null)
{
     using (cerStream)
     {
         byte[] bytes = new byte[cerStream.Length];
         using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
         {
             cerStream.Read(bytes, 0, bytes.Length);
             fs.Write(bytes, 0, bytes.Length);
         }
     }
}
```

## Langkah 5

: Menyimpan Sertifikat

Terakhir, kami menyimpan sertifikat yang diekstrak sebagai file. Dalam contoh ini, sertifikat disimpan dengan nama "input.cer" di direktori yang ditentukan. Anda dapat mengubah kode sesuai kebutuhan Anda. Berikut cuplikan kode untuk menyimpan sertifikat:

```csharp
using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
{
     fs.Write(bytes, 0, bytes.Length);
}
```

Selesai! Anda telah berhasil mengekstrak informasi tanda tangan menggunakan Aspose.PDF untuk .NET. Jangan ragu untuk mengintegrasikan kode ini ke dalam aplikasi Anda sendiri atau memodifikasinya sesuai kebutuhan Anda.

### Contoh kode sumber untuk Ekstrak Info Tanda Tangan menggunakan Aspose.PDF untuk .NET 
```csharp
try
{
	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string input = dataDir + "ExtractSignatureInfo.pdf";
	using (Document pdfDocument = new Document(input))
	{
		foreach (Field field in pdfDocument.Form)
		{
			SignatureField sf = field as SignatureField;
			if (sf != null)
			{
				Stream cerStream = sf.ExtractCertificate();
				if (cerStream != null)
				{
					using (cerStream)
					{
						byte[] bytes = new byte[cerStream.Length];
						using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
						{
							cerStream.Read(bytes, 0, bytes.Length);
							fs.Write(bytes, 0, bytes.Length);
						}
					}
				}
			}
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Kesimpulan

Dalam tutorial ini, kami membahas panduan langkah demi langkah tentang cara mengekstrak informasi tanda tangan dari dokumen PDF menggunakan pustaka Aspose.PDF for .NET. Kami membahas proses mengimpor pustaka yang diperlukan, mengatur jalur dokumen, mengekstrak informasi tanda tangan, mengekstrak sertifikat, dan menyimpannya ke dalam file. Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah mengambil detail tanda tangan dan mengolahnya sesuai kebutuhan.

### Pertanyaan yang Sering Diajukan

#### T: Mengapa saya perlu mengekstrak informasi tanda tangan dari dokumen PDF?

A: Mengekstrak informasi tanda tangan dari dokumen PDF berguna untuk memvalidasi keaslian dokumen yang ditandatangani dan menganalisis sertifikat yang digunakan untuk tanda tangan. Proses ini membantu memastikan integritas konten yang ditandatangani dan dapat menjadi penting untuk tujuan hukum dan keamanan.

#### T: Apa itu Aspose.PDF untuk .NET?

J: Aspose.PDF untuk .NET adalah pustaka yang memungkinkan pengembang untuk bekerja dengan dokumen PDF dalam aplikasi .NET. Pustaka ini menyediakan berbagai fitur untuk membuat, memodifikasi, dan berinteraksi dengan file PDF secara terprogram.

#### T: Apa saja prasyarat untuk mengekstrak informasi tanda tangan menggunakan Aspose.PDF untuk .NET?

A: Untuk mengekstrak informasi tanda tangan, Anda memerlukan pengetahuan dasar tentang bahasa pemrograman C#, pustaka Aspose.PDF untuk .NET yang terinstal di sistem Anda, dan dokumen PDF valid yang berisi satu atau beberapa bidang tanda tangan.

#### T: Bagaimana cara mengimpor pustaka yang diperlukan untuk proses ekstraksi?

A: Anda dapat mengimpor pustaka yang diperlukan dengan menambahkan`using` petunjuk untuk`Aspose.Pdf` Dan`System.IO` di awal berkas C# Anda. Arahan ini memungkinkan Anda menggunakan kelas dan metode yang diperlukan untuk mengekstrak informasi tanda tangan.

#### T: Bagaimana cara menentukan dokumen PDF untuk mengekstrak informasi tanda tangan?

 A: Anda dapat mengatur jalur ke dokumen PDF dengan mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan jalur sebenarnya ke dokumen Anda dalam cuplikan kode yang diberikan. Jalur ini digunakan untuk memuat dokumen PDF yang ingin Anda ekstrak informasi tanda tangannya.

#### T: Bagaimana proses mengekstrak informasi tanda tangan dari dokumen PDF?

A: Proses ekstraksi melibatkan pengulangan melalui kolom formulir dokumen PDF, memeriksa apakah setiap kolom merupakan kolom tanda tangan, dan jika ya, mengekstrak sertifikat terkait. Sertifikat yang diekstraksi dapat disimpan sebagai file untuk analisis atau validasi lebih lanjut.

#### T: Bagaimana sertifikat diekstrak dari bidang tanda tangan?

A: Sertifikat diekstraksi dari bidang tanda tangan menggunakan`ExtractCertificate()` metode yang disediakan oleh`SignatureField` kelas di Aspose.PDF untuk .NET. Metode ini mengembalikan aliran yang berisi data sertifikat.

#### T: Bagaimana cara menyimpan sertifikat yang diekstrak sebagai file?

 A: Anda dapat menyimpan sertifikat yang diekstrak sebagai file dengan membaca aliran sertifikat dan menulis isinya ke file menggunakan`FileStream` kelas. Kode yang diberikan dalam tutorial ini menunjukkan proses ini.

#### T: Dapatkah saya menggunakan sertifikat yang diekstrak ini untuk validasi tanda tangan?

A: Ya, sertifikat yang diekstrak dapat digunakan untuk validasi tanda tangan. Anda dapat menganalisis detail sertifikat dan memverifikasi keasliannya untuk memastikan integritas dokumen yang ditandatangani.

#### T: Bagaimana saya dapat mengintegrasikan kode ini ke dalam aplikasi saya sendiri?

J: Anda dapat mengintegrasikan kode yang diberikan ke dalam aplikasi C# Anda sendiri dengan mengikuti panduan langkah demi langkah. Ubah jalur dan nama file sesuai kebutuhan, dan masukkan kode ke dalam proyek Anda yang sudah ada.

#### T: Apakah ada fitur lain di Aspose.PDF untuk .NET yang terkait dengan manajemen tanda tangan?

A: Ya, Aspose.PDF untuk .NET menyediakan berbagai fitur untuk bekerja dengan tanda tangan digital, termasuk menandatangani dokumen, memverifikasi tanda tangan, dan menambahkan informasi stempel waktu. Anda dapat menjelajahi dokumentasi resmi untuk detail lebih lanjut tentang fitur-fitur ini.

#### T: Di mana saya dapat menemukan sumber daya tambahan untuk menggunakan Aspose.PDF untuk .NET?

 A: Untuk informasi lebih lanjut, tutorial, dan sumber daya tentang penggunaan Aspose.PDF untuk .NET,[Aspose.PDF untuk .NET](https://reference.aspose.com/pdf/net/).

#### T: Apakah mungkin untuk mengekstrak tanda tangan dari dokumen PDF yang terenkripsi?

J: Kemampuan untuk mengekstrak tanda tangan dari dokumen PDF terenkripsi mungkin bergantung pada pengaturan enkripsi dan izin dokumen tersebut. Anda mungkin perlu memastikan bahwa Anda memiliki izin yang diperlukan untuk mengakses dan mengekstrak informasi tanda tangan.

#### T: Dapatkah saya mengekstrak beberapa tanda tangan dari satu dokumen PDF?

A: Ya, Anda dapat mengubah kode yang diberikan untuk mengulang semua kolom tanda tangan dalam dokumen PDF dan mengekstrak informasi tanda tangan dari masing-masing kolom. Ini memungkinkan Anda untuk mengekstrak informasi tentang beberapa tanda tangan yang ada dalam dokumen.

#### T: Apa saja kasus penggunaan praktis untuk mengekstrak informasi tanda tangan?

A: Beberapa kasus penggunaan praktis untuk mengekstrak informasi tanda tangan termasuk memvalidasi keaslian dokumen yang ditandatangani secara digital, menganalisis rincian sertifikat untuk tujuan kepatuhan, dan memelihara catatan tanda tangan dan penanda tangan untuk tujuan audit.

#### T: Apakah ada pertimbangan hukum saat mengekstrak informasi tanda tangan?

A: Mengekstrak informasi tanda tangan dapat memiliki implikasi hukum, terutama saat menangani dokumen yang mengikat secara hukum. Pastikan Anda mematuhi peraturan dan hukum yang relevan terkait tanda tangan elektronik dan keaslian dokumen di wilayah hukum Anda.