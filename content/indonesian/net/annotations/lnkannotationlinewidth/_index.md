---
title: lnk Lebar Garis Anotasi
linktitle: lnk Lebar Garis Anotasi
second_title: Aspose.PDF untuk Referensi .NET API
description: Artikel ini memberikan panduan langkah demi langkah untuk mengatur lebar garis Anotasi lnk menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 110
url: /id/net/annotations/lnkannotationlinewidth/
---
Aspose.PDF adalah alat yang ampuh dan banyak digunakan untuk bekerja dengan file PDF di aplikasi .NET. Ini menyediakan berbagai fitur untuk membuat, mengedit, dan memanipulasi file PDF, termasuk kemampuan untuk menambahkan anotasi ke halaman. Dalam tutorial ini, kami akan menjelaskan cara mengatur lebar garis anotasi tautan menggunakan Aspose.PDF untuk .NET.

Setelah Anda memiliki prasyarat ini, buat proyek aplikasi konsol baru di Visual Studio. Kemudian, tambahkan referensi ke perpustakaan Aspose.PDF untuk .NET dengan mengklik kanan proyek di Solution Explorer, memilih "Kelola Paket NuGet," dan mencari "Aspose.PDF" di Manajer Paket NuGet.

Untuk menambahkan anotasi lnk ke dokumen PDF, ikuti langkah-langkah berikut:

##  Langkah 1: Buat yang baru`Document` object.
```csharp
Document doc = new Document();
```
## Langkah 2: Tambahkan halaman baru ke dokumen.
```csharp
doc.Pages.Add();
```
##  Langkah 3: Buat daftar`Point` arrays that represent the ink gesture for the annotation.
```csharp
IList<Point[]> inkList = new List<Point[]>();
```
##  Langkah 4: Buat yang baru`LineInfo` object that defines the properties of the ink gesture.
```csharp
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
```
##  Langkah 5: Buat yang baru`Aspose.Pdf.Point` array that represents the gesture from the `LineInfo` object.
```csharp
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}
```
## Langkah 6: Tambahkan isyarat ke daftar isyarat tinta.
```csharp
inkList.Add(gesture);
```
##  Langkah 7: Buat yang baru`InkAnnotation` object that represents the link annotation.
```csharp
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
```
## Langkah 8: Tetapkan subjek dan judul anotasi.
```csharp
a1.Subject = "Test";
a1.Title = "Title";
```
## Langkah 9: Atur warna anotasi.
```csharp
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```
##  Langkah 10: Buat yang baru`Border` object that defines the properties of the annotation's border.
```csharp
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
```
## Langkah 11: Tambahkan anotasi ke halaman.
```csharp
doc.Pages[1].Annotations.Add(a1);
```
## Langkah 12: Simpan dokumen ke file.
```csharp
// Simpan file keluaran
doc.Save(dataDir);


```
### Contoh menunjukkan Lebar Garis Anotasi lnk dengan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);

dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
// Simpan file keluaran
doc.Save(dataDir);
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara mengatur lebar garis anotasi tautan dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Aspose.PDF untuk .NET menyediakan berbagai alat dan fitur untuk bekerja dengan dokumen PDF, termasuk kemampuan untuk membuat dan menyesuaikan anotasi tautan. Dengan mengikuti panduan langkah demi langkah dan menggunakan kode sumber C# yang disediakan, pengembang dapat dengan mudah menambahkan tautan interaktif ke dokumen PDF mereka, sehingga meningkatkan pengalaman pengguna dan interaktivitas aplikasi mereka. Aspose.PDF untuk .NET adalah perpustakaan serbaguna yang memberdayakan pengembang .NET untuk bekerja dengan file PDF secara efisien dan efektif.

### FAQ

#### T: Apa yang dimaksud dengan anotasi tautan dalam dokumen PDF?

J: Anotasi tautan dalam dokumen PDF adalah elemen interaktif yang memungkinkan Anda membuat hyperlink atau tindakan yang mengarahkan pengguna ke lokasi lain dalam dokumen yang sama, situs web eksternal, atau dokumen PDF berbeda.

#### T: Bagaimana cara mengatur lebar garis anotasi tautan menggunakan Aspose.PDF untuk .NET?

J: Untuk mengatur lebar garis anotasi tautan menggunakan Aspose.PDF untuk .NET, Anda dapat membuat`InkAnnotation` objek dan tentukan properti lebar garis.

#### T: Properti apa yang dapat dikustomisasi untuk anotasi tautan di Aspose.PDF untuk .NET?

J: Anda dapat menyesuaikan berbagai properti anotasi tautan di Aspose.PDF untuk .NET, seperti lokasi, ukuran, warna, properti batas (lebar, gaya, pola garis putus-putus, dan efek), subjek, judul, dan visibilitas.

#### T: Dapatkah saya membuat anotasi tautan yang berisi beberapa gerakan tinta?

 J: Ya, Anda dapat membuat anotasi tautan yang berisi beberapa gerakan tinta dengan menambahkan beberapa gerakan tinta`Point` array ke`InkAnnotation` obyek.

#### T: Bagaimana cara menambahkan anotasi tautan ke halaman tertentu pada dokumen PDF?

 J: Untuk menambahkan anotasi tautan ke halaman tertentu pada dokumen PDF, Anda perlu menentukan nomor halaman saat membuat`InkAnnotation` obyek. Misalnya,`new InkAnnotation(doc.Pages[1], ...)` menambahkan anotasi tautan ke halaman pertama.