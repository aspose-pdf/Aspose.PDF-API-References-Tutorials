---
title: Ekstrak Teks yang Disorot Dalam File PDF
linktitle: Ekstrak Teks yang Disorot Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara mengekstrak teks yang disorot dalam file PDF menggunakan Aspose.PDF untuk .NET dengan panduan langkah demi langkah ini.
type: docs
weight: 60
url: /id/net/annotations/extracthighlightedtext/
---
Untuk mengekstrak teks yang disorot dalam file PDF, Anda dapat menggunakan Aspose.PDF untuk .NET API. API ini menyediakan cara sederhana untuk mengambil semua teks yang telah disorot dalam dokumen.

## Langkah 1: Muat dokumen PDF

 Langkah pertama dalam mengekstrak teks yang disorot dalam file PDF adalah memuat dokumen menggunakan Aspose.PDF untuk .NET API. Anda dapat melakukan ini dengan membuat instance baru dari`Document` kelas dan meneruskan jalur ke dokumen PDF sebagai parameter. 

```csharp
// Jalur ke direktori dokumen.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

## Langkah 2: Ulangi semua anotasi

 Langkah selanjutnya adalah mengulang semua anotasi dalam dokumen PDF. Anda dapat melakukan ini menggunakan a`foreach` lingkaran, seperti ini:

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	// Kode ada di sini
}
```

## Langkah 3: Filter anotasi markup teks

 Di dalam`foreach` loop, Anda perlu memfilter semua anotasi yang bukan anotasi markup teks. Anda dapat melakukan ini dengan memeriksa apakah anotasi tersebut merupakan turunan dari`TextMarkupAnnotation` kelas.

```csharp
if (annotation is TextMarkupAnnotation)
{
	// Kode ada di sini
}
```

## Langkah 4: Ambil fragmen teks yang disorot

 Setelah Anda memfilter semua anotasi markup teks, Anda dapat mengambil fragmen teks yang disorot untuk setiap anotasi. Anda dapat melakukannya dengan menelepon`GetMarkedTextFragments()` metode pada`TextMarkupAnnotation` obyek.

```csharp
TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
```

## Langkah 5: Tampilkan teks yang disorot

 Terakhir, Anda dapat menampilkan teks yang disorot kepada pengguna. Anda dapat melakukan ini dengan mengulang masing-masing`TextFragment` objek di`TextFragmentCollection` dan menelepon`Text` Properti.

```csharp
foreach (TextFragment tf in collection)
{
	Console.WriteLine(tf.Text);
}
```

### Contoh kode sumber untuk Ekstrak Teks yang Disorot menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");

foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	if (annotation is TextMarkupAnnotation)
	{
		TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
		TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
		foreach (TextFragment tf in collection)
		{
			Console.WriteLine(tf.Text);
		}
	}
}
```

## Kesimpulan

Dalam tutorial ini, kita menjelajahi cara mengekstrak teks yang disorot dari dokumen PDF menggunakan Aspose.PDF untuk .NET. Dengan mengikuti panduan langkah demi langkah dan menggunakan kode sumber C# yang disediakan, pengembang dapat dengan mudah mengekstrak dan mengelola teks yang disorot dalam dokumen PDF mereka.

### FAQ untuk mengekstrak teks yang disorot dalam file PDF

#### T: Apa yang dimaksud dengan anotasi markup teks dalam dokumen PDF?

J: Anotasi markup teks adalah anotasi yang menyorot atau menandai teks tertentu dalam dokumen PDF. Contoh anotasi markup teks mencakup sorotan, garis bawah, dan coretan.

#### T: Bisakah saya mengekstrak teks dari jenis anotasi lain menggunakan Aspose.PDF untuk .NET?

J: Ya, Aspose.PDF untuk .NET menyediakan berbagai metode untuk mengekstrak teks dari berbagai jenis anotasi, termasuk anotasi markup teks, anotasi teks bebas, dan banyak lagi.

#### T: Apakah Aspose.PDF untuk .NET mendukung ekstraksi teks dari file PDF yang dilindungi kata sandi?

 J: Ya, Aspose.PDF untuk .NET mendukung ekstraksi teks dari file PDF yang dilindungi kata sandi. Anda harus memberikan kata sandi yang benar saat memuat dokumen PDF menggunakan`Document` kelas.

#### T: Dapatkah saya memfilter teks yang disorot berdasarkan kriteria lain, seperti warna atau penulis?

J: Ya, Anda dapat memfilter teks yang disorot berdasarkan kriteria lain, seperti warna, penulis, atau tanggal pembuatan. Aspose.PDF untuk .NET menyediakan metode untuk mengakses dan memfilter anotasi berdasarkan propertinya.

#### T: Apakah mungkin untuk menyimpan teks yang diekstraksi dan disorot ke file terpisah?

J: Ya, Anda dapat menyimpan teks yang disorot yang diekstrak ke file terpisah atau menyimpannya dalam struktur data untuk diproses atau dianalisis lebih lanjut.
