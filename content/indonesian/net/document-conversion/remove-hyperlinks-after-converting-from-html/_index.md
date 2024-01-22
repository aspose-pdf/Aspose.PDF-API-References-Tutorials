---
title: Hapus Hyperlink Setelah Mengonversi Dari Html
linktitle: Hapus Hyperlink Setelah Mengonversi Dari Html
second_title: Aspose.PDF untuk Referensi .NET API
description: Panduan langkah demi langkah untuk menghapus hyperlink setelah mengonversi HTML ke PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 250
url: /id/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
Dalam tutorial ini, kami akan memandu Anda melalui proses menghapus hyperlink dari file PDF yang dihasilkan dari file HTML menggunakan Aspose.PDF untuk .NET. Hyperlink adalah tautan yang dapat diklik dan dapat mengalihkan ke halaman atau situs web lain. Dengan mengikuti langkah-langkah di bawah ini, Anda akan dapat menghapus hyperlink dari file PDF yang dihasilkan.

## Prasyarat
Sebelum memulai, pastikan Anda memenuhi prasyarat berikut:

- Pengetahuan dasar tentang bahasa pemrograman C#.
- Pustaka Aspose.PDF untuk .NET diinstal di sistem Anda.
- Lingkungan pengembangan seperti Visual Studio.

## Langkah 1: Memuat file HTML dan menghapus hyperlink
Pada langkah ini, kita akan memuat file HTML dan menghapus hyperlink dari dokumen PDF yang dihasilkan. Gunakan kode berikut:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Muat file HTML menggunakan opsi pemuatan HTML
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());

// Telusuri anotasi halaman pertama dokumen
foreach(Annotation a in doc.Pages[1].Annotations)
{
     // Periksa apakah anotasinya berupa tautan
     if (a.AnnotationType == AnnotationType.Link)
     {
         LinkAnnotation the = (LinkAnnotation)a;
        
         // Periksa apakah tindakannya bertipe GoToURIAction
         if (the.Action is GoToURIAction)
         {
             GoToURIAction gta = (GoToURIAction)the.Action;
             gta.URI = "";
            
             // Gunakan penyerap fragmen teks untuk menemukan fragmen teks yang cocok
             TextFragmentAbsorber tfa = new TextFragmentAbsorber();
             tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
             doc.Pages[a.PageIndex].Accept(tfa);
            
             // Ulangi fragmen teks yang cocok dan hapus atribut dari hyperlink
             foreach(TextFragment tf in tfa.TextFragments)
             {
                 tf.TextState.Underline = false;
                 tf.TextState.ForegroundColor = Color.Black;
             }
         }
        
         // Hapus anotasi dari halaman
         doc.Pages[a.PageIndex].Annotations.Delete(a);
     }
}
```

 Pastikan untuk mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan direktori sebenarnya tempat file HTML Anda berada.

## Langkah 2: Menyimpan file PDF yang dihasilkan
Terakhir, kami akan menyimpan file PDF yang dihasilkan tanpa hyperlink. Gunakan kode berikut:

```csharp
// Simpan file PDF yang dihasilkan
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 Kode di atas menyimpan file PDF yang dihasilkan dengan nama file`"RemoveHyperlinksFromText_out.pdf"`.

### Contoh kode sumber untuk Menghapus Hyperlink Setelah Mengonversi Dari Html menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
doc.Save(new MemoryStream());
foreach (Annotation a in doc.Pages[1].Annotations)
{
	if (a.AnnotationType == AnnotationType.Link)
	{
		LinkAnnotation la = (LinkAnnotation)a;
		if (la.Action is GoToURIAction)
		{
			GoToURIAction gta = (GoToURIAction)la.Action;
			gta.URI = "";
			TextFragmentAbsorber tfa = new TextFragmentAbsorber();
			tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
			doc.Pages[a.PageIndex].Accept(tfa);
			foreach (TextFragment tf in tfa.TextFragments)
			{
				tf.TextState.Underline = false;
				tf.TextState.ForegroundColor = Color.Black;
			}
		}
		doc.Pages[a.PageIndex].Annotations.Delete(a);
	}
}
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

## Kesimpulan
Dalam tutorial ini, kami membahas proses langkah demi langkah menghapus hyperlink dari file PDF yang dihasilkan dari file HTML menggunakan Aspose.PDF untuk .NET. Dengan mengikuti petunjuk yang dijelaskan di atas, Anda akan berhasil menghapus hyperlink dari file PDF yang dihasilkan.

### FAQ

#### T: Apa itu Aspose.PDF untuk .NET?

J: Aspose.PDF untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang bekerja dengan dokumen PDF dalam aplikasi C#. Ia menawarkan berbagai fungsi, termasuk kemampuan untuk mengkonversi file HTML ke PDF dan memanipulasi konten PDF.

#### T: Mengapa saya ingin menghapus hyperlink dari file PDF?

J: Ada berbagai alasan untuk menghapus hyperlink dari file PDF. Misalnya, Anda mungkin ingin menghilangkan tautan eksternal untuk tujuan pencetakan atau pengarsipan atau memastikan bahwa konten PDF tidak dapat dinavigasi melalui hyperlink.

#### T: Bagaimana cara memuat file HTML dan menghapus hyperlink menggunakan Aspose.PDF untuk .NET?

 J: Untuk memuat file HTML dan menghapus hyperlink, Anda dapat menggunakan Aspose.PDF untuk .NET`HtmlLoadOptions` kelas. Ulangi anotasi halaman PDF untuk menemukan anotasi tautan dan ubah atributnya.

#### T: Bisakah saya menyesuaikan nama file keluaran untuk PDF yang dihasilkan?

J: Ya, Anda dapat menyesuaikan nama file keluaran untuk file PDF yang dihasilkan dengan memodifikasi kode yang menyimpan dokumen PDF. Cukup ubah nama file yang diinginkan di`doc.Save()` metode.

#### T: Apakah mungkin untuk menghapus hyperlink secara selektif berdasarkan kriteria tertentu?

J: Ya, Anda dapat menghapus hyperlink secara selektif berdasarkan kriteria tertentu. Misalnya, Anda dapat memilih untuk hanya menghapus tautan eksternal atau tautan yang mengarah ke URL tertentu.