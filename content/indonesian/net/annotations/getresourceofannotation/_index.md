---
title: Dapatkan Sumber Daya Anotasi
linktitle: Dapatkan Sumber Daya Anotasi
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara mengambil sumber daya anotasi menggunakan Aspose.PDF untuk .NET dengan panduan langkah demi langkah ini.
type: docs
weight: 90
url: /id/net/annotations/getresourceofannotation/
---
Contoh ini menunjukkan cara mendapatkan sumber anotasi dengan Aspose.PDF untuk .NET. Untuk mendapatkan sumber daya anotasi menggunakan Aspose.PDF untuk .NET, ikuti langkah-langkah berikut:

## Langkah 1: Tetapkan jalur direktori tempat dokumen berada.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Buka dokumen PDF yang berisi anotasi yang sumber dayanya ingin Anda dapatkan.

```csharp
Document doc = new Document(dataDir + "AddAnnotation.pdf");
```

## Langkah 3: Buat anotasi.

```csharp
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
```

## Langkah 4: Tambahkan anotasi ke halaman di dokumen.

```csharp
doc.Pages[1].Annotations.Add(sa);
```

## Langkah 5: Simpan dokumen.

```csharp
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Langkah 6: Buka dokumen yang dimodifikasi.

```csharp
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Langkah 7: Dapatkan tindakan anotasi.

```csharp
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
```

## Langkah 7: Dapatkan rendisi aksi.

```csharp
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
```

## Langkah 8: Dapatkan klip media.

```csharp
MediaClip clip = (rendition as MediaRendition).MediaClip;
```

## Langkah 9: Dapatkan spesifikasi file.

```csharp
FileSpecification data = (clip as MediaClipData).Data;
```

## Langkah 10: Baca data media.

```csharp
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
   ms.Write(buffer, 0, read);
}
```

## Langkah 11: Cetak nama rendisi dan operasi rendisi.

```csharp
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

Dengan mengikuti langkah-langkah ini, Anda bisa dengan mudah mendapatkan sumber anotasi dalam dokumen PDF menggunakan Aspose.PDF untuk .NET.

### Contoh kode sumber untuk Mendapatkan Sumber Anotasi menggunakan Aspose.PDF untuk .NET:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buka dokumen
Document doc = new Document(dataDir + "AddAnnotation.pdf");
//Buat anotasi
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
doc.Pages[1].Annotations.Add(sa);
// Simpan Dokumen
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
// Buka dokumen
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
//Dapatkan tindakan anotasi
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
//Dapatkan rendisi dari tindakan rendisi
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
// Klip Media
MediaClip clip = (rendition as MediaRendition).MediaClip;
FileSpecification data = (clip as MediaClipData).Data;
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
//Data media dapat diakses di FileSpecification.Contents
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
ms.Write(buffer, 0, read);
}
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

## Kesimpulan

Dalam tutorial ini, kita menjelajahi cara mendapatkan sumber daya anotasi tertentu dari dokumen PDF menggunakan Aspose.PDF untuk .NET. Dengan mengikuti panduan langkah demi langkah dan menggunakan kode sumber C# yang disediakan, pengembang dapat dengan mudah mengakses dan mengelola anotasi, termasuk anotasi rendisi, dalam dokumen PDF mereka.

### FAQ

#### T: Apa yang dimaksud dengan rendisi dalam konteks anotasi PDF?

J: Dalam konteks anotasi PDF, rendisi adalah presentasi konten multimedia. Memungkinkan untuk menyematkan multimedia, seperti audio atau video, dalam dokumen PDF. Anotasi rendisi menentukan media yang akan disajikan dan cara memainkannya.

#### T: Bisakah saya mendapatkan nama file media yang terkait dengan anotasi rendisi?

J: Ya, Anda bisa mendapatkan nama file media yang terkait dengan anotasi rendisi menggunakan Aspose.PDF untuk .NET. Nama file media dapat diakses melalui`FileSpecification` dari`MediaClip` obyek.

#### T: Dapatkah Aspose.PDF untuk .NET mengekstrak file media dari anotasi rendisi?

J: Ya, Aspose.PDF untuk .NET dapat mengekstrak data media dari anotasi rendisi, yang mencakup konten audio atau video, dan menyimpannya sebagai file terpisah.

#### T: Bagaimana cara mengakses data media anotasi rendisi?

 A: Data media anotasi rendisi dapat diakses melalui`FileSpecification.Contents` properti dari`MediaClipData` obyek.

#### T: Bisakah saya memodifikasi media yang terkait dengan anotasi rendisi menggunakan Aspose.PDF untuk .NET?

J: Aspose.PDF untuk .NET menyediakan metode untuk mengakses dan mengubah data media yang terkait dengan anotasi rendisi. Anda dapat memperbarui atau mengganti file media yang digunakan oleh anotasi rendisi.