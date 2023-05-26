---
title: Özel Ek Açıklama Alın
linktitle: Özel Ek Açıklama Alın
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuz ile bir PDF belgesinde belirli açıklamaları almak için Aspose.PDF for .NET'i nasıl kullanacağınızı öğrenin.
type: docs
weight: 80
url: /tr/net/annotations/getparticularannotation/
---
.NET'te PDF'lerle çalışıyorsanız, bir PDF belgesinden belirli bir not alma ihtiyacı duyabilirsiniz. Bu kılavuzda, C# kullanarak bir PDF belgesinden belirli bir açıklamayı almak için Aspose.PDF for .NET'i nasıl kullanacağınızı göstereceğiz.

Bir PDF belgesinden belirli bir açıklamayı almak için şu basit adımları izleyin:

## 1. Adım: PDF Belgesinden Özel Ek Açıklama Alın

Öncelikle Aspose.PDF for .NET kitaplığının kurulu olduğundan ve projenizde referans verildiğinden emin olun.

Ardından, Document sınıfının yeni bir örneğini oluşturun ve belge dizinine giden yolu kullanarak PDF belgenizi yükleyin.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "GetParticularAnnotation.pdf");
```

## Adım 2: Aşağıdaki kodu kullanarak belirli bir açıklama alabilirsiniz:

```csharp
TextAnnotation textAnnotation = (TextAnnotation)pdfDocument.Pages[1].Annotations[1];
```

Bu kod, PDF belgesinin ikinci sayfasındaki ikinci açıklamayı alır.

## Adım 3: Son olarak, aşağıdaki kodu kullanarak ek açıklamanın özelliklerini alabilirsiniz:

```csharp
Console.WriteLine("Title : {0} ", textAnnotation.Title);
Console.WriteLine("Subject : {0} ", textAnnotation.Subject);
Console.WriteLine("Contents : {0} ", textAnnotation.Contents);
```

Bu kod, açıklamanın başlığını, konusunu ve içeriğini konsolda görüntüler.


### Aspose.PDF for .NET kullanarak Özel Ek Açıklama Almak için Örnek Kaynak Kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Belgeyi aç
	Document pdfDocument = new Document(dataDir + "GetParticularAnnotation.pdf");

	// Belirli ek açıklamayı alın
	TextAnnotation textAnnotation = (TextAnnotation)pdfDocument.Pages[1].Annotations[1];

	// Ek açıklama özelliklerini al
	Console.WriteLine("Title : {0} ", textAnnotation.Title);
	Console.WriteLine("Subject : {0} ", textAnnotation.Subject);
	Console.WriteLine("Contents : {0} ", textAnnotation.Contents);

```

