---
title: lnk Ek Açıklaması Ekle
linktitle: lnk Ek Açıklaması Ekle
second_title: .NET API Referansı için Aspose.PDF
description: Adım adım kılavuz ve tam kaynak koduyla Aspose.PDF for .NET kullanarak C#'ta PDF belgelerine Mürekkep Açıklaması özelliğini nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 20
url: /tr/net/annotations/addlnkannotation/
---
Aspose.PDF for .NET, geliştiricilerin çeşitli PDF işlemlerini gerçekleştirmesine olanak tanıyan güçlü bir kütüphanedir. Böyle bir işlem, PDF belgelerine Mürekkep Açıklaması eklemektir. Bu makalede, Aspose.PDF for .NET kullanarak Mürekkep Açıklaması eklemek için C# kaynak kodunu açıklayan adım adım bir kılavuz sunacağız. Başlayalım!

## Aspose.PDF for .NET'in Mürekkep Açıklaması Özelliğini Anlamak

C# kaynak koduna dalmadan önce, Mürekkep Açıklamasının ne olduğunu ve kullanımlarını anlayalım.

Mürekkep Açıklaması, PDF belgelerine serbest biçimli mürekkep açıklamaları çizmenin bir yoludur. Bir kalem veya fare ile açıklamalar oluşturmanıza olanak tanır. Bu özellik diyagramlar, çizimler veya diğer türde açıklamaları çizmeniz gereken durumlarda kullanışlıdır.

## Adım 1: Yeni Bir Belge Oluşturma

Bir PDF belgesine Mürekkep Açıklaması eklemenin ilk adımı, Belge sınıfının yeni bir örneğini oluşturmaktır. Bu, aşağıdaki kod parçacığı kullanılarak elde edilir:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
Page pdfPage = doc.Pages.Add();
```

Burada Document sınıfının yeni bir örneğini oluşturup ona yeni bir sayfa ekliyoruz.

## Adım 2: Mürekkep Açıklaması Oluşturma

Bir sonraki adım InkAnnotation sınıfının bir örneğini oluşturmaktır. Bu, aşağıdaki kod parçacığı kullanılarak yapılır:

```csharp
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(stroke.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);
```

Burada öncelikle System.Drawing.Rectangle sınıfını kullanarak bir dikdörtgen oluşturuyoruz ve bunu FromRect yöntemini kullanarak Aspose.Pdf.Rectangle'a dönüştürüyoruz. Daha sonra dikdörtgeni, noktaların listesini ve açıklamanın eklendiği sayfayı kullanarak InkAnnotation sınıfının bir örneğini oluştururuz.

Daha sonra InkAnnotation'ın başlık, renk, kapak stili, kenarlık ve opaklık gibi çeşitli özelliklerini ayarlıyoruz. Son olarak Annotations.Add metodunu kullanarak açıklamayı sayfaya ekliyoruz.

## Adım 3: Belgeyi Kaydetme

Son adım, PDF belgesini Mürekkep Açıklaması eklenmiş olarak kaydetmektir. Bu, aşağıdaki kod parçacığı kullanılarak elde edilir:

```csharp
dataDir = dataDir + "AddlnkAnnotation_out.pdf";
doc.Save(dataDir);
```

Burada çıktı dosyası adını veri dizinine birleştirip Save yöntemini kullanarak belgeyi kaydediyoruz.

### Aspose.PDF for .NET kullanarak Mürekkep Açıklaması Eklemek için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DATA DIRECTORY";


Document doc = new Document();
Page pdfPage = doc.Pages.Add();
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(stroke.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);

dataDir = dataDir + "AddlnkAnnotation_out.pdf";
// Çıkış dosyasını kaydet
doc.Save(dataDir);
```

## Çözüm

Bu eğitimde Aspose.PDF for .NET kullanarak bir PDF belgesine Mürekkep Açıklamalarının nasıl ekleneceğini araştırdık. Geliştiriciler, sağlanan adım adım kılavuzu ve C# kaynak kodunu takip ederek, Mürekkep Açıklaması işlevini PDF işleme uygulamalarında kolayca uygulayabilirler.

### SSS'ler

#### S: PDF belgesindeki Mürekkep Açıklaması nedir?

C: PDF belgesindeki Mürekkep Açıklaması, kullanıcıların kalem veya fare kullanarak serbest biçimli mürekkep açıklamaları çizmesine olanak tanır. PDF'ye elle çizilmiş çizimler, diyagramlar veya diğer serbest el açıklamalarını eklemek için yaygın olarak kullanılır.

#### S: Mürekkep Açıklamasının görünümünü özelleştirebilir miyim?

C: Evet, Aspose.PDF for .NET, Mürekkep Açıklamasının görünümünü özelleştirmek için renk, opaklık, kapak stili, kenarlık genişliği ve daha fazlası gibi çeşitli özellikler sağlar. Geliştiriciler bu özellikleri kendi özel gereksinimlerini karşılayacak şekilde ayarlayabilir.

#### S: Tek bir PDF sayfasına birden fazla Mürekkep Açıklaması eklemek mümkün mü?

C: Evet, Aspose.PDF for .NET'i kullanarak tek bir PDF sayfasına birden fazla Mürekkep Açıklaması ekleyebilirsiniz. Her Mürekkep Açıklamasının kendine ait noktaları ve özelleştirilmiş görünümü olabilir.

#### S: Mevcut PDF belgelerine Mürekkep Açıklamaları ekleyebilir miyim?

C: Evet, Aspose.PDF for .NET, hem yeni oluşturulan PDF belgelerine hem de mevcut PDF dosyalarına Mürekkep Açıklamaları eklemenizi sağlar. Mevcut bir PDF'yi açabilir, Mürekkep Açıklamaları ekleyebilir ve güncellenen belgeyi kaydedebilirsiniz.

#### S: PDF belgelerindeki Mürekkep Açıklamalarının yaygın kullanım durumları nelerdir?

C: Mürekkep Açıklamaları, PDF formlarına imzalar veya el yazısı notlar ekleme, mimari planlara veya mühendislik çizimlerine açıklama ekleme ve ortak inceleme için belgeleri işaretleme dahil olmak üzere çok çeşitli uygulamalar için kullanışlıdır.