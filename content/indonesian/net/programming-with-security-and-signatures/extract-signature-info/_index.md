---
title: Ekstrak Info Tanda Tangan
linktitle: Ekstrak Info Tanda Tangan
second_title: Aspose.PDF untuk Referensi .NET API
description: Mengekstraksi informasi tanda tangan menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 80
url: /id/net/programming-with-security-and-signatures/extract-signature-info/
---
Proses mengekstraksi informasi tanda tangan dari dokumen PDF bisa sangat berguna dalam berbagai skenario. Apakah Anda perlu memvalidasi keaslian dokumen yang ditandatangani atau menganalisis sertifikat yang digunakan untuk tanda tangan, pustaka Aspose.PDF untuk .NET memberikan solusi yang mudah. Dalam tutorial ini, kami akan memandu Anda melalui proses langkah demi langkah mengekstraksi informasi tanda tangan menggunakan kode sumber C# yang disediakan.

## Persyaratan

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

1. Pengetahuan dasar bahasa pemrograman C#.
2. Aspose.PDF untuk perpustakaan .NET diinstal pada sistem Anda.
3. Dokumen PDF yang valid dengan satu atau lebih bidang tanda tangan.

Sekarang, mari selami detail penerapannya.

## Langkah 1: Mengimpor Perpustakaan yang Diperlukan

 Untuk memulai, Anda perlu mengimpor perpustakaan yang diperlukan ke proyek C# Anda. Dalam hal ini, kita perlu mengimpor`Aspose.Pdf` Dan`System.IO` ruang nama. Ini dapat dilakukan dengan menambahkan kode berikut di awal file C# Anda:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Langkah 2: Mengatur Jalur Dokumen

Selanjutnya, Anda perlu mengatur jalur ke dokumen PDF yang ingin Anda ekstrak informasi tanda tangannya. Mengganti`"YOUR DOCUMENTS DIRECTORY"` dalam cuplikan kode berikut dengan jalur sebenarnya ke dokumen Anda:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

## Langkah 3: Mengekstraksi Informasi Tanda Tangan

Sekarang, mari beralih ke bagian utama kode tempat kita mengekstrak informasi tanda tangan dari dokumen PDF. Kami mengulangi setiap bidang dalam formulir dokumen dan memeriksa apakah itu merupakan bidang tanda tangan. Jika kolom tanda tangan ditemukan, kami melanjutkan dengan mengekstraksi sertifikat. Tambahkan cuplikan kode berikut:

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

Pada langkah ini, kami mengekstrak sertifikat dari kolom tanda tangan dan menyimpannya sebagai file. Sertifikat yang diekstraksi dapat dianalisis lebih lanjut atau digunakan untuk tujuan validasi. Cuplikan kode di bawah ini menunjukkan proses ekstraksi dan penyimpanan:

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

Terakhir, kami menyimpan sertifikat yang diekstrak sebagai file. Dalam contoh ini, sertifikat disimpan dengan nama "input.cer" di direktori yang ditentukan. Anda dapat memodifikasi kode sesuai kebutuhan Anda. Berikut cuplikan kode untuk menyimpan sertifikat:

```csharp
using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
{
     fs.Write(bytes, 0, bytes.Length);
}
```

Itu dia! Anda telah berhasil mengekstrak informasi tanda tangan menggunakan Aspose.PDF untuk .NET. Jangan ragu untuk mengintegrasikan kode ini ke dalam aplikasi Anda sendiri atau memodifikasinya sesuai kebutuhan Anda.

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

Dalam tutorial ini, kita mempelajari panduan langkah demi langkah tentang cara mengekstrak informasi tanda tangan dari dokumen PDF menggunakan pustaka Aspose.PDF untuk .NET. Kami membahas proses mengimpor perpustakaan yang diperlukan, mengatur jalur dokumen, mengekstrak informasi tanda tangan, mengekstrak sertifikat, dan menyimpannya ke file. Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah mengambil detail tanda tangan dan menggunakannya sesuai kebutuhan.

### FAQ

#### T: Mengapa saya perlu mengekstrak informasi tanda tangan dari dokumen PDF?

J: Mengekstraksi informasi tanda tangan dari dokumen PDF berguna untuk memvalidasi keaslian dokumen yang ditandatangani dan menganalisis sertifikat yang digunakan untuk tanda tangan. Proses ini membantu memastikan integritas konten yang ditandatangani dan penting untuk tujuan hukum dan keamanan.

#### T: Apa itu Aspose.PDF untuk .NET?

J: Aspose.PDF untuk .NET adalah perpustakaan yang memungkinkan pengembang bekerja dengan dokumen PDF di aplikasi .NET. Ini menyediakan berbagai fitur untuk membuat, memodifikasi, dan berinteraksi dengan file PDF secara terprogram.

#### T: Apa saja prasyarat untuk mengekstrak informasi tanda tangan menggunakan Aspose.PDF untuk .NET?

J: Untuk mengekstrak informasi tanda tangan, Anda memerlukan pengetahuan dasar tentang bahasa pemrograman C#, pustaka Aspose.PDF untuk .NET yang diinstal di sistem Anda, dan dokumen PDF valid yang berisi satu atau lebih bidang tanda tangan.

#### T: Bagaimana cara mengimpor perpustakaan yang diperlukan untuk proses ekstraksi?

J: Anda dapat mengimpor perpustakaan yang diperlukan dengan menambahkan`using` arahan untuk`Aspose.Pdf` Dan`System.IO` di awal file C# Anda. Arahan ini memungkinkan Anda untuk menggunakan kelas dan metode yang diperlukan untuk mengekstrak informasi tanda tangan.

#### T: Bagaimana cara menentukan dokumen PDF untuk mengekstrak informasi tanda tangan?

 A: Anda dapat mengatur jalur ke dokumen PDF dengan mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan jalur sebenarnya ke dokumen Anda dalam cuplikan kode yang disediakan. Jalur ini digunakan untuk memuat dokumen PDF yang informasi tanda tangannya ingin Anda ekstrak.

#### T: Bagaimana proses mengekstraksi informasi tanda tangan dari dokumen PDF?

J: Proses ekstraksi melibatkan iterasi melalui kolom formulir dokumen PDF, memeriksa apakah setiap kolom merupakan kolom tanda tangan, dan jika demikian, mengekstraksi sertifikat terkait. Sertifikat yang diekstraksi dapat disimpan sebagai file untuk analisis atau validasi lebih lanjut.

#### T: Bagaimana cara sertifikat diambil dari bidang tanda tangan?

J: Sertifikat diekstraksi dari bidang tanda tangan menggunakan`ExtractCertificate()` metode yang disediakan oleh`SignatureField` kelas di Aspose.PDF untuk .NET. Metode ini mengembalikan aliran yang berisi data sertifikat.

#### T: Bagaimana cara menyimpan sertifikat yang diekstrak sebagai file?

 J: Anda dapat menyimpan sertifikat yang diekstrak sebagai file dengan membaca aliran sertifikat dan menulis isinya ke file menggunakan`FileStream` kelas. Kode yang disediakan dalam tutorial menunjukkan proses ini.

#### T: Dapatkah saya menggunakan sertifikat yang diekstraksi ini untuk validasi tanda tangan?

A: Ya, sertifikat yang diekstrak dapat digunakan untuk validasi tanda tangan. Anda dapat menganalisis rincian sertifikat dan memverifikasi keasliannya untuk memastikan integritas dokumen yang ditandatangani.

#### T: Bagaimana cara mengintegrasikan kode ini ke dalam aplikasi saya sendiri?

J: Anda dapat mengintegrasikan kode yang disediakan ke dalam aplikasi C# Anda sendiri dengan mengikuti panduan langkah demi langkah. Ubah jalur dan nama file sesuai kebutuhan, dan sertakan kode tersebut ke dalam proyek Anda yang sudah ada.

#### T: Apakah ada fitur lain di Aspose.PDF untuk .NET yang terkait dengan manajemen tanda tangan?

J: Ya, Aspose.PDF untuk .NET menyediakan serangkaian fitur untuk bekerja dengan tanda tangan digital, termasuk menandatangani dokumen, memverifikasi tanda tangan, dan menambahkan informasi stempel waktu. Anda dapat menjelajahi dokumentasi resmi untuk rincian lebih lanjut tentang fitur-fitur ini.

#### T: Di mana saya dapat menemukan sumber daya tambahan untuk menggunakan Aspose.PDF untuk .NET?

 A: Untuk informasi lebih lanjut, tutorial, dan sumber daya tentang penggunaan Aspose.PDF untuk .NET,[Aspose.PDF untuk .NET](https://reference.aspose.com/pdf/net/).

#### T: Apakah mungkin mengekstrak tanda tangan dari dokumen PDF terenkripsi?

J: Kemampuan untuk mengekstrak tanda tangan dari dokumen PDF terenkripsi mungkin bergantung pada pengaturan enkripsi dan izin dokumen. Anda mungkin perlu memastikan bahwa Anda memiliki izin yang diperlukan untuk mengakses dan mengekstrak informasi tanda tangan.

#### T: Dapatkah saya mengekstrak banyak tanda tangan dari satu dokumen PDF?

J: Ya, Anda dapat memodifikasi kode yang disediakan untuk mengulangi semua bidang tanda tangan di dokumen PDF dan mengekstrak informasi tanda tangan dari masing-masing bidang. Ini memungkinkan Anda mengekstrak informasi tentang banyak tanda tangan yang ada dalam dokumen.

#### T: Apa saja kasus penggunaan praktis untuk mengekstrak informasi tanda tangan?

J: Beberapa kasus penggunaan praktis untuk mengekstrak informasi tanda tangan termasuk memvalidasi keaslian dokumen yang ditandatangani secara digital, menganalisis rincian sertifikat untuk tujuan kepatuhan, dan memelihara catatan tanda tangan dan penandatangan untuk tujuan audit.

#### T: Apakah ada pertimbangan hukum saat mengambil informasi tanda tangan?

J: Mengekstraksi informasi tanda tangan mungkin mempunyai implikasi hukum, terutama ketika menangani dokumen yang mengikat secara hukum. Pastikan Anda mematuhi peraturan dan undang-undang terkait dengan tanda tangan elektronik dan keaslian dokumen di yurisdiksi Anda.