---
title: PDF Açıklaması Ekle
linktitle: Ek Açıklama Ekle
second_title: .NET API Referansı için Aspose.PDF
description: Bu C# kaynak kodunu kullanarak Aspose.PDF for .NET ile metin PDF açıklamalarını nasıl ekleyeceğinizi öğrenin. Ek açıklamalarınızı belirli ayrıntılar ve simgelerle özelleştirin.
type: docs
weight: 10
url: /tr/net/annotations/addannotation/
---
PDF belgelerine ek açıklamalar eklemek, işbirliğini ve inceleme süreçlerini geliştirebilecek güçlü bir özelliktir. Aspose.PDF for .NET, C# kullanarak PDF belgelerine programlı olarak açıklama eklemeyi kolaylaştırır. Bu kılavuzda, bir PDF belgesine açıklama eklemek için Aspose.PDF for .NET'in nasıl kullanılacağını adım adım açıklayacağız.

## Adım 1: Yeni Bir Proje Oluşturun ve Aspose.PDF for .NET'i Kurun

Ek açıklama ekleme kodunu yazmaya başlamadan önce yeni bir proje oluşturmamız ve Aspose.PDF for .NET'i kurmamız gerekiyor. Aspose.PDF for .NET'i yüklemek için şu adımları izleyin:

1. Visual Studio'yu açın ve yeni bir C# projesi oluşturun.
2. Solution Explorer'da projeye sağ tıklayın ve "NuGet Paketlerini Yönet" seçeneğini seçin.
3. "Aspose.PDF"yi arayın ve "Yükle"yi seçin.

Kurulum tamamlandıktan sonra kodu yazmaya başlayabiliriz.

## Adım 2: PDF Belgesini açın

Ek açıklamalar eklemenin ilk adımı PDF belgesini açmaktır. Belgeyi açmak için aşağıdaki kodu kullanabiliriz:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");
```

Bu kodda açmak istediğimiz PDF belgesinin yolunu belirtiyoruz. "VERİ DİZİNİ"ni veri dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: Ek Açıklamayı Oluşturun

 Bir açıklama eklemek için yeni bir örnek oluşturmamız gerekir.`TextAnnotation` sınıf. Yeni bir metin açıklaması oluşturmak için aşağıdaki kodu kullanabiliriz:

```csharp
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;
```

Bu kodda PDF belgesinin ikinci sayfasında yeni bir metin açıklaması oluşturuyoruz. Ek açıklamanın başlık, konu, durum, içerik, açık ve simge özelliklerini de belirliyoruz.

## 4. Adım: Ek Açıklamayı Özelleştirin

 Ek açıklamanın görünümünü aşağıdakileri kullanarak özelleştirebiliriz:`Border` sınıf. Ek açıklamanın kenarlığını özelleştirmek için aşağıdaki kodu kullanabiliriz:

```csharp
Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);
```

 Bu kodda yeni bir tane oluşturuyoruz.`Border`nesneyi seçin ve genişlik ve çizgi özelliklerini ayarlayın. Daha sonra ayarladık`Border` yeni açıklamanın özelliği`Border` nesne. Son olarak ayarları yaptık`Rect` Ek açıklamanın konumunu ve boyutunu belirtme özelliğini kullanın.

## Adım 5: Ek Açıklamayı PDF Belgesine Ekleme

Ek açıklamayı oluşturup özelleştirdikten sonra, onu PDF belgesine eklememiz gerekir. Ek açıklamayı PDF belgesine eklemek için aşağıdaki kodu kullanabiliriz:

```csharp
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

Bu kodda, açıklamayı PDF belgesinin ikinci sayfasının açıklama koleksiyonuna ekliyoruz.

## Adım 6: Çıktı Dosyasını Kaydedin

Son olarak, eklenen açıklamayla birlikte PDF belgesini kaydetmemiz gerekiyor. Çıktı dosyasını kaydetmek için aşağıdaki kodu kullanabiliriz:

```csharp
dataDir = dataDir + "AddAnnotation_out.pdf";
pdfDocument.Save(dataDir);
```
### Aspose.PDF for .NET kullanarak Açıklama Eklemek için örnek kaynak kodu


```csharp   
 // Belgeler dizininin yolu.
string dataDir = "YOUR DATA DIRECTORY";

// Belgeyi aç
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");

// Ek açıklama oluştur
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;

Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);

// Sayfanın ek açıklamalar koleksiyonuna ek açıklama ekleyin
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddAnnotation_out.pdf";
// Çıkış dosyasını kaydet
pdfDocument.Save(dataDir);
```
Bu kod, Aspose.PDF for .NET kullanılarak bir PDF sayfasına belirli bir başlık, konu, durum, içerik ve simge içeren bir metin açıklamasının nasıl ekleneceğini gösterir. Bu kodu, PDF belgelerinize ek açıklamalar ekleme gereksinimlerinize göre değiştirebilirsiniz. VERİ DİZİNİNİZİ, PDF dosyanızın bulunduğu ve çıktı dosyasını kaydetmek istediğiniz gerçek dizin yolu ile değiştirmeyi unutmayın.

## Çözüm

Aspose.PDF for .NET kullanarak PDF belgelerine açıklamalar eklemek, belge işbirliğini ve inceleme süreçlerini geliştirmek için değerli bir araç sunar. Geliştiriciler, bu makalede sağlanan adım adım kılavuzu izleyerek ek açıklama yeteneklerini C# uygulamalarına sorunsuz bir şekilde entegre edebilir.

### SSS'ler

#### S: Aspose.PDF for .NET kullanılarak ne tür açıklamalar eklenebilir?

C: Aspose.PDF for .NET, metin açıklamaları, damgalar, bağlantılar, şekiller ve daha fazlasını içeren çeşitli açıklama türlerini destekler. Geliştiriciler bu ek açıklamaların görünümünü ve özelliklerini kendi özel ihtiyaçlarına uyacak şekilde özelleştirebilir.

#### S: Çok sayfalı bir PDF belgesindeki belirli sayfalara açıklamalar ekleyebilir miyim?

C: Evet, Aspose.PDF for .NET, açıklamayı eklemek istediğiniz sayfayı belirtmenize olanak tanır. Gerektiğinde belirli bir sayfayı seçebilir veya birden fazla sayfaya ek açıklamalar ekleyebilirsiniz.

#### S: Ek açıklamaların görünümünü nasıl özelleştiririm?

C: Ek açıklamalar, kenarlık genişliği, renk, çizgi stili, metin stili ve daha fazlası gibi özellikler kullanılarak özelleştirilebilir. Aspose.PDF for .NET, açıklamaların görünümünü uyarlamak için zengin seçenekler sunar.

#### S: Aspose.PDF for .NET kullanarak köprüleri açıklama olarak eklemek mümkün müdür?

C: Evet, Aspose.PDF for .NET'i kullanarak PDF belgelerine açıklama olarak köprüler ekleyebilirsiniz. Köprü ek açıklamaları, harici URL'lere veya aynı belge içindeki belirli konumlara bağlantı vermek için kullanılabilir.

#### S: Orijinal içeriği değiştirmeden mevcut PDF belgelerine açıklamalar eklenebilir mi?

C: Evet, Aspose.PDF for .NET, PDF belgesinin orijinal içeriğini değiştirmeden ek öğeler olarak açıklamalar ekler. Orijinal PDF içeriği bozulmadan kalır.