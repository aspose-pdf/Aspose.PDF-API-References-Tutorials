---
title: Bağlantı Ek Açıklama Ekle
linktitle: Bağlantı Ek Açıklama Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Adım adım kılavuz ve tam kaynak kodu ile Aspose.PDF for .NET kullanarak C# dilinde Ink Annotation özelliğinin PDF belgelerine nasıl ekleneceğini öğrenin.
type: docs
weight: 20
url: /tr/net/annotations/addlnkannotation/
---
Aspose.PDF for .NET, geliştiricilerin çeşitli PDF işlemlerini gerçekleştirmesini sağlayan güçlü bir kitaplıktır. Böyle bir işlem, PDF belgelerine Mürekkep Açıklaması eklemektir. Bu makalede, Aspose.PDF for .NET kullanarak Ink Annotation eklemek için C# kaynak kodunu açıklayan adım adım bir kılavuz sağlayacağız. Başlayalım!

## Aspose.PDF for .NET'in Mürekkep Açıklama Özelliğini Anlama

C# kaynak koduna dalmadan önce, Ink Annotation'ın ne olduğunu ve kullanımlarını anlayalım.

Mürekkep Açıklaması, PDF belgelerine serbest biçimli mürekkep notları çizmenin bir yoludur. Kalem veya fare ile ek açıklamalar oluşturmanıza olanak tanır. Bu özellik, diyagramlar, eskizler veya diğer açıklama türlerini çizmeniz gereken durumlarda kullanışlıdır.

## 1. Adım: Yeni Belge Oluşturma

Bir PDF belgesine Ink Annotation eklemenin ilk adımı Document sınıfının yeni bir örneğini oluşturmaktır. Bu, aşağıdaki kod parçacığı kullanılarak elde edilir:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
Page pdfPage = doc.Pages.Add();
```

Burada Document sınıfının yeni bir örneğini oluşturuyoruz ve ona yeni bir sayfa ekliyoruz.

## 2. Adım: Mürekkep Açıklaması Oluşturma

Sonraki adım, InkAnnotation sınıfının bir örneğini oluşturmaktır. Bu, aşağıdaki kod parçacığı kullanılarak yapılır:

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

Burada ilk olarak System.Drawing.Rectangle sınıfını kullanarak bir dikdörtgen oluşturuyoruz ve bunu FromRect metodunu kullanarak Aspose.Pdf.Rectangle'a dönüştürüyoruz. Daha sonra dikdörtgeni, bir nokta listesini ve ek açıklamanın eklendiği sayfayı kullanarak InkAnnotation sınıfının bir örneğini oluştururuz.

Ardından, InkAnnotation'ın başlık, renk, büyük harf stili, kenarlık ve opaklık gibi çeşitli özelliklerini ayarlarız. Son olarak Annotations.Add metodunu kullanarak notu sayfaya ekliyoruz.

## 3. Adım: Belgeyi Kaydetme

Son adım, PDF belgesini Mürekkep Açıklaması eklenmiş olarak kaydetmektir. Bu, aşağıdaki kod parçacığı kullanılarak elde edilir:

```csharp
dataDir = dataDir + "AddlnkAnnotation_out.pdf";
doc.Save(dataDir);
```

Burada çıktı dosyası adını veri dizinine birleştiriyoruz ve Save yöntemini kullanarak belgeyi kaydediyoruz.

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
// Çıktı dosyasını kaydet
doc.Save(dataDir);
```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesine Mürekkep Ek Açıklamalarının nasıl ekleneceğini inceledik. Geliştiriciler, sağlanan adım adım kılavuzu ve C# kaynak kodunu izleyerek Mürekkep Ek Açıklama işlevini PDF işleme uygulamalarında kolayca uygulayabilir.

### SSS

#### S: PDF belgesindeki Mürekkep Açıklaması nedir?

Y: Bir PDF belgesindeki Mürekkep Açıklaması, kullanıcıların kalem veya fare kullanarak serbest biçimli mürekkep açıklamaları çizmesine olanak tanır. Bir PDF'ye elle çizilmiş eskizler, diyagramlar veya diğer serbest el açıklamaları eklemek için yaygın olarak kullanılır.

#### S: Mürekkep Açıklamasının görünümünü özelleştirebilir miyim?

C: Evet, Aspose.PDF for .NET, Mürekkep Açıklamasının görünümünü özelleştirmek için renk, opaklık, kapak stili, kenarlık genişliği ve daha fazlası gibi çeşitli özellikler sağlar. Geliştiriciler, bu özellikleri kendi özel gereksinimlerini karşılayacak şekilde ayarlayabilir.

#### S: Tek bir PDF sayfasına birden fazla Mürekkep Ek Açıklama eklemek mümkün müdür?

C: Evet, Aspose.PDF for .NET'i kullanarak tek bir PDF sayfasına birden fazla Mürekkep Açıklaması ekleyebilirsiniz. Her Mürekkep Açıklamasının kendi noktaları ve özelleştirilmiş görünümü olabilir.

#### S: Mevcut PDF belgelerine Mürekkep Açıklamaları ekleyebilir miyim?

C: Evet, Aspose.PDF for .NET hem yeni oluşturulan PDF belgelerine hem de mevcut PDF dosyalarına Mürekkep Ek Açıklamaları eklemenizi sağlar. Mevcut bir PDF'yi açabilir, Mürekkep Ek Açıklamaları ekleyebilir ve güncellenen belgeyi kaydedebilirsiniz.

#### S: PDF belgelerinde Mürekkep Ek Açıklamaları için bazı genel kullanım durumları nelerdir?

C: Mürekkep Ek Açıklamaları, PDF formlarına imza veya el yazısı notlar ekleme, mimari planlara veya mühendislik çizimlerine açıklama ekleme ve ortak inceleme için belgeleri işaretleme dahil olmak üzere çok çeşitli uygulamalar için kullanışlıdır.