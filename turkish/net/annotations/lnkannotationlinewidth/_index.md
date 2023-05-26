---
title: lnk Ek Açıklama Satır Genişliği
linktitle: lnk Ek Açıklama Satır Genişliği
second_title: Aspose.PDF for .NET API Referansı
description: Bu makale, Aspose.PDF for .NET kullanarak lnk Açıklamanın çizgi genişliğini ayarlamak için adım adım bir kılavuz sunmaktadır.
type: docs
weight: 110
url: /tr/net/annotations/lnkannotationlinewidth/
---
Aspose.PDF, .NET uygulamalarında PDF dosyalarıyla çalışmak için güçlü ve yaygın olarak kullanılan bir araçtır. Sayfalara açıklamalar ekleme yeteneği de dahil olmak üzere PDF dosyalarını oluşturmak, düzenlemek ve değiştirmek için çeşitli özellikler sağlar. Bu öğreticide, Aspose.PDF for .NET kullanarak bir bağlantı notunun çizgi genişliğini nasıl ayarlayacağımızı açıklayacağız.

Bu ön koşullara sahip olduğunuzda, Visual Studio'da yeni bir konsol uygulama projesi oluşturun. Ardından, Solution Explorer'da projeye sağ tıklayarak, "NuGet Paketlerini Yönet"i seçerek ve NuGet Paket Yöneticisinde "Aspose.PDF"yi arayarak Aspose.PDF for .NET kitaplığına bir referans ekleyin.

Bir PDF belgesine bağlantı notu eklemek için şu adımları izleyin:

##  Yeni bir tane oluştur`Document` object.
```csharp
Document doc = new Document();
```
## Belgeye yeni bir sayfa ekleyin.
```csharp
doc.Pages.Add();
```
##  listesi oluştur`Point` arrays that represent the ink gesture for the annotation.
```csharp
IList<Point[]> inkList = new List<Point[]>();
```
##  Yeni bir tane oluştur`LineInfo` object that defines the properties of the ink gesture.
```csharp
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
```
##  Yeni bir tane oluştur`Aspose.Pdf.Point` array that represents the gesture from the `LineInfo` object.
```csharp
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}
```
## Hareketi mürekkep hareketleri listesine ekleyin.
```csharp
inkList.Add(gesture);
```
##  Yeni bir tane oluştur`InkAnnotation` object that represents the link annotation.
```csharp
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
```
## Ek açıklamanın konusunu ve başlığını ayarlayın.
```csharp
a1.Subject = "Test";
a1.Title = "Title";
```
## Ek açıklamanın rengini ayarlayın.
```csharp
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```
##  Yeni bir tane oluştur`Border` object that defines the properties of the annotation's border.
```csharp
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
```
## Ek açıklamayı sayfaya ekleyin.
```csharp
doc.Pages[1].Annotations.Add(a1);
```
## Belgeyi bir dosyaya kaydedin.
```c// Save output file
doc.Save(dataDir);


```
### Örnek, Aspose.PDF for .NET ile lnk Annotation Line Width'i göstermektedir.

```csharp


// Belgeler dizininin yolu.
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
// Çıktı dosyasını kaydet
doc.Save(dataDir);


```
