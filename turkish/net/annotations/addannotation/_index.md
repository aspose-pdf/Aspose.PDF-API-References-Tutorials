---
title: Açıklama Ekle
linktitle: Açıklama Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Bu C# kaynak kodunu kullanarak Aspose.PDF for .NET ile nasıl metin açıklamaları ekleyeceğinizi öğrenin. Ek açıklamalarınızı belirli ayrıntılar ve simgelerle özelleştirin.
type: docs
weight: 10
url: /tr/net/annotations/addannotation/
---

PDF belgelerine ek açıklamalar eklemek, işbirliğini ve inceleme süreçlerini geliştirebilen güçlü bir özelliktir. Aspose.PDF for .NET, C# kullanarak PDF belgelerine programlı olarak açıklamalar eklemeyi kolaylaştırır. Bu kılavuzda, bir PDF belgesine açıklama eklemek için Aspose.PDF for .NET'in nasıl kullanılacağını adım adım açıklayacağız.

## Adım 1: Yeni Bir Proje Oluşturun ve Aspose.PDF for .NET'i Kurun

Açıklama eklemek için kodu yazmaya başlamadan önce, yeni bir proje oluşturmamız ve Aspose.PDF for .NET'i kurmamız gerekiyor. Aspose.PDF for .NET'i yüklemek için şu adımları izleyin:

1. Visual Studio'yu açın ve yeni bir C# projesi oluşturun.
2. Solution Explorer'da projeye sağ tıklayın ve "NuGet Paketlerini Yönet" seçeneğini seçin.
3. "Aspose.PDF"yi arayın ve "Yükle"yi seçin.

Kurulum tamamlandıktan sonra kodu yazmaya başlayabiliriz.

## Adım 2: PDF Belgesini Açın

Açıklama eklemenin ilk adımı, PDF belgesini açmaktır. Belgeyi açmak için aşağıdaki kodu kullanabiliriz:

```
string dataDir = "YOUR DATA DIRECTORY";
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");
```

Bu kodda açmak istediğimiz PDF belgesinin yolunu belirtiyoruz. "VERİ DİZİNİNİZİ" veri dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: Açıklamayı Oluşturun

 Ek açıklama eklemek için, yeni bir örnek oluşturmamız gerekir.`TextAnnotation` sınıf. Yeni bir metin ek açıklaması oluşturmak için aşağıdaki kodu kullanabiliriz:

```
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;
```

Bu kodda, PDF belgesinin ikinci sayfasında yeni bir metin notu oluşturuyoruz. Ek açıklamanın başlık, konu, durum, içerik, açık ve simge özelliklerini de ayarladık.

## 4. Adım: Ek Açıklamayı Özelleştirin

 Ek açıklamanın görünümünü kullanarak özelleştirebiliriz.`Border` sınıf. Ek açıklamanın kenarlığını özelleştirmek için aşağıdaki kodu kullanabiliriz:

```
Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);
```

 Bu kodda yeni bir tane oluşturuyoruz.`Border` nesne ve genişlik ve tire özelliklerini ayarlayın. daha sonra ayarlıyoruz`Border`ek açıklamanın özelliği yeni`Border` nesne. Son olarak, ayarlıyoruz`Rect` konumunu ve boyutunu belirtmek için ek açıklamanın özelliği.

## Adım 5: Açıklamayı PDF Belgesine Ekleyin

Ek açıklamayı oluşturup özelleştirdikten sonra, onu PDF belgesine eklememiz gerekiyor. Ek açıklamayı PDF belgesine eklemek için aşağıdaki kodu kullanabiliriz:

```
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

Bu kodda, ek açıklamayı PDF belgesinin ikinci sayfasının açıklama koleksiyonuna ekliyoruz.

## Adım 6: Çıktı Dosyasını Kaydedin

Son olarak, eklenen ek açıklama ile PDF belgesini kaydetmemiz gerekiyor. Çıktı dosyasını kaydetmek için aşağıdaki kodu kullanabiliriz:

```
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
	// Çıktı dosyasını kaydet
	pdfDocument.Save(dataDir);
```
Bu kod, Aspose.PDF for .NET kullanılarak bir PDF sayfasına belirli bir başlık, konu, durum, içerik ve simge içeren bir metin notunun nasıl ekleneceğini gösterir. Bu kodu, PDF belgelerinize ek açıklamalar eklemek için gereksinimlerinize göre değiştirebilirsiniz. VERİ DİZİNİNİZİ, PDF dosyanızın bulunduğu ve çıktı dosyasını kaydetmek istediğiniz asıl dizin yolu ile değiştirmeyi unutmayın.